---

title: Resource management system, method and program for selecting candidate tag
abstract: Resource management system, method and program for selecting candidate tag are provided. The tag can be readily attached to a resource by presenting a candidate tag also to a resource newly registered in a database. The degree of similarity of a new registration resource to each of a plurality of already-registered resources that have been already registered in the database is calculated. A tag attached to an already-registered resource of which the degree of similarity is large is selected as a candidate for a tag to be attached to the new registration resource. Thereby, a candidate tag can be also presented to a resource newly registered in the database. A user can further readily attach a tag compared to a conventional system.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=09069867&OS=09069867&RS=09069867
owner: Sony Corporation
number: 09069867
owner_city: Tokyo
owner_country: JP
publication_date: 20070328
---
The present application claims priority to Japanese Patent Application JP 2006 095051 filed in the Japanese Patent Office on Mar. 30 2006 the entire contents of which is being incorporated herein by reference.

The present invention relates to a resource management system a method for selecting a candidate tag and a candidate tag selecting program and is applicable to the case of managing many resources by using a tag.

Hereinafter on the Internet a system in which many users attach a tag to a common resource a picture and a web bookmark for arrangement has been generally used.

For example in the Flickr that is a picture sharing service for sharing a picture on the network see http www.flickr.com an arbitrary tag such as TOKYO FOOD or PARTY is attached to associated with a picture uploaded on a database so that only a resource having a specified tag can be retrieved and extracted. Further because resources are unnecessary to be classified in a specified hierarchical structure a plurality of different images can be attached to one resource as tags so that resources can be arranged further flexibly.

This tag attachment may be individually performed. However in the case where many users share the same resource it works further effectively. For example in the del.icio.us that is a social bookmark service for sharing an web bookmark on the network see http del.icio.us a user can attach an arbitrary tag such as PROGRAMMING GUIDE SERVICE or SHOPPING to a bookmarked web page for arrangement.

Further this del.icio.us has a candidate tag present function in that if the same web page has been already bookmarked by other user a tag attached by the above other user is presented as a candidate tag. Thereby if a desired tag has been already attached by other user it is unnecessary to enter the character string and the user can readily perform tag attachment by selecting the presented candidate tag with a mouse or the like.

However in the aforementioned candidate tag present function when in newly performing a bookmark registration of an web page that has not been bookmarked by other user because existent tag information cannot be used the user have to enter a tag explicitly. Therefore there has been a tendency that as to a famous web page of which the degree of sharing is high such that many tags have been already attached plentiful tags will be attached and it can be readily retrieved however as to an web page newly bookmarked because a tag attachment operation is complicated tag attachment is not performed so actively.

As the above in a conventional social bookmark service there has been a problem that a tag attachment operation to a new bookmark is complicated.

In view of the foregoing it is desirable to provide a resource management system a method for selecting a candidate tag and a candidate tag selecting program in that a tag can be readily attached to a resource newly registered.

According to an embodiment there is provided degree of similarity calculating means for calculating the degree of similarity of a new registration resource newly registered in a database to each of a plurality of already registered resources that have been already registered in the database and candidate tag selecting means for selecting a tag attached to an already registered resource of which the degree of similarity calculated by the degree of similarity calculating means is large as a candidate for a tag to be attached to the new registration resource.

By selecting a tag attached to a resource of which the degree of similarity is high as a candidate tag a candidate tag can be also presented to a resource newly registered in a database. Thereby a user can further readily attach a tag compared to a conventional system.

The nature principle and utility of the present invention will become more apparent from the following detailed description when read in conjunction with the accompanying drawings in which like parts are designated by like reference numerals or characters.

Additional features and advantages are described herein and will be apparent from the following Detailed Description and the figures.

Referring to the reference numeral designates a bookmark sharing system as a whole. The bookmark sharing system is formed by that a plurality of user terminals are connected to a bookmark server via the Internet .

Each user terminal is an information processing unit having an Internet connection function such as a personal computer a personal digital assistant PDA and a cellular phone. Each of them accesses an web server on the Internet not shown according to a user operation obtains web page data and displays an web page based on the above obtained web page data to make a user view it.

In addition to this in the bookmark sharing system by that the user of the user terminal registers a user account on the bookmark server a bookmark list peculiar to the above user account can be formed in the bookmark server . The registration user of the bookmark sharing system hereinafter it is also simply referred to as user can register the bookmark of an arbitrary web page in the user s own bookmark list hereinafter it is also simply referred to as bookmark an web page .

