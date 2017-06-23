---

title: Printer with ink transfer roller and cleaning station
abstract: A printer has a chassis with a pair of guide rails. A retractable print media tray assembly is arranged on the guide rails in a displaceable manner. At least one print engine is arranged on the chassis and has an ink ejecting printhead assembly configured to eject ink onto an associated ink transfer roller. At least one cleaning station is engaged with a respective ink transfer roller and configured to clean residual ink from the transfer roller, subsequent to transfer of ink from the transfer roller onto the print media.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07744208&OS=07744208&RS=07744208
owner: Silverbrook Research Pty Ltd.
number: 07744208
owner_city: Balmain, New South Wales
owner_country: AU
publication_date: 20070923
---
The present application is a Continuation of U.S. application Ser. No. 11 501 775 filed Aug. 10 2006 which is a Continuation of U.S. application Ser. No. 10 273 848 filed on Oct. 21 2002 now issued U.S. Pat. No. 7 187 470 which is a continuation of U.S. appllication Ser. No. 09 459 409 filed on Dec. 11 1999 now issued U.S. Pat. No. 7 239 407 all of which is herein incorporated by reference.

This invention relates to a printing system. More particularly the invention relates to a controller for controlling printing on both surfaces of a sheet of print media and to a method of controlling printing on both surfaces of a sheet of print media.

According to a first aspect of the invention there is provided a controller for controlling printing on both surfaces of a sheet of print media the controller including 

a second print controller for controlling printing by a page width printhead of a second print engine substantially simultaneously with the printing by the printhead of the first print engine 

a first communications link interconnecting the first print controller and the second print controller for synchronizing the print controllers and

a second communications link interconnecting at least one of the print controllers with a host system for receipt from the host system of descriptions of pages to be printed on said surfaces of the sheet of print media by the print engines.

The invention also provides in another broad form a printer configured to simultaneously print on both surfaces of a sheet of media including 

first memory configured to receive from a host system descriptions of all pages to be printed on the surfaces of the sheets of print media 

a first print engine configured to print on a first surface of the print media the print engine receiving descriptions of pages to be printed from the first memory 

a second print engine configured to print on a second surface of the print media the second print engine receiving descriptions of pages to be printed from the second memory and

a first controller configured to transfer descriptions of pages to be printed by the second print engine from the first memory to the second memory.

Preferably the first controller also controls the first print engine. Preferably the printer includes a second controller that controls the second print engine.

In this specification unless the context clearly indicate otherwise the term page width printhead is to be understood as a printhead having a printing zone that prints one line at a time on a page the line being parallel either to a longer edge or a shorter edge of the page. The line is printed as a whole as the page moves past the printhead and the printhead is stationary i.e. it does not raster.

The first print controller is preferably a master print controller with the second print controller being a slave print controller operable under command of the master print controller on receipt of signals via the first communications link.

The first communications link may be a bidirectional link enabling the transmission of data from the slave print controller to the master print controller. Thus after the printing of a page or more frequently the master print controller may obtain ink consumption information from the slave print controller via the first communications link. The master print controller uses this to update the remaining ink volume in an ink cartridge. Further the master print controller and slave print controller may also exchange error events and host initiated printer reset commands via the first communications link.

The master print controller may have the second communications link connected to it to present a unified view to the host system to mask the presence of the slave print controller. The master print controller may print described pages on a rear surface of the print media with the slave print controller printing on a front surface of the print media so that the master print controller always has a page buffer available for a page description destined for the slave print controller.

Print synchronization may be achieved by the master print controller controlling a printing operation of the slave print controller. Printhead interfaces of both print controllers may be synchronized to a shared line synchronization signal generated by one of the print controllers.

According to a second aspect of the invention there is provided a method of controlling printing on both surfaces of a sheet of print media the method including the steps of 

receiving data relating to a first page to be printed in a first print controller of a first print engine 

transmitting the data relating to the first page from the first print controller to a second print controller of a second print engine 

controlling printing by the print engines under command of the first print controller to achieve synchronization of printing of the pages by the first print controller and the second print controller on rear and front surfaces of the print media respectively.

In a further broad form the invention provides method of manipulating print data in a printer capable of simultaneously printing on both surfaces of a sheet of print media the method including the steps of 

simultaneously accessing the first and second data to simultaneously print the first and second pages on both surfaces of the print media.

Preferably the receiving and transferring of the first data is under the control of a first controller. Preferably printing of said second data is controlled by the first controller and preferably the printing of said first data is controlled by a second controller.

The method may include synchronizing printhead interfaces of both print controllers by means of a shared line synchronization signal generated by the first print controller which is a master print controller. Further the method may include transmitting data relating to the pages to be printed from a host system to the master print controller by means of a host communications link the master print controller determining whether or not said data are to be routed to the second print controller which is a slave print controller.

The method may also include receiving said data in its entirety in a memory of the master print controller before forwarding it to the slave print controller.

The method may include selecting the master print controller to print the rear surface of the print media to ensure that the master print controller always has a page buffer available for a page description destined for the slave print controller.

As described above the method may include periodically transmitting predetermined data from the slave print controller to the master print controller.

The printer in accordance with the invention is a high performance color printer which combines photographic quality image reproduction with magazine quality text reproduction. It utilizes an 8 page width microelectromechanical inkjet printhead which produces 1600 dots per inch dpi bi level CMYK Cyan Magenta Yellow black . In this description the printhead technology shall be referred to as Memjet and the printer shall be referred to as CePrint .

CePrint is conceived as an original equipment manufacture OEM part designed for inclusion primarily in consumer electronics CE devices. Intended markets include televisions VCRs PhotoCD players DVD players Hi fi systems Web Internet terminals computer monitors and vehicle consoles. As will be described in greater detail below it features a low profile front panel and provides user access to paper and ink via an ejecting tray. It operates in a horizontal orientation under domestic environmental conditions.

CePrint exists in single and double sided versions. The single sided version prints 30 full color A4 or Letter pages per minute. The double sided version prints 60 full color pages per minute i.e. 30 sheets per minute . Although CePrint supports both paper sizes it is configured at time of manufacture for a specific paper size.

CePrint reproduces black text and graphics directly using bi level black and continuous tone contone images and graphics using dithered bi level CMYK. For practical purposes CePrint supports a black resolution of 800 dpi and a contone resolution of 267 pixels per inch ppi .

CePrint is embedded in a CE device and communicates with the CE device host processor via a relatively low speed 1.5 MBytes s connection. CePrint relies on the host processor to render each page to the level of contone pixels and black dots. The host processor compresses each rendered page to less than 3 MB for sub two second delivery to the printer. CePrint decompresses and prints the page line by line at the speed of its micro electromechanical inkjet Memjet printhead. CePrint contains sufficient buffer memory for two compressed pages 6 MB allowing it to print one page while receiving the next but does not contain sufficient buffer memory for even a single uncompressed page 119 MB .

The double sided version of CePrint contains two printheads which operate in parallel. These printheads are fed by separate data paths each of which replicates the logic found in the single sided version of CePrint. The double sided version has a correspondingly faster connection to the host processor 3 MB s .

Table 1 gives a summary product specification of the single sided and double sided versions of the CePrint unit.

A Memjet printhead produces 1600 dpi bi level CMYK. On low diffusion paper each ejected drop forms an almost perfectly circular 22.5 mm diameter dot. Dots are easily produced in isolation allowing dispersed dot dithering to be exploited to its fullest. Since the Memjet printhead is page width and operates with a constant paper velocity the four color planes are printed in perfect registration allowing ideal dot on dot printing. Since there is consequently no spatial interaction between color planes the same dither matrix is used for each color plane.

A page layout may contain a mixture of images graphics and text. Continuous tone contone images and graphics are reproduced using a stochastic dispersed dot dither. Unlike a clustered dot or amplitude modulated dither a dispersed dot or frequency modulated dither reproduces high spatial frequencies i.e. image detail almost to the limits of the dot resolution while simultaneously reproducing lower spatial frequencies to their full color depth when spatially integrated by the eye. A stochastic dither matrix is carefully designed to be free of objectionable low frequency patterns when tiled across the image. As such its size typically exceeds the minimum size required to support a number of intensity levels i.e. 16 16 8 bits for 257 intensity levels . CePrint uses a dither volume of size 64 64 3 8 bits. The volume provides an extra degree of freedom during the design of the dither by allowing a dot to change states multiple times through the intensity range rather than just once as in a conventional dither matrix.

Human contrast sensitivity peaks at a spatial frequency of about 3 cycles per degree of visual field and then falls off logarithmically decreasing by a factor of 100 beyond about 40 cycles per degree and becoming immeasurable beyond 60 cycles per degree. At a normal viewing distance of 12 inches about 300 mm this translates roughly to 200 300 cycles per inch cpi on the printed page or 400 600 samples per inch according to Nyquist s theorem. Contone resolution beyond about 400 pixels per inch ppi is therefore of limited utility and in fact contributes slightly to color error through the dither.

Black text and graphics are reproduced directly using bi level black dots and are therefore not antialiased i.e. low pass filtered before being printed. Text is therefore supersampled beyond the perceptual limits discussed above to produce smoother edges when spatially integrated by the eye. Text resolution up to about 1200 dpi continues to contribute to perceived text sharpness assuming low diffusion paper of course .

CePrint prints A4 and Letter pages with full edge bleed. Corresponding page image sizes are set out in Table 2 for various spatial resolutions and color depths used in the following discussion. Note that the size of an A4 page exceeds the size of a Letter page although the Letter page is wider. Page buffer requirements are therefore based on A4 while line buffer requirements are based on Letter.

The act of interrupting a Memjet based printer during the printing of a page produces a visible discontinuity so it is advantageous for the printer to receive the entire page before commencing printing to eliminate the possibility of buffer underrun. Furthermore if the transmission of the page from the host to the printer takes significant time in relation to the time it takes to print the page then it is advantageous to provide two page buffers in the printer so that one page can be printed while the next is being received. If the transmission time of a page is less than its 2 second printing time then double buffering allows the full 30 pages minute page rate of CePrint to be achieved.

Assuming it is economic for the printer to have a maximum of only 8 MB of memory i.e. a single 64 Mbit DRAM then less than 4 MB is available for each page buffer in the printer imposing a limit of less than 4 MB on the size of the page image. To allow for program and working memory in the printer we limit this to 3 MB per page image.

Assuming the printer has only a typical low speed connection to the host processor then the speed of this connection is 1 2 MB s i.e. 2 MB s for parallel port 1.5 MB s for USB and 1 MB s for 10 Base T Ethernet . Assuming 2 second page transmission i.e. equal to the printing time this imposes a limit of 2 4 MB on the size of the page image i.e. a limit similar to that imposed by the size of the page buffer.

In practice because the host processor and the printer can be closely coupled a high speed connection between them may be feasible.

Whatever the speed of the host connection required by the single sided version of CePrint the double sided version requires a connection of twice that speed.

Page rendering or rasterization can be split between the host processor and printer in various ways. Some printers support a full page description language PDL such as Postscript and contain correspondingly sophisticated renderers. Other printers provide special support only for rendering text to achieve high text resolution. This usually includes support for built in or downloadable fonts. In each case the use of an embedded renderer reduces the rendering burden on the host processor and reduces the amount of data transmitted from the host processor to the printer. However this comes at a price. These printers are more complex than they might be and are often unable to provide full support for the graphics system of the host through which application programs construct render and print pages. They fail to exploit the possibly high performance of the host processor.

CePrint relies on the host processor to render pages i.e. contone images and graphics to the pixel level and black text and graphics to the dot level. CePrint contains only a simple rendering engine which dithers the contone data and combines the results with any foreground bi level black text and graphics. This strategy keeps the printer simple and independent of any page description language or graphics system. It fully exploits the high performance expected in the host processor of a multimedia CE device. The downside of this strategy is the potentially large amount of data which must be transmitted from the host processor to the printer. We therefore use compression to reduce the page image size to the 3 MB required to allow a sustained printing rate of 30 pages minute.

An 8.3 11.7 A4 page has a bi level CMYK page image size of 119 MBytes at 1600 dpi and a contone CMYK pagesize of 59.3 MB at 400 ppi.

We use JPEG compression to compress the contone data. Although JPEG is inherently lossy for compression ratios of 10 1 or less the loss is usually negligible. To achieve a high quality compression ratio of less than 10 1 and to obtain an integral contone to bi level ratio we choose a contone resolution of 267 ppi. This yields a contone CMYK pagesize of 25.5 MB a corresponding compression ratio of 8.5 1 to fit within the 3 MB page limit and a contone to bi level ratio of 1 6 in each dimension.

A full page of black text and or graphics rasterized at printer resolution 1600 dpi yields a bi level image of 29.6 MB. Since rasterizing text at 1600 dpi places a heavy burden on the host processor for a small gain in quality we choose to rasterize text at 800 dpi. This yields a bi level image of 7.4 MB requiring a lossless compression ratio of less than 2.5 1 to fit within the 3 MB page limit. We achieve this using a two dimensional bi level compression scheme similar to the compression scheme used in Group 4 Facsimile.

