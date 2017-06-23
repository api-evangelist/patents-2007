---

title: Method and system for searching across independent applications
abstract: A method and system are provided for searching across independent applications. A first seedlist () is provided from a first application (), the first seedlist () including a list of data items () for crawling by a search engine (). The data items () are owned by the first application (). A second seedlist () is also provided from a second independent application (), the second seedlist () including annotation data () for crawling by a search engine (). The annotation data () relates to the data items () of the first application (). A search index () provides searchable data from the two or more applications (), the searchable data relating to the same set of data items ().
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08140507&OS=08140507&RS=08140507
owner: International Business Machines Corporation
number: 08140507
owner_city: Armonk
owner_country: US
publication_date: 20070702
---
This invention relates to the field of searching. In particular the invention relates to searching across independent applications to create searchable content.

Search engines allow an application to make its content searchable. A known approach for making data searchable is by using seedlists also know as sitemaps. In this approach an application provides the search engine with a list of data items that needs to be made searchable the seedlist. Crawling happens in two phases. First the search engine crawls the seedlist information containing metadata about the data items that need to be crawled. Then in a second phase the pieces of content from the application themselves are retrieved and the data is made searchable. Note that this second phase is optional and there are cases in which only the metadata in the seedlist is retrieved and made searchable.

An application of this approach is Google Sitemap Protocol Google is a trade mark of Google Inc. that allows a webmaster to inform search engines about pages on their sites that are available for crawling. In its simplest form a sitemap is an XML Extensible Markup Language file that lists URLs Uniform Resource Locators for a site along with additional metadata about each URL for example when it was last updated how often it usually changes and how important it is relative to other URLs in the site so that search engines can more intelligently crawl the site.

Web crawlers usually discover pages from links within the site and from other sites. Sitemaps supplement this data to allow crawlers that support sitemaps to pick up all URLs in the sitemap and learn about those URLs using the associated metadata.

Seedlists are a generalization of sitemaps since sitemaps contains only URLs and very little metadata about them while seedlists contains a lot of metadata about the data items including for example security information. The term seedlist as used herein should be interpreted as including sitemaps.

In some types of application content is not created in the application but instead existing content from other sources is commented upon annotated tagged or classified etc. For example applications that aggregate content and annotations already exist in the web such as http answers.shopping.com. This application aggregates data of products and in particular prices from various web sites. However the content of such applications is obtained through traditional web crawling and content extraction or using web services APIs Application Programming Interfaces . Additionally this aggregation is usually not used to improve the searchability of the items only to add more metadata comments ratings etc. and this aggregation is done explicitly with a knowledge of the domain and the metadata expected.

Another example of an application that references and adds metadata to existing content from other sources is an application for social bookmarking such as Dogear a trade mark of International Business Machines Corporation or del.icio.us a trade mark of Yahoo Inc. . Social bookmarking lets users centrally store categorized and share a set of personal web bookmarks with others. Tags are stored in relation to content from other sources on the web or in an Intranet. Thus bookmarks are easier to find since they can be retrieved using the tags they have been associated with.

These applications which provide metadata in the form of annotations to content from external sources are referred to as annotating applications. Currently each such annotating application manages the searchability of its annotations independently from the searchability of the external content itself.

Enterprise search engines aim to make all the content or data available in an enterprise searchable. The problem arises as to how to manage content and annotations applied in an independent application in the context of an enterprise search engine.

It is an aim of the present invention that all available metadata relating to a content should be used when making content searchable.

According to a first aspect of the present invention there is provided a method for searching comprising providing a first seedlist from a first application the first seedlist including a list of data items for crawling by a search engine wherein the data items are owned by the first application providing a second seedlist from a second independent application the second seedlist including annotation data for crawling by a search engine wherein the annotation data relates to the data items of the first application.

According to a second aspect of the present invention there is provided a system for searching comprising a first seedlist crawler for crawling a seedlist from a first application the first seedlist including a list of data items for crawling wherein the data items are owned by the first application a second seedlist crawler for crawling a seedlist from a second independent application the second seedlist including annotation data for crawling wherein the annotation data relates to the data items of the first application.

According to a third aspect of the present invention there is provided a computer program product stored on a computer readable storage medium for searching across independent applications comprising computer readable program code means for performing the steps of providing a first seedlist from a first application the first seedlist including a list of data items for crawling by a search engine wherein the data items are owned by the first application providing a second seedlist from a second independent application the second seedlist including annotation data for crawling by a search engine wherein the annotation data relates to the data items of the first application.

In this case both applications the creating application and the annotating application provide a seedlist. Data and annotations can be consolidated in one search index or in different search indexes.

It will be appreciated that for simplicity and clarity of illustration elements shown in the figures have not necessarily been drawn to scale. For example the dimensions of some of the elements may be exaggerated relative to other elements for clarity. Further where considered appropriate reference numbers may be repeated among the figures to indicate corresponding or analogous features.