Additionally in the bookmark sharing system when in registering a bookmark in the bookmark list the user can attach an arbitrary tag to the above bookmark. Further the user also can retrieve a bookmark registered by other user by using an arbitrary tag as a keyword.

That is in the bookmark server the lists of their respective bookmarks of each user have been stored in a bookmark database in a hard disk drive . If receiving a bookmark registration request from the user terminal the Central Processing Unit CPU of the bookmark server enters this in the bookmark list of the registration user by associating an web page with a tag that are specified in the above bookmark registration request.

Further if receiving a bookmark retrieval request from the user terminal the CPU of the bookmark server performs retrieval from the bookmark database by using the tag specified by the above registration request as a keyword extracts a bookmark to which the same tag as the specified tag has been attached as the retrieval result and returns this to the user terminal .

In this manner in the bookmark sharing system users can register their own bookmark lists in the bookmark server respectively. At the same time many bookmarks registered by each user can be shared among all of the registration users and a desired bookmark can be retrieved using a tag from among the above many bookmarks.

In addition to the above configuration at the time when a user newly registers an arbitrary web page in a bookmark list if this new registration page has been already registered by other user the bookmark server presents a tag attached to the already registered page by the other user or the like as a candidate tag.

That is if accepting a predetermined bookmark registration operation by the user via input means such as a keyboard the user terminal transmits the Uniform Resource Locator URL of the new registration page that was specified by the user as an object of a bookmark in this operation to the bookmark server with a bookmark registration temporary request.

If receiving the bookmark registration temporary request transmitted from the user terminal by responding this the CPU of the bookmark server returns display data for displaying a bookmark registration screen shown in to the user terminal . Thereby the bookmark registration screen is displayed in the above user terminal .

As shown in in the bookmark registration screen a URL display field to display the URL of the new registration page specified as the bookmark object in the bookmark registration temporary request hereinafter it is referred to as new registration URL a page name display field to display the name of the new registration page a tag display field to display a tag to be attached to the new registration page and a bookmark registration button to register the new registration page in the user s bookmark list are displayed.

In the URL display field the page name display field and the tag display field an arbitrary character can be entered by the user via input means such as a keyboard provided in the user terminal . For example in the page name display field a page name attached to the new registration page is automatically displayed. However the above page name can be freely changed by the user. Similarly the URL displayed in the URL display field can also be freely changed by the user. Thereby a lower order page a higher order page or the like in the web page can be arbitrary specified and set as a new registration URL. Further in the tag display field one or a plurality of character strings to be attached to a bookmark can be arbitrary entered by the user as a tag.

Further at a part lower than the tag display field in the bookmark registration screen one or a plurality of candidate tags recommended by the bookmark server for the new registration URL specified in the bookmark registration temporary request are displayed. This candidate tag is that the bookmark server selected a tag related to the new registration URL by candidate tag selecting processing that will be described later. Then the user can select an arbitrary one of the displayed candidate tags to make it display in the tag display field .

That is if accepting a candidate tag selecting operation by the user via the input means such as a keyboard by responding to this the user terminal copies the character string of the selected candidate tag and displays it in the tag display field . In this manner in the bookmark sharing system the bookmark server presents candidate tags related to a new registration URL. Thereby the user can readily perform tag attachment.

Then if accepting a pressing operation of the bookmark registration button by the user via the input means by responding to this the user terminal transmits the new registration URL and the page name and an attached tag to the bookmark server with a bookmark registration request.

If receiving the bookmark registration request transmitted from the user terminal by responding to this the CPU of the bookmark server associates the page name and the tag with the new registration URL received at the same time and registers this in this user s bookmark list as an already registered URL.

Further at this time the CPU of the bookmark server accesses an web page specified by the new registration URL obtains a document described in the above web page as already registered text data and registers this in the bookmark list in association with the already registered URL.

Next the aforementioned candidate tag selecting processing for a new registration URL by the bookmark server will be described in detail.

If receiving a bookmark registration temporary request from the user terminal the CPU of the bookmark server retrieves the same URL as the new registration URL that was received with the above bookmark registration temporary request from the bookmark lists of all of users on the bookmark database.

