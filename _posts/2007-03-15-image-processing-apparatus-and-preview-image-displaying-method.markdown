---

title: Image processing apparatus and preview image displaying method
abstract: An image processing apparatus which previews a read image is disclosed. The image processing apparatus includes a preview image processing unit in which a user is allowed to set a processing condition for the read preview image by operating on the read preview image and a preview image processed by the processing condition is displayed together with the setting of the processing condition on a displaying section.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07643187&OS=07643187&RS=07643187
owner: Ricoh Company, Ltd.
number: 07643187
owner_city: Tokyo
owner_country: JP
publication_date: 20070315
---
The present invention generally relates to an image processing apparatus and a preview image displaying method in the image processing apparatus which allows operability close to human senses.

Recently in an image processing apparatus having a copying function a scanning function and so on a method is proposed in which a processing condition by a user is easily determined when an image is formed by using the above function.

For example in Patent document 1 an image processing apparatus is disclosed. In the image processing apparatus an image is pre scanned by selecting a reading condition in a scanner and a reading condition having a high recognition rate is automatically selected by applying an OCR optical character recognition process to the pre scanned image. With this the processing condition is easily determined by the user.

In addition in Patent Document 2 a scanner and a control method thereof are disclosed. In the scanner a preview image pre scanned by a user is rotated corresponding to necessity and the user scans the image by setting a suitable rotational angle.

However when a user copies images documents by setting processing conditions such as both side printing aggregation of pages and stapling sheets an output document may be different from that the user desires to obtain. Consequently the user tries a copy of the images by setting processing conditions and confirms the copied document. Then the user changes the processing conditions if necessary.

In some cases corresponding to the settings of the processing conditions documents are stapled and a thumbnail image of the staple documents is displayed. However the stapled image is displayed in a fixed small image from which the stapled status is hardly recognized.

Consequently the user cannot recognize whether the documents are stapled by the set processing conditions before the document is actually printed.

That is in the conventional method a visually recognition method of the status to be output and a changing method of settings are not provided. Therefore the user cannot easily determine the settings of the processing conditions visually and intuitively before an image is output.

In a preferred embodiment of the present invention there is provided an image processing apparatus and a preview image displaying method in the image processing apparatus which allows operability close to human senses.

Features and advantages of the present invention are set forth in the description that follows and in part will become apparent from the description and the accompanying drawings or may be learned by practice of the invention according to the teachings provided in the description. Features and advantages of the present invention will be realized and attained by an image processing apparatus and a preview image displaying method in the image processing apparatus particularly pointed out in the specification in such full clear concise and exact terms as to enable a person having ordinary skill in the art to practice the invention.

To achieve one or more of these and other advantages according to one aspect of the present invention there is provided an image processing apparatus which previews a read image. The image processing apparatus includes a preview image processing unit in which a user is allowed to set a processing condition for the read preview image by operating on the read preview image and a preview image processed by the processing condition is displayed together with the setting of the processing condition on a displaying section.

According to an embodiment of the present invention a user can set a processing condition for printing an image by directly operating a preview image. In addition the processing condition can be set by a click and a drag on the preview image. Therefore the user can visually and intuitively set the processing condition.

Moreover the user can designate a staple position by touching a desirable position on the preview image. In addition operability of the user can be increased by operation buttons and an operation on the preview image.

The best mode of carrying out the present invention is described with reference to the accompanying drawings.

The software group includes various functions to be realized by programs which are executed by a CPU central processing unit described below in a controller described below . The hardware resource includes a plotter a scanner and so on. The operating panel receives an instruction from a user and displays information for the user.

The software group includes an application layer and a platform layer . An OS operating system on the application layer and the platform layer executes software in the application layer and the platform layer in parallel.

The application layer includes for example copy application software for supplying a copy function to a user. The application layer can include other application software.

The platform layer manages the use of the hardware resource by interpreting a process request from the application layer . The platform layer includes an MCS memory control service and an IMH image memory handler . The MCS obtains a memory region and releases the obtained memory region utilizes an HDD described below controls compressing image data and expanding the compressed image data and controls other functions. The IMH manages a memory.

When the copy application software requests the MCS to obtain an image for previewing the image the MCS requests the IMH to obtain an image read by the scanner . When the scanner obtains an image requested by the IMH the scanner informs the IMH of obtaining the image. The IMH informs the MCS of obtaining the image. The MCS informs the copy application software of obtaining the image. The copy application software communicates with the operating panel so that the obtained image is previewed.

The preview image is displayed on the operating panel and a user performs a desirable operation on the preview image on the operating panel . When processing conditions are determined by a user operation the copy application software receives the processing conditions from the operating panel and makes the IMH execute a process on the image read by the scanner via the MCS . The IMH makes the plotter form an image on a predetermined recording medium on which image the process is to be applied.

As shown in the controller includes the CPU a system memory an NB north bridge an ASIC application specific integrated circuit a local memory a HDD hard disk drive and an external interface .

The operating panel is connected to the ASIC . The plotter and the scanner are connected to the ASIC via a PCI peripheral component interconnect bus .

