---

title: System and method for collecting user interest data
abstract: A method for collecting user data includes: collecting content of a user action event; modifying a user interest data model which stores user interest data according to the content of the user action event collected. In this way, the interest and concerns of the user are effectively tracked. Furthermore, the method and system provided by embodiments of the invention features little disturbance to user and accurate collection of user information, thus effectively shows the interest of user. Through method and system provided by embodiments of the invention, the user data can be collected effectively and the interest of the user is well represented.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07801891&OS=07801891&RS=07801891
owner: Huawei Technologies Co., Ltd.
number: 07801891
owner_city: Shenzhen
owner_country: CN
publication_date: 20070312
---
The priority benefit of Chinese Patent Application No. 2006100801023.5 filed May 19 2006 the entire disclosure of which is hereby incorporated herein by reference is claimed.

The invention relates to intelligent application services and particularly to a system and a method for collecting user data.

Information industry is in a time of great changes and rapid development the whole industry will inevitably go through stages of access oriented service oriented and user oriented. Telecommunication operators and Internet companies are competing intensely to absorb users varieties of wireless value added services and Internet value added services are occupying more and more proportions in the profits of these companies and attach crucial strategic importance to the categorization of users. Scientific categorization may provide definite objects for companies in marketing and provide customized products and services for the users therefore operators may raise service level while improving users experience.

It is important to collect user data build user data models and finds out potential demands of the user in order to raise service level. User data are the key to the habit and interest of the user. Only the user data is obtained better services may be provided to the user.

In order to acquire the interest of the user a network browser usually obtains the user data through the following four ways 

1. Make a statistic of the Uniform Resource Locator URL addresses of the websites that the user has visited 

All of the foregoing methods for acquiring user interest require participation of the user which greatly annoys the user moreover the user interest collected may be incomplete inaccurate and incapable of tracking the shift of interest and concerns of the user.

modifying a user interest data model which stores user interest data according to the content of the user action event collected.

an information collection agent configured to collect content of a user action event and send the information collected to an information filter and management module 

the information filter and management module configured to receive content of the user action event from the information collection agent maintain and manage the user interest data model in the user database according to the content received and send a modification request to a modification module 

the modification module configured to receive a modification request from the information filter and management module modify the user interest data model according to the modification request.

It can be seen from the above technical scheme that in embodiments of the invention a user interest data model is built and an information collection agent collects information of a user action event when the user uses a browser or a document processor. Thus the information concerned by the user is collected through the information collected and the user interest data model may be modified continuously using the collected information concerned by the user. In this way the interests and concerns of the user are effectively tracked. The invention features little disturbance to the user and accurate user information collected and thus effectively shows the interest of the user.

The embodiments of the invention build a user interest data model to store user interest data collect content of a user action event when the user opens a browser or a document processor and modify the user interest data model according to the content of the user action event collected.

The invention is hereinafter described in details with reference to the accompanying drawings and preferred embodiments to make the technical solution and merits thereof more apparent.

The browser document processor is configured to execute a user action event when the user requires to browse or process a document and to trigger the information collection agent to collect content of the user action event. The browser document processor is a major tool for the user to browse and process documents. The browser document processor receives an instruction from the user executes the instruction and sends action executed to the information collection agent via an event message. The browser document processor may be different software components such as Internet Explorer IE Netscape Firefox Word Adobe Reader etc.

The information collection agent is configured to collect content of the user action event. The information collection agent receives the event message from the browser document processor collects content of the user action event according to the event message received converts the format of the content of the user action event and analyzes the content of the user action event according to pre configured event criteria collect temporary data information concerned by the user e.g. generates a temporary etyma table or a text file etc. stores the temporary data information in an information collection cache and sends the temporary data information to the information filter and management module.

The information filter and management module is configured to receive the temporary data information from the information collection agent generate a system etyma table and store the system etyma table into the user database maintain and manage e.g. create modify and delete the user interest data model based on the system etyma table in the user database and send a modification request to the modification module.

The user database is a core database of the whole system configured to store the user interest data model and the system etyma table.

The modification module is configured to receive the modification request from the information filter and management module modify the user interest data model according to the system etyma table in the user database and return a modification response to the information filter and management module and update the user database according to the user interest data model modified.

The user interest data model which is modified continuously along with the actions of the user may track and reflect the interest and concerns of the user. An external system may obtain the interest of the user from the user database to provide better services for the user.