As long as the image and text regions of a page are non overlapping any combination of the two fits within the 3 MB limit. If text lies on top of a background image then the worst case is a compressed page image size approaching 6 MB depending on the actual text compression ratio . This fits within the printer s page buffer memory but prevents double buffering of pages in the printer thereby reducing the printer s page rate by two thirds i.e. to 10 pages minute.

As described above the host processor renders contone images and graphics to the pixel level and black text and graphics to the dot level. These are compressed by different means and transmitted together to the printer.

The printer contains two 3 MB page buffers one for the page being received from the host and one for the page being printed. The printer expands the compressed page as it is being printed. This expansion consists of decompressing the 267 ppi contone CMYK image data halftoning the resulting contone pixels to 1600 dpi bi level CMYK dots decompressing the 800 dpi bi level black text data and compositing the resulting bi level black text dots over the corresponding bi level CMYK image dots.

CePrint is conceived as an OEM part designed for inclusion primarily in consumer electronics CE devices. Intended markets include televisions VCRs PhotoCD players DVD players Hi fi systems Web Internet terminals computer monitors and vehicle consoles. It features a low profile front panel and provides user access to paper and ink via an ejecting tray. It operates in a horizontal orientation under domestic environmental conditions.

Because of the simplicity of the page width Memjet printhead CePrint contains an ultra compact print mechanism which yields an overall product height of 40 mm for the single sided version and 60 mm for the double sided version.

The nature of an OEM product dictates that it should be simple in style and reflect minimum dimensions for inclusion into host products. CePrint is styled to be accommodated into all of the target market products and has minimum overall dimensions of 40 mm high 272 mm wide 416 mm deep. The only cosmetic part of the product is the front fascia and front tray plastics. These can be re styled by a manufacturer if they wish to blend CePrint with a certain piece of equipment.

Front views of the two versions of CePrint or the printer are illustrated in respectively of the drawings and are designated generally by the reference numeral . It is to be noted that mechanically both versions are the same apart from the greater height of the double sided version to accommodate a second print engine instead of a pinch roller. This will be described in greater detail below. Side and plan views of the single sided version of CePrint are illustrated in respectively. The side view of the double sided version of CePrint is illustrated in .

CePrint is a motorized A4 Letter paper tray with a removable ink cartridge and a Memjet printhead mechanism. It includes a front panel housing a paper eject button a power LED an out of ink LED and an out of paper LED . A paper tray is slidably arranged relative to the front panel . When the paper tray is in its home position a paper output slot is defined between the front panel and the paper tray .

The front panel fronts a housing containing the working parts of the printer . As illustrated in 5 of the drawings the housing in the case of the double sided version is stepped at towards the front panel to accommodate the second print engine. The housing covers a metal chassis fascias the molded paper tray an ink cartridge three motors a flex PCB a rigid PCB and various injection moldings and smaller parts to achieve a cost effective high volume product.

The printer is simple to operate only requiring user interaction when paper or ink need replenishing as indicated by the front panel LEDs or respectively. The paper handling mechanisms are similar to current printer applications and are therefore considered reliable. In the rare event of a paper jam the action of ejecting the paper tray allows the user to deal with the problem. The tray has a sensor which retracts the tray if the tray is pushed. If the tray jams on the way in this is also sensed and the tray is re ejected. This allows the user to be lazy in operating the tray by just pushing it to close and protects the unit from damage should the tray get knocked while in the out position. It also caters for children sticking fingers in the tray while closing. Ink is replaced by inserting a new cartridge into the paper tray and securing it by a cam lock lever mechanism.

The overall views of CePrint are shown in . As shown in the chassis includes base metalwork on which front roller wheels of the paper tray are slidable. A bracket accommodates motors and and gears and for ejecting the paper tray and driving a paper pick up roller .

Attached to the bracket and the base metalwork are two guide rails that allow the molded paper tray and its rear roller wheels to slide forward. As described above the tray also sits on front rollers and this provides a strong low friction and steady method of ejection and retraction. The flex PCB runs from the main PCB via the motors and to a contact molding and a lightpipe area . An optical sensor on the flex PCB allows the tray ejector motor to retract the tray independently of the eject button if the tray is pushed when in the out position by sensing a hole in a gear wheel . Similarly the tray is ejected if there is any stoppage during retraction.

The contact molding has a foam pad that the flex PCB is fixed onto and provides data and power contacts to the printhead and bus bars during printing.

A transfer roller has two end caps that run in low friction bearing assemblies . One of the end caps has an internal gear that acts on a small gear which transfers power through a reduction gear to a worm drive. This is reduced further via another gear to a motor worm drive mounted on an output shaft of a stepper motor arranged within the transfer roller . This solution for a motor drive assembly that is housed inside the transfer roller saves space for future designs and mounts onto a small chassis that is attached to ink connector moldings .

An ink connector has four pins with an ejector plate and springs that interfaces with the ink cartridge . The ink cartridge is accessed via a cam lock lever and spring . The ink is conducted through molded channels into a flexible four channel hose connector that interfaces with a printhead cartridge end cap . The other end of the printhead cartridge has a different flexible sealing connector on the end cap to allow ink to be drawn through the cartridge during assembly and effectively charge the unit and ink connector with ink in a sealed environment. The printhead and ink connector assemblies are mounted directly into the paper tray .

The paper tray has several standard paper handling components namely a metal base channel with low friction pads sprung by two compression springs and two metal paper guides with arms secured by rivets. The paper is aligned to one side of the tray by a spring steel clip . The tray is normally configured to take A4 paper but Letter size paper is accommodated by relocating one of the paper guide assemblies and clipping a plate into the paper tray to provide a rear stop. The paper tray can accommodate up to 150 sheets.

As is standard practice for adding paper the metal base channel is pushed down and is latched using a tray lock molding and a return spring . When paper has been added and the tray retracted the tray lock molding is unlatched by hitting a metal return in the base metalwork .

The printer is now ready to print. When activated the paper pick up roller is driven by a small drive gear that meshes with another drive gear and a normal motor . The roller is located to the base metalwork by two heat staked retainer moldings . A small molding on the end of the pick up roller acts with a sensor on the flex PCB to accurately position the pick up roller in a parked position so that paper and tray can be withdrawn without touching it when ejecting. This accurate positioning also allows the roller to feed the sheet to the transfer roller with a fixed number of revolutions. As the transfer roller is running at a similar speed there should be no problem with take up of the paper. An optical sensor mounted into the housing finds the start of each sheet and engages a transfer motor so there is no problem if for example a sheet has moved forward of the roller during any strange operations.

The main PCB is mounted onto the base metalwork via standard PCB standoffs and is fitted with a data connector and a DC connector .

The front panel is mounted onto the base metalwork using snap details and a top metal cover completes the overall product with RFI EMI integrity via four fixings .

The print engine is shown in greater detail in and is designated generally by the reference numeral . The Memjet printhead assembly is in turn designated by the reference numeral . This represents one of the four possible ways to deploy the Memjet printhead in conjunction with the ink cartridge in a product such as CePrint 

The Memjet printhead prints onto the titanium nitride TiN coated transfer roller which rotates in an anticlockwise direction to transfer the image onto a sheet of paper . The paper is pressed against the transfer roller by a spring loaded rubber coated pinch roller in the case of the single sided version. As illustrated in in the case of the double sided version the paper is pressed against one of the transfer rollers under the action of the opposite transfer roller . After transferring the image to the paper the transfer roller continues past a cleaning sponge and finally a rubber wiper . The sponge and the wiper form a cleaning station for cleaning the surface of the transfer roller .

While operational the printhead assembly is held off the transfer roller by a solenoid as shown in . When not operational the printhead assembly is parked against the transfer roller as shown in . The printhead s integral elastomeric seal seals the printhead assembly and prevents the Memjet printhead from drying out.

In the double sided version of CePrint 10 there are dual print engines each with its associated printhead assembly and transfer roller mounted in opposition as illustrated in . The lower print engine is fixed while the upper print engine pivots and is sprung to press against the paper . As previously described the upper transfer roller takes the place of the pinch roller in the single sided version.

The relationship between the ink cartridge printhead assembly and the transfer roller is shown in greater detail in of the drawings. The ink cartridge has four reservoirs and for cyan magenta yellow and black ink respectively.

Each reservoir is in flow communication with a corresponding reservoir in the printhead assembly . These reservoirs in turn supply ink to a Memjet printhead chip via an ink filter . It is to be noted in that the elastomeric capping seal is arranged on both sides of the printhead chip to assist in sealing when the printhead assembly is parked against the transfer roller .

This section describes the printer control protocol used between a host and CePrint . It includes control and status handling as well as the actual page description.

The printer control protocol defines the format and meaning of messages exchanged by the host processor and the printer . The control protocol is defined independently of the transport protocol between the host processor and the printer since the transport protocol depends on the exact nature of the connection.

Each message consists of a 16 bit message code followed by message specific data which may be of fixed or variable size.

The reset printer command can be used to reset the printer to clear an error condition and to abort printing.

The start document command is used to indicate the start of a new document. This resets the printer s page count which is used in the double sided version to identify odd and even pages. The end document command is simply used to indicate the end of the document.

The description of an output page consists of a page header which describes the size and resolution of the page followed by one or more page bands which describe the actual page content. The page header is transmitted to the printer in the start page command. Each page band is transmitted to the printer in a page band command. The last page band is followed by an end page command. The page description is described in detail in Table 4.2.

A printer status message is normally sent in response to a get printer status command. However the nature of the connection between the host processor and the printer may allow the printer to send unsolicited status messages to the host processor. Unsolicited status messages allow timely reporting of printer exceptions to the host processor and thereby to the user without requiring the host processor to poll the printer on a frequent basis.

CePrint reproduces black at full dot resolution 1600 dpi but reproduces contone color at a somewhat lower resolution using halftoning. The page description is therefore divided into a black layer and a contone layer. The black layer is defined to composite over the contone layer.

The black layer consists of a bitmap containing a 1 bit opacity for each pixel. This black layer matte has a resolution which is an integer factor of the printer s dot resolution. The highest supported resolution is 1600 dpi i.e. the printer s full dot resolution.

The contone layer consists of a bitmap containing a 32 bit CMYK color for each pixel. This contone image has a resolution which is an integer factor of the printer s dot resolution. The highest supported resolution is 267 ppi i.e. one sixth the printer s dot resolution.

The contone resolution is also typically an integer factor of the black resolution to simplify calculations in the printer driver. This is not a requirement however.

The black layer and the contone layer are both in compressed form for efficient transmission over the low speed connection to the printer.

CePrint prints with full edge bleed using an 8.5 printhead. It imposes no margins and so has a printable page area which corresponds to the size of its paper A4 or Letter .

The target page size is constrained by the printable page area less the explicit target left and top margins specified in the page description.

Apart from being implicitly defined in relation to the printable page area each page description is complete and self contained. There is no data transmitted to the printer separately from the page description to which the page description refers.

The page description consists of a page header which describes the size and resolution of the page followed by one or more page bands which describe the actual page content.

The page header contains a signature and version which allow the printer to identify the page header format. If the signature and or version are missing or incompatible with the printer then the printer can reject the page.

The page header defines the resolution and size of the target page. The black and contone layers are clipped to the target page if necessary. This happens whenever the black or contone scale factors are not factors of the target page width or height.

The target left and top margins define the positioning of the target page within the printable page area.

The black layer parameters define the pixel size of the black layer and its integer scale factor to the target resolution.

The contone layer parameters define the pixel size of the contone layer and its integer scale factor to the target resolution.

The black layer parameters define the height of the black band and the size of its compressed band data. The variable size black band data follows the fixed size parts of the page band header.

The contone layer parameters define the height of the contone band and the size of its compressed page data. The variable size contone band data follows the variable size black band data.

Table 9 shows the format of the variable size compressed band data which follows the page band header.

The variable size black band data and the variable size contone band data are aligned to 8 byte boundaries. The size of the required padding is included in the size of the fixed size part of the page band header structure and the variable size black band data.

The entire page description has a target size of less than 3 MB and a maximum size of 6 MB in accordance with page buffer memory in the printer.

The following sections describe the format of the compressed black layer and the compressed contone layer.

The Group 3 Facsimile compression algorithm losslessly compresses bi level data for transmission over slow and noisy telephone lines. The bi level data represents scanned black text and graphics on a white background and the algorithm is tuned for this class of images it is explicitly not tuned for example for halftoned bi level images . The 1D Group 3 algorithm runlength encodes each scanline and then Huffman encodes the resulting runlengths. Runlengths in the range 0 to 63 are coded with terminating codes. Runlengths in the range 64 to 2623 are coded with make up codes each representing a multiple of 64 followed by a terminating code. Runlengths exceeding 2623 are coded with multiple make up codes followed by a terminating code. The Huffman tables are fixed but are separately tuned for black and white runs except for make up codes above 1728 which are common . When possible the 2D Group 3 algorithm encodes a scanline as a set of short edge deltas 0 1 2 3 with reference to the previous scanline. The delta symbols are entropy encoded so that the zero delta symbol is only one bit long etc. Edges within a 2D encoded line which can t be delta encoded are runlength encoded and are identified by a prefix. 1D and 2D encoded lines are marked differently. 1D encoded lines are generated at regular intervals whether actually required or not to ensure that the decoder can recover from line noise with minimal image degradation. 2D Group 3 achieves compression ratios of up to 6 1.

