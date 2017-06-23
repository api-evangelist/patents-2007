---

title: Graphic system comprising a fragment graphic module and relative rendering method
abstract: A graphic system having a central processing unit; a system memory coupled to the central processing unit; a display unit provided with a corresponding screen; a graphic module coupled to and controlled by the central processing unit to render an image on the screen of the display unit, the graphic module including a fragment graphic module having a depth test buffer for storing a current depth value; a depth test stage coupled to the depth test buffer for comparing the current depth value with a depth coordinate associated with an incoming fragment and defining a resulting fragment; a test stage for testing the resulting fragment and defining a retained fragment; a buffer writing stage operatively associated with the test stage for receiving the retained fragment, the buffer writing stage coupled to the depth test buffer for updating the current depth value with a depth value of the retained fragment.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08169442&OS=08169442&RS=08169442
owner: STMicroelectronics S.r.l.
number: 08169442
owner_city: Agrate Brianza
owner_country: IT
publication_date: 20071227
---
The present disclosure relates to a 3D three dimensional graphic pipeline module and more particularly to a system having a fragment pipeline graphic module.

Computer graphics is the technique of generating images or pictures in discernable form such as on a display device or printer with a computer. The generation of pictures or images is commonly called rendering. Generally in three dimensional computer graphics geometry that represents surfaces or volumes of objects in a scene is translated into pixels and then displayed on the display device.

In computer graphics each object to be rendered is composed of a number of primitives. A primitive is a simple geometric entity such as e.g. a point a line a triangle a square a polygon or high order surface. A single primitive is also defined by a set of attributes that belongs to the primitive e.g. colors texture coordinates and user defined properties and that are associated in a proper way to all the pixels of the screen. This information is included in a so called fragment so that every pixel to be displayed on the screen can be rightly colored on the display according to the fragment attributes set at a certain pixel onto the screen.

The processing of a fragment is performed by a sub graphic pipeline of a typical graphic pipeline called fragment graphic pipeline.

The OpenGL ES Standard imposes certain constraints on the order of the operative modules of a fragment graphic pipeline.

It is observed that the order of the operative module of the fragment graphic pipeline often implies processing of a fragment by expensive operation modules even if the same fragment at the end of the fragment graphic pipeline processing is discarded because it does not have a displayable fragment on the screen.

Since bandwidth dedicated to expensive operative modules is usually limited it has been noticed that there is a need for a fragment graphic pipeline that reduces unnecessary use of the bandwidth during processing of a fragment in the fragment graphic pipeline.

In accordance with a particular embodiment of the present disclosure a graphic system is provided that includes a central processing unit a display unit having a corresponding screen and a graphic module coupled to and controlled by the central processing unit to render an image on a screen of the display unit. Particularly the graphic module includes a fragment graphic module having a depth test buffer for storing a current depth value a depth test stage coupled to the depth test buffer for comparing the current depth value with a depth coordinate associated with an incoming fragment and defining a resulting fragment a test stage for testing the resulting fragment and defining a retained fragment a buffer writing stage operatively associated with the test stage for receiving the retained fragment the buffer writing stage coupled to the depth test buffer for updating the current depth value with a depth value of the retained fragment.

According to another embodiment the fragment graphic module includes a depth test buffer for storing a current depth value a depth test stage coupled to the depth test buffer for comparing the current depth value with a depth coordinate associated with an incoming fragment and defining a resulting fragment a test stage for testing the resulting fragment and defining a retained fragment and a buffer writing stage operatively associated with the test stage for receiving the retained fragment. The buffer writing stage is coupled to the depth test buffer for updating the current depth value with a depth value of the retained fragment.

In accordance with another particular embodiment a method for rendering an image on a screen of a display unit of a graphic system having a graphic module coupled to and controlled by a central processing unit is provided. The method includes storing a current depth value associated to a current fragment in a depth test buffer performing a depth test by comparing the current depth value with a depth value associated with an incoming fragment and defining a resulting fragment testing the resulting fragment to define a retained fragment and updating the current depth value with a depth value of the retained fragment.