In addition the system for collecting user interest data may be constructed in a distributive architecture. In such case the system further includes a data communication module which is configured to communicate between the information collection agent and the information filter and management module. Mechanism and principle of the data communication module are based or existing distributive architecture technologies e.g. Common Object Request Broker Architecture CORBA Web Services etc. and will not be described herein.

In order to track the interest and concerns of the user the information collection agent in the embodiment of the invention is triggered according to the action of the user e.g. browsing or processing a document to collect the content of the user action event and store the content of the user action event collected into the user interest data model built in advance and continuously modifies the user interest data model according to the content collected. In this way the interest and concerns of the user are tracked effectively. The user interest data model may be built in the user database. The user interest data model includes many interest keywords which represent the interests of the user. Each keyword corresponds to a weight which shows the user s concern for the keyword. The collection of content of the user action event is usually triggered by a user action e.g. clicking a hyperlink attaching a bookmark copying and pasting contents scrolling a scroll bar etc.

After the collection of the user action event the information collection agent converts the format of the content collected. As different browser document processors supports different data formats the information collection agent converts the format of the content collected into an intermediate format supported by the information collection agent e.g. an extensible Markup Language XML format for centralized management. The information collection agent may also collect for the centralized management the content of the user action event by an Application Program Interface API hook function according to the user action and modify the format of the content collected by the API hook function to a text character format thus the information collection agent need not convert the format of the collected content any more. Then the information collection agent analyzes the syntax and grammar of the content collected and generates a temporary etyma table the information collection agent filters the temporary etyma table according to an etyma frequency statistic algorithm and generates a system etyma table. The etyma frequency statistic algorithm is real time and may reflect the current interest of the user at current time and shift of the interest of the user. The etyma frequency statistic algorithm will be described in detail hereinafter. Finally the user interest data model is modified according to the system etyma table generated by the information collection agent and the modification mainly includes inserting keywords deleting existing keywords and modifying weights of the keywords in the user interest data model.

The structures and interaction principles of the browser document processor and the information collection agent are described in details hereinafter.

Most of the current browser document processors are designed based on a Model View Control MVC pattern in which a browser document processor may be divided into a data module a display module and a control module. The data module is configured to execute application objects e.g. data contents including documents and graphics. The display module displays the application objects under control of the control module. The control module controls all the modules in the browser document processor to collaborate including responding to a user action event controlling response modes of the data module and the display module etc.

The plug in component interface is a data interaction interface communicated between the information collection agent and the browser document processor e.g. a Component Object Model COM interface which involves a software component technology put forward by Microsoft based on Windows applications.

A user action event processing module configured to receive an event message from the control module in the browser document processor and return a response to the control module filter the event message received and send the event message to be processed to an agent controller through an event notification 

The agent controller configured to receive the event notification from the user action event processing module and return a event notification response to the user action event processing module send an action content import request to a content collection module requesting to import the content of the user action event 

The content collection module configured to receive the action content import request from the agent controller send an OnRequest message to the data module in the browser document processor to obtain the content of the user action event send the content obtained to a format conversion module or an analyzing module and return an action content import response to the agent controller 

The format conversion module configured to receive the content of a user action event from the content collection module convert the format of the content into a pre defined intermediate format and send the content converted to the analyzing module. It should be noted that if the content of the user action event sent by the content collection module is in a text character format the format conversion module is not required and the content sent by the content collection module is directly sent to the analyzing module.

The analyzing module configured to analyze the syntax and grammar of the content received according to a pre defined analysis method collect temporary data information concerned by the user e.g. generate a temporary etyma table or a text file etc. and store the temporary data information into the information collection cache.

The foregoing are the structures and interaction principles of the browser document processor and the information collection agent. Provided that the operation system adopted in the embodiments of the invention is the Windows operation system presented by Microsoft the user action event processing module in the information collection agent listens to through the plug in component interface the event message in the control module of the browser document processor. Once the user triggers a pre configured event in the control module the user action event processing module informs through the agent controller the content collection module to obtain content of the user action event. is a flowchart illustrating the collection of the content of a user action event according to an embodiment of the invention. The process of collecting user interest data is hereinafter described with reference to .

Suppose the application object is a document action e.g. reading a document with the browser document processor including Open Cut Copy Paste Forward Back etc. The control module executes the document action and returns an execution result to the user.

Steps the control module sends an event message through a SendMessage function to the user action event processing module and the user action event processing module returns a response to the control module upon the receipt of the event message.

Long SendMessage Long ProcessID Long Msg Long Event Hwnd ConObj String Param where Long stands for a long integer data type and String stands for a character data type.