The Group 4 Facsimile algorithm losslessly compresses bi level data for transmission over error free communications lines i.e. the lines are truly error free or error correction is done at a lower protocol level . The Group 4 algorithm is based on the 2D Group 3 algorithm with the essential modification that since transmission is assumed to be error free 1D encoded lines are no longer generated at regular intervals as an aid to error recovery. Group 4 achieves compression ratios ranging from 20 1 to 60 1 for the CCITT set of test images.

The design goals and performance of the Group 4 compression algorithm qualify it as a compression algorithm for the bi level black layer. However its Huffman tables are tuned to a lower scanning resolution 100 400 dpi and it encodes runlengths exceeding 2623 awkwardly. At 800 dpi our maximum runlength is currently 6400. Although a Group 4 decoder core might be available for use in the printer controller chip Section 7 it might not handle runlengths exceeding those normally encountered in 400 dpi facsimile applications and so would require modification.

Since most of the benefit of Group 4 comes from the delta encoding a simpler algorithm based on delta encoding alone is likely to meet our requirements. This approach is described in detail below.

The edge delta and runlength EDRL compression format is based loosely on the Group 4 compression format and its precursors.

EDRL uses three kinds of symbols appropriately entropy coded. These are create edge kill edge and edge delta. Each line is coded with reference to its predecessor. The predecessor of the first line is defined to a line of white. Each line is defined to start off white. If a line actually starts of black the less likely situation then it must define a black edge at offset zero. Each line must define an edge at its left hand end i.e. at offset page width.

An edge can be coded with reference to an edge in the previous line if there is an edge within the maximum delta range with the same sense white to black or black to white . This uses one of the edge delta codes. The shorter and likelier deltas have the shorter codes. The maximum delta range 2 is chosen to match the distribution of deltas for typical glyph edges. This distribution is mostly independent of point size. A typical example is given in Table 10.

An edge can also be coded using the length of the run from the previous edge in the same line. This uses one of the create edge codes for short 7 bit and long 13 bit runlengths. For simplicity and unlike Group 4 runlengths are not entropy coded. In order to keep edge deltas implicitly synchronized with edges in the previous line each unused edge in the previous line is killed when passed in the current line. This uses the kill edge code. The end of page code signals the end of the page to the decoder.

Note that 7 bit and 13 bit runlengths are specifically chosen to support 800 dpi A4 Letter pages. Longer runlengths could be supported without significant impact on compression performance. For example if supporting 1600 dpi compression the runlengths should be at least 8 bit and 14 bit respectively. A general purpose choice might be 8 bit and 16 bit thus supporting up to 40 wide 1600 dpi pages.

The full set of codes is defined in Table 11. Note that there is no end of line code. The decoder uses the page width to detect the end of the line. The lengths of the codes are ordered by the relative probabilities of the codes occurrence.

Note that the foregoing describes the compression format not the compression algorithm per se. A variety of equivalent encodings can be produced for the same image some more compact than others. For example a pure runlength encoding conforms to the compression format. The goal of the compression algorithm is to discover a good if not the best encoding for a given image.

The following is a simple algorithm for producing the EDRL encoding of a line with reference to its predecessor.

Note that the algorithm is blind to actual edge continuity between lines and may in fact match the wrong edges between two lines. Happily the compression format has nothing to say about this since it decodes correctly and it is difficult for a wrong match to have a detrimental effect on the compression ratio.

For completeness the corresponding decompression algorithm is given below. It forms the core of the EDRL Expander unit in the printer controller chip Section 7 .

Table 12 shows the compression performance of Group 4 and EDRL on the CCITT test documents used to select the Group 4 algorithm. Each document represents a single page scanned at 400 dpi. Group 4 s superior performance is due to its entropy coded runlengths tuned to 400 dpi features.

Magazine text is typically typeset in a typeface with serifs such as Times at a point size of 10. At this size an A4 Letter page holds up to 14 000 characters though a typical magazine page holds only about 7 000 characters. Text is seldom typeset at a point size smaller than 5. At 800 dpi text cannot be meaningfully rendered at a point size lower than 2 using a standard typeface. Table 13 illustrates the legibility of various point sizes.

Table 14 shows Group 4 and EDRL compression performance on pages of text of varying point sizes rendered at 800 dpi. Note that EDRL achieves the required compression ratio of 2.5 for an entire page of text typeset at a point size of 3. The distribution of characters on the test pages is based on English language statistics.

For a point size of 9 or greater EDRL slightly outperforms Group 4 simply because Group 4 s runlength codes are tuned to 400 dpi.

These compression results bear out the observation that entropy encoded runlengths contribute much less to compression than 2D encoding unless the data is poorly correlated vertically such as in the case of very small characters.

The JPEG compression algorithm lossily compresses a contone image at a specified quality level. It introduces imperceptible image degradation at compression ratios below 5 1 and negligible image degradation at compression ratios below 10 1.

JPEG typically first transforms the image into a color space which separates luminance and chrominance into separate color channels. This allows the chrominance channels to be subsampled without appreciable loss because of the human visual system s relatively greater sensitivity to luminance than chrominance. After this first step each color channel is compressed separately.

The image is divided into 8 8 pixel blocks. Each block is then transformed into the frequency domain via a discrete cosine transform DCT . This transformation has the effect of concentrating image energy in relatively lower frequency coefficients which allows higher frequency coefficients to be more crudely quantized. This quantization is the principal source of compression in JPEG. Further compression is achieved by ordering coefficients by frequency to maximize the likelihood of adjacent zero coefficients and then runlength encoding runs of zeroes. Finally the runlengths and non zero frequency coefficients are entropy coded. Decompression is the inverse process of compression.

The CMYK contone layer is compressed to an interleaved color JPEG bytestream. The interleaving is required for space efficient decompression in the printer but may restrict the decoder to two sets of Huffman tables rather than four i.e. one per color channel . If luminance and chrominance are separated then the luminance channels can share one set of tables and the chrominance channels the other set.

If luminance chrominance separation is deemed necessary either for the purposes of table sharing or for chrominance subsampling then CMY is converted to YCrCb and Cr and Cb are duly subsampled. K is treated as a luminance channel and is not subsampled.

The JPEG bytestream is complete and self contained. It contains all data required for decompression including quantization and Huffman tables.

A printer controller consists of the CePrint central processor CCP chip a 64 MBit RDRAM and a master QA chip .

The CCP contains a general purpose processor and a set of purpose specific functional units controlled by the processor via a processor bus . Only three functional units are non standard an EDRL expander a halftoner compositor and a printhead interface which controls the Memjet printhead .

Software running on the processor coordinates the various functional units to receive expand and print pages. This is described in the next section.

Page expansion and printing proceeds as follows. A page description is received from the host via a host interface and is stored in main memory . 6 MB of main memory is dedicated to page storage. This can hold two pages each not exceeding 3 MB or one page up to 6 MB. If the host generates pages not exceeding 3 MB then the printer operates in streaming mode i.e. it prints one page while receiving the next. If the host generates pages exceeding 3 MB then the printer operates in single page mode i.e. it receives each page and prints it before receiving the next. If the host generates pages exceeding 6 MB then they are rejected by the printer. In practice the printer driver prevents this from happening.

A page consists of two parts the bi level black layer and the contone layer. These are compressed in distinct formats the bi level black layer in EDRL format the contone layer in JPEG format. The first stage of page expansion consists of decompressing the two layers in parallel. The bi level layer is decompressed by the EDRL expander unit the contone layer by a JPEG decoder .

The second stage of page expansion consists of halftoning the contone CMYK data to bi level CMYK and then compositing the bi level black layer over the bi level CMYK layer. The halftoning and compositing is carried out by the halftoner compositor unit .

Finally the composited bi level CMYK image is printed via the printhead interface unit which controls the Memjet printhead .

Because the Memjet printhead prints at high speed the paper must move past the printhead at a constant velocity. If the paper is stopped because data cannot be fed to the printhead fast enough then visible printing irregularities will occur. It is therefore important to transfer bi level CMYK data to the printhead interface at the required rate.

A fully expanded 1600 dpi bi level CMYK page has an image size of 119 MB. Because it is impractical to store an expanded page in printer memory each page is expanded in real time during printing. Thus the various stages of page expansion and printing are pipelined. The page expansion and printing data flow is described in Table 15. The aggregate traffic to from main memory via an interface of 182 MB s is well within the capabilities of current technologies such as Rambus.

Each stage communicates with the next via a shared FIFO in main memory . Each FIFO is organized into lines and the minimum size in lines of each FIFO is designed to accommodate the output window in lines of the producer and the input window in lines of the consumer. Inter stage main memory buffers are described in Table 16. The aggregate buffer space usage of 6.3 MB leaves 1.7 MB free for program code and scratch memory out of the 8 MB available .

Contone page decompression is carried out by the JPEG decoder . Bi level page decompression is carried out by the EDRL expander . Halftoning and compositing is carried out by the halftoner compositor unit . These functional units are described in the following sections.

Each functional unit contains one or more on chip input and or output FIFOs. Each FIFO is allocated a separate channel in a multi channel DMA controller . The DMA controller handles single address rather than double address transfers and so provides a separate request acknowledge interface for each channel.

Each functional unit stalls gracefully whenever an input FIFO is exhausted or an output FIFO is filled.

The processor programs each DMA transfer. The DMA controller generates the address for each word of the transfer on request from the functional unit connected to the channel. The functional unit latches the word onto or off the data bus when its request is acknowledged by the DMA controller . The DMA controller interrupts the processor when the transfer is complete thus allowing the processor to program another transfer on the same channel in a timely fashion.

In general the processor will program another transfer on a channel as soon as the corresponding main memory FIFO is available i.e. non empty for a read non full for a write .

The granularity of channel servicing implemented in the DMA controller depends somewhat on the latency of main memory .

The EDRL expander unit EEU is shown in greater detail in . The unit decompresses an EDRL compressed bi level image.

The input to the EEU is an EDRL bitstream. The output from the EEU is a set of bi level image lines scaled horizontally from the resolution of the expanded bi level image by an integer scale factor to 1600 dpi.

Once started the EEU proceeds until it detects an end of page code in the EDRL bitstream or until it is explicitly stopped via its control register.

The EEU relies on an explicit page width to decode the bitstream. This must be written to a page width register prior to starting the EEU .

The scaling of the expanded bi level image relies on an explicit scale factor. This must be written to a scale factor register prior to starting the EEU .

The EDRL compression format is described in Section 6.2.3.2. It represents a bi level image in terms of its edges. Each edge in each line is coded relative to an edge in the previous line or relative to the previous edge in the same line. No matter how it is coded each edge is ultimately decoded to its distance from the previous edge in the same line. This distance or runlength is then decoded to the string of one bits or zero bits which represent the corresponding part of the image. The decompression algorithm is defined in Section 6.2.3.2.

The EEU consists of a bitstream decoder a state machine edge calculation logic two runlength decoders and a runlength re encoder .

The bitstream decoder decodes an entropy coded codeword from the bitstream and passes it to the state machine . The state machine returns the size of the codeword to the bitstream decoder which allows the decoder to advance to the next codeword. In the case of a create edge code the state machine uses the bitstream decoder to extract the corresponding runlength from the bitstream. The state machine controls the edge calculation logic and runlength decoding encoding as defined in Table 19.

The edge calculation logic is quite simple. The current edge offset in the previous reference and current coding lines are maintained in a reference edge register and edge register respectively. The runlength associated with a create edge code is output directly to the runlength decoder . and is added to the current edge. A delta code is translated into a runlength by adding the associated delta to the reference edge and subtracting the current edge. The generated runlength is output to the runlength decoder . and is added to the current edge. The next runlength is extracted from the runlength encoder and added to the reference edge. A kill edge code simply causes the current reference edge to be skipped. Again the next runlength is extracted from the runlength encoder and added to the reference edge.

Each time the edge calculation logic generates a runlength representing an edge it is passed to the runlength decoder .. While the runlength decoder . decodes the run it generates a stall signal to the state machine . Since the runlength decoder is slower than the edge calculation logic there is not much point in decoupling it. The expanded line accumulates in a line buffer large enough to hold an 8.5 800 dpi line 850 bytes .

The previously expanded line is also buffered in a buffer . It acts as a reference for the decoding of the current line. The previous line is re encoded as runlengths on demand. This is less expensive than buffering the decoded runlengths of the previous line since the worst case is one 13 bit runlength for each pixel 20 KB at 1600 dpi . While the runlength encoder encodes the run it generates a stall signal to the state machine . The runlength encoder uses the page width to detect end of line. The current line buffer and the previous line buffer are concatenated and managed as a single FIFO to simplify the runlength encoder .