In accordance with another embodiment of the present disclosure a fragment graphic pipeline for processing incoming fragments having attributes associated with pixels of an image to be rendered on a display screen is provided. The pipeline includes a depth stencil test stage adapted to compare a depth value of the incoming fragment with a depth value stored in a depth test buffer the depth stencil test stage adapted to further compare planar coordinates in the incoming fragment with test planar coordinates stored in a stencil buffer that define the active area on the display screen to determine if the incoming fragment is included in the active area of the display screen at least a first texturing blending stage and a last texturing blending stage coupled to the depth stencil stage and adapted to apply color attributes to the incoming fragment an alpha test stage coupled to the last texturing blending stage and adapted to compare a transparency level of the incoming fragment and a reference transparency and to forward down the pipeline the incoming fragment that passes the alpha test stage comparison of the transparency level and a buffer writing stage coupled to the alpha test stage to receive the incoming fragment that passes the alpha test stage and adapted to update the depth test buffer to replace the current depth value with a depth value of the incoming fragment that passes the alpha test stage.

In accordance with another aspect of the foregoing embodiment the pipeline includes a scissor test stage ahead of the depth stencil test stage in the pipeline and adapted to delimit an active portion of the display screen when rendering an image in that portion of the display screen.

In accordance with another aspect of the foregoing embodiment the scissor test stage is adapted to generate only incoming fragments that are included in the active portion of the display screen defined by planar coordinates of a bottom left corner and an upper right corner of the active area.

In accordance with another aspect of the foregoing embodiment the buffer writing stage is further adapted to update the stencil test buffer.

In accordance with another aspect of the foregoing embodiment the pipeline comprises the depth stencil test stage is configured to perform the depth test by only reading the depth test buffer while the buffer stage is adapted to only update the depth test buffer.

In accordance with another aspect of the foregoing embodiment the pipeline comprises a color buffer write stage operatively associated with the buffer writing stage and adapted to generate pixel information from the incoming fragment that has been processed through the pipeline.

In accordance with another aspect of the foregoing embodiment the pipeline includes at least one additional texturing blending stage coupled between the buffer writing stage and the color buffer write stage.

In accordance with another aspect of the foregoing embodiment the pipeline includes an additional depth stencil test stage coupled between the alpha test stage and the buffer writing stage and adapted to perform depth and stencil testing of the incoming fragment and to update the depth test buffer and the stencil test buffer.

In accordance with another aspect of the foregoing embodiment the pipeline includes an enabling disabling stage coupled to an input of the depth stencil test stage and adapted to introduce a processing delay to provide time for reading of the depth test buffer by the depth stencil test stage before writing to the depth test buffer by the buffer writing stage.

As an example the mobile phone can be a cellular phone provided with an antenna a transceiver Tx Rx connected to the antenna and an audio circuit AV CIRC connected with the transceiver . A speaker and a microphone are connected to the audio circuit unit .

The mobile phone is further provided with a CPU central processing unit for controlling various functions and particularly the operation of the transceiver and the audio circuit unit according to a control program stored in a system memory MEM connected to the CPU . Graphic module is connected to and controlled by the CPU . Moreover mobile phone is provided with a display unit having a corresponding screen e.g. a liquid crystal display DSPY and a user interface such as an alphanumeric keyboard K B .

The graphic module is configured to perform a set of graphic functions to render an image on a screen of the display . Preferably the graphic module is a graphic engine configured to rendering images offloading performing of the task from the CPU . As used herein the term graphic engine means a device that performs rendering in hardware or software not running on a CPU but on another coprocessor such as a DSP digital signal processor . The term graphic accelerator or graphic coprocessor are also employed in the field are equivalent to the term graphic engine. 

Alternatively the graphic module can be a graphic processing unit GPU wherein the rendering functions are performed on the basis of hardware and software instructions executed on a dedicated processor such as a DSP. In accordance with a further embodiment some or all the rendering functions are performed by the CPU .