In the following detailed description numerous specific details are set forth in order to provide a thorough understanding of the invention. However it will be understood by those skilled in the art that the present invention may be practiced without these specific details. In other instances well known methods procedures and components have not been described in detail so as not to obscure the present invention.

Referring to a schematic flow diagram shows a process known in the art of indexing the content of an application . The application is the content owner. For example the application may be a content repository which provides storage searching and retrieval of hierarchical data.

The seedlist provides information in the form of a list of data items describing the contents of application that need to be made searchable and that are available for crawling by a seedlist crawler . For example the seedlist may provide a list of URLs on a web site that are available for crawling. The seedlist can include additional information about each data item such as when it was last updated how often it changes its importance etc. The seedlist enables the search engine to crawl the content more intelligently.

The seedlist crawler of the search engine then crawls the content using the seedlist information . In some cases the content itself is found in the seedlist and crawling the content is not required. In some applications the content itself is not available at indexing time.

The seedlist crawler provides a searchable form of the content to a search index . The seedlist crawler also provides a searchable form of the associated information to a search index .

Referring to a similar schematic flow diagram to that of is shown for a method and system in accordance with an embodiment of the invention. As in the diagram is divided into application space and search engine space .

An application owns the content which is to be made searchable. The application provides a first seedlist to provide information relating to the content .

The first seedlist provides information in the form of a list of data items in the content of application that need to be made searchable and that are available for crawling by a first seedlist crawler . The first seedlist can include additional information about each data item such as when it was last updated how often it changes its importance etc.

The first seedlist crawler of the search engine then crawls the content using the seedlist information . In some cases the content itself is found in the first seedlist and crawling the content is not required.

The first seedlist crawler provides a searchable form of the content together with a searchable form of the associated information to a search index . Up to this point processing is as described in .

Additionally as shown in an annotating application provides annotations on the content of the application . The term annotating application is used for any system providing metadata or annotations relating to content where the content is from another source.

The annotating application provides a second seedlist which is a metadata seedlist providing information relating to the annotations of the annotating application . With respect to the output of the annotating application the terms metadata and annotation are used interchangeably to signify that this data refers to the content managed by application namely the content . More than one annotating application such as annotating application can refer to the same external content in the described example content .

A second seedlist crawler of the search engine then crawls the annotations of the annotating application retrieving the seedlist information from inside the seedlist . The second seedlist crawler provides a searchable form of the information of the annotations to the search index . Thus the annotations of the annotating application are made searchable in the search engine together with the data initiating from application that is the searchable content together with its metadata .

It is possible to index all data related to a given content from the first and second seedlists in the same index . The second seedlist crawler for an annotating application may be modified to enable annotations to be merged into the search index for a given content. Alternatively as described further with reference to the second seedlist crawler may index the data relating to the content and the annotations provided by the annotating applications in different search indexes.

Referring to a first embodiment of a search engine is shown. The search engine includes a search index a first seedlist crawler for crawling a seedlist from a content owning application and a second seedlist crawler for crawling a metadata seedlist from an annotating application.

A merging mechanism is provided for merging the annotation data into the search index for a given content. It needs to be determined which collection of a search index contains a given content. One way of achieving this is to ask each collection if they contain Document X X being the ID of the document for which annotation data has been retrieved from the annotating application. It is assumed that a piece of content has a universal document ID for example a URL and URN Uniform Resource Name .

The merging mechanism may be provided as part of the second seedlist crawler as shown in or as part of the search index .

The following example describes the embodiment described in and . The following seedlist defined by the owner of a web site is provided 

This seedlist describes the web page whose URL is http www.example.com index.html and specifies as metadata that the content of this page is updated daily.

The annotation seedlist specifies that http www.example.com index.html is the URL of a very good vegetables shop.

The first seedlist crawler crawls the first seedlist and indexes its data daily then the seedlist crawler uses the URL found in the seedlist to crawl the site itself http www.example.com index.html . The second seedlist crawler crawls the second seedlist. Using the merge mechanism the second seedlist crawler checks whether some information has been stored in the index in relation to the specified web site http www.example.com index.html.

The second seedlist crawler then updates the metadata related to this web site with the additional information very good vegetable shop . As a result of this operation when users of the search engine search for very good vegetable shop the URL of http www.example.com index.html is more likely to be returned as a search result.

The search engine gives a unified view of a content such as a document and its metadata including annotation data. To be efficient this merging requires the ability to update metadata without re fetching the content

It is also possible for the content to be virtually aggregated through the seedlist of an annotating application. That is indexing a metadata seedlist without the content seedlist. The metadata seedlist from an annotating application would describe in the seedlist that the content must be fetched. Effectively this tells the crawler to retrieve the content data through the URL supplied thus achieving a powerful content and metadata aggregation infrastructure.

Referring to a second embodiment of a search engine is provided in which the annotation data from an annotating application is stored in a different search index to that of the content and metadata from the content owning application. The content and metadata from the content owning application are indexed in index while the annotation data from the annotating application is indexed in a different index . In this embodiment unification between the indexes is done at query time.