The second runlength decoder . decodes the output runlength to a line buffer large enough to hold an 8.5 1600 dpi line 1700 bytes . The runlength passed to this output runlength decoder . is multiplied by the scale factor from the register so this decoder . produces 1600 dpi lines. The line is output scale factor times through the output pixel FIFO. This achieves the required vertical scaling by simple line replication. The EEU could be designed with edge smoothing integrated into its image scaling. A simple smoothing scheme based on template matching can be very effective. This would require a multi line buffer between the low resolution runlength decoder and the smooth scaling unit but would eliminate the high resolution runlength decoder.

The EDRL stream decoder decodes entropy coded EDRL codewords in the input bitstream. It uses a two byte input buffer viewed through a 16 bit barrel shifter whose left most significant edge is always aligned to a codeword boundary in the bitstream. A decoder connected to the barrel shifter decodes a codeword according to Table 18 and supplies the state machine with the corresponding code.

The state machine in turn outputs the length of the code. This is added modulo 8 by an accumulator to the current codeword bit offset to yield the next codeword bit offset. The bit offset in turn controls the barrel shifter . If the codeword bit offset wraps then the carry bit controls the latching of the next byte from the input FIFO. At this time byte is latched to byte and the FIFO output is latched to byte . It takes two cycles of length to fill the input buffer. This is handled by starting states in the state machine .

The EDRL expander state machine controls the edge calculation and runlength expansion logic in response to codes supplied by the EDRL stream decoder . It supplies the EDRL stream decoder with the length of the current codeword and supplies the edge calculation logic with the delta value associated with the current delta code. The state machine also responds to start and stop control signals from a control register and the end of line EOL signal from the edge calculation logic .

The state machine also controls the multi cycle fetch of the runlength associated with a create edge code.

The runlength decoder expands a runlength into a sequence of zero bits or one bits of the corresponding length in the output stream. The first run in a line is assumed to be white color . Each run is assumed to be of the opposite color to its predecessor. If the first run is actually black color then it must be preceded by a zero length white run. The runlength decoder keeps track of the current color internally.

The runlength decoder appends a maximum of 8 bits to the output stream every clock. Runlengths are typically not an integer multiple of 8 and so runs other than the first in an image are typically not byte aligned. The runlength decoder maintains in a byte space register the number of bits available in the byte currently being built. This is initialized to 8 at the beginning of decoding and on the output of every byte.

The decoder starts outputting a run of bits as soon as the next run line latches a non zero value into a runlength register . The decoder effectively stalls when the runlength register goes to zero.

A number of bits of the current color are shifted into an output byte register each clock. The current color is maintained in a 1 bit color register . The number of bits actually output is limited by the number of bits left in the runlength and by the number of spare bits left in the output byte. The number of bits output is subtracted from the runlength and the byte space. When the runlength goes to zero it has been completely decoded although the trailing bits of the run may still be in the output byte register pending output. When the byte space goes to zero the output byte is full and is appended to the output stream.

A 16 bit barrel shifter the output byte register and the color register together implement an 8 bit shift register which can be shifted multiple bit positions every clock with the color as the serial input.

An external reset line is used to reset the runlength decoder at the start of a line. An external next run line is used to request the decoding of a new runlength. It is accompanied by a runlength on an external runlength line . The next run line should not be set on the same clock as the reset line . Because next run inverts the current color the reset of the color sets it to one not zero. An external flush line is used to flush the last byte of the run if incomplete. It can be used on a line by line basis to yield byte aligned lines or on an image basis to yield a byte aligned image.

An external ready line indicates whether the runlength decoder is ready to decode a runlength. It can be used to stall the external logic.

The runlength encoder detects a run of zero or one bits in the input stream. The first run in a line is assumed to be white color . Each run is assumed to be of the opposite color to its predecessor. If the first run is actually black color then the runlength encoder generates a zero length white run at the start of the line. The runlength decoder keeps track of the current color internally.

The runlength encoder reads a maximum of 8 bits from the input stream every clock. It uses a two byte input buffer viewed through a 16 bit barrel shifter whose left most significant edge is always aligned to the current position in the bitstream. An encoder connected to the barrel shifter encodes an 8 bit partial runlength according to Table 20. The 8 bit runlength encoder uses the current color to recognize runs of the appropriate color.

The 8 bit runlength generated by the 8 bit runlength encoder is added to the value in a runlength register . When the 8 bit runlength encoder recognizes the end of the current run it generates an end of run signal which is latched by a ready register . The output of the ready register indicates that the encoder has completed encoding the current runlength accumulated in the runlength register . The output of the ready register is also used to stall the 8 bit runlength encoder . When stalled the 8 bit runlength encoder outputs a zero length run and a zero end of run signal effectively stalling the entire runlength encoder .

The output of the 8 bit runlength encoder is limited by the remaining page width. The actual 8 bit runlength is subtracted from the remaining page width and is added to a module 8 bit position accumulator used to control the barrel shifter 258 and clock the byte stream input.

An external reset line is used to reset the runlength encoder at the start of a line. It resets the current color and latches a page width signal on line into a page width register . An external next run line is used to request another runlength from the runlength encoder . It inverts the current color and resets the runlength register and ready register . An external flush line is used to flush the last byte of the run if incomplete. It can be used on a line by line basis to process byte aligned lines or on an image basis to process a byte aligned image.

An external ready line indicates that the runlength encoder is ready to encode a runlength and that the current runlength is available on a runlength line . It can be used to stall the external logic.

The EEU has an output rate of 124 M 1 bit black pixels s. The core logic generates one runlength every clock. The runlength decoders and the runlength encoder generate consume up to 8 pixels bits per clock. One runlength decoder . and the runlength encoder operate at quarter resolution 800 dpi . The other runlength decoder . operates at full resolution 1600 dpi .

A worst case bi level image consisting of a full page of 3 point text converts to approximately 6 M runlengths at 800 dpi the rendering resolution . At 1600 dpi the horizontal output resolution this gives an average runlength of about 20. Consequently about 40 of 8 pixel output bytes span two runs and so require two clocks instead of one. Output lines are replicated vertically to achieve a vertical resolution of 1600 dpi. When a line is being replicated rather than generated it has a perfect efficiency of 8 pixels per clock thus the overhead is halved to 20 .

The full resolution runlength decoder in the output stage of the EEU is the slowest component in the EEU . The minimum clock speed of the EEU is therefore dictated by the output pixel rate of the EEU 124 Mpixels s divided by the width of the runlength decoder 8 adjusted for its worst case overhead 20 . This gives a minimum speed of about 22 MHz.

The input to the JPEG decoder is a JPEG bitstream. The output from the JPEG decoder is a set of contone CMYK image lines.

When decompressing the JPEG decoder writes its output in the form of 8 8 pixel blocks. These are sometimes converted to full width lines via an page width 8 strip buffer closely coupled with the codec. This would require a 67 KB buffer. We instead use 8 parallel pixel FIFOs with shared bus access and 8 corresponding DMA channels as shown in .

The JPEG decoder has an output rate of 3.5 M 32 bit CMYK pixels s. The required clock speed of the decoder depends on the design of the decoder.

The halftoner compositor unit HCU combines the functions of halftoning the contone CMYK layer to bi level CMYK and compositing the black layer over the halftoned contone layer.

The input to the HCU is an expanded 267 ppi CMYK contone layer and an expanded 1600 dpi black layer. The output from the HCU is a set of 1600 dpi bi level CMYK image lines.

Once started the HCU proceeds until it detects an end of page condition or until it is explicitly stopped via its control register .

The HCU generates a page of dots of a specified width and length. The width and length must be written to page width and page length registers of the control registers prior to starting the HCU . The page width corresponds to the width of the printhead. The page length corresponds to the length of the target page.

The HCU generates target page data between specified left and right margins relative to the page width. The positions of the left and right margins must be written to left margin and right margin registers of the control registers prior to starting the HCU . The distance from the left margin to the right margin corresponds to the target page width.

The HCU consumes black and contone data according to specified black and contone page widths. These page widths must be written to black page width and contone page width registers of the control registers prior to starting the HCU . The HCU clips black and contone data to the target page width. This allows the black and contone page widths to exceed the target page width without requiring any special end of line logic at the input FIFO level.

The relationships between the page width the black and contone page widths and the margins are illustrated in .

The HCU scales contone data to printer resolution both horizontally and vertically based on a specified scale factor. This scale factor must be written to a contone scale factor register of the control registers prior to starting the HCU .

The consumer of the data produced by the HCU is the printhead interface . The printhead interface requires bi level CMYK image data in planar format i.e. with the color planes separated. Further it also requires that even and odd pixels are separated. The output stage of the HCU therefore uses 8 parallel pixel FIFOs one each for even cyan odd cyan even magenta odd magenta even yellow odd yellow even black and odd black.

An input contone CMYK FIFO is a full 9 KB line buffer. The line is used contone scale factor times to effect vertical up scaling via line replication. FIFO write address wrapping is disabled until the start of the last use of the line. An alternative is to read the line from main memory contone scale factor times increasing memory traffic by 44 MB s but avoiding the need for the on chip 9 KB line buffer.

A multi threshold dither unit is shown in of the drawings. A general 256 layer dither volume provides great flexibility in dither cell design by decoupling different intensity levels. General dither volumes can be large a 64 64 256 dither volume for example has a size of 128 KB. They are also inefficient to access since each color component requires the retrieval of a different bit from the volume. In practice there is no need to fully decouple each layer of the dither volume. Each dot column of the volume can be implemented as a fixed set of thresholds rather than 256 separate bits. Using three 8 bit thresholds for example only consumes 24 bits. Now n thresholds define n 1 intensity intervals within which the corresponding dither cell location is alternately not set or set. The contone pixel value being dithered uniquely selects one of the n 1 intervals and this determines the value of the corresponding output dot.

We dither the contone data using a triple threshold 64 64 3 8 bit 12 KB dither volume. The three thresholds form a convenient 24 bit value which can be retrieved from the dither cell ROM in one cycle. If dither cell registration is desired between color planes then the same triple threshold value can be retrieved once and used to dither each color component. If dither cell registration is not desired then the dither cell can be split into four subcells and stored in four separately addressable ROMs from which four different triple threshold values can be retrieved in parallel in one cycle. Using the addressing scheme shown below the four color planes share the same dither cell at vertical and or horizontal offsets of 32 dots from each other.

Each triple threshold unit converts a triple threshold value and an intensity value into an interval and thence a one or zero bit. The triple thresholding rules are shown in Table 22. The corresponding logic is shown in .

A composite unit of the HCU composites a black layer dot over a halftoned CMYK layer dot. If the black layer opacity is one then the halftoned CMY is set to zero.

Given a 4 bit halftoned color CMYKand a 1 bit black layer opacity K the composite logic is as defined in Table 23.

A clock enable generator of the HCU generates enable signals for clocking the contone CMYK pixel input the black dot input and the CMYK dot output.

As described earlier the contone pixel input buffer is used as both a line buffer and a FIFO. Each line is read once and then used contone scale factor times. FIFO write address wrapping is disabled until the start of the final replicated use of the line at which time the clock enable generator generates a contone line advance enable signal which enables wrapping.

The clock enable generator also generates an even signal which is used to select the even or odd set of output dot FIFOs and a margin signal which is used to generate white dots when the current dot position is in the left or right margin of the page.

The clock enable generator uses a set of counters. The internal logic of the counters is defined in Table 24. The logic of the clock enable signals is defined in Table 25.

The HCU has an output rate of 124 M 4 bit CMYK pixels s. Since it generates one pixel per clock it must be clocked at at least 124 MHz.

CePrint uses an 8.5 CMYK Memjet printhead as described in Section 9. The printhead consists of 17 segments arranged in 2 segment groups. The first segment group contains 9 segments and the second group contains 8 segments. There are 13 600 nozzles of each color in the printhead making a total of 54 400 nozzles.

The printhead interface is a standard Memjet printhead interface as described in Section 10 configured with the following operating parameters 

Although the printhead interface has a number of external connections not all are used for an 8.5 printhead so not all are connected to external pins on the CCP . Specifically the value for SegmentGroups implies that there are only 2 SRClock pins and 2 SenseSegSelect pins. All 36 ColorData pins however are required.

CePrint prints an 8.3 11.7 page in 2 seconds. The printhead must therefore print 18 720 lines 11.7 1600 dpi in 2 seconds which yields a line time of about 107 s. Within the printhead interface a single Print Cycle and a single Load Cycle must both complete within this time. In addition the paper must advance by about 16 m in the same time.

In high speed print mode the Memjet printhead can print an entire line in 100 s. Since all segments fire at the same time 544 nozzles are fired simultaneously with each firing pulse. This leaves 7 s for other tasks between each line.

The 1600 SRClock pulses 800 each of SRClock1 and SRClock2 to the printhead SRClock1 has 36 bits of valid data and SRClock2 has 32 bits of valid data must also take place within the 107 s line time. Restricting the timing to 100 s the length of an SRClock pulse cannot exceed 100 s 1600 62.5 ns. The printhead must therefore be clocked at 16 MHz.