The local memory and the HDD are connected to the ASIC and the CPU is connected to the ASIC via the NB which is a CPU chip set. The ASIC is connected to the NB via an AGP accelerated graphic port .

The CPU controls all the elements in the image processing apparatus . The CPU operates the MCS and the IMH on the OS and operates the copy application software in the application layer .

The NB connects the CPU to the system memory the ASIC and the external interface . The NB is connected to the external interface via a PCI bus .

The system memory stores image data for writing. The local memory is a buffer for storing image data for copying and for storing code data. The ASIC is an image processing IC having hardware elements. The HDD is storage for storing image data document data programs font data form data and so on.

The external interface connects the image processing apparatus to a network such as the Internet and a LAN.

The operating screen CPU controls all the elements in the operating panel by communicating with the controller . In addition the operating screen CPU controls a display on the LCD panel by reading a program stored in the program memory and executing the program.

The program memory stores all the programs for controlling all the elements in the operating panel . The touch panel controller controls the LCD panel corresponding to a user operation on a screen displayed on the LCD panel via the LCD panel controller . The display data memory stores image data which are used for displaying a preview image. The LCD panel controller controls a display on the LCD panel corresponding to the user operation. The LCD panel provides a touch panel function.

A preview image described below is displayed on the liquid crystal panel . The function selecting button includes a copy button a document button a facsimile button a printer button and a scanner button and one of the buttons is selected by a user. The operating button includes a program button a reset button and a preheat button.

From the ten key button the user inputs a figure. The button includes a trial copy button and clear stop buttons for canceling the operation. The user starts operations by pushing the start button . The power of the image processing apparatus is turned on by pushing the power switch

Next referring to the IMH and the operating panel for displaying a preview image are described in detail.

The compression expansion processing section compresses image data stored in the expansion memory and image data read by the scanner when the image data are stored in the HDD . In addition the compression expansion processing section expands the image data stored in the HDD when the image data are processed by the plotter or are stored in the expansion memory

The image synthesis processing section synthesizes image data read by the scanner by storing the image data in the expansion memory based on an initial processing condition and synthesizes image data stored in the expansion memory based on a set processing condition. The synthesized image data are output by the plotter as print data.

The expansion memory is a part of the local memory which can be used by the IMH and stores processed image data.

The PCI controller includes a PCI memory and an interrupt processing section and controls access to the scanner and the plotter vi the PCI bus refer to . The PCI memory temporarily stores image data read by the scanner and image data for an image to be formed by the plotter .

The interrupt processing section generates an interrupt signal corresponding to timing when the image synthesis processing section forms an image. Since the scanner reads image data line by line when the interruption signal is generated every one line reading a preview image is formed by synthesizing line images and one line image is sequentially displayed. In addition when the preview image is displayed by rotating the image the number of image transfer clocks generated by the scanner at each one line reading is counted and the interrupt signal is generated when the counted number equals clocks for the lines of one page.

As shown in the operating panel includes a display synthesis processing section a symbol mark region and an LCD controller .

The display synthesis processing section is realized when the operating screen CPU executes a program stored in the program memory and synthesizes a symbol mark stored in the symbol mark region with image data from expansion memory to form a preview image.

The symbol mark region is a part of the display data memory and stores picture images such as a staple mark and a punch mark beforehand. The LCD controller displays a synthesized preview image and also displays a screen based on an instruction by the user on the LCD panel .

The compression expansion processing section compresses the received image data and stores the compressed image data in the HDD . The image synthesis processing section synthesizes the received image data and stores the synthesized image data in the expansion memory

In the operating panel the display synthesis processing section forms a preview image display data by synthesizing the image data received from the expansion memory in the IMH with the picture image stored in the symbol mark region . The LCD controller displays the preview image display data on the LCD panel .

In the operating panel the display synthesis processing section forms a preview image display data by synthesizing the image data received from the expansion memory in the IMH with the picture image stored in the symbol mark region . The LCD controller displays the preview image display data on the LCD panel .

In the operating panel the display synthesis processing section forms a preview image display data by synthesizing the image data received from the expansion memory in the IMH with the picture image stored in the symbol mark region . The LCD controller displays the preview image display data on the LCD panel .

In this case a process is not needed in which the compression expansion processing section expands image data by reading the image data from the HDD . Therefore the memory resources can be effectively used and the power consumption can be reduced.

In the operating panel the display synthesis processing section forms a preview image display data by synthesizing the image data received from the expansion memory in the IMH with a picture image stored in the symbol mark region . The LCD controller displays the preview image display data on the LCD panel .

In the embodiment of the present invention in order to easily determine a processing condition for printing an image by directly operating a preview image displayed on the operating panel the following method is established which method designates a processing condition based on user psychology.

 1 . A staple button is pushed a binding position of documents is clicked and a staple position is designated.

 2 . A page is turned a finishing state of a document is confirmed and a staple position of the document is designated.

 3 . When the head and tail of a stapled document are wrong a staple position of the document is designated by changing the head and tail.

 2 . A staple position and the head and tail of a document are set in an image processing apparatus corresponding to the page turning direction.

 3 . When the head and tail of a stapled document are wrong the head and tail of the rear surface is changed by changing the head and tail of the front surface.

 3 . When some documents are aggregated in one sheet the staple position may be at the side of the sheet having a small page number.

 5 . A short stroke is suitable when a page is turned and a page turning direction is suitable which easily turns a page.

