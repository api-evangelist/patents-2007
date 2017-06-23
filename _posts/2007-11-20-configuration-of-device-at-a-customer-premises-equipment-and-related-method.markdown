---

title: Configuration of device at a customer premises equipment and related method
abstract: A device at a Customer Premises Equipment that comprising Device Dependent Services that are to be configured by a remote Auto-Configuration Server is claimed. The device comprises also Device Independent Services on top of a Service Platform (SPLF). The device is hereby adapted to be configured by a plurality of Auto-Configuration Servers and comprises therefore a Native Service Management being one of the Device Independent Services. This Native Service Management comprises furthermore a receiver part to receive device dependent service information of the Device Dependent Services and a splitter part to split the device dependent service information into different parts, and to transmit each part to a distinct Device Independent Service. Each distinct Device Independent Services being coupled via a common Management Agent being one of the Device Independent Services, to one of the plurality of Auto-Configuration Servers, whereby only the respective part of the Device Dependent Services that is associated to the device dependent service information that is forwarded to the associated Device Independent Service is configured by the associated Auto-configuration Server (FIGURE).
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08880655&OS=08880655&RS=08880655
owner: Alcatel Lucent
number: 08880655
owner_city: Boulogne-Billancourt
owner_country: FR
publication_date: 20071120
---
The present invention relates to a method to configure Device Dependent Services and to a device that executes the method.

Indeed mass home network deployment requires remote configuration of the Customer Premises Equipment by a Customer Premises configuration Server also called Automatic configuration Server called hereafter shortly ACS in order to reduce the operator OPEX caused by help desk calls. The DSL Forum has defined the Customer Premises Equipment Wide Area Network Management Protocol shortly called WAN Management Protocol in the Technical Report TR 069. In this TR 069 Technical Report the remote configuration and management is today defined as being done by one ACS only which is a huge limitation in terms of business model.

Adapting the Technical Report TR 069 to support management of Customer Premises Equipment by multiple ACS s simultaneously would require significant changes to this protocol and would create problems of backward compatibility with existing deployments.

An alternative solution would be to pass through a Northbound interface of an ACS. Such a master ACS plays then the role of a proxy for a slave ACS. However such a specific northbound interface would have a lot of limitations. One of these limitations becomes clear in the example when hereby an end user X has to choose between a Service Provider SP A and another Service Provider SP B for his services. When this user X chooses the first Service Provider SP A for its basic service offering e.g. connectivity firewall settings . . . while this user X wants the other Service Provider SP B to offer him with an advanced service such as e.g. IPTV for example. In the assumption of a master ACS it means that the second Service Provider SP B would have to contact the ACS of the Service Provider SP A and asks it to make some configuration for itself. It also means that SP A is now aware that end user X has selected SP B for an advanced service that he could provide himself. There is here clearly a lack of confidentiality that could negatively affect both Service Providers SP B can loss a client and needs to proxy information to SP A and SP A can try to regain its customer for this advanced service.

It has to be explained that the ACS is today managing device dependent parameters also called Native Parameters of the device dependent services called Native Services. These Native Parameters are supported by the firmware of the CPE device. The ACS can employ the Native Services and configure the Native Parameters through an interface of the CPE device. Examples of these Native Services are firewalls Network Address Translation support for Quality of Service such as traffic classification and queuing etc.

When the device has a service platform another entity is managing the device independent services on top of this service platform also called bundles.

It has to be explained that a service platform i.e. a Framework for Service Management can be implemented by means of e.g. OSGi running on a Java Virtual Machine or e.g. by a service platform created on top of .NET or e.g. a service platform build on top of Linux etc.

The device independent services bundles are applications that do not depend on device specific features but only rely on the features offered by the service platform. As such bundles can be e.g. end users applications or they can be services that are not device dependent such as e.g. QoS monitoring of the home network .

Furthermore it has to be explained that such bundles have certain properties. By exporting a service interface to a predefined service platform s service registry other bundles can act upon a particular bundle and thus change the bundles properties. With the existing technology one can control exported services. Hereby services registered in the service registry are only visible to certain bundles and not to others.