The search engine includes search indexes a first seedlist crawler for crawling a seedlist from a content owning application and a second seedlist crawler for crawling an metadata seedlist from an annotating application.

The search engine includes a first search index containing the content itself and any metadata obtained by the first seedlist crawler and a second search index containing the annotation data relating to the content as obtained by the second seedlist crawler .

In the second embodiment the information about the same content could be spread over multiple search indexes. Therefore at query time there is a need to do some merging. For a given content hit the other collections would need to be queried as to whether they have additional information about that content and then a merge carried out.

Following the example given above the content of page http www.example.com index.html and the annotation data related to this page it being a very good vegetables shop would be stored in two different indexes.

Given a query good vegetable shop http www.example.com index.html would be returned from the second index and information would need to be extracted from the first index to get all the information about http www.example.com index.html. Querying data in the second embodiment is less powerful than in the first embodiment since content and annotations are queried separately in each index. For example if the application content document contains the word CAT while the corresponding annotation associated by the annotating application is DOG in the first embodiment CAT and DOG are stored together and associated with the document. So the query CAT DOG is very likely to return the document. In the second embodiment CAT is associated with the document in one index while DOG is associated with the document in a second index. Thus the query CAT DOG run on each index separately may not return the document.

It is determined if the content of the URL is in the search index collection. If the content is in the collection the annotation data is merged with the content data in the search index.

If the content of the URL is not in the search index collection the seedlist crawler returns an action to update the content. The seedlist crawler retrieves the content data from the URL and merges this with the annotation data and stores in the search index.

In a seedlist of an annotating application provides annotations relating to content identified by a URL. A seedlist crawler for the annotating application crawls the seedlist and obtains the annotation data. The annotation data is entered in a search index with a reference to the URL.

In a query is made to multiple search indexes for a set of keywords to be searched. Each index returns a set of results and the sets of results from the indexes are merged . The sets of results returned from the indexes may include results located via the annotation data. For example using the example given above if the search keywords were very good vegetable shop the URL of http www.example.com index.html may be returned as a result due to the annotation data provided in the search index.

For each search result URL all metadata related to the URL is retrieved from all the search indexes that contain annotation data metadata or content data relating to the URL. The query result is then returned .

Different seedlists created by different services can be used to annotate the same content. This allows different views of the content to be considered in the searchable index.

The described approach is completely passive automated and standardized. The described method and system allow applications to register themselves and add annotation data they want to contribute. There is no need to know in advance anything about the format of the pages containing the annotation data or specific APIs to use.

Applications are used to publish seedlists sitemaps to be crawlable and publish their updates. By allowing sitemaps to contain annotation data and item IDs and merging sitemaps annotation data into the search index the described approach enables the searchable data to be enriched with additional annotation data coming from various systems and enhances its searchability

Referring to an exemplary system for implementing the invention includes a data processing system suitable for storing and or executing program code including at least one processor coupled directly or indirectly to memory elements through a bus system . The memory elements can include local memory employed during actual execution of the program code bulk storage and cache memories which provide temporary storage of at least some program code in order to reduce the number of times code must be retrieved from bulk storage during execution.

The memory elements may include system memory in the form of read only memory ROM and random access memory RAM . A basic input output system BIOS may be stored in ROM . System software may be stored in RAM including operating system software . Software applications may also be stored in RAM .

The system may also include a primary storage means such as a magnetic hard disk drive and secondary storage means such as a magnetic disc drive and an optical disc drive. The drives and their associated computer readable media provide non volatile storage of computer executable instructions data structures program modules and other data for the system . Software applications may be stored on the primary and secondary storage means as well as the system memory .

The computing system may operate in a networked environment using logical connections to one or more remote computers via a network adapter .

Input output devices can be coupled to the system either directly or through intervening I O controllers. A user may enter commands and information into the system through input devices such as a keyboard pointing device or other input devices for example microphone joy stick game pad satellite dish scanner or the like . Output devices may include speakers printers etc. A display device is also connected to system bus via an interface such as video adapter .

A search system as described for searching collaboration across independent applications may be provided as a service to a customer over a network.

The invention can take the form of an entirely hardware embodiment an entirely software embodiment or an embodiment containing both hardware and software elements. In a preferred embodiment the invention is implemented in software which includes but is not limited to firmware resident software microcode etc.

The invention can take the form of a computer program product accessible from a computer usable or computer readable medium providing program code for use by or in connection with a computer or any instruction execution system. For the purposes of this description a computer usable or computer readable medium can be any apparatus that can contain store communicate propagate or transport the program for use by or in connection with the instruction execution system apparatus or device.

The medium can be an electronic magnetic optical electromagnetic infrared or semiconductor system or apparatus or device or a propagation medium. Examples of a computer readable medium include a semiconductor or solid state memory magnetic tape a removable computer diskette a random access memory RAM a read only memory ROM a rigid magnetic disk and an optical disk. Current examples of optical disks include compact disk read only memory CD ROM compact disk read write CD R W and DVD.

Improvements and modifications can be made to the foregoing without departing from the scope of the present invention.