As shown in Table 1 the browser document processing module and the information collection agent are generally two independent processes. The parameters in the SendMessage include the ProcessID of the process that receives the event message Msg is used for identifying the type of the event message Event is the identifier of the user action event customized by the browser document processor and the information collection agent ConObj is the application object handle i.e. the address of the document object in the memory and Param represents some extended parameters such as Content offset browsing elapsed time etc.

The filter criteria are determined in accordance with pre set events in the user action event processing module. It may be set through a customized User Interface UI that which event needs to be responded and whose content needs to be collected. The filter criteria may be set according to practical applications or be default events pre set by the system.

In Table 2 the parameter Event is of a predefined message type which is similar to the message in the Windows operation system and is a common technique adopted by those skilled in the art and will not be explained herein. It should be noted that the filter criteria i.e. the events are set in the user action event processing module in advance to filter the event message received if the event message received carries a pre set event proceed to the next step otherwise discard the event message.

Steps the user action event processing module sends the event message to be processed to the agent controller through an event notification and the agent controller returns an event notification response to the user event process module.

Steps the agent controller sends an action content import request to the content collection module and the content collection module returns an action content import response to the agent controller.

The agent controller obtains the handle of the application object and sends the handle and the process identifier of the application object to the content collection module the content collection module sends according to the handle and the process identifier received an OnRequest message to the data module in the browser document processor to obtain the content of the user action event The OnRequest message includes 

1 collect the full content of the document object. The content collection module may obtain the document object directly and the format conversion module may convert the format of the document object into a standard intermediate format such as the XML format 

2 collect the content of a specific user action e.g. the content selected by a mouse during a click or copy action or during a mouse hovering time. In such case the API hook function may be adopted. The process of collecting the content of the user action event by the hook function is described hereinafter taking the mouse hovering time as an example 

All characters in the Windows system are outputted through two API functions i.e. TextOut and ExtTextOut . The two API functions are actions called by a Windows Graphic Device Interface GDI and are responsible for outputting characters in a Windows interface. In order to obtain all the characters outputted in the Window interface a JMP instruction is added into the TextOut function. The installation of the API hook function described in the above step 3 is actually a process of adding a JMP instruction in the Windows API function to jump to an appointed address so that the characters outputted may be obtained.

The collection of the content of a Copy action is described hereafter with reference to an embodiment of the invention in which the Windows system is adopted.

First configure filter criteria through the API function. Provided that the value of the Copy action event is 10001011 set a Copy action event in the user action event processing module through calling the SetEvent UE COPY function in existing API functions where the UE COPY is the macro definition of 1000011.

When browsing a document the user puts what he concerns into the clipboard through a Copy Ctrl C action the browser document processor responds to the Copy action and calls the function SendMessage 1964 WM OPER UE COPY con hdc NULL to send via the plug in component interface an event message to user action event processing module in the information collection agent. The WM OPER is the macro definition of operation system message definition and the con hdc is a pointer pointing to the content copied.

Since the Copy action event has been set in the user action processing module the user action event processing module filters the event carried in the event message and sends an event notification to the agent controller. Upon the receipt of the event notification the agent controller requests the content collection module to collect the content of Copy action. Then the content collection module calls the API functions to obtain the content of Copy action. The process of obtaining the content of the Copy action i.e. the content in the clipboard using the Windows API functions is an existing Window application programming technique and will not be explained herein.

After the collection of the content shown in the format conversion module converts the format of the content collected and performs a syntax and grammar analysis.

The process of format conversion i.e. the conversion of the format of the content collected into a pre defined intermediate format has already been explained in the fore going description and will not be repeated herein. Whichever method is adopted the system always gets the content in a text character format. The analyzing module performs a word segmentation for the content of the user action event generates a temporary etyma table stores the temporary etyma table into the information collection cache and generates a system etyma table based on the temporary etyma table.

Step perform an automatic word segmentation for the content obtained in the text character format generate temporary keywords and store the temporary keywords into a temporary etyma table.

The automatic word segmentation is an existing technique including binary segmentation algorithm word table segmentation algorithm etc. The details of the automatic word segmentation algorithms may be obtained from relevant references and will not be described herein. A frequently used automatic word segmentation algorithm is a binary segmentation algorithm which is applicable for Chinese and other Asian languages such as Korean and Japanese.

The keywords refer to the strings that frequently appear in the content obtained. For example set a frequency threshold in advance and a string is determined to be a keyword if the emergence frequency of the string is greater than the frequency threshold. A keyword has to be a notional word with a meaning such as football etc. While conjunctions prepositions and modals such as too also to etc. are not suitable to be keywords.