The printhead interface has a nominal pixel rate of 124 M 4 bit CMYK pixels s. However because it is only active for 100 s out of every 107 s it must be clocked at at least 140 MHz. This can be increased to 144 MHz to make it an integer multiple of the printhead speed.

The processor runs the control program which synchronizes the other functional units during page reception expansion and printing. It also runs the device drivers for the various external interfaces and responds to user actions through the user interface.

It must have low interrupt latency to provide efficient DMA management but otherwise does not need to be particularly high performance.

The DMA controller supports single address transfers on 29 channels see Table 26 . It generates vectored interrupts to the processor on transfer completion.

The Rambus interface provides the high speed interface to the external 8 MB 64 Mbit Rambus DRAM RDRAM .

The host interface provides a connection to the host processor with a speed of at least 1.5 MB s or 3 MB s for the double sided version of CePrint .

A speaker interface contains a small FIFO used for DMA mediated transfers of sound clips from main memory an 8 bit digital to analog converter DAC which converts each 8 bit sample value to a voltage and an amplifier which feeds an external speaker . When the FIFO is empty it outputs a zero value.

The processor outputs a sound clip to the speaker simply by programming the DMA channel of the speaker interface .

A parallel interface provides I O on a number of parallel external signal lines. It allows the processor to sense or control the devices listed in Table 27.

A serial interface provides two standard low speed serial ports. One port is used to connect to the master QA chip . The other is used to connect to a QA chip in the ink cartridge. The processor mediated protocol between the two is used to authenticate the ink cartridge. The processor can then retrieve ink characteristics from the QA chip as well as the remaining volume of each ink. The processor uses the ink characteristics to properly configure the Memjet printhead . It uses the remaining ink volumes updated on a page by page basis with ink consumption information accumulated by the printhead interface to ensure that it never allows the printhead to be damaged by running dry.

The QA chip in the ink cartridge contains information required for maintaining the best possible print quality and is implemented using an authentication chip. The 256 bits of data in the authentication chip are allocated as follows 

Before each page is printed the processor must check the amount of ink remaining to ensure there is enough for an entire worst case page. Once the page has been printed the processor multiplies the total number of drops of each color obtained from the printhead interface by the drop volume. The amount of printed ink is subtracted from the amount of ink remaining. The unit of measurement for ink remaining is nanolitres so 32 bits can represent over 4 liters of ink. The amount of ink used for a page must be rounded up to the nearest nanolitre i.e. approximately 1000 printed dots .

An inter CCP interface provides a bi directional high speed serial communications link to a second CCP and is used in multi CCP configurations such as the double sided version of the printer which contains two CCPs.

The link has a minimum speed of 30 MB s to support timely distribution of page data and may be implemented using a technology such as IEEE 1394 or Rambus.

A standard JTAG Joint Test Action Group interface not shown is included for testing purposes. Due to the complexity of the chip a variety of testing techniques are required including BIST Built In Self Test and functional block isolation. An overhead of 10 in chip area is assumed for overall chip testing circuitry.

The double sided version of CePrint contains two complete print engines or printing units one for the front of the paper one for the back. Each printing unit consists of a printer controller a printhead assembly containing a Memjet printhead and a transfer roller . Both printing units share the same ink supply.

The back side or lower printing unit acts as the master unit. It is responsible for global printer functions such as communicating with the host handling the ink cartridge handling the user interface and controlling the paper transport. The front side or upper printing unit acts as a slave unit. It obtains pages from the host processor via the master unit and is synchronized by the master unit during printing.

Both printer controllers consist of a CePrint central processor CCP and a local 8 MB RDRAM . The external interfaces of the master unit are used in the same way as in the single sided version of CePrint but only the memory interface and the printhead interface of the slave unit are used. An external master slave pin on the CCP selects the mode of operation.

The master CCP M presents a unified view of the printer to the host processor. It hides the presence of the slave CCP S.

Pages are transmitted from the host processor to the printer in page order. The first page of a document is always a front side page and front side and back side pages are always interleaved. Thus odd numbered pages are front side pages and even numbered pages are back side pages. To print in single sided mode on either the front side or back side of the paper the host must send appropriate blank pages to the printer . The printer expects a page description for every page.

When the master CCP M receives a page command from the host processor relating to an odd numbered page it routes the command to the slave CCP S via the inter CCP serial link . To avoid imposing undue restrictions on the host link and its protocol each command is received in its entirety and stored in the master s local memory M before being forwarded to the memory S of the slave. This introduces only a small delay because the inter CCP link is fast. To ensure that the master CCP M always has a page buffer available for a page destined for the slave the master is deliberately made the back side CCP so that it receives the front side odd numbered page before it receives the matching back side even numbered page.

Once the master CCP M and the slave CCP S have received their pages the master CCP M initiates actual printing. This consists of starting the page expansion and printing processes in the master CCP M and initiating the same processes in the slave CCP S via a command sent over the inter CCP serial link .

To achieve perfect registration between the front side and back side printed pages the printhead interfaces of both CCPs are synchronized to a common line synchronization signal. The synchronization signal is generated by the master CCP M.

Once the printing pipelines in both CCPs are sufficiently primed as indicated by the stall status of the line loader format unit LLFU of the printhead interface Section 10.4 the master CCP M starts the line synchronization generator unit LSGU of the printhead interface Section 10.2 . The master CCP M obtains the status of the slave CCP S LLFU via a poll sent over the inter CCP serial link .

After the printing of a page or more frequently the master M obtains ink consumption information from the slave S over the inter CCP link . It uses this to update the remaining ink volume in the ink cartridge as described in Section 7.5.4.1.

The master and slave CCPs M S also exchange error events and host initiated printer reset commands over the inter CCP link .

The Memjet printhead is a drop on demand 1600 dpi inkjet printer that produces bi level dots in up to 4 colors to produce a printed page of a particular width. Since the printhead prints dots at 1600 dpi each dot is approximately 22.5 mm in diameter and spaced 15.875 mm apart. Because the printing is bi level the input image should be dithered or error diffused for best results.

Typically a Memjet printhead for a particular application is page width. This enables the printhead to be stationary and allows the paper to move past the printhead . illustrates a typical configuration.

The Memjet printhead is composed of a number of identical inch Memjet segments. The segment is therefore the basic building block for constructing the printhead .

This section examines the structure of a single segment the basic building block for constructing the Memjet printhead .

The nozzles within a single segment are grouped for reasons of physical stability as well as minimization of power consumption during printing. In terms of physical stability a total of 10 nozzles share the same ink reservoir. In terms of power consumption groupings are made to enable a low speed and a high speed printing mode.

Memjet segments support two printing speeds to allow speed power consumption trade offs to be made in different product configurations.

In the low speed printing mode 4 nozzles of each color are fired from the segment at a time. The exact number of nozzles fired depends on how many colors are present in the printhead. In a four color e.g. CMYK printing environment this equates to 16 nozzles firing simultaneously. In a three color e.g. CMY printing environment this equates to 12 nozzles firing simultaneously. To fire all the nozzles in a segment 200 different sets of nozzles must be fired.

In the high speed printing mode 8 nozzles of each color are fired from the segment at a time. The exact number of nozzles fired depends on how many colors are present in the printhead. In a four color e.g. CMYK printing environment this equates to 32 nozzles firing simultaneously. In a three color e.g. CMY printing environment this equates to 24 nozzles firing simultaneously. To fire all the nozzles in a segment 100 different sets of nozzles must be fired.

The power consumption in the low speed mode is half that of the high speed mode. Note however that the energy consumed to print a page is the same in both cases.

A single pod consists of 10 nozzles sharing a common ink reservoir. 5 nozzles are in one row and 5 are in another. Each nozzle produces dots 22.5 mm in diameter spaced on a 15.875 mm grid to print at 1600 dpi. shows the arrangement of a single pod with the nozzles numbered according to the order in which they must be fired.

Although the nozzles are fired in this order the relationship of nozzles and physical placement of dots on the printed page is different. The nozzles from one row represent the even dots from one line on the page and the nozzles on the other row represent the odd dots from the adjacent line on the page. shows the same pod with the nozzles numbered according to the order in which they must be loaded.

The nozzles within a pod are therefore logically separated by the width of 1 dot. The exact distance between the nozzles will depend on the properties of the Memjet firing mechanism. The printhead is designed with staggered nozzles designed to match the flow of paper.

One pod of each color are grouped together into a chromapod. The number of pods in a chromapod will depend on the particular application. In a monochrome printing system such as one that prints only black there is only a single color and hence a single pod. Photo printing application printheads require 3 colors cyan magenta yellow so Memjet segments used for these applications will have 3 pods per chromapod one pod of each color . The expected maximum number of pods in a chromapod is 4 as used in a CMYK cyan magenta yellow black printing system such as a desktop printer . This maximum of 4 colors is not imposed by any physical constraints it is merely an expected maximum from the expected applications of course as the number of colors increases the cost of the segment increases and the number of these larger segments that can be produced from a single silicon wafer decreases .

A chromapod represents different color components of the same horizontal set of 10 dots on different lines. The exact distance between different color pods depends on the Memjet operating parameters and may vary from one Memjet design to another. The distance is considered to be a constant number of dot widths and must therefore be taken into account when printing the dots printed by the cyan nozzles will be for different lines than those printed by the magenta yellow or black nozzles. The printing algorithm must allow for a variable distance up to about 8 dot widths between colors. illustrates a single chromapod for a CMYK printing application.

Five chromapods are organized into a single podgroup. A podgroup therefore contains 50 nozzles for each color. The arrangement is shown in with chromapods numbered 0 4 and using a CMYK chromapod as the example. Note that the distance between adjacent chromapods is exaggerated for clarity.

Two podgroups are organized into a single phasegroup. The phasegroup is so named because groups of nozzles within a phasegroup are fired simultaneously during a given firing phase this is explained in more detail below . The formation of a phasegroup from 2 podgroups is entirely for the purposes of low speed and high speed printing via 2 PodgroupEnable lines.

During low speed printing only one of the two PodgroupEnable lines is set in a given firing pulse so only one podgroup of the two fires nozzles. During high speed printing both PodgroupEnable lines are set so both podgroups fire nozzles. Consequently a low speed print takes twice as long as a high speed print since the high speed print fires twice as many nozzles at once.

Two phasegroups PhasegroupA and PhasegroupB are organized into a single firegroup with 4 firegroups in each segment. Firegroups are so named because they all fire the same nozzles simultaneously. Two enable lines AEnable and BEnable allow the firing of PhasegroupA nozzles and PhasegroupB nozzles independently as different firing phases. The arrangement is shown in . The distance between adjacent groupings is exaggerated for clarity.

A single segment contains a total of 800 C nozzles where C is the number of colors in the segment. A Print Cycle involves the firing of up to all of these nozzles dependent on the information to be printed. A Load Cycle involves the loading up of the segment with the information to be printed during the subsequent Print Cycle.

Each nozzle has an associated NozzleEnable bit that determines whether or not the nozzle will fire during the Print Cycle. The NozzleEnable bits one per nozzle are loaded via a set of shift registers.

Logically there are C shift registers per segment one per color each 800 deep. As bits are shifted into the shift register for a given color they are directed to the lower and upper nozzles on alternate pulses. Internally each 800 deep shift register is comprised of two 400 deep shift registers one for the upper nozzles and one for the lower nozzles. Alternate bits are shifted into the alternate internal registers. As far as the external interface is concerned however there is a single 800 deep shift register.

Once all the shift registers have been fully loaded 800 load pulses all of the bits are transferred in parallel to the appropriate NozzleEnable bits. This equates to a single parallel transfer of 800 C bits. Once the transfer has taken place the Print Cycle can begin. The Print Cycle and the Load Cycle can occur simultaneously as long as the parallel load of all NozzleEnable bits occurs at the end of the Print Cycle.

The Load Cycle is concerned with loading the segment s shift registers with the next Print Cycle s NozzleEnable bits.

Each segment has C inputs directly related to the C shift registers where C is the number of colors in the segment . These inputs are named ColorNData where N is 1 to C for example a 4 color segment would have 4 inputs labeled ColorData ColorData ColorData and ColorData . A single pulse on the SRClock line transfers C bits into the appropriate shift registers. Alternate pulses transfer bits to the lower and upper nozzles respectively. A total of 800 pulses are required for the complete transfer of data. Once all 800 C bits have been transferred a single pulse on the PTransfer line causes the parallel transfer of data from the shift registers to the appropriate NozzleEnable bits.

The parallel transfer via a pulse on PTransfer must take place after the Print Cycle has finished. Otherwise the NozzleEnable bits for the line being printed will be incorrect.

It is important to note that the odd and even dot outputs although printed during the same Print Cycle do not appear on the same physical output line. The physical separation of odd and even nozzles within the printhead as well as separation between nozzles of different colors ensures that they will produce dots on different lines of the page. This relative difference must be accounted for when loading the data into the printhead . The actual difference in lines depends on the characteristics of the inkjet mechanism used in the printhead . The differences can be defined by variables Dand Dwhere Dis the distance between nozzles of different colors and Dis the distance between nozzles of the same color. Table 30 shows the dots transferred to a C color segment on the first 4 pulses.