There is an exception to the user psychology therefore in the embodiment of the present invention candidates for providing the user with easy operations are determined and the user can select one of the candidates.

Referring to a relationship between a staple position and a page turning direction is described. In an example in which four pages are aggregated in one sheet is described. The number written in each sheet and is the image order scanned by the scanner for example the number corresponds to the page number. The image order is referred to as the read image . . . n. In addition a staple position sp is shown by a bold line and a punch position ph is shown by o and a page turning direction d is shown by an arrow.

In in vertical direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the staple positions sp are designated at the left sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the staple positions sp are predicted at the right sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple positions sp are at the right sides of the read images and in the sheet and at the left sides of the read images and in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the staple positions sp are designated at the right sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the staple positions sp are predicted at the left sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple positions sp are at the left sides of the read images and in the sheet and at the right sides of the read images and in the sheet .

In in horizontal direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the staple positions sp are designated at the upper sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the staple positions sp are predicted at the lower sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple positions sp are at the lower sides of the read images and in the sheet and at the upper sides of the read images and in the sheet .

In in horizontal direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the staple positions sp are designated at the upper sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the staple positions sp are predicted at the lower sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple positions sp are at the lower sides of the read images and in the sheet and at the upper sides of the read images and in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the staple position sp is designated at the upper left side of the read image along the side the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower right side of the read image .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the upper right side of the read image in the sheet and at the upper left side of the read image in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the staple position sp is designated at the upper right side of the read image along the side the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower left side of the read image .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the upper left side of the read image in the sheet and at the upper right side of the read image in the sheet .

In in horizontal direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the staple position sp is designated at the upper left side of the read image along the upper side the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower right side of the read image along the lower side.

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the lower left side of the read image in the sheet and at the upper left side of the read image in the sheet .

In in horizontal direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the staple position sp is designated at the upper right side of the read image along the upper side the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower left side of the read image along the lower side.

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the lower right side of the read image in the sheet and at the upper right side of the read image in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the staple position sp is designated at the upper left corner of the read image the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower right corner of the read image .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the upper right corner of the read image in the sheet and at the upper left corner of the read image in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the staple position sp is designated at the upper right corner of the read image the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower left corner of the read image .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the upper left corner of the read image in the sheet and at the upper right corner of the read image in the sheet .

In in horizontal direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the staple position sp is designated at the upper left corner of the read image the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower right corner of the read image .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the upper right corner of the read image in the sheet and at the upper left corner of the read image in the sheet .

In in horizontal direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the staple position sp is designated at the upper right corner of the read image the page turning direction d is predicted from the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the staple position sp is predicted at the lower left corner of the read image .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The staple position sp is at the upper left corner of the read image in the sheet and at the upper right corner of the read image in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the punch position ph is designated at the left sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the punch position ph is predicted at the right sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The punch position ph is at the right sides of the read images and in the sheet and at the left sides of the read images and in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the punch position ph is designated at the upper sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the punch position sp is predicted at the lower sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The punch position ph is at the lower sides of the read images and in the sheet and at the upper sides of the read images and in the sheet .

In in horizontal direction sheets and the read images are aggregated in the order of upper left upper right lower left and lower right positions. In when the punch position ph is designated at the upper sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the punch position ph is predicted at the lower sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The punch position ph is at the lower sides of the read images and in the sheet and at the upper sides of the read images and in the sheet .

In in vertical direction sheets and the read images are aggregated in the order of upper right lower right upper left and lower left positions. In when the punch position ph is designated at the right sides of the read images and the page turning direction d is predicted from the read image to the read image the read image to the read image . On the other hand when the page turning direction d is designated from the read image to the read image the read image to the read image the punch position ph is predicted at the left sides of the read images and .

In when the sheet is turned the sheets and are a two page spread. The sheet is a rear surface of the sheet . The punch position ph is at the left sides of the read images and in the sheet and at the right sides of the read images and in the sheet .

The image processing apparatus forms the table shown in based on methods similar to those shown in and stores the table in the HDD .

In the binding method of the document items of 2 position stapling 1 position stapling and punching are shown and each item has a position and a rear surface direction for a front surface. In the page turning direction items of left direction turning right direction turning and upper direction turning are shown and each item has horizontal writing and vertical writing.

Further in the position a left side a right side and an upper side are shown. In the rear surface direction for front surface the same direction and the head and tail reversed direction are shown.

In pattern a user scans an image by setting a processing condition displays a preview image and prints the image and simultaneously stores the image.

In pattern a user scans an image by setting a processing condition displays a preview image processes the image and prints the image and simultaneously stores the image.

Next processes to execute all the operations which can perform the above three patterns are described.

Referring to the processes are described. First the image processing apparatus determines whether a processing condition is designated by a user instruction S . When the image processing apparatus determines that the processing condition is designated by the user YES in S the user designates the processing condition S . When the image processing apparatus does not determine that the processing condition is designated by the user NO in S the process goes to S.

