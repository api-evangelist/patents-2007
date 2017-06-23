---

title: Method and apparatus for searching extensible markup language (XML) data
abstract: Extensible Markup Language (XML) data is represented as a list of structures with each structure in the list representing an aspect of the XML. A set of frequently used elements is extracted from the list of structure representation and stored in packed vectors. The packed vector representation allows Single Instruction Multiple Data (SIMD) instructions to be used directly on the XML data to increase the speed at which the XML data may be searched while minimizing the memory needed to store the XML data.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08341165&OS=08341165&RS=08341165
owner: Intel Corporation
number: 08341165
owner_city: Santa Clara
owner_country: US
publication_date: 20071203
---
This disclosure relates to Extensible Markup Language XML in particular to improving the speed at which an XML document is searched.

XML is an open standard general purpose markup language used to encode documents to facilitate the sharing of data via the Internet. XML is similar to HTML used to create documents on the World Wide Web incorporating text graphics sound video and hyperlinks. However XML differs from HTML by employing tags that indicate the logical structure instead of the display specifications of the coded data.

There are many different ways to represent XML data in memory structures. For example XML data may be represented as 1 character sequences as recommended by the World Wide Web Consortium W3C 2 character sequences with secondary indexes to improve access speed 3 a list of structures each structure representing some aspect of the XML data or 4 trees of structures each structure representing some aspect of the XML data.

A typical list of structures representation of XML data uses structure types to represent different features of XML data and connects these structures into a list in document order. Typical structure types are elements attributes character data namespaces processing instructions and comments.

The list of structures representation of XML data has the advantage of being relatively compact compared to a trees of structures representation and is also easier to automatically process than character sequences. Thus it is a good compromise between slow character sequence processing and a trees of structures representation which may require a large memory.

A search of an XML document may be logically specified using the hierarchy exposed by the XML data for example find the children of a node b which is the child of a node a is expressed in the World Wide Web Consortium W3C XML Path Language XPath syntax as a b in a way similar to the use of regular expressions with character sequences. However the use of a hierarchical search model over data that is stored as a list of structures may be slow in comparison to searching data that is represented as a tree of structures where pointers between the structures may be used to limit the search space. Thus a tree of structures representation provides for random access to the XML data whereas a list of structures only provides for sequential access.

Although the following Detailed Description will proceed with reference being made to illustrative embodiments of the claimed subject matter many alternatives modifications and variations thereof will be apparent to those skilled in the art. Accordingly it is intended that the claimed subject matter be viewed broadly and be defined only as set forth in the accompanying claims.

Referring to element includes a namespace declared using xmlns having a name ns and a Uniform Resource Identifier uri namespace that is a compact sequence of characters that identifies an abstract or physical resource. Element also includes an attribute having a name a and a value attribute . The illustrates a list of structures that may be used to represent the XML document shown in . A typical list of structures representation of XML data uses different structure types to represent different features of XML data and connects these structures into a list in document order. Typical structure types are elements for example start element end element attributes namespaces processing instructions comments and character data for example text.

As shown in the list of structures to represent the XML document shown in includes element types a b c and d namespace attribute and text that are represented by structures . . . including start and end element structures namespace structures attribute structures and text structures.

Thus element type a that is is represented by a start element structure a namespace structure an attribute structure a text structure and an end element structure . Structure   corresponds to structure corresponds to xmins ns namespace structure corresponds to a attribute structure corresponds to the newline and tab and structure corresponds to in the XML document shown in .

In order to reduce the performance difference between searching a tree of structures representation of an XML document and a list of structures representation of the XML document the structures in the tree of structures may be enhanced with offsets or pointers which provide direct links between the structures or by moving infrequently accessed data to secondary storage mechanisms to reduce the amount of memory read. Hierarchical searches may also be evaluated together so that the access cost is amortized over a number of searches. However even if these techniques are used the performance of searches is still limited by the time it takes to scan through all of the data in the XML document to find a particular type of element.

As the length number of bits in each structure in the list of structures is variable a search for a particular element type requires a sequential search through the XML document byte by byte to find a match. An XML document may have thousands of records thus a scan from start to end of an XML document for a particular record is very time consuming.

The scanning speed of the list of structures representation is improved to aid the searching process by storing the XML data in a format suitable for Single Instruction Multiple Data SIMD instructions according to the principles of the present invention. A SIMD instruction may be used to perform a search of a plurality of structure elements in parallel.