In accordance with the sort middle rendering the screen of the display is divided in a plurality of 2D two dimensional ordered portions i.e. 2D tiles such as for example square tiles. As an example the screen is partitioned into 2D files having size 16 16 pixels or 64 64 pixels.

The graphic engine illustrated in includes a driver a geometry stage also known as TnL stage Transform and Lighting stage a binner stage a parser stage a rasterizer stage and a fragment graphic module that is coupled to the display not shown in of the mobile phone of .

The driver is a block having interface tasks and is configured to accept commands from programs e.g. application programming interface API running on the CPU and then translate them into specialized commands for the other blocks of the graphic engine .

The graphic engine is configured to process primitives and apply transformations into the geometry stage to them so as to move 3D objects. As defined above a primitive is a simple geometric entity such as e.g. a point a line a triangle a square a polygon or high order surface. Reference is often made to triangles which can be univocally defined by the coordinates of their vertexes without other types of employable primitives.

The binner stage is adapted to acquire from the geometry stage primitives coordinates and associate them with each tile of the screen . The binner stage is coupled to a scene buffer which is a memory able to store information relating primitive data provided by the binner stage . Preferably the scene buffer is external to the graphic module and particularly is allocated in an external memory . As an example the external memory can be the system memory of the graphic system illustrated in .

The parser stage is coupled to the scene memory and is responsible for reading for each tile the information in the scene buffer and passing such information to the rasterizer stage . The parser stage is coupled to the binner stage to receive synchronization signals.

The rasterizer stage is located between the parser stage and the fragment graphic module and is configured to receive and process primitive data from the parser stage so as to generate a fragment completely inside a current tile under processing to be processed by the fragment graphic module .

As defined a fragment is a set of pixel information referred to the same primitive so that a correct color of a pixel to be written in the scene memory is produced by the fragment graphic module .

The set of pixel information included in a fragment comprise attribute values of each pixel such as data relating to color planar position coordinates x and y depth position coordinate z texture coordinates alpha value stencil value etc. As an example a triangle vertex has the following attributes color position and coordinates associated with texture. As known to the skilled person a texture is an image e.g. a bitmap image that could be mapped on the primitive. As defined a pixel is a two dimensional memory location in which color information relating red R green G blue B and transparency values A can be stored.

The graphic module of further comprises an internal graphic memory coupled to the fragment graphic module which is a memory able to store information provided by the fragment graphic module . As explained below the fragment graphic module is arranged to read from and to write in the internal memory information relating to a fragment under processing received from the rasterizer stage .

The fragment graphic module also called fragment pipeline is configured to perform processing of an incoming fragment F received from the rasterizer stage to produce a color to be written into the display memory .

The fragment graphic module comprises a scissor test stage an enabling disenabling stage a depth stencil test stage a test stage a buffer writing stage and a color buffer writing stage .

The scissor test stage is configured for checking if planar coordinates x y of the incoming fragment F received by the rasterizer stage are such that the incoming fragment is included within an active portion of the screen in which a image will be rendered. As known by the skilled person of computer graphic the active portion employable in the scissor test is defined by planar coordinates of the bottom left corner and the upper right corner preferably stored in the scene buffer . As an example the active portion of the screen is a rectangle of the screen.

The scissor test stage is normally used to delimit the active portion of the screen when the rendering of an image in that portion of the screen is required.

An incoming fragment that passes the scissor test is a fragment that is included in the active portion of the screen defined by planar coordinates of bottom left corner and upper right corner stored in the scene memory . An incoming fragment which does not pass the scissor test is discarded i.e. killed by the scissor test stage .

Typically the scissor test stage is configured as disenabled and the active portion of the screen is the entire screen itself.

In a particular embodiment the scissor test stage can be embedded within the rasterizer stage in order to generate only fragments included in the active portion of the screen defined by planar coordinates of bottom left corner and upper right corner stored in the scene memory .

Particularly the depth stencil test stage is configured for comparing a current depth coordinate Z stored in a depth buffer coupled to the depth stencil test stage with a depth coordinate Z of the incoming fragment F and defining a resulting fragment. Preferably the depth buffer is allocated into the internal memory of the graphic module of .

