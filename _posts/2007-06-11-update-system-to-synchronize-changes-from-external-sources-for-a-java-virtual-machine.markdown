---

title: Update system to synchronize changes from external sources for a java virtual machine
abstract: Embodiments of the present invention provide a security cache update mechanism for J2EE where changes to external sources affecting information in the security cache are automatically propagated into the security cache. In some embodiments, the update mechanism utilizes a standards based mechanism, such as a Service Provisioning Markup Language (SPML) exchange, to propagate changes at these external sources.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09069638&OS=09069638&RS=09069638
owner: Red Hat, Inc.
number: 09069638
owner_city: Raleigh
owner_country: US
publication_date: 20070611
---
The present invention relates to computer security and more particularly it relates to maintaining a security cache current.

Java Platform Enterprise Edition Java EE or J2EE is a widely used platform for server programming in the Java language. A J2EE container is a runtime entity that provides services to specialized Java components. Services provided by a container typically include life cycle management security deployment and component specific services. Containers are used in a wide variety of Java components such as Enterprise Javabeans EJB Web pages Java Server Pages JSP servlets applets and application clients.

For security information J2EE containers typically cache their security cache in the Java Virtual Machine JVM to avoid round trip latency to third party sources like a database or a directory service. But when these sources change information like password changes role changes the security cache can become inconsistent with what is current.

Typically J2EE containers employ a timeout feature to attempt to keep their security cache current. However timeouts are generally insufficient in keeping security caches current in dynamic environments.

Accordingly it may be desirable to provide methods and systems that allow J2EE containers to keep their security caches more current.

Embodiments of the present invention provide a security cache update mechanism for J2EE where changes to external sources affecting information in the security cache are automatically propagated into the security cache. Such external sources may any system that provides information cached in a Java application. For example a directory server or other type of database server may be the source of information in the J2EE security cache that requires provisioning of updates. In some embodiments the update mechanism utilizes a standards based mechanism such as a Service Provisioning Markup Language SPML exchange to propagate changes at these external sources.

Reference will now be made in detail to the exemplary embodiments of the invention which are illustrated in the accompanying drawings. Wherever possible the same reference numbers will be used throughout the drawings to refer to the same or like parts.

Client may be any computer system that utilizes the services of another computer system i.e. web server and application server . As shown in client may be implemented using components well known to those skilled in the art such as a personal computer laptop computer personal digital assistant a mobile phone and the like. In the embodiments shown in client may be used to run Web applications via an application such as web browser.

Web server is computer system that accepts requests from clients such as client and serving responses along with optional data contents. In the embodiment shown this content served by web server is usually one or more Web pages that includes hypertext markup language HTML documents and linked objects images video audio etc. .

Web server may be implemented on a machine that comprises well known hardware and software. Well known software for web server may be software such as Apache HTTP Server from the Apache Software Foundation Internet Information Services by Microsoft Corporation and Sun Java System Web Server from Sun Microsystems Inc. One skilled in the art will recognize that any of the many different Web server programs available are consistent with the principles of the present invention.

Application server is software that provides applications to client . Application server may be configured to handle security business logic data access for the applications provided to the client . Application server may provide a variety of Web based applications such as e commerce applications content management applications customer relations management applications and the like.

Application server may be implemented on various software platforms. For example application server may be implemented on the well known J2EE platform from Sun Microsystems Inc. In addition application server may comprise middleware to enable applications to intercommunicate with dependent applications like web server database management systems etc.

Application server may be implemented using well known software. For example application server may be implemented using software such WebLogic server from BEA Systems Inc. JBoss from Red Hat Inc. Websphere from the IBM Corporation and the like.

Accordingly application server may implement the Java programming language and provide Web modules using servlets and JavaServer pages. Other functions of application server may also employ Java. For example business logic provided by application server may be built into Enterprise JavaBeans EJBs . J2EE provides standards for containing the Web components. Security services such as authentication and authorization may be implemented using the Java Authentication and Authorization Service JAAS or similar service.