Data can be clocked into a segment at a maximum rate of 20 MHz which will load the entire 800 C bits of data in 40 s.

A single Memjet printhead segment contains 800 nozzles. To fire them all at once would consume too much power and be problematic in terms of ink refill and nozzle interference. This problem is made more apparent when we consider that a Memjet printhead is composed of multiple inch segments each with 800 nozzles. Consequently two firing modes are defined a low speed printing mode and a high speed printing mode 

When one of the PodgroupEnable lines is set only the specified Podgroup s 4 nozzles will fire as determined by ChromapodSelect and NozzleSelect. When both of the PodgroupEnable lines are set both of the podgroups will fire their nozzles. For the low speed mode two fire pulses are required with PodgroupEnable 10 and 01 respectively. For the high speed mode only one fire pulse is required with PodgroupEnable 11.

The duration of the firing pulse is given by the AEnable and BEnable lines which fire the PhasegroupA and PhasegroupB nozzles from all firegroups respectively. The typical duration of a firing pulse is 1.3 1.8 ms. The duration of a pulse depends on the viscosity of the ink dependent on temperature and ink characteristics and the amount of power available to the printhead . See Section 9.1.3 for details on feedback from the printhead in order to compensate for temperature change.

The AEnable and BEnable are separate lines in order that the firing pulses can overlap. Thus the 200 phases of a low speed Print Cycle consist of 100 A phases and 100 B phases effectively giving 100 sets of Phase A and Phase B. Likewise the 100 phases of a high speed print cycle consist of 50 A phases and 50 B phases effectively giving 50 phases of phase A and phase B.

For the low speed printing mode the firing order is similar. For each phase of the high speed mode where PodgroupEnable was 11 two phases of PodgroupEnable 01 and 10 are substituted as follows 

When a nozzle fires it takes approximately 100 s to refill. The nozzle cannot be fired before this refill time has elapsed. This limits the fastest printing speed to 100 s per line. In the high speed print mode the time to print a line is 100 s so the time between firing a nozzle from one line to the next matches the refill time. The low speed print mode is slower than this so is also acceptable.

The firing of a nozzle also causes acoustic perturbations for a limited time within the common ink reservoir of that nozzle s pod. The perturbations can interfere with the firing of another nozzle within the same pod. Consequently the firing of nozzles within a pod should be offset from each other as long as possible. We therefore fire four nozzles from a chromapod one nozzle per color and then move onto the next chromapod within the podgroup.

As the ink channel is 300 mm long and the velocity of sound in the ink is around 1500 m s the resonant frequency of the ink channel is 2.5 MHz. Thus the low speed mode allows 50 resonant cycles for the acoustic pulse to dampen and the high speed mode allows 25 resonant cycles. Consequently any acoustic interference is minimal in both cases.

A segment produces several lines of feedback. The feedback lines are used to adjust the timing of the firing pulses. Since multiple segments are collected together into a printhead it is effective to share the feedback lines as a tri state bus with only one of the segments placing the feedback information on the feedback lines.

A pulse on the segment s SenseSegSelect line ANDed with data on Color1Data selects if the particular segment will provide the feedback. The feedback sense lines will come from that segment until the next SenseSegSelect pulse. The feedback sense lines are as follows 

The printing process has a strong tendency to stay at the equilibrium temperature. To ensure that the first section of a printed image such as a photograph has a consistent dot size the equilibrium temperature must be met before printing any dots. This is accomplished via a preheat cycle.

The Preheat cycle involves a single Load Cycle to all nozzles of a segment with is i.e. setting all nozzles to fire and a number of short firing pulses to each nozzle. The duration of the pulse must be insufficient to fire the drops but enough to heat up the ink. Altogether about 200 pulses for each nozzle are required cycling through in the same sequence as a standard Print Cycle.

Feedback during the Preheat mode is provided by Tsense and continues until equilibrium temperature is reached about 30 C. above ambient . The duration of the Preheat mode is around 50 milliseconds and depends on the ink composition.

Preheat is performed before each print job. This does not affect performance as it is done while the data is being transferred to the printer.

In order to reduce the chances of nozzles becoming clogged a cleaning cycle can be undertaken before each print job. Each nozzle is fired a number of times into an absorbent sponge.

The cleaning cycle involves a single Load Cycle to all nozzles of a segment with 1s i.e. setting all nozzles to fire and a number of firing pulses to each nozzle. The nozzles are cleaned via the same nozzle firing sequence as a standard Print Cycle. The number of times that each nozzle is fired depends upon the ink composition and the time that the printer has been idle. As with preheat the cleaning cycle has no effect on printer performance.

A Memjet printhead is composed of a number of identical inch printhead segments. These inch segments are manufactured together or placed together after manufacture to produce a printhead of the desired length. Each inch segments prints 800 1600 dpi bi level dots in up to 4 colors over a different part of the page to produce the final image. Although each segment produces 800 dots of the final image each dot is represented by a combination of colored inks.

A 4 inch printhead for example consists of 8 segments typically manufactured as a monolithic printhead. In a typical 4 color printing application cyan magenta yellow black each of the segments prints bi level cyan magenta yellow and black dots over a different part of the page to produce the final image.

An 8 inch printhead can be constructed from two 4 inch printheads or from a single 8 inch printhead consisting of 16 segments. Regardless of the construction mechanism the effective printhead is still 8 inches in length.

A 2 inch printhead has a similar arrangement but only uses 4 segments. Likewise a full bleed A4 Letter printer uses 17 segments for an effective 8.5 inch printing area.

Since the total number of nozzles in a segment is 800 C see Table 29 the total number of nozzles in a given printhead with S segments is 800 CS. Thus segment N is responsible for printing dots 800N to 800N 799.

A number of considerations must be made when wiring up a printhead. As the width of the printhead increases the number of segments increases and the number of connections also increases. Each segment has its own ColorData connections C of them as well as SRClock and other connections for loading and printing.

When the number of segments S is small it is reasonable to load all the segments simultaneously by using a common SRClock line and placing C bits of data on each of the ColorData inputs for the segments. In a 4 inch printer S 8 and therefore the total number of bits to transfer to the printhead in a single SRClock pulse is 32. However for an 8 inch printer S 16 and it is unlikely to be reasonable to have 64 data lines running from the print data generator to the printhead.

Instead it is convenient to group a number of segments together for loading purposes. Each group of segments is small enough to be loaded simultaneously and share an SRClock. For example an 8 inch printhead can have 2 segment groups each segment group containing 8 segments. 32 ColorData lines can be shared for both groups with 2 SRClock lines one per segment group.

When the number of segment groups is not easily divisible it is still convenient to group the segments. One example is a 8.5 inch printer for producing A4 Letter pages. There are 17 segments and these can be grouped as two groups of 9 9 C bits of data going to each segment with all 9 C bits used in the first group and only 8 C bits used for the second group or as 3 groups of 6 again C bits are unused in the last group .

As the number of segment groups increases the time taken to load the printhead increases. When there is only one group 800 load pulses are required each pulse transfers C data bits . When there are G groups 800 G load pulses are required. The bandwidth of the connection between the data generator and the printhead must be able to cope and be within the allowable timing parameters for the particular application.

If G is the number of segment groups and L is the largest number of segments in a group the printhead requires LC ColorData lines and G SRClock lines. Regardless of G only a single PTransfer line is required it can be shared across all segments.

Since L segments in each segment group are loaded with a single SRClock pulse any printing process must produce the data in the correct sequence for the printhead. As an example when G 2 and L 4 the first SRClock1 pulse will transfer the ColorData bits for the next Print Cycle s dot 0 800 1600 and 2400. The first SRClock2 pulse will transfer the ColorData bits for the next Print Cycle s dot 3200 4000 4800 and 5600. The second SRClock1 pulse will transfer the ColorData bits for the next Print Cycle s dot 1 801 1601 and 2401. The second SRClock2 pulse will transfer the ColorData bits for the next Print Cycle s dot 3201 4001 4801 and 5601.

After 800 G SRClock pulses 800 to each of SRClock1 and SRClock2 the entire line has been loaded into the printhead and the common PTransfer pulse can be given.

It is important to note that the odd and even color outputs although printed during the same Print Cycle do not appear on the same physical output line. The physical separation of odd and even nozzles within the printhead as well as separation between nozzles of different colors ensures that they will produce dots on different lines of the page. This relative difference must be accounted for when loading the data into the printhead. The actual difference in lines depends on the characteristics of the inkjet mechanism used in the printhead. The differences can be defined by variables Dand Dwhere Dis the distance between nozzles of different colors and Dis the distance between nozzles of the same color. Considering only a single segment group Table 32 shows the dots transferred to segment n of a printhead during the first 4 pulses of the shared SRClock.

With regards to printing we print 4 C nozzles from each segment in the low speed printing mode and 8 C nozzles from each segment in the high speed printing mode.

While it is certainly possible to wire up segments in any way we only consider the situation where all segments fire simultaneously. This is because the low speed printing mode allows low power printing for small printheads e.g. 2 inch and 4 inch and the controller chip design assumes there is sufficient power available for the large print sizes such as 8 18 inches . It is a simple matter to alter the connections in the printhead to allow grouping of firing should a particular application require it.

When all segments are fired at the same time 4 CS nozzles are fired in the low speed printing mode and 8 CS nozzles are fired in the high speed printing mode. Since all segments print simultaneously the printing logic is the same as defined in Section 9.1.2.2.

A segment produces several lines of feedback as defined in Section 9.1.3. The feedback lines are used to adjust the timing of the firing pulses. Since multiple segments are collected together into a printhead it is effective to share the feedback lines as a tri state bus with only one of the segments placing the feedback information on the feedback lines at a time.

Since the selection of which segment will place the feedback information on the shared Tsense Vsense Rsense and Wsense lines uses the Color1Data line the groupings of segments for loading data can be used for selecting the segment for feedback.

Just as there are G SRClock lines a single line is shared between segments of the same segment group there are G SenseSegSelect lines shared in the same way. When the correct SenseSegSelect line is pulsed the segment of that group whose Color1Data bit is set will start to place data on the shared feedback lines. The segment previously active in terms of feedback must also be disabled by having a 0 on its Color1Data bit and this segment may be in a different segment group. Therefore when there is more than one segment group changing the feedback segment requires two steps disabling the old segment and enabling the new segment.

This section assumes that the printhead has been constructed from a number of segments as described in the previous sections. It assumes that for data loading purposes the segments have been grouped into G segment groups with L segments in the largest segment group. It assumes there are C colors in the printhead. It assumes that the firing mechanism for the printhead is that all segments fire simultaneously and only one segment at a time places feedback information on a common tri state bus. Assuming all these things Table 33 lists the external connections that are available from a printhead 

The printhead interface PHI is the means by which the processor loads the Memjet printhead with the dots to be printed and controls the actual dot printing process. The PHI contains 

The units within the PHI are controlled by a number of registers that are programmed by the processor . In addition the processor is responsible for setting up the appropriate parameters in the DMA controller for the transfers from memory to the LLFU. This includes loading white all 0 s into appropriate colors during the start and end of a page so that the page has clean edges.

The PHI is capable of dealing with a variety of printhead lengths and formats. In terms of broad operating customizations the PHI is parameterized as follows 

The internal structure of the PHI allows for a maximum of 4 colors 9 segments per transfer and 4 transfers. Transferring 4 colors to 9 segments is 36 bits per transfer and 4 transfers to 9 segments equates to a maximum printed line length of 18 inches. The total number of dots per line printed by an 18 inch 4 color printhead is 115 200 18 1600 4 .

In the PHI there are two LSGUs . The first LSGU produces LineSync0 which is used to control the Memjet Interface in all synchronized chips. The second LSGU produces LineSync1 which is used to pulse the paper drive stepper motor.

The Master Slave pin on the chip allows multiple chips to be connected together for side by side printing front back printing etc. via a Master Slave relationship. When the Master Slave pin is attached to VDD the chip is considered to be the Master and LineSync pulses generated by the two LineSyncGen units are enabled onto the two tri state LineSync common lines LineSync0 and LineSync1 shared by all the chips . When the Master Slave pin is attached to GND the chip is considered to be the Slave and LineSync pulses generated by the two LineSyncGen units are not enabled onto the common LineSync lines. In this way the Master chip s LineSync pulses are used by all PHIs on all the connected chips.

The following sections detail the LineSyncGen Unit the Line Loader Format Unit and Memjet Interface respectively.

The LineSyncGen units LSGU are responsible for generating the synchronization pulses required for printing a page. Each LSGU produces an external LineSync signal to enable line synchronization. The generator inside the LGSU generates a LineSync pulse when told to go and then every so many cycles until told to stop.

The exact number of cycles between LineSync pulses is determined by the CyclesBetweenPulses register one per generator. It must be at least long enough to allow one line to print 100 s or 200 ms depending on whether the speed is low or high and another line to load but can be longer as desired for example to accommodate special requirements of paper transport circuitry . If the CyclesBetweenPulses register is set to a number less than a line print time the page will not print properly since each LineSync pulse will arrive before the particular line has finished printing.

