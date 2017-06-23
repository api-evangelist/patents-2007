---

title: Process and system for automated collection of business information from a business entity's accounting system
abstract: There is provided a method, performed by a processor. The method includes obtaining accounting data from a first database, and sending the accounting data to a second database, wherein the second database is located remotely from the first database.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08799116&OS=08799116&RS=08799116
owner: The Dun & Bradstreet Corporation
number: 08799116
owner_city: Short Hills
owner_country: US
publication_date: 20070928
---
An automated embedded data collection system enables a collection of business information e.g. identity and trade data directly through a small business accounting software applications. More specifically business information is collected by leveraging software applications and processes to push trade and business identity data and or financial credit data directly from the small business accounting programs to a credit company s data storage facility. This manner of collecting business information enhances quality of collected data and increase accuracy and depth of responses to customer credit inquiries.

Business information companies and directory providers do not currently use software applications to collect financial trade and credit data from small to medium businesses. However there is tremendous value in such data as access to such data would allow collection and or credit agencies to understand credit worthiness of many small to medium businesses with which the agencies transact business.

Business performance information which includes but is not limited to accounts receivable or trade information has become extremely important in today s business marketplace both in making credit decisions and in establishing reciprocal trade relationships between companies. Banks CPA firms corporations credit companies insurers and other underwriters have a need to monitor business performance information of their customers in order to minimize risk and avoid financial surprises. Moreover the stability of manufacturing and service providing companies is often dependent on one or more key component s or services suppliers. Financial or operating problems at these suppliers could cause a chain reaction that adversely affects their business partners. As a result manufacturing and service companies also have a need to review business performance information of suppliers and other partner businesses upon which they are dependent in order to insure that their future business operations remain stable.

Financial information on publicly traded companies is easily obtainable due to standardization of financial record keeping in accordance with generally accepted accounting principles GAAP and quarterly filing and disclosure requirements imposed by the U.S. Securities and Exchange Commission SEC . However for partnerships and other private business ventures obtaining accurate and standardized financial information e.g. accounts receivable or trade information is much more difficult. Private businesses typically maintain their own financial records on site or through assistance of an outside accountant using one of a number of commercial off the shelf COTS financial accounting software programs. Such software programs for example QuickBooks are ubiquitously well known in the accounting profession. QuickBooks is a registered trademark of Intuit Inc. or one of its subsidiaries. All of these programs in one form or another maintain financial records including balance sheets income statements individual account statements and other well known financial records.

As a result of the decentralized and unreported nature of small or private business financial information it is often difficult for interested parties to obtain standardized financial information on businesses with which they are or may be interested in doing business. It may also be difficult to perform relevant comparisons between similarly situated businesses. Typically companies in such a position will utilize a financial data gathering firm such as Dun Bradstreet to generate a report summarizing any known financial information about the business of interest. Such a report has come to be known in the profession as a D B. A problem with this type of financial reporting is that information about a company obtained by these financial information gathering firms is largely obtained through solicitation from the company itself. Once this self reported information gets into the information gathering firm s possession the submitting company no longer has control over its distribution. As a result companies are generally reluctant to provide full disclosure and may even be incentivized to mislead companies seeking to gather information on them. Also because financial data gathering firms must rely on the willingness of businesses to disclose information to them it is unlikely that uniform information will be available for all reporting companies. As a result a consumer of such information will have difficulty in making a balanced comparison between two or more similarly situated businesses based on financial metrics. Another problem with conventional financial data gathering firms is that the data collection method may be disjointed consisting of various sources that must be manually assimilated into a format that is valuable to consumers of such information. This is a labor intensive process which increases the ultimate cost for such information and likely reduces its accuracy.

Accordingly there is a need for an improved system for sharing financial information of businesses with interested parties which ameliorates or overcomes the deficiencies of known systems.

One such system for selective sharing of business performance information is disclosed in U.S. Patent Publication No. 2005 0240467 which discloses an automated system for allowing a submitter business to selectively share business performance information with requester businesses through a business performance information sharing data center computer system over the Internet. A submitter business uploads a data file including business performance information such as a trial balance report generated by the business own accounting software program. The uploaded file is converted from the submitter defined format to a standardized format. Various business performance data analyses are performed on the standardized format data including generating standardized business performance reports and analyzing the data in accordance with financial metrics. After the business performance data have been formatted and analyzed the submitter will specify one or more companies authorized to view the business performance data including specifying a level of business performance detail from a plurality of levels of detail and or a business performance time period for which that authorized company may view business performance information.

Although some companies collect trade and identity information via manual processes there is however a need for an automatic system that collects trade and identity information.

There is provided a method performed by a processor. The method includes obtaining accounting data from a first database and sending the accounting data to a second database wherein the second database is located remotely from the first database.