In the case where the resulting fragment is a previous fragment F the depth stencil test stage is configured to kill the incoming fragment F since it has not passed the depth test fragment labeled as not visible . In the case that the resulting fragment is the incoming fragment F the depth stencil test stage is configured to label the incoming fragment as visible and to forward it down the fragment pipeline graphic module .

With current depth coordinate Z is defined the last depth coordinate stored in the depth test buffer relating to a previously fragment F which results as visible. 

The depth stencil test stage is further configured to perform a stencil test on the incoming fragment F.

Particularly the depth stencil test stage is configured to compare planar coordinates X Y of the incoming fragment F with a set of test planar coordinates read from a stencil test buffer allocated into the internal memory . The set of test planar coordinates stored in the stencil test buffer defines an active area of the screen having a particular shape e.g. a star in which an image will be rendered. In other words the stencil test stage is configured to test if the incoming fragment F is included in the area of the screen defined by and stored in the stencil test buffer .

The depth stencil stage is configured to kill a fragment that does not pass the stencil or the depth test and to forward down the fragment pipeline graphic module a fragment that does pass the stencil and or the depth test.

The test stage includes a first texture blending stage coupled to the depth stencil test stage for applying a first color attribute C to the incoming fragment F. The test stage further includes a second texturing blending stage coupled to the first texturing blending stage for applying to the incoming fragment F a second color attribute C for combining it with the first color attribute C.

As defined by the OpenGL ES standard the number of texturing blending stages provided in a fragment graphic module has a minimum value of two and maximum value of N typically up to eight. A number of texturing blending stages greater than two implies costs with reference to the level of the employed memory band and to the workload of the graphic engine. According to the particular embodiment illustrated in the fragment graphic module includes the minimum number of texture blend stages two for compliance with the OpenGL ES standard.

The texturing blending operations performed by the first and second texturing blending stage comprise a first operation of reading a texture image mapped from the texture coordinates of the incoming fragment F in an external memory as the scene memory coupled to the texturing blending stages in which a set of reference texture images are stored. Following the first and second texturing blending stages are configured to perform a second operation of coloring the incoming fragment F on the basis of colors coming from the mapped texture image.

In view of the first and second operations required the processing of a fragment by the first and second texturing blending stage is considered expensive.

The test stage further comprises an alpha test stage coupled to the second texture blend stage to process the incoming fragment F processed by the first and second texturing blending stage. As known by the skilled person the alpha test operation performed by the alpha test stage is another binary filter operation to be overcome by a fragment processed in the fragment graphic module and particularly refers to the level of transparency of a fragment.

The alpha test stage is configured to compare a transparency level value T of the incoming fragment F and a reference transparency level value T defined by the OpenGL ES standard as acceptable for the fragment graphic pipeline. The alpha test stage is configured to forward down the fragment pipeline a fragment which overcomes the alpha test and to kill a fragment that does not pass the alpha test.

As it will be described in the following with reference to the enabling disenabling stage the test stage first texturing blending test stage second texturing blending stage and alpha test stage can be also defined as a critical area.

The buffer writing stage is coupled to the alpha test stage to receive the incoming fragment F that overcomes the alpha test.

The buffer writing stage is configured to update the depth test buffer by replacing the current depth value Z with the depth coordinate Z of the incoming fragment F that has also overcome the alpha test and will be visible on the screen.

The position of the depth test stage before the test stage avoids advantageously performing the expensive texturing and blending operations on a not visible fragment. In fact the fragment graphic module is configured to kill a fragment not visible before forwarding it to the texturing blending stages.

Fragment graphic pipelines of prior designs have the depth stencil test stage located after the texturing blending stages and alpha test stage. If the alpha test stage is disenabled the fragment pipeline is arranged to kill a fragment as not visible only after the processing of the same fragment by texturing blending stages.