Then the image processing apparatus reads a document by the scanner S and forms an image by synthesizing line images S . In the image synthesis images in each line or in one page are sequentially synthesized to form a preview image by the designated processing condition. The synthesis of one line image and the one page image are automatically switched based on the designated processing condition described below .

Next a preview image is displayed on the operating panel S . Then it is determined whether the user instructs to print the preview image S . When it is determined that the user instructs to print the preview image YES in S the image processing apparatus prints the preview image by the plotter S .

When the user does not instruct to print the preview image NO in S it is determined whether the user instructs to apply a process to the preview image S . When it is determined that the user instructs to apply a process to the preview image YES in S the image processing apparatus makes the user designate a processing condition and applies the process to the preview image based on the processing condition S and the process returns to S.

When a preview image is displayed after reading a document a first document image IMG is displayed on a sheet image SHT in the preview image displaying region and a message for example SELECT MODE for instructing a user to operate is displayed on the message region . In order to select a mode the user pushes for example the staple button and designates the staple position.

In addition to the automatic page turning button a scroll bar can be disposed at the right side of the preview image displaying region . With this the user can view pages by using the scroll bar.

In the following main buttons for executing the embodiment of the present invention are shown and other buttons may be omitted.

When the user pushes the rotation button shown in on the screen G as shown in a rotation method selecting button is displayed. The rotation method selecting button includes a head and tail reversing button a right direction rotation button a left direction rotation button an angle designation region and an OK button for determining the rotation angle.

The user can change the head and tail of the sheet image SHT by operating the head and tail reversing button . In addition the user can rotate the sheet image SHT clockwise on a 90 basis by operating the right direction rotation button and can rotate the sheet image SHT counterclockwise on a 90 basis by operating the left direction rotation button . Further the user can designate the rotation angle by selecting one of 90 180 270 360 0 by operating an up and down button in the angle designation region . When the rotation angle is determined the user pushes the OK button . Then the user executes a next process.

When the user pushes the automatic page turning button shown in on the screen G as shown in a page turning speed selecting button is displayed. The page turning speed selecting button includes a fast button a normal button a slow button a page turning speed designating region and a start button for starting the page turning with the designated speed.

The user can select fast speed by operating the fast button can select normal speed by operating the normal button and can select slow speed by operating the slow button

In addition the user can change the speed by operating an up and down button in the page turning speed designating region . When the page turning speed is determined the user pushes the start button . With this preview images are sequentially displayed at the selected speed on the preview image displaying region in the order of the pages of the document read by the scanner .

In the message region of the screen G for example a message SELECT STAPLE MARK AT DESIRABLE POSITION is displayed and the user selects for example the staple mark STPL on the sheet image SHT. The selected staple mark STPL is changed to a staple mark STPL by being exaggerated and the staple mark STPL is displayed on a screen G.

In the message region of the screen G for example a message PUSH ENTER is displayed and the user push an enter button on the screen G. When the user pushes the enter button on the screen G a screen G is displayed.

On the screen G only the staple mark STPL is displayed on the sheet image SHT and SELECT MODE is displayed on the message region . The user can continuously select another mode for example the both side printing or the document aggregation. For example when the user selects the document aggregation button processes of the document aggregation shown in are started.

The aggregation candidate includes a button which aggregates two documents into one sheet a button which aggregates four documents into one sheet and a button which aggregates nine documents into one sheet.

For example when a user selects the button a screen G is displayed. In the message region of the screen G for example a message PUSH ENTER BUTTON WHEN ORDER IS SUITABLE PUSH PREFERABLE ARRANGEMENT BUTTON WHEN ORDER IS TO BE CHANGED is displayed and a document arrangement candidate is displayed instead of displaying the aggregation candidate .

The document arrangement candidate includes buttons and . In the button four documents are arranged in the order of upper left upper right lower left and lower right positions. In the button four documents are arranged in the order of upper left lower left upper right and lower right positions. In the button four documents are arranged in the order of upper right upper left lower right and lower left positions. In the button four documents are arranged in the order of upper right lower right upper left and lower left positions.

When the screen G is displayed the four documents are displayed in the arrangement order of the button . In the screen G the staple mark STPL selected by the user the first document image IMG a second document image IMG a third document image IMG and a fourth document image IMG are displayed on the sheet image SHT.

When the user satisfies the arrangement order shown by the button the user pushes the enter button . However when the user does not satisfy the arrangement order shown by the button the user can change the arrangement order by selecting one of the buttons through

When the user pushes the enter button a screen G is displayed. In the message region of the screen G the message SELECT MODE is displayed. When the user pushes the both side printing button a screen shown in is displayed.

The both side preview selection includes a development view button for previewing a development view a reverse button for previewing a reversed preview image and a head and tail changing button for changing the head and tail.

On the other hand as shown in when the user drags on the screen in a direction a from the lower left position to the upper right position on the sheet image SHT as shown in a warning screen is shown in the screen G.

In in the warning screen a message for example WARNING DOCUMENT CANNOT BE TURNED IN DESIGNATED DIRECTION is displayed. The user pushes an enter button and designates again a page turning direction.