A Single Instruction Multiple Data SIMD instruction performs the same operation simultaneously on multiple elements in a dataset. In order to allow a single SIMD instruction to inspect a number of structures the elements of the dataset are typically stored in a packed vector that is a data structure that includes a plurality of elements of the same size. Instead of loading data from each structure on a byte by byte basis the XML data is stored in a format suitable for use by SIMD instructions.

In an embodiment a set of structures are arranged in parallel form so that the data is readily accessible to a SIMD instruction. The list of structures shown in for the XML document shown in is logically split into two parts 1 a primary list that groups key information in a parallel layout and 2 a secondary list of the residual data in standard serial form.

The primary list may be extracted from the XML document that is represented as a list of structures in response to an Application Programming Interface API request to perform a search in the XML document. A list to packed vector converter may be used to extract elements from the list of structures representation to produce the packed vector representation in the primary list .

Each element from the list of structures representation that is stored in the primary list is either a type or a name of a structure. In the embodiment shown the operand size used by a SIMD instruction is 64 bits that is 8 bytes . Thus 32 4 8 bytes contiguous bytes of memory are allocated for the primary list to store all of the structure types and structure names corresponding to the 15 structures shown in the list of structures representation in .

The first eight bytes B B a set of eight parallel entries store the structure types corresponding to the first eight structures . . . in the list of structures representation shown in . The next eight bytes B B store the structure names corresponding to the first eight structures . . . in the list of structures representation shown in . Bytes B through B store the structure types corresponding to structures   . . .   in the list of structures representation shown in and bytes B through B store the store the structure types corresponding to structures   . . .   in the list of structures representation shown in .

The structure types stored in bytes B B and bytes B B include a start element SE type structure an end element EE type structure a namespace NS type structure an attribute A type structure and a Text T type structure. The structure names include a b ns and a.

The structure type and structure names are the most common fields in the XML document to be searched. The key data items in the primary list are the structure type stored in bytes B B and bytes B B and optionally the structure names stored in bytes B B and bytes B B . For the structure name the representation allows the substitution of a string of characters by a number representing that string as is common in XML data representations. Also as shown each structure type and structure name may be encoded in a byte.

The primary list may be searched for specific structure type and or structure name using SIMD instructions. For example two SIMD equality comparisons that operate on the bytes B B B B of the primary list may be used to search the XML document for a specific type of structure.

Thus the packed vector representation in the primary list shown in logically reduces the scanning cost by 8 by searching 8 bytes in parallel. More complex searches may be performed by combining SIMD equality operations with the bytes ranges B B B B .

While all data in the list of structures representation may be arranged in the primary list there are infrequently used items which may increase the time to search the primary list for a particular structure name or type. Thus in an embodiment infrequently used elements in the list of structures representation for example uri and attribute values are not included in the primary list . Instead of searching sequentially through the list of structures representation the XML document is stored in the primary list of packed vectors and a secondary list.

The secondary list arranged in a more conventional serial way is used in addition to the primary list to search the infrequently used items if the search in the primary list does not result in a match. The secondary list stores pointers to data DP . In the example shown in 23 pointers DP DP are shown. Each pointer DP may have 4 or 8 bytes dependent on whether a CPU in the system is 32 bits 4 byte or 64 bits 8 byte . Each entry B B in the primary list is associated with three entries DP in the secondary list stream . These three entries store pointers to the additional information required to describe the infrequently accessed XML data that is not stored in the primary list .

The first entry is for storing a pointer to a prefix string for the record structure . . . the second entry is for storing a pointer to a name string or a pointer to a URI string and the third entry is for storing a pointer to a text string. As not all structure types use all three entries unused entries are shown as 0 in the secondary list shown in .

In the example shown in Pn represents a pointer to a prefix string for record n Nn represents a pointer to a name string for n Un represents a pointer to a URI string for n and Tn represents a pointer to a text string for record n . These fields are stored as prefix name URI and text that is in three entries. The name and URI share the second entry because no structure type requires both name and URI.

An offset into the secondary list may be calculated for a specific structure   . . .   by multiplying the position of the structure in the primary list by 3 times the size of entries in the secondary list for example 4 or 8.

In another embodiment the primary and secondary lists may be interleaved into one structure and or the parallel data representation may be used selectively for some parts of the input but not others. In either case the principle of parallel data layout of XML data for improving search efficiency still applies.

To interleave the primary and secondary streams first a fixed number of structures are encoded in primary stream format and stored in memory. Next the same fixed number of structures is encoded in secondary stream format and stored in the next consecutive memory locations in the memory. This process is repeated as many times as is needed to encode all of the data. illustrates an embodiment of a structure extracted from the list of structures shown in with primary and secondary lists interleaved. As shown in the primary list is stored at and and the secondary list is stored at and .