Furthermore the position of the buffer writing stage after the alpha test stage allows advantageously updating of the depth test buffer with the depth coordinates of a fragment that has overcome after the depth test also the alpha test. In the following the depth stencil test stage will process another incoming fragment by comparing the depth coordinates of an incoming fragment with a current depth value stored in the depth buffer that corresponds to the last processed fragment that has overcome the depth and alpha tests. The depth test buffer is not updated with a depth coordinate of a fragment which does not overcome the alpha test.

Furthermore the solution of is improved with reference to known fragment pipeline of the prior designs in which the depth stencil test stage is configured to read from and write in the depth test buffer. In fact in prior designs the depth stencil stage is typically configured to perform both reading and updating the depth test buffer with the depth coordinate of the fragment that overcame the depth test. In the prior arrangement a fragment that passes the depth test can be processed by the texturing blending stages and the alpha test stage. When the fragment does not overcome the alpha test processing by the depth test stage of a following fragment will be made with reference to an inconsistent current depth coordinate since it corresponds to a fragment that has passed the depth test but which was killed by the alpha test and therefore was labeled as not visible. 

As clearly explained above the fragment graphic module illustrated in performs the depth test of following incoming fragments processed by the fragment graphic module with reference to the depth test buffer that has been updated with a current depth value corresponding to a fragment which has passed both the depth test and the alpha test.

In a fragment graphic pipeline in accordance with the OpenGL ES Standard of prior designs the depth stencil test stage is typically configured to read from and write in the depth test buffer.

The fragment graphic module in accordance with is advantageously configured for reading and writing the depth test buffer in two different stages. In fact the depth stencil test stage located before the first texture blend stage is configured to perform the depth test by only reading the depth buffer while the buffer writing stage located after the alpha test stage is arranged for only updating the depth test buffer .

The color buffer write stage is operatively associated with the buffer writing stage and is configured to write the scene memory with the pixel information fragment which have been processed by the fragment graphic module .

The fragment graphic module can include additional stages e.g. blending stages between the buffer writing stage and the color buffer write stage not shown in .

The fragment graphic module can further include a depth stencil test stage located between the alpha test stage and the buffer writing stage and configured to perform depth and stencil test of a fragment and to update depth and stencil test buffer.

The enabling disenabling stage is provided in order to improve the performance of the fragment graphic module of the device in which a processing delay is introduced since the reading of the depth buffer is performed before the writing of the depth buffer .

In a fragment graphic pipeline as known by the skilled person the processing delay is measured by the number of fragments processed by the fragment pipeline.

The fragment graphic module illustrated in is configured for so called parallel fragment processing. As an example each stage of the fragment graphic module is arranged to process simultaneously ten fragments depth stencil test stage processes the fragment first texturing blending stage processes the fragment second texturing blending stage processes the fragment and so on.

This fragment graphic module arrangement so called accelerated in hardware configuration enables performing M different operations on M different fragments in parallel. Parallel processing is quicker than the so called serial processing in which the fragment graphic pipeline is dedicated to process one fragment at a time.

Reference is now made to the case in which the incoming fragment F having planar coordinates X Y is received by the depth stencil test stage in a number of fragments so as a previous fragment F is under processing by the test stage to be in the critical area and the depth test buffer is not updated with the depth coordinate of the previous fragment F.

In this scenario the depth stencil test stage will compare the depth coordinate of incoming fragment F with a current depth coordinate that is not the depth coordinate of the previous fragment processed by the depth stencil test stage having the same planar coordinates X Y. In this case the depth stencil test stage will carry out dirty reads of the depth test buffer .

The depth test made on a inconsistent current depth value dirty reads is due to the delay introduced between the reading operation of the depth test buffer before first texturing blending operation and the writing updating of the depth test buffer after the alpha test stage .

The scenario described above is related only the case in which the incoming fragment and the previous fragment have the same planar X Y coordinates and therefore the test of the respective depth coordinate results is important in order to establish the fragment to be visible on the screen.

It should be observed that there are very low chances that processed fragments present the same planar X Y coordinates typically in 1 of the cases .

In any case the fragment graphic module illustrated in is arranged to solve the side effect described above by means of the enabling disenabling stage and the further depth stencil stage .