The LineSync pulse is not used directly from the LGSU . The LineSync pulse is enabled onto a tri state LineSync line only if the Master Slave pin is set to Master. Consequently the LineSync pulse is only used in the form as generated by the Master chip pulses generated by Slave chips are ignored .

The Memjet interface MJI transfers data to the Memjet printhead and controls the nozzle firing sequences during a print.

The MJI is simply a State Machine see which follows the printhead loading and firing order described in Section 9.2. 1 Section 9.2.2 and includes the functionality of the Preheat Cycle and Cleaning Cycle as described in Section 9.1.4 and Section 9.1.5. Both high speed and low speed printing modes are available although the MJI always fires a given nozzle from all segments in a printhead simultaneously there is no separate firing of nozzles from one segment and then others . Dot counts for each color are also kept by the MJI .

The MJI knows how many lines it has to print for the page. When the MJI is told to go it waits for a LineSync pulse before it starts the first line. Once it has finished loading printing a line it waits until the next LineSync pulse before starting the next line. The MJI stops once the specified number of lines has been loaded printed and ignores any further LineSync pulses.

The MJI is therefore directly connected to the LLFU LineSync0 shared between all synchronized chips and the external Memjet printhead .

The MJI accepts 36 bits of data from the LLFU . Of these 36 bits only the bits corresponding to the number of segments and number of colors will be valid. For example if there are only 2 colors and 9 segments bits will be valid for segment 0 bits will be invalid bits will be valid for segment 1 bits will be invalid etc. The state machine does not care which bits are valid and which bits are not valid it merely passes the bits out to the printhead . The data lines and control signals coming out of the MJI can be wired appropriately to the pinouts of the chip using as few pins as required by the application range of the chip see Section 10.3.1 for more information .

The MJI has a number of connections to the printhead including a maximum of 4 colors clocked in to a maximum of 9 segments per transfer to a maximum of 4 segment groups. The lines coming from the MJI can be directly connected to pins on the chip although not all lines will always be pins. For example if the chip is specifically designed for only connecting to 8 inch CMYK printers only 32 bits of data need to be transferred each transfer pulse. Consequently 32 pins of data out 8 pins per color and not 36 pins are required. In the same way only 2 SRClock pulses are required so only 2 pins instead of 4 pins are required to cater for the different SRClocks. And so on.

If the chip must be completely generic then all connections from the MJI must be connected to pins on the chip and thence to the Memjet printhead .

Table 37 lists the maximum connections from the MJI many of which are always connected to pins on the chip. Where the number of pins is variable a footnote explains what the number of pins depends upon. The sense of input and output is with respect to the MJI . The names correspond to the pin connections on the printhead .

The duration of firing pulses on the AEnable and BEnable lines depend on the viscosity of the ink which is dependant on temperature and ink characteristics and the amount of power available to the printhead . The typical pulse duration range is 1.3 to 1.8 s. The MJI therefore contains a programmable pulse duration table indexed by feedback from the printhead . The table of pulse durations allows the use of a lower cost power supply and aids in maintaining more accurate drop ejection.

The Pulse Duration table has 256 entries and is indexed by the current Vsense and Tsense settings on lines and respectively. The upper 4 bits of address come from Vsense and the lower 4 bits of address come from Tsense. Each entry is 8 bits and represents a fixed point value in the range of 0 4 ms. The process of generating the AEnable and BEnable lines is shown in .

The 256 byte table is written by the processor before printing the first page. The table may be updated in between pages if desired. Each 8 bit pulse duration entry in the table combines 

The MJI maintains a count of the number of dots of each color fired from the printhead . The dot count for each color is a 32 bit value individually cleared under processor control. At 32 bits length each dot count can hold a maximum coverage dot count of 17 8 inch 12 inch pages although in typical usage the dot count will be read and cleared after each page or half page.

The dot counts are used by the processor to update the QA chip see Section 7.5.4 in order to predict when the ink cartridge runs out of ink. The processor knows the volume of ink in the cartridge for each of the colors from the QA chip . Counting the number of drops eliminates the need for ink sensors and prevents the ink channels from running dry. An updated drop count is written to the QA chip after each page. A new page will not be printed unless there is enough ink left and allows the user to change the ink without getting a dud half printed page which must be reprinted.

The layout of the dot counter for Color1 is shown in . The remaining 3 dot counters Color1DotCount Color2DotCount and Color3DotCount are identical in structure.

The processor communicates with the MJI via a register set. The registers allow the processor to parameterize a print as well as receive feedback about print progress.

The following pseudocode illustrates the logic required to load a printhead for a single line. Note that loading commences only after the LineSync pulse arrives. This is to ensure the data for the line has been prepared by the LLFU and is valid for the first transfer to the printhead .

The line loader format unit LLFU loads the dots for a given print line into local buffer storage and formats them into the order required for the Memjet printhead . It is responsible for supplying the pre calculated nozzleEnable bits to the Memjet interface for the eventual printing of the page.

The printing uses a double buffering scheme for preparing and accessing the dot bit information. While one line is being loaded into the first buffer the pre loaded line in the second buffer is being read in Memjet dot order. Once the entire line has been transferred from the second buffer to the printhead via the Memjet interface the reading and writing processes swap buffers. The first buffer is now read and the second buffer is loaded up with the new line of data. This is repeated throughout the printing process as can be seen in the conceptual overview of .

The size of each buffer is 14 KBytes to cater for the maximum line length of 18 inches in 4 colors 18 1600 4 bits 115 200 bits 14 400 bytes . The size for both Buffer 0 and Buffer 1 is 28.128 KBytes. While this design allows for a maximum print length of 18 inches it is trivial to reduce the buffer size to target a specific application.

Since one buffer is being read from while the other is being written to two sets of address lines must be used. The 32 bits DataIn from the common data bus are loaded depending on the WriteEnables which are generated by State Machine in response to the DMA Acknowledges.

A multiplexor chooses between the two 4 bit outputs of Buffer 0 and Buffer 1 and sends the result to a 9 entry by 4 bit shift register . After a maximum of 9 read cycles the number depends on the number of segments written to per transfer and whenever an Advance pulse comes from the MJI the current 36 bit value from the shift register is gated into a 36 bit Transfer register where it can be used by the MJI .

Note that not all the 36 bits are necessarily valid. The number of valid bits of 36 depends on the number of colors in the printhead the number of segments and the breakup of segment groups if more than one segment group . For more information see Section 9.2.

A single line in an L inch C color printhead consists of 1600 L C color dots. At 1 bit per colored dot a single print line consists of 1600 LC bits. The LLFU is capable of addressing a maximum line size of 18 inches in 4 colors which equates to 108 800 bits 14 KBytes per line. These bits must be supplied to the MJI in the correct order for being sent on to the printhead . See Section 9.2.1 for more information concerning the Load Cycle dot loading order but in summary 2 LC bits are transferred to the printhead in SegmentGroups transfers with a maximum of 36 bits per transfer. Each transfer to a particular segment of the printhead must load all colors simultaneously.

Each of the two buffers is broken into 4 sub buffers 1 per color. The size of each sub buffer is 3600 bytes enough to hold 18 inches of single color dots at 1600 dpi. The memory is accessed 32 bits at a time so there are 900 addresses for each buffer requiring 10 bits of address .

All the even dots are placed before the odd dots in each color s buffer as shown in . If there is any unused space it is placed at the end of each color s buffer.

The amount of memory actually used is directly related to the printhead length. If the printhead is 18 inches there are 1800 bytes of even dots followed by 1800 bytes of odd dots with no unused space. If the printhead is 12 inches there are 1200 bytes of even dots followed by 1200 odd dots and 1200 bytes unused.

The number of sub buffers gainfully used is directly related to the number of colors in the printhead. This number is typically 3 or 4 although it is quite feasible for this system to be used in a 1 or 2 color system with some small memory wastage . In a desktop printing environment the number of colors would be 4 Color Cyan Color Magenta Color Yellow Color Black.

The address decoding circuitry is such that in a given cycle a single 32 bit access can be made to all 4 sub buffers either a read from all 4 or a write to one of the 4. Only one bit of the 32 bits read from each color buffer is selected for a total of 4 output bits. The process is shown in . 15 bits of address allow the reading of a particular bit by means of 10 bits of address being used to select 32 bits and 5 bits of address choose 1 bit from those 32. Since all color buffers share this logic a single 15 bit address gives a total of 4 bits out one per color. Each buffer has its own WriteEnable line to allow a single 32 bit value to be written to a particular color buffer in a given cycle. The 32 bits of DataIn are shared since only one buffer will actually clock the data in.

Note that regardless of the number of colors in the printhead 4 bits are produced in a given read cycle one bit from each color s buffer .

Address Generation for reading is straightforward. Each cycle we generate a bit address which is used to fetch 4 bits representing 1 bit per color for a particular segment. By adding 400 to the current bit address we advance to the next segment s equivalent dot. We add 400 not 800 since the odd and even dots are separated in the buffer. We do this firstly SegmentGroups sets of SegmentsPerXfer times to retrieve the data representing the even dots the dot data is transferred to the MJI 36 bits at a time and another SegmentGroups sets of SegmentsPerXfer times to load the odd dots. This entire process is repeated 400 times incrementing the start address each time. Thus all dot values are transferred in the order required by the printhead in 400 2 SegmentGroups SegmentsPerXfer cycles.

In addition we generate the TransferWriteEnable control signal. Since the LLFU starts before the MJI we must transfer the first value before the Advance pulse from the MJI . We must also generate the next value in readiness for the first Advance pulse. The solution is to transfer the first value to the Transfer register after SegmentsPerXfer cycles and then to stall SegmentsPerXfer cycles later waiting for the Advance pulse to start the next SegmentsPerXfer cycle group. Once the first Advance pulse arrives the LLFU is synchronized to the MJI . However the LineSync pulse to start the next line must arrive at the MJI at least 2SegmentsPerXfer cycles after the LLFU so that the initial Transfer value is valid and the next 32 bit value is ready to be loaded into the Transfer register .

The final transfer may not be fully utilized. This occurs when the number of segments per transfer does not divide evenly into the actual number of segments in the printhead. An example of this is the 8.5 inch printhead which has 17 segments. Transferring 9 segments each time means that only 8 of the last 9 segments will be valid. Nonetheless the timing requires the entire 9th segment value to be generated even though it is not used . The actual address is therefore a don t care state since the data is not used.

The write process is also straightforward. 4 DMA request lines are output to the DMA controller . As requests are satisfied by the return DMA Acknowledge lines the appropriate 8 bit destination address is selected the lower 5 bits of the 15 bit output address are don t care values and the acknowledge signal is passed to the correct buffer s WriteEnable control line the Current Write Buffer is CurrentReadBuffer . The 10 bit destination address is selected from the 4 current addresses one address per color. As DMA requests are satisfied the appropriate destination address is incremented and the corresponding TransfersRemaining counter is decremented. The DMA request line is only set when the number of transfers remaining for that color is non zero.

When controlling a print the processor programs and starts the LLFU in read mode to ensure that the first line of the page is transferred to the buffer. When the interrupts arrive from the DMA controller the processor can switch LLFU buffers and program the MJI . The processor then starts the LLFU in read write mode and starts the MJI . The processor should then wait a sufficient period of time to ensure that other connected printer controllers have also started their LLFUs and MJIs if there are no other connected printer controllers the processor must wait until the Stall bit of the LLFU is set a duration of 2 SegmentsPerXfer cycles . The processor can then program the LGSU to start the synchronized print. As interrupts arrive from the DMA controllers the processor can reprogram the DMA channels swap LLFU buffers and restart the LLFU in read write mode. Once the LLFU has effectively filled its pipeline it will stall until the next Advance pulse from the MJI . The MJI does not have to be touched during the print.

If for some reason the processor wants to make any changes to the MJI or LLFU registers during an inter line period it should ensure that the current line has finished printing loading by polling the status bits of the MJI and the Go bits of the LLFU .

We assume that the printer driver is closely coupled with the host graphics system so that the printer driver can provide device specific handling for different graphics and imaging operations in particular compositing operations and text operations.

We assume that the host provides support for color management so that device independent color can be converted to CePrint specific CMYK color in a standard way based on a user selected CePrint specific ICC International Color Consortium color profile. The color profile is normally selected implicitly by the user when the user specifies the output medium in the printer i.e. plain paper coated paper transparency etc. . The page description sent to the printer always contains device specific CMYK color.

We assume that the host graphics system renders images and graphics to a nominal resolution specified by the printer driver but that it allows the printer driver to take control of rendering text. In particular the graphics system provides sufficient information to the printer driver to allow it to render and position text at a higher resolution than the nominal device resolution.

We assume that the host graphics system requires random access to a contone page buffer at the nominal device resolution into which it composites graphics and imaging objects but that it allows the printer driver to take control of the actual compositing i.e. it expects the printer driver to manage the page buffer.

The printer s page description contains a 267 ppi contone layer and an 800 dpi black layer. The black layer is conceptually above the contone layer i.e. the black layer is composited over the contone layer by the printer. The printer driver therefore maintains a page buffer which correspondingly contains a medium resolution contone layer and a high resolution black layer.