Referring to screens in which the sheet image SHT is turned are described. In a screen G shown in the sheet image SHT is started to be turned. In a screen G shown in the sheet image SHT first page is turned and the rear surface of the sheet image SHT second page and a sheet image SHT third page are shown. In a screen G shown in the sheet image SHT has been almost turned and the rear surface of the sheet image SHT second page is shown.

In in a screen G the sheet images SHT and SHT are bound by the staple mark STPL. In the message region in the screen G a message for example CLICK DESIRABLE PAGE CLICKED PAGE IS DISPLAYED PUSH ENTER .

For example when the user clicks the screen G at a point in as shown in in a screen G only the rear surface of sheet image SHT second page is enlarged and displayed.

When the user pushes the head and tail changing button in the screen G shown in as shown in a preview image in which the head and tail of the rear surface of the sheet image SHT is changed is shown.

Next referring to processes for designating the page turning direction are described. A case is described. In this case first the user selects the both side printing and the document aggregation and after this the staple position is selected.

When the user drags in a direction a from lower to upper direction a screen G is displayed. In the screen G the staple marks STPL and STPL are displayed along the upper side of the sheet image SHT. In addition in the message region of the screen G a message for example PUSH ENTER BUTTON is displayed.

When the user pushes an enter button the sheet image SHT is determined as the preview image for printing.

Next processes for designating the page turning direction on the sheet image SHT are described. is a diagram showing processes for designating the page turning direction.

In the page turning direction is designated to be a direction facing the staple marks STPL and STPL from lower to upper positions . That is when the user drags on the screen G in a direction a as shown in the sheet image SHT is started to be turned. is a diagram showing screens in which the sheet image SHT is turned.

As shown in when the user drags on the screen G in a direction a from left to right direction a warning screen is shown in the screen G of . In FIG. in the warning screen a message for example WARNING DOCUMENT CANNOT BE TURNED IN DESIGNATED DIRECTION is displayed. The user pushes an enter button and designates again a page turning direction.

Referring to turning the sheet image SHT is described. In the turning progress is displayed as frames of moving images. In in the screen G the sheet image SHT is started to be turned. In in a screen G the rear surface of the sheet image SHT second page and the front surface of the sheet image SHT third page are started to be displayed. In in a screen G the rear surface of the sheet image SHT second page has been almost displayed.

Then as shown in when the sheet image SHT has been completely turned the rear surface of the sheet image SHT second page is displayed. is a diagram showing a screen G in which the rear surface of the sheet image SHT second page is displayed.

When the user pushes the development view button on the screen G a screen flow processes shown in is executed. is a diagram showing processes to display a development view.

In in a screen G the sheet images SHT and SHT are bound by the staple marks STPL and STPL. In the message region in the screen G a message for example CLICK DESIRABLE PAGE THEN IMAGE OF CLICKED PAGE IS DISPLAYED PUSH ENTER BUTTON .

For example when the user clicks the screen G at a point in as shown in in a screen G only the rear surface of sheet image SHT second page is enlarged and displayed.

When the user pushes the head and tail changing button on the screen G a preview image shown in or in which the head and tail of the rear surface of the sheet image SHT are reversed is shown in a screen Gor G

In on the screen G the head and tail of each image in the SHT are reversed. That is the head and tail of the images in the rear surface of the sheet image SHT are reversed. In on the screen G the positions of the staple marks STPL and STPL are only reversed.

Next processes in which a processing condition is determined before reading a document are described. is a diagram showing processes screen flow in which a processing condition is determined before reading a document. In on a screen G a processing condition is determined before reading a document.

In the message region on the screen G a message for example PUSH ENTER WHEN ORDER IS SUITABLE PUSH PREFERABLE ARRANGEMENT BUTTON WHEN ORDER IS TO BE CHANGED is displayed.

When the user desires to change the arrangement order of documents the user pushes one of the buttons in the document arrangement candidate . On the screen G the order is shown by numbers 1 2 3 and 4 on the sheet image SFT. When the user pushes an enter button the image processing apparatus reads a first document. As shown in a screen G a first document image IMG is displayed at the position of 1 on the sheet image SHT.

When the image processing apparatus reads a second document as shown in a screen G a second document image IMG is displayed at the position of 2 on the sheet image SHT. When the image processing apparatus reads a third document as shown in a screen G a third document image IMG is displayed at the position of 3 on the sheet image SHT. In addition when the image processing apparatus reads a fourth document as shown in a screen G a fourth document image IMG is displayed at the position of 4 on the sheet image SHT.

Next a staple position adjusting method is described. When a document image exists at a staple position the staple position must be adjusted. is a diagram showing processes screen flow for adjusting a staple position.

On a screen G of when the staple marks STPL and STPL are designated to overlap the document image IMG and or the document image IMG a warning screen having a message for example WARNING IMAGE EXISTS AT DESIGNATED STAPLE POSITION is displayed. The warning screen includes a staple position adjusting button a document image position adjusting button a document image reducing button and a non adjustment button in which the current staple positions are used.