At block the list to packed vector converter waits to receive a request to process an XML document . The request to process the XML document may result from an API call to process an XML document. JAXP is an example of an API call that is used for processing XML documents in JAVA. If a request is received processing continues with block . If not processing continues with block .

At block the XML document that has been stored as a list of structures representation as shown in is parsed to extract the structure type from N consecutive structures. For example referring to if N is eight the structure type is extracted from the first eight structures   . . .    in the list of structures representation with the first structure type being start element SE type and the eighth structure type being end element EE . Processing continues with block .

At block as the N structure types are extracted from the list of structures representation the structure types are stored in contiguous memory locations in a primary list . Processing continues with block .

At block after the structure type has been extracted from each of the N elements the list of structures representation is parsed for N structure names one per structure corresponding to the N structures from which the structure type was extracted. Processing continues with block .

At block as the structure names are extracted from the list of structures representation the structure names are stored in contiguous memory locations in the primary list starting with the memory location after the Nth structure type has been stored. One location is reserved for storing the structure type for each of the N structures irrespective of whether there is a structure name associated with the structure. For example as shown in byte B is reserved for storing the structure name associated with structure   even though structure   does not have a structure name. Processing continues with block .

At block the list to packed vector converter determines if there is another structure in the list of structures representation to be processed. If so processing continues with block to process the remaining structure s in the list of structures representation . If not processing continues with block .

At block after the primary list has been generated from the list of structures representation the primary list may be searched for specific structure types and or structure names. Eight bytes in a packed vector in the primary list may be compared in parallel with a byte to search for a match using a SIMD instruction. For example an x86 MMX comparison instruction such as a compare packed bytes for equal PCMPEQB instruction performs a compare for equality of packed bytes in a destination operand and a source operand. Processing continues with block to wait for another request.

The system includes a processor a Memory Controller Hub MCH and an Input Output I O Controller Hub ICH . The MCH includes a memory controller that controls communication between the processor and memory . The processor and MCH communicate over a system bus .

The processor may be any one of a plurality of processors that support Streaming SIMD Extensions SSE instructions such as a single core Intel Pentium IV processor a single core Intel Celeron processor an Intel XScale processor or a multi core processor such as Intel Pentium D Intel Xeon processor or Intel Core Duo processor or any other type of processor.

The memory may be Dynamic Random Access Memory DRAM Static Random Access Memory SRAM Synchronized Dynamic Random Access Memory SDRAM Double Data Rate 2 DDR2 RAM or Rambus Dynamic Random Access Memory RDRAM or any other type of memory.

The ICH may be coupled to the MCH using a high speed chip to chip interconnect such as Direct Media Interface DMI . DMI supports 2 Gigabit second concurrent transfer rates via two unidirectional lanes.

The ICH may include a storage Input Output I O controller for controlling communication with at least one storage device coupled to the ICH . The storage device may be for example a disk drive Digital Video Disk DVD drive Compact Disk CD drive Redundant Array of Independent Disks RAID tape drive or other storage device. The ICH may communicate with the storage device over a storage protocol interconnect using a serial storage protocol such as Serial Attached Small Computer System Interface SAS or Serial Advanced Technology Attachment SATA .

The ICH may also include a Network Interface Communications NIC controller for controlling communications over the Internet with at least one other system . The memory may store a list to packed vector converter for for generating a primary list from a list of structures representation of an XML document . The XML document may be stored in the RAID array or in another system accessible via the Internet . The packed vector converter operates on a list of structures representation of the XML document that may be stored in memory . The packed vector converter generates a primary list and a secondary list from the list of structures representation of the XML document according to the principles of the present invention.

An embodiment of the invention has been described for a 64 bit SIMD instruction that is a SIMD instruction that operates on 64 bits 8 bytes in parallel. However the invention is not limited to operating on 64 bits in parallel. An embodiment o the invention may use a SIMD instruction that operates on more than 64 bits in parallel for example using 128 bit registers to operate on 16 bytes in parallel.

It will be apparent to those of ordinary skill in the art that methods involved in embodiments of the present invention may be embodied in a computer program product that includes a computer usable medium. For example such a computer usable medium may consist of a read only memory device such as a Compact Disk Read Only Memory CD ROM disk or conventional ROM devices or a computer diskette having a computer readable program code stored thereon.

While embodiments of the invention have been particularly shown and described with references to embodiments thereof it will be understood by those skilled in the art that various changes in form and details may be made therein without departing from the scope of embodiments of the invention encompassed by the appended claims.