The graphics systems renders and composites objects into the page buffer bottom up i.e. later objects obscure earlier objects. This works naturally when there is only a single layer but not when there are two layers which will be composited later. It is therefore necessary to detect when an object being placed on the contone layer obscures something on the black layer.

When obscuration is detected the obscured black pixels are composited with the contone layer and removed from the black layer. The obscuring object is then laid down on the contone layer possibly interacting with the black pixels in some way. If the compositing mode of the obscuring object is such that no interaction with the background is possible then the black pixels can simply be discarded without being composited with the contone layer. In practice of course there is little interaction between the contone layer and the black layer.

The printer driver specifies a nominal page resolution of 267 ppi to the graphics system. Where possible the printer driver relies on the graphics system to render image and graphics objects to the pixel level at 267 ppi with the exception of black text. The printer driver fields all text rendering requests detects and renders black text at 800 dpi but returns non black text rendering requests to the graphics system for rendering at 267 ppi.

Ideally the graphics system and the printer driver manipulate color in device independent RGB deferring conversion to device specific CMYK until the page is complete and ready to be sent to the printer. This reduces page buffer requirements and makes compositing more rational. Compositing in CMYK color space is not ideal.

Ultimately the graphics system asks the printer driver to composite each rendered object into the printer driver s page buffer. Each such object uses 24 bit contone RGB and has an explicit or implicitly opaque opacity channel.

The printer driver maintains the two layer page buffer in three parts. The first part is the medium resolution 267 ppi contone layer. This consists of a 24 bit RGB bitmap. The second part is a medium resolution black layer. This consists of an 8 bit opacity bitmap. The third part is a high resolution 800 dpi black layer. This consists of a 1 bit opacity bitmap. The medium resolution black layer is a subsampled version of the high resolution opacity layer. In practice assuming the low resolution is an integer factor n of the high resolution e.g. n 800 267 3 each low resolution opacity value is obtained by averaging the corresponding n n high resolution opacity values. This corresponds to box filtered subsampling. The subsampling of the black pixels effectively antialiases edges in the high resolution black layer thereby reducing ringing artifacts when the contone layer is subsequently JPEG compressed and decompressed.

When a black object of opacity is composited with the black layer the black layer is updated as follows 

The object opacity is simply ored with the black layer opacity Rule 1 and the corresponding part of the medium resolution black layer is re computed from the high resolution black layer Rule 2 .

When a contone object of color Cand opacity is composited with the contone layer the contone layer and the black layer are updated as follows 1 if 0 Rule 3 0 if 0 Rule 4 0 if 0 Rule 5 1 Rule 6 

Wherever the contone object obscures the black layer even if not fully opaquely the affected black layer pixels are pushed from the black layer to the contone layer i.e. composited with the contone layer Rule 3 and removed from the black layer Rule 4 and Rule 5 . The contone object is then composited with the contone layer Rule 6 .

If a contone object pixel is fully opaque i.e. x y 255 then there is no need to push the corresponding black pixels into the background contone layer Rule 3 since the background contone pixel will subsequently be completely obliterated by the foreground contone pixel Rule 6 .

Once page rendering is complete the printer driver converts the contone layer to CePrint specific CMYK with the help of color management functions provided by the graphics system.

The printer driver then compresses and packages the black layer and the contone layer into a CePrint page description as described in Section 6.2. This page description is delivered to the printer via the standard spooler.

Note that the black layer is manipulated as a set of 1 bit opacity values but is delivered to the printer as a set of 1 bit black values. Although these two interpretations are different they share the same representation and so no data conversion is required.

The forward discrete cosine transform DCT is the costliest part of JPEG compression. In current high quality software implementations the forward DCT of each 8 8 block requires 12 integer multiplications and 32 integer additions. On typical modern general purpose processors an integer multiplication requires 10 cycles and an integer addition requires 2 cycles. This equates to a total cost per block of 184 cycles.

The 26.4 MB contone layer consists of 432 538 JPEG blocks giving an overall forward DCT cost of about 80 Mcycles. At 150 MHz this equates to about 0.5 seconds which is 25 of the 2 second rendering time allowed per page.

A CE oriented processor may have DSP support in which case the presence of single cycle multiplication makes the JPEG compression time negligible.

The printer control protocol supports the transmission of the page to the printer as a series of bands. If the graphics system also supports banded output then this allows the printer driver to reduce its memory requirements by rendering the image one band at a time. Note however that rendering one band at a time can be more expensive than rendering the whole page at once since objects which span multiple bands have to be handled multiple times.

Although banded rendering can be used to reduce memory requirements in the printer driver buffers for two bands are still required. One buffer is required for the band being transmitted to the printer another buffer is required for the band being rendered. A single buffer may suffice if the connection between the host processor and printer is sufficiently fast. The band being transmitted to the printer may also be stored on disk if a disk drive is present in the system and only loaded into memory block by block during transmission.

In the Windows 9x NT CE printing system a printer is a graphics device and an application communicates with it via the graphics device interface GDI . The printer driver graphics DLL dynamic link library implements the device dependent aspects of the various graphics functions provided by GDI.

The spooler handles the delivery of pages to the printer and may reside on a different machine to the application requesting printing. It delivers pages to the printer via a port monitor which handles the physical connection to the printer. The optional language monitor is the part of the printer driver which imposes additional protocol on communication with the printer and in particular decodes status responses from the printer on behalf of the spooler.

The printer driver user interface DLL implements the user interface for editing printer specific properties and reporting printer specific events.

The printer driver language monitor and user interface DLL must implement the implement the relevant aspects of the printer control protocol described in Section 6. The remainder of this section describes the design of the printer driver graphics DLL. It should be read in conjunction with the appropriate Windows 9x NT CE DDK documentation.

GDI provides functions which allow an application to draw on a device surface i.e. typically an abstraction of a display screen or a printed page. For a raster device the device surface is conceptually a color bitmap. The application can draw on the surface in a device independent way i.e. independently of the resolution and color characteristics of the device.

The application has random access to the entire device surface. This means that if a memory limited printer device requires banded output then GDI must buffer the entire page s GDI commands and replay them windowed into each band in turn. Although this provides the application with great flexibility it can adversely affect performance.

GDI supports color management whereby device independent colors provided by the application are transparently translated into device dependent colors according to a standard ICC International Color Consortium color profile of the device. A printer driver can activate a different color profile depending for example on the user s selection of paper type on the driver managed printer property sheet.

GDI supports line and spline outline graphics paths images and text. Outline graphics including outline font glyphs can be stroked and filled with bit mapped brush patterns. Graphics and images can be geometrically transformed and composited with the contents of the device surface. While Windows 95 NT4 provides only boolean compositing operators Windows 98 NT5 provides proper alpha blending.

A raster printer can in theory utilize standard printer driver components under Windows 9x NT CE and this can make the job of developing a printer driver trivial. This relies on being able to model the device surface as a single bitmap. The problem with this is that text and images must be rendered at the same resolution. This either compromises text resolution or generates too much output data compromising performance.

As described earlier CePrint s approach is to render black text and images at different resolutions to optimize the reproduction of each. The printer driver is therefore implemented according to the generic design described in Section 11.

The driver therefore maintains a two layer three part page buffer as described in Section 11.2 and this means that the printer driver must take over managing the device surface which in turn means that it must mediate all GDI access to the device surface.

DrvEnablePDEV indicates to GDI via the flGraphicsCaps member of the returned DEVINFO structure the graphics rendering capabilities of the driver. This is discussed further below.

DrvEnableSurface creates a device surface consisting of two conceptual layers and three parts the 267 ppi contone layer 24 bit RGB color the 267 ppi black layer 8 bit opacity and the 800 dpi black layer 1 bit opacity. The virtual device surface which encapsulates these two layers has a nominal resolution of 267 ppi so this is the resolution at which GDI operations take place.

Although the aggregate page buffer requires about 34 MB of memory the size of the page buffer can be reduced arbitrarily by rendering the page one band at a time as described in Section 12.3.4.

DrvStartDoc sends the start document command to the printer and DrvEndDoc sends the 15 end document command.

DrvSendPage converts the contone layer from RGB to CMYK using GDI provided color management functions compresses both the contone and black layers and sends the compressed page as a single band to the printer in a page band command .

Managing the device surface and mediating GDI access to it means that the printer driver must support the following additional functions 

Copying images stroking paths and filling regions all occur on the contone layer while rendering solid black text occurs on the bi level black layer. Furthermore rendering non black text also occurs on the contone layer since it isn t supported on the black layer. Conversely stroking or filling with solid black can occur on the black layer if we so choose .

Although the printer driver is obliged to hook the aforementioned functions it can punt function calls which apply to the contone layer back to the corresponding GDI implementations of the functions since the contone layer is a standard format bitmap. For every DrvXxx function there is a corresponding EngXxx function provided by GDI.

As described in Section 11.2 when an object destined for the contone layer obscures pixels on the black layer the obscured black pixels must be transferred from the black layer to the contone layer before the contone object is composited with the contone layer. The key to this process working is that obscuration is detected and handled in the hooked call before it is punted back to GDI. This involves determining the pixel by pixel opacity of the contone object from its geometry and using this opacity to selectively transfer black pixels from the black layer to the contone layer as described in Section 11.2.

It is possible to determine the geometry of each contone object before it is rendered and thus determine efficiently which black pixels it obscures. In the case of DrvCopyBits and DrvPaint the geometry is determined by a clip object CLIPOBJ which can be enumerated as a set of rectangles.

In the case of DrvStrokePath things are more complicated. DrvStrokePath supports both straight line and B zier spline curve segments and single pixel wide lines and geometric wide lines. The first step is to avoid the complexity of B zier spline curve segments and geometric wide lines altogether by clearing the corresponding capability flags GCAPS BEZIERS and GCAPS GEOMETRICWIDE in the flGraphicsCaps member of the driver s DEVINFO structure. This causes GDI to reformulate such calls as sets of simpler calls to DrvPaint. In general GDI gives a driver the opportunity to accelerate high level capabilities but simulates any capabilities not provided by the driver.

What remains is simply to determine the geometry of a single pixel wide straight line. Such a line can be solid or cosmetic. In the latter case the line style is determined by a styling array in the specified line attributes LINEATTRS . The styling array specifies how the line alternates between being opaque and transparent along its length and so supports various dashed line effects etc.

When the brush is solid black straight lines can also usefully be rendered to the black layer though with the increased width implied by the 800 dpi resolution.

In the case of a DrvTextOut things are also more complicated. Firstly the opaque background if any is handled like any other fill on the contone layer see DrvPaint . If the foreground brush is not black or the mix mode is not effectively opaque or the font is not scalable or the font indicates outline stroking then the call is punted to EngTextOut to be applied to the contone layer. Before the call is punted however the driver determines the geometry of each glyph by obtaining its bitmap via FONTOBJ cGetGlyphs and makes the usual obscuration check against the black layer.

If punting a DrvTextOut call is not allowed the documentation is ambiguous then the driver should disallow complex text operations. This includes disallowing outline stroking by clearing the GCAPS VECTOR FONT capability flag and disallowing complex mix modes by clearing the GCAPS ARBMIXTXT capability flag .

If the foreground brush is black and opaque and the font is scalable and not stroked then the glyphs are rendered on the black layer. In this case the driver determines the geometry of each glyph by obtaining its outline again via FONTOBJ cGetGlyphs but as a PATHOBJ . The driver then renders each glyph from its outline at 800 dpi and writes it to the black layer. Although the outline geometry uses device coordinates i.e. at 267 ppi the coordinates are in fixed point format with plenty of fractional precision for higher resolution rendering.

The driver must set the GCAPS HIGHRESTEXT flag in the DEVINFO to request that glyph positions again in 267 ppi device coordinates be supplied by GDI in high precision fixed point format to allow accurate positioning at 800 dpi. The driver must also provide an implementation of the DrvGetGlyphMode function so that it can indicate to GDI that glyphs should be cached as outlines rather than bitmaps. Ideally the driver should cache rendered glyph bitmaps for efficiency memory allowing. Only glyphs below a certain point size should be cached.

As described in Section 6 the printer control protocol supports banded output by breaking the page description into a page header and a number of page bands. GDI supports banded output to a printer to cater for printer drivers and printers which have limited internal buffer memory.

GDI can handle banded output without application involvement. GDI simply records all the graphics operations performed by the application in a metafile and then replays the entire metafile to the printer driver for each band in the page. The printer driver must clip the graphics operations to the current band as usual. Banded output can be more efficient if the application takes note of the RC BANDING bit in the driver s raster capabilities returned by GetDeviceCaps when called with the RASTERCAPS index and only performs graphics operations relevant to each band.

If banded output is desired because memory is limited then the printer driver must enable banding by calling EngMarkBandingSurface in DrvEnableSurface. It must also support the following additional functions 

Like DrvSendPage DrvNextBand converts the contone layer from RGB to CMYK using GDI provided color management functions compresses both the contone and black layers and sends the compressed page band to the printer in a page band command .