If the same URL as the new registration URL has been registered in some bookmark lists as an already registered URL the CPU obtains a tag attached to the above already registered URL from the bookmark database and transmits this to the user terminal as a candidate tag with display data for displaying the bookmark registration screen .

On the contrary if the same URL as the new registration URL has not been registered in any bookmark lists that is if this URL will be registered in the bookmark database for the first time the CPU cannot select a candidate tag in this state. Therefore the CPU of the bookmark server accesses a new registration page specified by the above new registration URL and obtains a character string described in the above new registration page as new registration text data.

Then the CPU compares the obtained new registration text data with all of already registered text data stored in the bookmark database and calculates the degree of similarity respectively the calculating method will be described later selects a predetermined number of for example ten already registered text data of which the degree of similarity to the above new registration text data is high and transmits a tag attached to the already registered URL corresponding to the above selected already registered text data of which the degree of similarity is high to the user terminal as a candidate tag with display data for displaying the bookmark registration screen . Then the user terminal displays the candidate tag received from the bookmark server in the bookmark registration screen to present this to the user.

In this manner the CPU of the bookmark server retrieves an already registered page having the contents similar to a new registration page and selects a tag attached to this as a candidate tag. Thereby a candidate tag can be also presented to a bookmark registered in the bookmark database for the first time.

Next the aforementioned method for calculating the degree of similarity between new registration text data and already registered text data and a method for selecting a candidate tag will be described.

As a method for calculating the degree of similarity between text data a method for obtaining the number of co occurrence of words a method using Latent Semantics Analysis LSA and the like have been generally used. These various methods for calculating the degree of similarity can be used in the present invention.

Further as a method for selecting a candidate tag if the degree of similarity between new registration text data and already registered text data Sim Newpage Webi was calculated as being within 1 to 1 a tag attached to the already registered page is added by the following formula Tagj Sim NewPage Webi hasTag Webi Tagj 1 

Here the W Tag is an weighting factor to determine whether or not Tag should be set as a candidate. Further if the tag Tagj has been attached to a certain web page Webi the tag factor hasTag Webi Tagj becomes 1 and if the tag Tagj has not been attached it becomes 0.

In this manner the weighting factor W Tag can be calculated about the respective tags attached to all of the already registered pages. Thereby an adequate number of for example ten tags of which the above weighting factor W Tag is large are selected and are transmitted to the user terminal as candidate tags.

Next the procedure of the aforementioned processing that the bookmark server selects a candidate tag for a new registration page and transmits this to the user terminal will be described in detail with reference to a flowchart shown in .

The CPU of the bookmark server enters a candidate tag selecting processing procedure RT from the start step and proceeds to step SP. If receiving a new registration URL from the user terminal with a bookmark registration temporary request the CPU proceeds to the next step SP.

In step SP the CPU retrieves the same URL as the above new registration URL from already registered URL in the bookmark database by using the received new registration URL as a retrieval keyword and proceeds to the next step SP.

In step SP the CPU determines whether the same already registered URL as the new registration URL has been registered in the bookmark database based on the retrieval result.

If an affirmative result is obtained in step SP this means that an web page that is going to be performed bookmark registration has already been registered in the bookmark database by other user. At this time the CPU proceeds to step SP to select a tag attached to the same already registered URL as the new registration URL as a candidate tag and proceeds to step SP.

On the contrary if a negative result is obtained in this step SP this means that the above web page will be registered in the bookmark database for the first time. At this time the CPU proceeds to step SP.

In step SP the CPU serving as degree of similarity calculating means accesses a new registration page specified by the new registration URL obtains a character string described in the above page as new registration text data and compares the above new registration text data with all of the already registered text data stored in the bookmark database and calculates the degree of similarity respectively. Then the CPU proceeds to the next step SP.

In step SP the CPU serving as candidate tag selection means calculates the respective weighting factors W Tag of tags attached to each already registered page based on the calculated degree of similarity and selects a tag of which the above weighting factor W Tag is large as a candidate tag. Then the CPU proceeds to the next step SP.

And then in step SP the CPU transmits the selected candidate tag to the user terminal and proceeds to the next step SP to finish the candidate tag selecting processing procedure.

According to the above configuration if a new registration page accepted from the user terminal has been already bookmarked by other user the bookmark server in the bookmark sharing system selects a tag that has been attached to this page by that other user as a candidate tag and transmits this to the user terminal . Thereby a tag attachment operation to the above new registration page can be readily performed.