Directory service represents the components that store and organize information about the users of system and an administrator of system to manage those users access to the resources of system . Directory service may comprise a database not shown that holds information about named objects that are managed. Directory service also provides the access interface to the data that is contained in this database. Directory service may be implemented using well known technologies. For example directory service may be implemented as a X.509 directory service or Lightweight Directory Access Protocol LDAP service.

There are several well known directory service implementations from various vendors. Among them are Red Hat Directory Server from Red Hat Inc. Active Directory by the Microsoft Corporation Apache Directory Server by the Apache Software Foundation and Sun Java System Directory Server by Sun Microsystems Inc.

Provisioning server is software that listens for provisioning requests in system and returns provisioning responses. In some embodiments provisioning server is configured as a SPML provisioning service provider. Provisioning server may be implemented as a separate software component of system or may be integrated with other components of system . For example provisioning server may be a component that is installed as part of directory server .

Network represents the communications infrastructure for allowing client and web server to communicate with each other. For example network may represent the Internet which is a worldwide publicly accessible network that uses the Internet Protocol IP suite of standards.

Network represents the communications infrastructure that allows web server application server directory service and provisioning server to communicate with each other. Network may be implemented as a local area network or may utilize one or more larger networks such as the Internet.

Application refers to the software that requests services and access to resources of system . Typically application may be an application such as a web browser that runs on client and connects to web server as necessary. In some embodiments application represents any application that utilizes Java.

Java Virtual Machine JVM is a set of computer software programs and data structures which implements the Java virtual machine on client . JVM interprets the Java bytecode and executes the code for application . JVM may be implemented using the well known JVM standard which is published by Sun Microsystems Inc.

Security cache is a block of memory for temporary storage of security data likely to be used again by JVM . Security cache may be configured as a pool of entries which each have a tag indicating the identity of the source of the data stored. Typically security cache is used for caching authentication information. Security cache may be configured with various properties to control its behavior. For example JVM may specify the initial size of security cache as well as the frequency or timeout of when security cache should be refreshed.

Security update client represents provisioning interface for updating the contents of security cache . In some embodiments security update client is a SPML compliant service that utilizes provisioning service for updates to security cache . Of note in order to secure the provisioning of updates to security cache security update client may establish trust relationships with provision service and directory service . The details of establishing and maintaining this trust relationship are well known to those skilled in the art and are beyond the scope of this specification.

Host operating system OS is the set of programs that manage the hardware and software resources of client . Several implementations of OS are well known to those skilled in the art. For example operating systems such as Windows from the Microsoft Corporation Mac OS from Apple Corporation and LINUX from Red Hat Inc. are well known.

Hardware represents the physical components of client . Such components including the processor memory disk drive and the like are well known to those skilled in the art.

In this example shown provisioning server may consider directory service as a resource and the security cache in client as a provisioning service target. The process flow for provisioning updates to security cache in client will now be further described.

In phase application server constructs an SPML document subscribing client to the provisioning service offered by provisioning server . The SPML document specifies the characteristics of the provisioning service. Such characteristics include whether updates should occur synchronously or asynchronously the schema of data being updated whether updates should be batch or individually processed identity of the source of updates and identity of the update target.

In phase provisioning server provisions the update service at client . In particular provisioning server takes the data passed in the SPML document from application server constructs its own SPML document and sends it to security update client at client .

In phase in order to fully service the request by application server provisioning server also forwards the SPML document to directory service . In response directory service identifies the subject of the provisioning request in the SPML document and establishes a data set for updates.

In phase security update client opens a connection with security update client . For example this connection may be a Java JDBC or ODBC connection with directory service . JDBC and ODBC are well known application programming interfaces of Java. Such connections provide methods for querying for updates in authentication information in directory service . Accordingly whenever changes are made in directory service they will automatically be propagated to security update client and security cache .

Other embodiments of the invention will be apparent to those skilled in the art from consideration of the specification and practice of the invention disclosed herein. For example instead of application server client or directory service may be the initial requester for provisioning updates to the security cache at client . In addition protocols other than SPML may be employed by the present invention. For example any form of extensible markup language XML protocol is consistent with the present invention. It is intended that the specification and examples be considered as exemplary only with a true scope and spirit of the invention being indicated by the following claims.