When the user finely adjusts the positions of the staple mark STPL and or the staple mark STPL the user selects one of the buttons and . When the user does not adjust the positions of the staple mark STPL and or the staple mark STPL the user pushes the button

The staple position adjustment includes a vertical adjustment button for vertically adjusting the staple position and a horizontal adjustment button for horizontally adjusting the staple position.

The user adjusts the positions of the staple marks STPL and STPL by using the buttons and . When the user determines the positions of the staple marks STPL and STPL the user pushes an enter button

The image processing apparatus again determines whether the staple position overlaps the document image IMG and or IMG. When the staple position overlaps the document image IMG and or IMG the image processing apparatus again displays the warning screen .

In the preview image displaying region the staple positions before adjustment are shown by broken line marks C and C on the sheet image SHT. Therefore the user can use the buttons and by viewing the screen G.

The document image position adjustment includes a vertical adjustment button for vertically adjusting the document image position and a horizontal adjustment button for horizontally adjusting the document image position.

The user adjusts the positions of the document images IMG through IMG by using the buttons and . When the user determines the positions of the document images IMG through IMG the user pushes the enter button

The image processing apparatus again determines whether the staple position overlaps the document image IMG and or IMG. When the staple position overlaps the document image IMG and or IMG the image processing apparatus again displays the warning screen .

In the preview image displaying region the document image positions before adjustment are shown by broken line marks D through D. Therefore the user can use the buttons and by viewing the screen G.

The user reduces the sizes of the document images IMG through IMG by using the buttons . When the user determines the scale factor of the document images IMG through IMG the user pushes the enter button

The image processing apparatus again determines whether the staple position overlaps the document image IMG and or IMG. When the staple position overlaps the document image IMG and or IMG the image processing apparatus again displays the warning screen .

In the preview image displaying region the sizes of the document images IMG through IMG before reduction are shown by broken line marks M through M. Therefore the user can use the button by viewing the screen G.

As described above in order that a staple position does not overlap a document image the user can adjust the staple position the document image position or can reduce the size of the document image by viewing the preview image displaying screen . In addition the user can combine the above adjustments reduction . That is a finishing process can be applied to the preview image. The finishing process includes a stapling process and a punching process.

In the staple position adjusting processes shown in the adjustment reduction can be applied to total pages of a document only a page designated by a user or a two page spread. That is the user may select the adjustment reduction .

First a user designates a binding position of documents S . The image processing apparatus searches for a position where the binding position overlaps an image S . In this case a binding margin can be considered.

The image processing apparatus determines whether the binding position overlaps the image based on the searched result S . When the binding position does not overlap the image NO in S the process ends.

When the binding position overlaps the image YES in S the image processing apparatus displays a warning S . The image processing apparatus determines whether a user adjusts the binding position S . When the user adjusts the binding position YES in S a button for adjusting the binding position is displayed S . Then the process returns to S and the processes on and after S are repeated.

The above processes for adjusting the overlap position where the binding position of the document overlaps the image can be executed in S shown in or in S shown in before a preview image is displayed when the staple position and or the punch position is designated. That is in S the processing condition is designated before the scanner reads the document and in S the processing condition is designated after the scanner reads the document.

Next timings of processes based on a processing condition in the image processing apparatus are described. Referring to the timings of the processes are described. The processes in S S and S shown in are realized in parallel based on a processing condition designated by the user. Each line of a document image read by the scanner is stored in the PCI memory and after this one band of the document image having predetermined number of lines is processed. The document images read by the scanner are shown by the IMG the IMG the IMG the IMG . . . .

In the interrupt processing section generates an interrupt signal each time when the scanner reads an image of one band having the predetermined number of lines. The HDD stores the one band image based on an image transfer clock and the image synthesis processing section and the expansion memory obtain the one band image based on the interrupt signal.

Each time when the one band image is stored in the expansion memory the display synthesis processing section synthesizes the one band images to form the document images IMG and IMG. The LCD controller displays the document image IMG in the order of band images L L L L and L. The band images L through L are almost simultaneously displayed. Since the display synthesis processing section stores the document image IMG the document image IMG can be simultaneously displayed when the page is turned. As shown in the document image is displayed in the order of band images L L L L and L.

When a user selects one of the buttons in the rotation method selecting button on the screen G and pushes the OK button in a preview image is rotated.

In signals of the document images IMG IMG and IMG read by the scanner are instantly stored in the PCI memory . In addition the HDD sequentially stores the document images IMG IMG and IMG based on an image transfer clock generated by the scanner .

When the rotation method is designated the interrupt processing section generates an interrupt signal each time when one of the document images IMG IMG and IMG is stored in the HDD . The image synthesis processing section instantly stores the document images IMG IMG and IMG by rotating the images in the expansion memory based on the interrupt signal.

Each time when the one band image is stored in the expansion memory the display synthesis processing section synthesizes the one band images to form the document images IMG IMG and IMG. The LCD controller displays the document images IMG IMG and IMG in this order on the LCD panel . The document images IMG IMG and IMG are almost simultaneously displayed. As shown in the document image IMG is vertically read and horizontally displayed.