Further even if the new registration page accepted from the user terminal has not been bookmarked by other user the bookmark server selects a tag that has been attached to a page having the similar contents to the new registration page in all of the web pages that have been performed bookmark registration in the bookmark database as a candidate tag and transmits this to the user terminal . Thereby a tag attachment operation can be also readily performed to an web page that will be completely newly performed bookmark registration in the bookmark database.

In the aforementioned embodiment it has dealt with the case where a tag factor is calculated based on the presence of tag attachment by setting a tag factor hasTag Webi Tagj 1 when a tag Tagj has been attached to a certain web page Webi and by setting a tag factor hasTag Webi Tagj 0 when a tag Tagj has not been attached. However the present invention is not only limited to this but also the tag factor may be calculated by considering the number of users who attached a tag. For example it can be considered that when n pieces of tag Tagj have been attached to a certain web page Webi a tag factor HasTag Webi Tagj n is set.

That is in a social tagging system as the bookmark sharing system of an embodiment of the present invention there is often a case where a plurality of users attach the same tag to a certain web page. For example in to a certain web page WebA a tag WINE has been attached by three users a tag BAR has been attached by two users and a tag RESTAURANT has been attached by one user. A tag factor in this case is hasTag WebA WINE 3 hasTag WebA BAR 2 and hasTag WebA RESTAURANT 1.

In this manner if calculating a weighting factor W Tag using a tag factor in consideration of the attached number of tags a candidate tag which reflects tag attachment state and is highly accurate can be selected.

Further in the aforementioned embodiment it has dealt with the case where the present invention is applied to tag attachment to an web page in the bookmark sharing system . However the present invention is not only limited to this but also it can be widely applied to the case of attaching a tag to various resources of which the degree of similarity can be calculated.

As such resources to which the present invention is applicable audio data and image data and the like can be considered. Then as a method for calculating the degree of similarity for audio data a similarity of power spectrum in musical compositions J. J. Aucouturier and F. Pachet Music similarity measures What s the use Proc. ISMIR 2002 pp. 157 63 2002 a similarity of rhythm J. Paulus and A. Klapuri Measuring the similarity of rhythmic patterns. Proc. ISMIR 2002 pp. 150 156 2002 the feature amount of a modulation spectrum Dixon E. Pampalk and G. Widmer Classification of dance music by periodicity patterns. Proc. ISMIR 2003 pp. 159 65 2003 or the like can be used. On the other hand as a method for calculating the degree of similarity for image data a method based on fractal images Takanori Yokoyama Toshinori Watanabe and Ken Sugawara Feature Amount Based on Correspondence of Fractal Coded Images and Similarity Retrieval the technical report by the Institute of Image Information and Television Engineers Vol. 26 No. 54 pp. 29 32 2002 or the like can be used.

Further in the aforementioned embodiment it has dealt with the case where the present invention is applied to a system in that a plurality of users attach a tag to a resource to manage information as a social tagging system. However the present invention is not only limited to this but also can be applied to an individual information management system in that one user manages information.

As an example of such individual information management system a text management system in that a tag is attached to a text memo and is managed on a computer can be considered for example. That is as shown in in the text management system an arbitrary tag is attached to a text memo entered by a user and the text memo can be retrieved using the above tag. Then if a new text memo is entered by the user the CPU of a computer executing the text management system calculates the degree of similarity between the above new text memo and existent text memos already entered and presents a tag that has been attached to a text memo of which the degree of similarity is high as a candidate tag for the new text memo. Thereby in this text management system the user can perform tag attachment to a text memo with a simple operation.

According to an embodiment there is provided degree of similarity calculating means for calculating the degree of similarity of a new registration resource newly registered in a database to each of a plurality of already registered resources that have been already registered in the database and candidate tag selecting means for selecting a tag attached to an already registered resource of which the degree of similarity calculated by the degree of similarity calculating means is large as a candidate for a tag to be attached to the new registration resource. Thereby a resource management system a method for selecting a candidate tag and a non transitory computer readable medium in that a candidate tag can be also presented to a resource newly registered in a database and a user can further readily attach a tag compared to a conventional system can be realized.

It should be understood that various changes and modifications to the presently preferred embodiments described herein will be apparent to those skilled in the art. Such changes and modifications can be made without departing from the spirit and scope of the present subject matter and without diminishing its intended advantages. It is therefore intended that such changes and modifications be covered by the appended claims.