Indeed each service platform has a service registry. A first bundle firstly registers at the service registry the fact that it has a first interface available. This means that another second bundle can find in this service registry this fact i.e. the first bundle made a first interface available to other bundles. Hereby the second bundle can also use this first interface. However in addition the first bundle can register at the service registry also the fact that it only makes this first interface available to some predefined other bundles. Hereby the second bundle can only use the first interface in the event when the first bundle explicitly made available the first interface for the second bundle i.e. the first bundle exported his first interface for the second bundle. In this way on the service registry a service interface can be opened i.e. exported for use by another bundle.

In this way a device at a Customer Premises Equipment comprises Device Dependent Services that can be configured by a remote Auto Configuration Server. The device further comprises also Device Independent Services on top of a Service Platform that are called bundles.

Such a device has however the drawback as described above of not being properly adapted to be auto configured simultaneously by more then one auto configuration server.

An object of the present invention is to provide a method and a device such as the above known type but which supports of being configured simultaneously by more then one auto configuration server without providing conflicts between the different auto configuration servers and without having to provide backward compatibilities with the existing deployments.

According to the invention this object is achieved due to the fact that the management of device dependent parameters is linked to a specific bundle s service interface on the service platform. This specific bundle called Native Services Management provides access towards the management of dedicated native service bundles and makes some parameters visible to e.g. only Service Provider A or it makes some parameters visible to only Service Provider B. The parameters that are made visible to one or to the other Service Provider is depending on the services and service providers that are chosen by the end users.

Indeed the Management Agent terminates the remote management protocol sessions from SP A and SP B. It makes sure that each of these sessions can only interact with its own bundle called device independent services DIS A for service provider SP A and device independent services DIS B for service provider B.

In this way since the Native Services Management bundle only makes the parameters visible for each service provider in their own bundle and the Management Agent makes sure that each of the remote management sessions can only interact with its own bundle this effectively makes remote management of Customer Premises Equipment by multiple ACS s simultaneously possible without changing the TR 069 protocol.

So the device is adapted to be configured by a plurality of Auto Configuration Servers and comprises therefore a Native Service Management being one of the Device Independent Services. And the Native Service Management comprises hereby

The Native Services Management enables remote management of the Device by different ACS s. Hereby multi service provider management access is enabled. Indeed each service provider such as Service Provider A and or Service Provider B can configure his own set of native device dependent parameters in addition to the already available configuration of device independent service parameters.

It is to be noticed that the term comprising used in the claims should not be interpreted as being limitative to the means listed thereafter. Thus the scope of the expression a device comprising means A and B should not be limited to devices consisting only of components A and B. It means that with respect to the present invention the only relevant components of the device are A and B.

Similarly it is to be noticed that the term coupled also used in the claims should not be interpreted as being limitative to direct connections only. Thus the scope of the expression a device A coupled to a device B should not be limited to devices or systems wherein an output of device A is directly connected to an input of device B. It means that there exists a path between an output of A and an input of B which may be a path including other devices or means.

The working of the device according to the present invention in accordance with its telecommunication environment that is shown in the FIGURE and will be explained by means of a functional description of the different blocks shown therein. Based on this description the practical implementation of the blocks will be obvious to a person skilled in the art and will therefore not be described in details. In addition the principle working of the method to configure device dependent services will be described in further detail.

The FIGURE shows an Access Node AN that is coupled to the Device at a Customer Premises Equipment D CPE and to two Auto configuration Servers ACS A and ACS B. The Auto configuration server ACS A is included to configure predetermined parameters of the device D CPE which are relevant to a Service Provider A not shown and Auto configuration server ACS B is included to configure predetermined parameters of the device D CPE which are relevant to Service Provider B not show .

The device D CPE comprises Hardware HW being the basic functional blocks of the device and a memory MEM that comprises the Firmware MEM FW being embedded in the hardware HW. The Memory can be implemented by a flash ROMs or as a binary image file that can be uploaded onto other parts of the hardware HW.

The Device Dependent Services DDS is a functional block being part of the Framework FW that executes the Native Services by means of setting predefined parameters to predefined values. As a matter of example the device dependent services functional block DDS comprises two parts DDS A and DD B. The DDS A part is the part of the device dependent services DDS that is related to predefined services which must be configured by Service provider A via the auto configuration server ACS A. The DDS B part is the part of the device dependent services DDS that is related to predefined services which must be configured by Service provider B via the auto configuration server ACS B.