The interrupt processing section generates an interrupt signal each time when the scanner reads an image of one band having the predetermined number of lines. The HDD stores the one band image based on an image transfer clock and the image synthesis processing section and the expansion memory obtain the one band image based on the interrupt signal.

Each time when the one band image is stored in the expansion memory the display synthesis processing section synthesizes the one band images to form the document images IMG and IMG. The LCD controller displays the document image IMG in the order of band images L L L L and L. The band images L through L are almost simultaneously displayed. The processes described above are almost the same as those shown in the normal operation in .

When the user designates to turn the document image IGM to a next document image IMG by a drag on a screen the LCD controller displays the document image IMG in the order of band images L L L L and L. When the document image IMG is displayed the display synthesis processing section synthesizes the band images to form a next document image the document image IMG .

When the user designates to turn the document image IGM the document image IMG is displayed. When the user designates to turn the document image IGM to a previous document image the document image IMG is displayed. With this the document image of a previous page or a next page can be easily displayed.

The interrupt processing section generates an interrupt signal each time when the scanner reads an image of one band having the predetermined number of lines. The HDD stores the one band image based on an image transfer clock and the image synthesis processing section and the expansion memory obtain the one band image based on the interrupt signal.

Each time when the one band images of a document image are stored in the expansion memory the display synthesis processing section synthesizes the one band images to form the document image IMG after synthesizing the one band images of the document image IMG the one band images of the document image IMG are synthesized. The above processes are continued to synthesize the one band images to form the document image IMG. The LCD controller displays the document image IMG in the order of band images L L L L and L after displaying the document image IMG the document image IMG is displayed. The above processes are continued to display the document image IMG. The band images L through L are almost simultaneously displayed.

Since the document images IMG through IMG are displayed after displaying the document image IMG and after synthesizing the one band images thereof the document image IMG is displayed longer than the document images IMG through IMG. Therefore the user can watch the document image IMG for a long time.

Next referring to cases are described. In the cases a preview image is displayed by aggregating two or more document images into one page. For example when four document images are aggregated into one page the sizes of the four document images are reduced. When an enlarged document image is reduced the image quality is degraded therefore it is preferable that the original document image be reduced. Therefore as shown in the data flow of the original document image stored in the HDD is used.

First referring to a first displaying method is described in which four document images are aggregated into one page. is a first timing chart in which a preview image is displayed by aggregating four document images into one page. In signals of the document images IMG IMG IMG and IMG read by the scanner are instantly stored in the PCI memory . In addition the signals of the document images IMG IMG IMG and IMG are sequentially stored in the HDD based on an image transfer clock generated at each time when an image of one band having the predetermined number of lines is read.

The interrupt processing section calculates interrupt timing from a reducing factor designated by a processing condition. When the size of a document image is to be reduced since the original document image is read from the HDD by thinning not reading all data thereof the reading speed is higher than the writing speed to the HDD . Therefore the interrupt timing is determined by a predetermined algorithm with the consideration of the writing speed. For example in a four document image aggregation each document image IMG IMG IMG or IMG is reduced to size and the reading speed is four times higher than the writing speed due to the thinning. Therefore the interrupt timing is the time when 75 of the document image IMG is written in the HDD .

The interrupt processing section generates an interrupt signal at the calculated interrupt timing. The image synthesis processing section sequentially reads the document images IMG through IMG based on the reading speed of the reducing factor while instantly storing the document images IMG through IMG in the expansion memory

Each time when the one band image of the reduced document image is stored in the expansion memory the display synthesis processing section synthesizes the reduced document images IMG through IMG to form display images. The LCD controller sequentially displays the reduced document images IMG through IMG on the LCD panel in one sheet region. The reduced document images IMG through IMG are instantly displayed. In the LCD controller of the displaying timings of the reduced document images IMG through IMG on one sheet in the order of upper left upper right lower left and lower right positions are shown.

Referring to screen flows by the displaying timings are described. is a diagram showing a first screen flow in which a preview image having the four reduced document images is displayed. is a diagram showing a second screen flow in which a preview image having the four reduced document images is displayed. is a diagram showing a third screen flow in which a preview image having the four reduced document images is displayed. is a diagram showing a fourth screen flow in which a preview image having the four reduced document images is displayed. The screen flow for displaying a preview image of four document image aggregation is completed by connecting the screen flows shown in .

In first the reduced document image IMG is displayed in the order of the one band images in the upper left position . Next in the reduced document image IMG is displayed in the order of the one band images in the upper right position and the reduced document image IMG is started to display in the order of the one band images in the lower left position . Then in the reduced document image IMG is displayed in the order of the one band images in the lower left position and the reduced document image IMG is started to display in the order of the one band images in the lower right . Finally in the reduced document image IMG is displayed in the lower right position . With this a preview image of the four document image aggregation is completed.

Next referring to a second displaying method is described in which four document images are aggregated into one page. In the second displaying method the band images of two reduced document images are simultaneously displayed. is a second timing chart in which a preview image is displayed by aggregating four document images into one page. In signals of the document images IMG IMG IMG and IMG read by the scanner are instantly stored in the PCI memory . In addition the signals of the document images IMG IMG IMG and IMG are sequentially stored in the HDD based on an image transfer clock generated at each time when an image of one band having the predetermined number of lines is read.

