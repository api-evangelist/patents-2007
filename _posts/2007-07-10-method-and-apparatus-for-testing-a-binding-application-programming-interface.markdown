---

title: Method and apparatus for testing a binding application programming interface
abstract: One embodiment of the present invention provides a system for testing a binding Application Programming Interface (API) on a device, wherein the binding API is bound to a native API for the device and provides different commands than the native API. During operation, the system executes a native-API test on the device through the native API to produce a native-API test-result. The system subsequently receives the native-API test-result from the device at a test-harness. Next, the system sends a binding-API test to a test-agent on the device which enables the test-agent to execute the binding-API test through the binding API to produce a binding-API test-result. The system then receives the binding-API test-result from the test-agent. Finally, the system compares the native-API test-result to the binding-API test-result to determine if the binding API is functionally equivalent to the native API.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08010950&OS=08010950&RS=08010950
owner: Oracle America, Inc.
number: 08010950
owner_city: Redwood Shores
owner_country: US
publication_date: 20070710
---
The present invention relates to software testing. More specifically the present invention relates to a method and apparatus for testing a binding Application Programming Interface API .

Computing systems usually provide programmers with a native Application Programming Interface API such as a set of system libraries to facilitate creating software applications for the computing systems. However using this native API to create complex software applications can be difficult because a native API typically provides only a basic set of commands to a programmer. Consequently programmers will often create a binding API which is bound to the native API but includes a greater selection of commands than the native API. However for a given command flow determining whether the binding API produces an equivalent result to the native API can be difficult because the binding API may not be mapped to the native API in a one to one relationship. Furthermore many binding APIs are designed for use with a resource constrained device which exacerbates the problem of testing the binding API because of a lack of resources for executing test code on the resource constrained device. Moreover binding APIs are often created at a high level of abstraction which enables the creation of hardware and operating system independent functionality but which further adds to the difficulty of testing the binding API.

Hence what is needed is a method and apparatus for testing a binding Application Programming Interface without the problems listed above.

One embodiment of the present invention provides a system for testing a binding Application Programming Interface API on a device wherein the binding API is bound to a native API for the device and provides different commands than the native API. During operation the system executes a native API test on the device through the native API to produce a native API test result. The system subsequently receives the native API test result from the device at a test harness. Next the system sends a binding API test to a test agent on the device which enables the test agent to execute the binding API test through the binding API to produce a binding API test result. The system then receives the binding API test result from the test agent. Finally the system compares the native API test result to the binding API test result to determine if the binding API is functionally equivalent to the native API.

In a variation on this embodiment the test result and the binding API test result can include images text video and audio.

In a variation on this embodiment comparing the native API test result to the binding API test result involves comparing function calls made while executing the native API test to function calls made while executing the binding API test.

In a variation on this embodiment the native API test and the API test include equivalent command flows.

In a variation on this embodiment the native API can be a hardware API a software API and a combination of the hardware API and the software API.

In a variation on this embodiment the test agent facilitates executing the binding API test by processing binding API commands which are associated with the binding API.

The following description is presented to enable any person skilled in the art to make and use the invention and is provided in the context of a parti cular application and its requirements. Various modifications to the disclosed embodiments will be readily apparent to those skilled in the art and the general principles defined herein may be applied to other embodiments and applications without departing from the spirit and scope of the present invention. Thus the present invention is not limited to the embodiments shown but is to be accorded the widest scope consistent with the principles and features disclosed herein.

The data structures and code described in this detailed description are typically stored on a computer readable storage medium which may be any device or medium that can store code and or data for use by a computer system. This includes but is not limited to volatile memory non volatile memory magnetic and optical storage devices such as disk drives magnetic tape CDs compact discs DVDs digital versatile discs or digital video discs or other media capable of storing computer readable media.

One embodiment of the present invention provides a test harness that facilitates testing a binding Application Programming Interface API on a computing device. This test harness executes two implementations of a command flow and then compares the results of executing the two implementations to determine if the two implementations are equivalent. Note that a first implementation of the command flow interacts with a native API associated with the device and a second implementation interacts with a binding API that is bound to the native API. If the results are equivalent then the binding API is functionally equivalent to the native API with respect to the command flow.

In one embodiment of the present invention the device can include a test agent that facilitates executing the second implementation of the command flow.

In one embodiment of the present invention the test harness can compare the results of the two implementations by performing a binary equivalence check a visual image comparison an audio comparison or any other method for comparing the results of the two implementations to determine if they are equivalent.