The enabling disenabling stage can be also called a hazard detection stage and includes a respective enabling disenabling buffer preferably embedded in the enabling disenabling stage for storing a track indicative of whether the previous fragment F is under processing by the test stage or if the processing of the previous fragment F by the test stage is terminated. Particularly the above mentioned track of a fragment has planar X Y coordinates of the fragment. In an alternative embodiment the enabling disenabling buffer can be allocated in the internal memory .

The enabling disenabling stage is arranged for checking if a new incoming fragment to be processed has the same position coordinates of a previous fragment processed by the enabling disenabling stage which has not reached the buffer writing stage depth test buffer not update with a consistent depth coordinate since they are under processing by the test stage .

In order to avoid performing the depth test on an incoming fragment with a no consistent current depth coordinate stored in the depth test buffer in case a hazard is detected incoming fragment having the same position coordinates of a previously fragment present in the critical area not yet processed by buffer writing module the enabling disenabling stage is configured to mark the incoming fragment as hazardous with a flag which means first depth stencil test not carry out on this fragment. Therefore the enabling disenabling stage is configured for enabling the further depth test stage and disabling the depth test stage when the previous fragment F has the planar coordinates of the incoming fragment F under processing by the test stage .

Furthermore the enabling disabling stage is arranged for enabling the depth test stage and disabling the further depth test stage when the test stage has terminated the processing of a previous fragment F i.e. no hazard detected .

The further depth stencil test stage is analogous to the depth stencil test stage and is configured to compare the depth coordinate of the fragment labeled as hazardous with a consistent current depth buffer. In fact by delaying the depth test on the incoming fragment after the alpha test stage it allows for the buffer writing stage to update the depth buffer stage with the consistent depth coordinate of the fragment having the same X Y position coordinates which in the mean time has left the critical area .

In an incoming fragment labeled as hazardous 1 of the cases the depth stencil test is postponed to a further depth stencil test stage located after the alpha test stage so that the buffer writing stage has the time for updating the depth buffer with the consistent depth coordinate of the fragment coming out from the critical area .

With reference to an example of organization of the memory embedded in the respective hazard buffer and a mechanism for searching planar X Y coordinates within said buffer will be described.

The hazard buffer illustrated in is configured to allow a search of a parallel type by an algorithm having a reduced number of steps e.g. four steps .

Inputs of the algorithm are planar coordinates X coordinate Y coordinate of an incoming fragment. In the following example each coordinate is n bits wide e.g. n 16 . However it is to be understood that the width of the coordinates may be shorter or longer. Each set is able to trace up to M different fragments e.g. M 4 . Hence a maximum of 16 bits is necessary to trace a single fragment. So in this embodiment every single set has a size of 64 bit.

step A A setID value is computed starting from the Nx and Ny LSB bits from both X Y planar coordinates. So this setID value is Nx Ny bits wide thus it is possible to directly address 2different sets 

step B an elemID value is computed putting together the remaining n Nx and n Ny MSB bits from both X Y planar coordinates. The variable elemID is at a maximum 16 bits wide 

step D checking to determine using 4 parallel searches if the computed elemID value is already stored inside the read set and if so the hazard is detected.

In is illustrated an example of a flow diagram of a functional block process by the depth stencil test stage on an incoming fragment F received from the enabling disenabling stage .

The flow diagram has a first checking block for controlling the status of the hazard flag of the incoming fragment.

If the fragment is marked as hazardous Y the depth stencil test stage does not process the incoming fragment depth test stage disenabled and further depth test stage enabled . The incoming fragment F is passed directly to the next stage of the fragment graphic module block .

If the fragment is marked as not hazardous N the depth stencil test stage processes the incoming fragment F depth test stage enabled and further depth test stage disenabled block and the stencil buffer is updated block .

The diagram flow further comprises a second checking block for controlling if the incoming fragment has to be passed to the next stage of the fragment graphic module or has to be killed as explained in the following.