The interrupt processing section calculates interrupt timing from a reducing factor designated by a processing condition. The calculation method of the interrupt timing is the same as that in the first displaying method described above.

The interrupt processing section generates an interrupt signal based on the calculated interrupt timing. The image synthesis processing section sequentially reads the document images IMG through IMG based on the reading speed of the reducing factor of the four document image aggregation while instantly storing the document images IMG through IMG in the expansion memory

Each time when the one band images of the reduced document image are stored in the expansion memory the display synthesis processing section sequentially synthesizes the reduced document images IMG through IMG to form display images. When the reduced document image IMG is formed the LCD controller simultaneously displays the reduced document images IMG and IMG on a predetermined region and when the reduced document image IMG is formed the LCD controller simultaneously displays the reduced document images IMG and IMG on another predetermined region.

In the LCD controller of the displaying timing to simultaneously display the reduced document images IMG and IMG on upper half position of one sheet and the displaying timing to simultaneously display the reduced document images IMG and IMG on lower half position of the one sheet are shown.

Referring to a screen flow by the displaying timings is described. is a diagram showing a screen flow in which a preview image having the four reduced document images is displayed based on the second timing chart. In the reduced document images IMG and IMG are simultaneously displayed in the order of the one band images in the upper half positions on one sheet. Then the reduced document images IMG and IMG are simultaneously displayed in the order of the one band images in the lower half positions on the one sheet.

Next referring to a third displaying method is described in which two document images are aggregated into one page. In the third displaying method the band images of two reduced document images are simultaneously displayed. is a third timing chart in which a preview image is displayed by aggregating two document images into one page. In signals of the document images IMG IMG IMG and IMG read by the scanner are instantly stored in the PCI memory . In addition the signals of the document images IMG IMG IMG and IMG are sequentially stored in the HDD based on an image transfer clock generated at each time when an image of one band having the predetermined number of lines is read.

The interrupt processing section calculates interrupt timing from a reducing factor designated by a processing condition. The calculation method of the interrupt timing is the same as that in the first displaying method described above. However in this case since the reducing factor is 50 the reading speed is twice that of the writing speed. Therefore the interrupt timing is the time when 50 of the document image IMG is written in the HDD .

Each time when the one band images of the reduced document image are stored in the expansion memory the display synthesis processing section sequentially synthesizes the reduced document images IMG through IMG to form display images. When the reduced document image IMG is formed the LCD controller simultaneously displays the reduced document images IMG and IMG on one sheet.

In since the display synthesis processing section stores the synthesized reduced document images IMG and IMG when the page is turned a next preview image formed of the reduced document images IMG and IMG can be quickly displayed.

Referring to a case is described. In this case a preview image of a document image is displayed by attaching a staple mark to the preview image. When the user pushes the staple button on the screen G displaying a preview image shown in the image processing apparatus synthesizes a staple mark on a band image where the staple mark is to be displayed and displays a preview image having the staple mark.

In one staple mark is attached to the document image IMG. However when plural staple marks are attached to the document image IMG the same processes as those shown in can be used. is a timing chart showing processes to attach a staple mark on a preview image of a document image. In signals of the document image IMG read by the scanner are instantly stored in the PCI memory

The interrupt processing section generates an interrupt signal each time when the scanner reads an image of one band having the predetermined number of lines. The HDD stores the one band image based on an image transfer clock and the image synthesis processing section and the expansion memory obtain the one band image based on the interrupt signal.

Each time when the one band images are stored in the expansion memory the display synthesis processing section synthesizes the one band images to form the document image IMG. The LCD controller displays the document image IMG in the order of band images L L L L and L. The band images L through L are almost simultaneously displayed.

When the user pushes the staple button and designates the position of a staple mark in the document image IMG which is previewed the display synthesis processing section synthesizes a part of the band image L where the staple is to be attached with a staple mark read from the symbol mark region partial synthesis and rewrites the position of the staple mark on a part of the band image where the staple mark is already positioned. Then the new staple mark position is displayed. In the LCD controller displays the staple mark position at a position L .

When the document images IMG IMG IMG . . . are read after reading the document image IMG the normal operation shown in is used.

When a preview image is displayed by being enlarged as shown in a part of the document image is replaced by a new image.

As described above according to the embodiment of the present invention a user can determine a processing condition for printing a document image by directly operating a preview image. In addition the user can determine the processing condition by operations such as a click and a drag. Further the user can visually and intuitively determine the processing condition.

Moreover according to the embodiment of the present invention when the user touches a desirable position on a preview image the user can designate a binding position by a staple. In addition since the user can operate on the preview image by touching a screen and pushing a button the operability for the user can be increased.

Further the present invention is not limited to the specifically disclosed embodiment and variations and modifications may be made without departing from the scope of the present invention.

The present invention is based on Japanese Priority Patent Application No. 2006 073406 filed on Mar. 16 2006 and Japanese Priority Patent Application No. 2007 060381 filed on Mar. 9 2007 with the Japanese Patent Office the entire contents of which are hereby incorporated herein by reference.