A system and method as described herein employed for collecting and retrieving financial transaction data from small to medium businesses directly from their financial accounting software overcomes a substantial credit information deficiency that now exists in the credit industry and allows for creditors and business partners to obtain more credit and business reports on small to medium companies. The preferred embodiment differs from the aforementioned conventional systems in that it is embedded directly into a customer s existing software application as opposed to just providing a hosted site to which to upload data and provides a trio of software process and end user incentives for the purpose of gathering identity and trade information from business software applications.

Embedded data collection enables the automated collection of business information including trade and identity information directly through business software applications by leveraging business software applications and processes to push and pull data from a customer s software applications to a credit company. For example at a determined frequency a plug in to the business software application will trigger an extraction pull from the appropriate data sources and aggregate organize and encrypt this data then the plug in will send push this data to the credit company.

Database is maintained by a first business entity e.g. a business that produced accounting data and database is maintained by a second business entity e.g. a credit company that evaluates accounting data to prepare a report for a creditor of the first business entity. Alternatively database may be maintained by an accounting firm that manages the books of several businesses where accounting data pertains to operations of the several businesses.

Although computer is represented in as a standalone computer computer may be configured with a plurality of devices e.g. processors memories servers coupled to one another via a network. Many implementations of database are possible. Some such implementations are a flat file a relational database management system RDBMS or a collection of spreadsheets.

In step a plug in that interfaces with accounting program is installed into computer . Plug in is a program module of instructions for controlling certain functions of computer . The functionality of plug in is described below.

In step computer obtains accounting data from database and prepares accounting data for transmission to database . More specifically computer pursuant to instructions contained in plug in invokes an application programming interface API of accounting program to locate access and extract accounting data from database and prepares to send accounting data to database . For example computer will locate the appropriate sources of data determined during the installation of plug in to identify qualifying records extract select those records and make additional extracts selects from other tables to make this data a complete record e.g. source name details current information relevant aged data . Plug in may therefore locate accounting data by using techniques such as for example parsing a text file or querying records in a RDBMS or extracting cells from a spreadsheet.

In step computer sends accounting data over a communication link automatically to database . A pull might be for example scheduled to occur a pre determined time or at a predetermined interval of time. Additionally a user of computer can initiate a transfer of accounting data from database to database .

In step database receives accounting data . Database may be managed for example by a credit company that creates or updates business records based upon accounting data .

Although plug in is represented a being installed into computer plug in may be embodied as a machine readable encoded program i.e. a plug in A and stored on a storage medium for subsequent installation into computer . Examples of storage medium include but are not limited to an optical storage medium a magnetic storage medium a magneto optical storage medium a flash memory medium and a ROM chip.

Screen shot is a view of a user s financial accounting software after plug in has been installed on computer and successfully loaded.

Screenshot demonstrates the pushing or pulling of accounting data e.g trade data from accounting program e.g. a user s accounting program to database e.g. a database of a credit company on a monthly schedule.

Screenshot demonstrates a capturing and storing of trade data accounts receivable data and or financial data on a hosted website.

Screenshot demonstrates an updating of database maintained by or for a credit company with detailed trade data accounts receivable data and or financial data sent to the credit company pursuant to instructions in plug in .

In step a user e.g. a customer downloads and installs plug in onto computer . The download may be accomplished via a communications link. In this regard the customer may visit an Internet website of a credit company that invites the customer to download plug in . The invitation may be presented in the form of an incentive such as an enrollment offer or an advertisement. Additionally the customer registers plug in .

In step an initial transfer of data between the customer and the credit company takes place. The customer uses accounting program as would be done in the ordinary course of business. In step financial data accumulate as usual but the data are also prepared for transmission to database .

In step a periodic transfer of data between computer and database takes place. Computer extracts in the background and without a requirement for user interaction accounting data from database and sends accounting data to database over a communication link. The time at which and the conditions under which the extraction and upload are performed are governable by user configurable triggers. Plug in is also user upgradable.

After step is completed operation returns to step . Operation remains at step until a proper entry point into step is again reached.

In step process registers a user on an enrolment site. If the user requires registration help then process progresses to step . If the user does not require registration help then process progresses to step .

In step the user can seek help from an enrolment help desk. After completion of step process returns to step .

In step process determines if registration is complete. If registration is not complete then process returns to step . If registration is complete then process advances to step .

In step the user is prompted for permission to send accounting data to the credit company. If permission is granted then process progresses to step . If permission is not granted then process progresses to step .

In step data is transferred by push or pull to the credit company. From step process progresses to step .

In step the credit company receives into temporary storage the data pushed or pulled in step . From step process progresses to step .

In step the credit company determines if the user is an approved provider. If the user is not an approved provider then process progresses to step . If the user is an approved provider then process progresses to step .

In step the user goes through a data provider approval process. From step process progresses to step .

In step the data processed in step are stored in a database e.g. database . From step process progresses to step .

In step the data stored by step are retrieved for use in preparation of information products for customers of the credit company.

While we have shown and described several embodiments in accordance with my invention it is to be clearly understood that the same may be susceptible to numerous changes apparent to one skilled in the art. Therefore we do not wish to be limited to the details shown and described but intend to show all changes and modifications that come within the scope of the appended claims.