If the incoming fragment overcome the depth test or the stencil buffer is updated the incoming fragment marked as not hazardous Y is forwarded to the next stage of the fragment graphic module block .

If the incoming fragment does not overcome the depth test and the stencil buffer is not updated N the incoming fragment is killed block .

The flow diagram includes a first checking block for controlling the status of the hazard flag of the incoming fragment.

If the incoming fragment is marked as not hazardous N the incoming fragment is passed to a second checking block to verify if the incoming fragment has passed the depth test and to a third checking block to verify if an updating of the depth buffer is needed.

With reference to the second checking block if the incoming fragment has passed the depth test Y it passes to the next stages of the fragment graphic module block . If the incoming fragment has not passed the depth test Y the fragment is killed block .

With reference to the third checking block if an updating of the depth buffer is needed the buffer writing stage is enabled to write the depth buffer block .

With reference to the first checking block if the incoming fragment is marked as hazardous Y the incoming fragment is processed by the further depth stencil test stage for performing depth test block and for updating the stencil buffer block . The incoming fragment processed by further depth stencil test stage is then forwarded to the second check block and the third check block . The processing of the incoming fragment then continues as described above.

With reference to the flow chart of an example of fragment graphic rendering method in the following simply method corresponding to the operation of the fragment graphic module of will now be described.

The method includes a step of storing STR by means of the buffer writing stage a current depth coordinate value Z in the depth test buffer corresponding to the last fragment F processed by the fragment graphic module and which results as visible. The method further includes a step of providing PRV an incoming fragment F generated by the rasterizer stage of the graphic engine .

The method continues with a step of enabling disenabling EN DIS for comparing planar coordinates of the incoming fragment with the set of position coordinates stored in the enabling disenabling buffer . It should be observed that in this example of operation as in 99 of the cases a hazard was not detected and therefore the incoming fragment is labeled as not hazardous. 

The incoming fragment F is received by the depth stencil test stage in which is performed the step of comparing CMP the current depth coordinate Z stored in the depth buffer with a depth coordinate Z of the incoming fragment and defining a resulting fragment. It is now supposed that the incoming fragment is more visible than the last fragment processed as visible F.

The method further includes the step of performing PF ST a stencil test on the incoming fragment F and the step of testing TST the incoming fragment F to define a retained fragment. Particularly the step of testing involves the step of performing on the incoming fragment F a first texture operation the step of performing a second texture operation and the step of performing the alpha test in which the processed incoming fragment F is processed by the alpha test to define the retained fragment fragment F .

Subsequently the method moves to the step of updating UPD by means of the buffer writing stage the depth buffer with the depth coordinate Z of the retained fragment F.

This is followed by the step of writing WRT the color buffer of the scene memory by means of the color buffer writing stage with the color pixel information included in the set of pixel information represented by the retained fragment F.

As is clear from the description of the above examples and embodiments the teachings of the disclosure are applicable to any type of graphic systems although they show particular advantages for embedded applications such as graphic applications to be run on systems having limited computing power and memory capacity.

It is important to note that the described solution has passed all the 1.1 OpenGL ES standard conformance tests. Furthermore a series of simulations of the operation of the fragment graphic module described herein and of a fragment pipeline of prior designs have been conducted in order to have an estimation in terms of Texture Unit Band Width reduction using a real game as reference. As a result a Texture Unit Band Width reduction that is comparable to the percentage of fragments killed by the depth test has been observed.

The various embodiments described above can be combined to provide further embodiments. All of the U.S. patents U.S. patent application publications U.S. patent applications foreign patents foreign patent applications and non patent publications referred to in this specification or listed in the Application Data Sheet are incorporated herein by reference in their entirety. Aspects of the embodiments can be modified if necessary to employ concepts of the various patents applications and publications to provide yet further embodiments.

These and others changes can be made to the embodiments in light of the above detailed description. In general in the following claims the terms used should not be construed to limit the claims to the specific embodiments disclosed in the specification and the claims but should be construed to include all possible embodiments along with the full scope of equivalents to which such claims are entitled. Accordingly the claims are not limited by the disclosure.