The device D CPE further comprises a Service Platform SPLF that provides the device Framework for a service platform such as described above.

In order to access the device dependent services DDS an Application Programming Interface API is included. Via this API interface the set of relevant parameters can be programmed with its respective value. Hereby the device dependent services or part of it is installed reinstalled activated or deactivated etc

Via the Application Programming interface the device dependent service parameters can be exported on top of the Service Platform SPLF of the device D CPE.

The device D CPE also comprises Device Independent Services DIS that are included to execute device independent services such as described above. These Device Independent Services are also called bundles. Each bundle executes its particular dedicated function.

In this way a Device Independent Services functional block is shown called DIS A. This is a bundle that implements the functions that are directed to the configuration of the configuration parameters that are relevant for device Dependent Services part A i.e. DDS A and that ought to be configured by the Auto configuration server ACS A.

Furthermore also a Device Independent Services functional block is shown called DIS B. This is a bundle that implements the functions that are directed to the configuration of the configuration parameters that are relevant for device Dependent Services part B i.e. DDS A and that ought to be configured by the Auto configuration server ACS B.

Also the Native Service Management NSM is a Device Dependent Services functional block and will be further explained in a further paragraph.

Finally the Management Agent MA is also a Device dependent services functional block that executes e.g. the known function of terminating the applicable protocol such as e.g. TR 069 and that further forwards the dedicated messages towards e.g. DIS A or DIS B.

Device dependent service information INF DDS is exported by the device dependent services DDS via the Application Programming Interface API on top of the Service Platform SPLF towards the Native Service Management NSM. The receiver part of the Native Service Management NSM REC receives this Device dependent service information INF DDS.

It has to be remarked that this device dependent service information INF DDS comprises inherently different parts e.g. the device dependent service information being relevant for service provider A called INF DDS A and the device dependent service information being relevant for service provider B called INF DDS B.

The Native Service Management NSM is included to split the device dependent service information INF DDS into these two parts i.e. INF DDS A and INF DDS B. This is done by the splitter part of the Native Service Management NSM SPL. Hereafter the splitter part NSM SPL makes visible a first part INF DDS A to the Device Independent Service DIS A and a second part INF DDS B to the Device Independent Services DIS B.

Each device independent services DIS A and DIS B makes this information available to the Management Agent MA by exporting a service interface i.e. DIS A exports a service interface M DDS A comprising only information related to the associated respective part DDS A of DDS and DIS B exports a service interface M DDS B comprising only information related to the associated respective part DDS B of DDS.

Indeed NSM SPL exports two service interfaces to the service registry a first being comprised in INF DDS A and a second being comprised in INF DDS B. The two service interfaces are registered in the registry whereby according to the above described mechanism NSM SPL specifies that INF DDS A is only made available to DIS A and INF DDS B is only made available to DIS B. This means that also in the other direction Bundle DIS A can only find information at the Service registry being related to INF DDS A and can consequently only use information of INF DDS A.

Finally the Management Agent forwards the device dependent service information DDS A and DDS B to the respective Auto configuration server ACS A and ACS B respectively.

Hereby it has to be explained that also in the downstream direction the respective Auto configuration servers ACS A and ACS B communicates only with its associated part of the device dependent services DDS respectively DDS A and DDS B via the common Management Agent MA and via the associated device independent services DIS respectively DIS A and DIS B and via the common Native Service Management NSM that further forwards the configuration values towards the associated device dependent services respectively DDS A and DDS B for configurations of its device dependent service parameters.

So the different parts of device dependent service information INF DDS A and INF DDS B is communicated in both directions whereby each respective auto configuration server ACS A and ACS B is enabled to configure its associated part respectively DDS A and DDS B of device dependent services DDS. However Auto configuration server ACS A is not able to configure parameters related to DDS B nor vice versa.

A final remark is that embodiments of the present invention are described above in terms of functional blocks. From the functional description of these blocks given above it will be apparent for a person skilled in the art of designing electronic devices how embodiments of these blocks can be manufactured with well known electronic components. A detailed architecture of the contents of the functional blocks hence is not given.

While the principles of the invention have been described above in connection with specific apparatus it is to be clearly understood that this description is made only by way of example and not as a limitation on the scope of the invention as defined in the appended claims.