Test harness can generally include any node on a network including computational capability and including a mechanism for communicating across the network. Furthermore test harness can include any system which facilitates execution of a test on a device such as device .

In one embodiment of the present invention test harness includes comparator . Comparator can generally include any system for comparing test results to determine if the test results are equivalent.

Network can generally include any type of wired or wireless communication channel capable of coupling together computing nodes. This includes but is not limited to a local area network a wide area network or a combination of networks. In one embodiment of the present invention network comprises the Internet.

Device can generally include any node on a network including computational capability and including a mechanism for communicating across the network. Furthermore device can include native API and test agent .

Native API can generally include any API that provides direct access to the hardware. This can include a hardware API a software API or a combination of a hardware API and a software API.

Test agent can generally include any system that facilitates executing a binding API test such as binding API test .

In one embodiment of the present invention test agent can be a hardware system a software system or a combination of a hardware system and a software system.

In one embodiment of the present invention user can request that device execute a given command associated with native API by requesting that device execute a corresponding command associated with binding API that is bound to the given command.

In one embodiment of the present invention test agent can execute any application or part of an application that uses binding API .

In one embodiment of the present invention device is capable of executing any application that uses native API such as native API test .

In one embodiment of the present invention device is capable of executing any application that uses binding API . Note that device may or may not execute the applications via test agent .

Database can generally include any type of system for storing data in non volatile storage. This includes but is not limited to systems based upon magnetic optical and magneto optical storage devices as well as storage devices based on flash memory and or battery backed up memory. Note that database can store golden data file .

Golden data file can generally include any data structure for storing a test result associated with native API test .

In one embodiment of the present invention golden data file can generally store any test result from a known correctly implemented API. In this embodiment native API is a known correctly implemented API. 

User can generally include an individual a group of individuals an organization a group of organizations a computing system a group of computing systems or any other entity that can interact with computing environment .

In one embodiment of the present invention device stores the native API test result in golden data file on database . In this embodiment test harness retrieves the native API test result from database .

In one embodiment of the present invention the native API test result can include images text video audio and any other type of data that native API test can produce.

Next test harness sends binding API test to test agent on device operation . This enables test agent to execute binding API test through binding API to produce a binding API test result. Test harness then receives the binding API test result from test agent operation .

In one embodiment of the present invention the binding API test result can include images text video audio and any other type of data that binding API test can produce.

In one embodiment of the present invention native API test and binding API test include equivalent command flows.

In one embodiment of the present invention test agent facilitates executing binding API test . This may involve processing binding API commands which are associated with binding API. .

In one embodiment of the present invention test agent may facilitate executing binding API test by mapping binding API function calls to native API function calls optimizing native API function calls based on the command flow of binding API test or any other process that facilitates executing binding API test . In this embodiment because test agent may optimize native API function calls comparing function calls made by native API test and binding API test may not sufficiently determine if binding API is functionally equivalent to native API .

In one embodiment of the present invention the implementation of binding API includes the mapping of binding API function calls to native API function calls and the optimization of native API function calls based on the command flow of binding API test . In this embodiment because binding API includes optimization of native API function calls comparing function calls made by native API test and binding API test may not sufficiently determine if binding API is functionally equivalent to native API .

In one embodiment of the present invention the optimization of native API function calls is static. In this embodiment the optimization of native API function calls may not be based on the command flow of binding API test .

In one embodiment of the present invention before executing a binding API function call that is bound to a native API function call test agent may execute multiple binding API function calls which are not bound to a native API function call. This enables binding API to provide user with a greater selection of function calls than native API may provide.

Test harness then uses comparator to compare the native API test result to the binding API test result operation to determine if binding API is functionally equivalent to native API . Note that for binding API to be functionally equivalent to native API binding API should produce the same results for a given command flow as native API produces for the given command flow.

In one embodiment of the present invention comparator may use a threshold to determine if the native API test result is equal to the binding API test result. For example suppose that the native API test result and the binding API test result are images and that the binding API test result is of a lower resolution than the native API test result. If the difference in resolution between the images is below the threshold comparator may still determine that the native API test result and the binding API test result are functionally equivalent.

In one embodiment of the present invention comparing the native API test result to the binding API test result may involve comparing function calls made while executing native API test and binding API test .

The foregoing descriptions of embodiments of the present invention have been presented only for purposes of illustration and description. They are not intended to be exhaustive or to limit the present invention to the forms disclosed. Accordingly many modifications and variations will be apparent to practitioners skilled in the art. Additionally the above disclosure is not intended to limit the present invention. The scope of the present invention is defined by the appended claims.