Step calculate the emergence frequency of each keyword in the temporary etyma table and store the keyword whose emergence frequency is greater than the preset frequency threshold into a system etyma table.

Step Calculate the variation rate of each keyword in the system etyma table and store the calculated result into the system etyma table.

The variation rate of keyword well reflects the shift of user s concern on the keyword. The decrease of the variation rate indicates that the user pays less attention to the keyword while the increase of the variation rate indicates that the user pays more attention to keyword. If the variation rate of a keyword is kept low or nearly zero for a long time it indicates that the user may no longer pay attention to the keyword. The variation rate of a keyword may be calculated through Equation 1 Variation rate of a keyword 

 1 Where Fi is the emergence frequency of the keyword i and the variation rate of the keyword i is the differential coefficient of the emergence frequency of the keyword i to time.

The variation rate in the system etyma table obtained through the Equation 1 is real time and reflects the variation of the etymons that the user is interested in.

The information filter and management module maintains and manages the system etyma table and modifies in cooperation with the modification module the user interest data model based on the system etyma table. is a flowchart of modifying the user interest data model according to an embodiment of the invention includes the following steps.

Step the information filter and management module sends a system etyma table update request to the user database.

The information filter and management module store the results calculated in steps and into the system etyma table to update the system etyma table.

Step the user database updates the system etyma table according to the system etyma table update request.

Step the user database returns a system etyma table update response to the information filter and management module indicating that the update has been completed.

Step the information filter and management module sends a user interest data model modification request to the modification module.

The user interest data model modification request carries the event identifier of the user action event and information of the updated etyma in the system etyma table.

The user interest data model may be modified upon the trigger of a pre determined event e.g. modify the user interest data at a pre determined time. In such case the system stores the identifier of the keyword imported into the system etyma table in each modification process.

The user interest data model may also be modified based on the collection of content of the user action event. In such case the information filter and management module needs to carry the event identifier of the user action event in the user interest data model modification request and send the user interest data model modification request to the modification module.

The basic storage structure of the user interest data model is shown in Table 6. As shown in Table 6 the Keyword Identifier Index field stores the identifier of the keyword imported into the system etyma table the modification identifier is used to distinguish different modification operations. The event identifier records the identifier of the user action event.

The modification of the user interest data model mainly includes inserting a keyword and or deleting an existing keyword and or modifying the weight of a keyword. The modification is described hereafter with reference to an embodiment in which the user interest data model is modified in real time based on the collection of content of a user action event.

When the user interest data model is modified based on the collection of content of the user action event besides the emergence frequency and variation rate of keyword the influences of user action event such as reading time bt inserting a bookmark bm scrolling a scrollbar sc and following a hyperlink fl etc. need to be considered. The calculation involved in the modification is shown in Equation 2 

where F is a set of user actions including reading time bt inserting a bookmark bm scrolling a scrollbar sc and following a hyperlink fl i.e. F fl bm sc fl cis the weight assigned to the user action event v and v is a mathematical symbol standing for a user action event. i stands for a keyword Ris the weight of the keyword i corresponding to the user action event v and is used in update of the user interest data model and f i is a two value function of the keyword i. When the user performs an action on keyword i the value of the f i is 1 otherwise the value of the f i is 0.

a modification weight Wmay be calculated out based on Rand the modification weight Wis used to update the user interest data model as shown in Equation 3 

Equation 3 is a function used for calculating the modification weight of the keyword i i.e. calculating the modification weight of the keyword i based on the emergence frequency the variation rate and weight obtained through Equation 2.

Table 7 shows a 2 dimensional table illustrating a storage structure of the user interest data model includes user identifier keyword and weight of the keyword. The weight of the keyword shows the continuous modification of the user interest data model and the extent that the user concerns on a keyword.

The user interest data model update request carries information of the user interest data model modified.

Step the user database updates the user interest data model according to the user interest data model update request.

Step the user database returns a user interest data model update response to the modification module.

Step the modification module returns a user interest data model modification response to the information filter and management module.

The embodiments of the invention effectively track the interest and concerns of the user through continuous modification of the user interest data model by the content of a user action event collected. Furthermore the embodiments of the invention feature little disturbance to users and accurate collection of user information and thus effectively shows the interest of the user.

The foregoing is only the preferred embodiments of the invention and is not for use in limiting the invention any modification equivalent replacement or improvement made under the spirit and principles of this invention is included in the protection scope of the invention.

