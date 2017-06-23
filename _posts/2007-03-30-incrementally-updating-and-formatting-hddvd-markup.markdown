---

title: Incrementally updating and formatting HD-DVD markup
abstract: Systems, methods, and/or techniques (“tools”) for incrementally updating and formatting high-definition digital versatile disk (HD-DVD) markup are described herein. The tools may receive first markup representing a first scene description to be read from a HD-DVD, and may map the first markup into a first area composite for presentation to a user. The tools may then receive second markup representing a second scene description to be read from the HD-DVD. In response to receiving the second markup, the tools may incrementally remap a portion of the first scene description into a second area composite for presentation to the user.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07814412&OS=07814412&RS=07814412
owner: Microsoft Corporation
number: 07814412
owner_city: Redmond
owner_country: US
publication_date: 20070330
---
This application claims the benefit of the filing date of U.S. Provisional Patent Application Ser. No. 60 883 763 filed on 5 Jan. 2007 to the fullest extent permitted by 35 U.S.C. 119. The contents of this provisional application are incorporated by this reference as if set forth verbatim herein.

High definition digital versatile disks HD DVD media and related players are becoming more popular and widely used. As more manufacturers enter this market competition increases tending to drive prices downwards. In this pricing environment software running within the HD DVD players typically runs on relatively inexpensive consumer hardware.

Transforming HD DVD content and style markup into tangible form for display is computationally expensive. Typically a reasonable goal for a rendering rate for HD DVD markup is approximately 24 frames per second for an acceptable user experience. Conventional techniques for transforming and rendering the HD DVD markup may face difficulties when attempting to reach this rendering rate goal due to performing the computationally expensive task of formatting all relevant HD DVD content and style markup on every clock pulse on low cost consumer hardware.

Systems methods and or techniques tools for incrementally updating and formatting high definition digital versatile disk HD DVD markup are described herein. The tools may receive first markup representing a first scene description to be read from a HD DVD and may map the first markup into a first area composite for presentation to a user. The tools may then receive second markup representing a second scene description to be read from the HD DVD. In response to receiving the second markup the tools may incrementally remap a portion of the first scene description into a second area composite for presentation to the user.

This Summary is provided to introduce a selection of concepts in a simplified form that are further described below in the Detailed Description. This Summary is not intended to identify key or essential features of the claimed subject matter nor is it intended to be used as an aid in determining the scope of the claimed subject matter. The term tools for instance may refer to system s method s computer readable instructions and or technique s as permitted by the context above and throughout the document.

The following document describes tools capable of performing and or supporting many techniques and processes. The following discussion describes exemplary ways in which the tools incrementally update and format high definition digital versatile disk HD DVD markup. This discussion also describes other techniques and or processes that the tools may perform.

For the purposes of formatting HD DVD content and style markup into tangible form as described herein the term state may refer to any of the states and or styles defined by the HD DVD spec and the term state transition refers to any change in value for any HD DVD state or style.

These HD DVD disks may include one or more machine readable components. These components may include for example a content mark up portion which may include an XML vocabulary that defines a structured tree of elements. These elements may specify visual or audio content that may be presented to the user when the HD DVD disks are played back.

The DVD disks may also include a style markup portion which may include an XML vocabulary that describes how the elements that are included in the content mark up portion are to appear when presented to the user. Put differently the content mark up portion may specify what elements are rendered to the user the style markup portion may specify how these elements are rendered to the user.

The DVD disks may also include a timing markup portion which may include an XML vocabulary that specifies one or more style markup changes over time.

The content mark up portion the style markup portion and the timing markup portion may be implemented in a declarative programming language. However a script portion may be implemented in an imperative programming vocabulary that causes non deterministic changes in the style markup over time.

The operative environments may enable the users to insert the HD DVD disks into an HD DVD player for playback as represented by the dashed line connecting the disk and the player . The HD DVD player may be a computer based system that includes one or more processors denoted at . These processors may also be categorized or characterized as having a given type or architecture but may or may not have the same type or architecture.

The HD DVD player may also include one or more instances of machine readable or computer readable storage media denoted generally at . The computer readable media may contain instructions that when executed by the processor perform any of the tools or related functions that are described herein as being performed by the HD DVD player. The processor may access and or execute the instructions embedded or encoded onto the computer readable media and or may access data stored in the computer readable media.

Turning in more detail to the computer readable media it may include one or more instances of a HD DVD transformation component . The HD DVD transformation component may include for example one or more software modules which when loaded into the processor and executed cause the HD DVD player to incrementally update and format HD DVD markup for rendering to the user.

The rendered output may include one or more textual elements denoted generally at . Examples of these text elements may include labels descriptions or other alphanumeric or character based information presented to the user in the rendered output .

The rendered output may include one or more instances of image and or video elements denoted generally at . These images or video elements may be included as part of user interface devices e.g. menu boxes or the like or may provide the main content included as an entertainment portion of the HD DVD disk e.g. a movie sporting event or the like .

The rendered output may include one or more instances of audio elements denoted generally at . These audio elements may be presented alone or in connection with other elements such as the image video elements .

The HD DVD player may cooperate with a presentation device to provide the rendered output to the user as represented by the dashed line . shows the dashed line as bi directional in nature to represent not only rendered output to the user but also any responses or input provided by the user.

The presentation device may include a display presentation device for providing the rendered output in visible form to the user. Examples of the display presentation device may include television sets monitors displays or the like implemented with any suitable display technology.

The presentation device may include an audio presentation device for providing the rendered output in audible form to the user. Examples of the audio presentation device may include speakers or similar devices for converting electrical signals to sound waves for reception by the human ear implemented with any suitable audio technology.

Having described the operating environments with the discussion now proceeds to a more detailed description of the HD DVD transformation component now presented with .

Taken as a whole the content markup the style markup and the timing markup define a document object model DOM . The DOM may be implemented as a tree data structure using an XML vocabulary. The DOM may include a plurality of individual markup elements denoted generally in at . Table above depicts sets of legal parent child element combinations providing specific examples of DOM states .

These markup elements may define a scene description for what is rendered on screen to the user. denotes this scene description generally at . While the scene description may specify what is rendered on screen to the user the scene description itself is expressed in a form defined by the HD DVD Specification as promulgated by the DVD Forum Steering Committee rather than a form that may be directly manifested or displayed on screen. The process of converting the scene description into a form suitable for display on screen is referred to herein as formatting. To perform this function the HD DVD transformation component may include an HD DVD formatter component which may include software instructions to format the scene description into a form suitable for display on screen.

The HD DVD formatter component converts or maps the scene description language into transformed content and style markup suitable for rendering on screen to the user. generally denotes the transformed content and style markup at . This transformed markup is input to an HD DVD rendering component which includes software instructions for rendering the transformed content and style markup into final rendered output form e.g. . This rendered output is suitable for presentation to the user via for example the presentation device taking into account any particularities specific to the presentation device .

Having described the HD DVD transformation component in more detail with the discussion now proceeds to a more detailed description of the HD DVD formatter component as it may process the scene description over time now presented with .

As shown in a scene description in a given initial state denoted at is represented by a corresponding DOM in an initial state denoted at . The HD DVD formatter maps the DOM state to an area composite structure denoted generally in at . More specifically the area composite state that corresponds to the DOM state is denoted at while the mapping process is denoted at .

The area composite may be implemented as a tree structure that indicates how the various elements specified in the DOM may be rendered on screen to the user. Thus the area composite may contain an arbitrary number of elements and generally elements . While the DOM may be specified in the markup language chosen by the author of the HD DVD the area composite is expressed in terms of the capabilities of the device on which the HD DVD content is displayed. The HD DVD rendering component may generate rendered output based on the contents of the area composite

One DOM node may produce multiple area nodes as when a DOM node that describes a paragraph produces multiple lines of text where the overall paragraph produces one area for example with a background color for the paragraph and in addition each line produces one area for example with some text and or images on that line . While one area node generally refers back to one DOM node this may not always be true. For example consider a case where a paragraph DOM node is fully specified by itself and no other DOM nodes and produces paragraph areas and line areas. Each of these paragraph areas and line areas will refer both generally and specifically to the paragraph DOM node and to no other DOM nodes.

However consider a case where a parent paragraph DOM node defines a background color and a child paragraph DOM node inherits that color. Then the paragraph area and line areas produced by the child paragraph DOM node will generally refer to the child paragraph DOM node. However strictly speaking these paragraph area and line areas will also be influenced by and associated with the parent paragraph DOM node that specified the background color.

When the clock pulse occurs this provides a signal to the HD DVD formatter that the scene description has changed states to . As shown in the new scene description may be associated with a new state of the DOM denoted at . denotes at any changes between the initial DOM state and the new DOM state

In turn the formatter may consider these changes when updating the area composite in response to the clock pulse . More specifically the formatter may perform an incremental re map of the DOM to an updated state of the area composite denoted at . The term incremental as used herein refers to the notion of re mapping only that portion of the new DOM state that has changed relative to the previous DOM state as distinguished from re mapping the entire new DOM state . denotes this incremental re mapping process generally at .

Once the area composite is updated to result in area composite the HD DVD rendering component may produce updated rendered output . The rendered output reflects the changes in the scene description triggered by the clock pulse as presented in final manifested form to the user.

Having described the HD DVD formatter component in more detail with the discussion now proceeds to a more detailed description of various approaches by which the formatter component may incrementally remap the DOM states as they transition over time now presented with .

The formatter component receives data representing a given current scene description denoted at and receives indication of successive clock pulses denoted at . In response to the clock pulses the current scene description transitions to a next scene description state with the formatter component receiving indications of the next scene description state

As shown in the different scene description states are associated with respective instances or states of the DOM as denoted at and . illustrates a time axis with example clock pulses occurring at discrete times and

As the DOM transitions from state to state for example the formatter component may determine how much the DOM changes from state to state. provides three examples of changes denoted respectively at and . The changes indicate changes in the DOM when transitioning from state to the changes indicate changes in the DOM when transitioning from state to and the changes indicate changes in the DOM when transitioning from state to

The formatter component and or other components of the HD DVD player may generate messages indicating the scope and content of these changes. illustrates three examples of these change notification messages at and collectively change notification messages . It is noted that implementations of the description herein may support any number of transitions of DOM states.

Depending on the nature and scope of a particular set of changes as reflected in the change notification messages the formatter component may employ different techniques for incrementally remapping or reformatting the DOM state to derive updated area composites. illustrates three techniques.

In a first scenario denoted at the formatter component performs no incremental work because of the changes . In this first scenario the transition in DOM state does not result in any incremental remapping or reformatting. Examples of when this first scenario may occur are given below.

In a second scenario denoted at the formatter component employs a some styles all elements technique. In this second technique the formatter component evaluates the all elements contained with the DOM markup tree but only evaluates the styles that change because of a state transition.

In a third scenario denoted at the formatter component employs a some styles single elements technique. In this third technique the formatter component evaluates a single node in the tree of markup and within that single node only evaluates those styles that were modified because of the state transition.

Having described the various approaches by which the formatter component may incrementally remap the DOM states as they transition over time with the discussion now proceeds to a description of process flows that the formatter component may perform now presented with .

The tools described herein may perform at least portions of the process flow in response to receiving the change notification message . Before proceeding with the description of and the other flow diagrams included herein it is noted that the blocks depicted in these flow diagrams are presented in the orders shown only for convenience but not for limitation. Implementations of these process flows may perform these blocks in any convenient order.

Block represents evaluating whether the formatting changes indicated in the change notification message correspond to related styles. If so the process flow may take Yes branch to block which represents processing any data together that correspond to related styles.

Styles may be related and processed together when multiple change notifications are delivered together. For example a change notification message e.g. may include change A change B change C and change D where changes B and C are related and may be processed together.

Styles may also be related and processed together when many styles affect the same portion of one area in the area composite. For example one portion of an area in the area composite is the background rectangle essentially the bounding box x0 y0 x1 y1 that describes where a background color and or background image are drawn if the area has a background color or background image. Many styles may affect this background rectangle including but not limited to style anchor style x style y style position style inlineProgressionDimension style blockProgressionDimension style writingMode style width and style height. Thus these styles may all be processed at once as ultimately the calculation to compute the background rectangle in the area will take into account each of these styles. However while the style color of the background rectangle is related to the bounding box for this area the color does not participate in the computation of the bounding box and changes in color would be processed separately from changes in width height etc.

Returning to block if the formatting changes indicated in the change notification message do not correspond to related styles then the process flow may take No branch to evaluation block .

Evaluation block represents determining whether past formatting results are available and if available whether these past results are still correct for the DOM state . If so the process flow may take Yes branch to block which represents using these past formatting results in the current reformatting operation triggered by the clock pulse .

From evaluation block if the result of the evaluation is negative the process flow may take No branch to evaluation block which represents evaluating whether any style changes triggered by the clock pulse affect all elements in the DOM or only a subset of the elements in the DOM. If the style changes are determined to affect only a subset of these elements then the process flow may take Yes branch to block which represents processing the affected useful subset of the elements within the DOM.

From evaluation block if the result of the evaluation is negative the process flow may take No branch to evaluation block which represents determining whether the transition from DOM state to state involves referencing and or dereferencing graphical assets. Examples of graphical assets include image or font files whose use may involve decompression operations.

From evaluation block if the result of the evaluation is positive then the process flow may take Yes branch to block which represents ordering any referencing and or dereferencing operations such that a properly authored application as stored on the HD DVD does not exceed platform limitations e.g. does not exceed limits of pixel buffers .

From evaluation block if the result of the evaluation is negative then the process flow may take No branch to block which represents associating a clean or dirty state with the various elements in the DOM tree. More specifically if the change in DOM state from to results in changes to particular elements of the DOM tree then block may include marking those particular elements as dirty and marking the remaining elements of the DOM tree as clean .

Block represents associating a clean or dirty state with the DOM tree as a whole. More specifically if the change from DOM state to DOM state results in any changes to the DOM tree then block may include marking the DOM tree as dirty . Otherwise if the change in DOM state does not result in changes to the DOM tree as a whole then block may include marking the DOM tree as clean .

Block represents reformatting on those elements and or styles within the DOM tree that have been marked as dirty by block and or .

The various operations shown in provide different optimization strategies. Implementations of the tools described herein may employ one or more of these optimization strategies as appropriate in different circumstances. More specifically these optimization strategies may support the some styles all elements technique e.g. block in and or the some styles single element technique e.g. block in .

Having described the process flows that the formatter component may perform with the discussion now proceeds to a description of organizing the HD DVD style data into layers now presented with .

As shown in the DOM state transitions to DOM state in response to the clock pulse resulting in the HD DVD formatter generating a change notification message . The styles are carried forward from .

The formatter may support the notion of layer structures. depicts two examples of layers at and generally but implementations of the tools described herein could support any number of layers. The layers may organize the various style data appearing in a given DOM state. In the example shown in the layer is associated with the style in the DOM state and with the style in the DOM state . Other layers e.g. layer may organize other styles although omits these relationships in the interests of clarity.

Examples of criteria by which the layers may organize the style data include separating the style data to support the applicative referential inline animated and scripted values allowed by a declarative language in which the HD DVD is authored. represents these values at blocks and respectively.

When the DOM changes state from to the formatter may report changes to different layers resulting from the state change. denotes these changes to the layers at . These changes may be expressed as for example one or more set operations for different styles in the individual layers as represented at block .

Block represents expressing these changes as one or more unset operations for different styles in the individual layers. Block represents expressing these layer changes as one or more get operations for the styles for the individual layers. Block represents expressing these layer changes as one or more get operations performed for all styles in all layers considering the relative priority of each layer to determine an effective value. Block represents separating the resulting tangible data by layers.

As examples of the set and unset operations consider a case where in the declarative content markup and declarative style markup the initial state of some element is that style x 10 px due style x being applied inline. Consider than in the declarative timing markup at a time 3 minutes into the playback of a movie the element is programmed to move from 10 px to 100 px over the course of 5 seconds and then move back over the course of 5 seconds.

For the entire duration of the movie including the portion in which animation is occurring the inline value of style x remains 10 px. This value was set during load and is never unset .

For the first 3 minutes of the movie no value of style x exists at the animated layer. At 3 minutes into the playback of the movie the animated value of style x is set to 10 px. For the next 10 seconds the animated value of style x is set to values from 10 thru 100 and back according to the performance of the system and other programming considerations.

At 3 minutes and 10 seconds into the playback of the movie the animated value of style x is unset . After 3 minutes and 10 seconds into the playback of the movie no value of style x exists at the animated layer. Now for the first 3 minutes of the movie the effective value is the value from the inline layer. From 3 00 to 3 10 the effective value is the value from the animated layer. At 3 10 the effective value is again the value from the inline layer.

As an example of the get operation consider again the button above with a static inline value of style x and an animated value of style x for some period of time. A get operation may be performed by formatting to determine the effective value essentially a component outside of the layer component asking for a final number. To accommodate this request the layer component may make subordinate calls to get the value stored at individual layers and then select from the available layers the appropriate effective value according to the precedence rules in the HD DVD spec. Thus there are two versions of get the layer get which serves to support the effective get 

Having described techniques for organizing the HD DVD style data into layers with the discussion now proceeds to a more detailed description of change notification messages now presented with .

As described above a change notification message e.g. may result when the DOM state transitions to the DOM state . Depending on the nature and scope of the changes resulting from the state transitions the change notification message may include different types of information.

In the example shown in the change notification message may indicate that one or more elements are changing because of the state transitions as represented at . Examples of elements are shown at and 

The change notification message may indicate that one or more styles are changing because of the state transitions as represented at . Examples of styles are shown at and 

The change notification message may indicate that one or more layers are changing because of the state transitions as represented at . Examples of layers are shown at 

Line represents instances in which changes to the DOM are expressed in one or more set operations. In such instances the change notification may specify a new value of the style as represented at block .

Having provided a more detailed description of change notification messages with the discussion now proceeds to a description of process flows for reactions to the change notification messages now presented with .

As shown in changes in DOM state specified in timing markup e.g. or in a script e.g. may result in change notification messages e.g. . In response to a change notification message the tools may perform at least part of the process flows .

Evaluation block represents determining whether the incoming change notification message specifies a set or unset operation. If the message specifies a set operation the process flow may take branch to evaluation block . If the message specifies an unset operation the process flow may take branch to block .

Block represents performing a get operation to obtain an effective style value as specified in the message .

Evaluation block represents determining whether the incoming message allows single element formatting. If so the process flow may take branch to block which represents adjusting tangible data related to the single element specified in the incoming message . Afterwards the process flow may proceed to an end state .

From evaluation block if single element formatting is not allowed the process flow may take branch to block which represents looking up the impact of the reformatting specified in the incoming message.

As an example of looking up the impact of formatting consider again the parent paragraph defining a background color and a child paragraph that inherits that color. If the background color of that parent paragraph changes then any child that inherits that changed value will also change. Thus the parent paragraph is not allowed to format style backgroundColor using single element formatting. The knowledge of whether or not this formatting is allowed is computed in block and stored as part of the configuration of the formatting software corresponding to the parent paragraph.

Block represents setting a bit or other suitable mechanism to indicate that the entire DOM tree is impacted by the reformatting specified in the incoming message and is therefore dirty . Afterwards the process flow may proceed to the end state .

From evaluation block if the question of whether or not single element formatting is allowed has not yet been determined the process flow may take branch to block which represents examining the current parent and or child in the tree. Afterwards the process flow may return to just before evaluation block as shown in .

In the configuration of the formatting software corresponding to some element is stored a reference to the parent element first child element and next sibling element. Using these three links the tree may be traversed up and or down and or across as appropriate. All or a part of the tree may be traversed to determine if single element formatting is permitted.

While a change notification message may not specify whether single element formatting is permitted the change notification message may include some information that informs the decision to either allow or disallow single element formatting.

As an example consider a parent button that defines background color red and a child button that defines background color blue. If the child button is changed to ignore the color blue and instead inherit the red background color from its parent then single element formatting is disabled for the parent as changes to the parent now affect the child.

As another example consider a parent paragraph with no explicit size and a child span that contains the text Hello World . The default size of this parent paragraph will then be based upon several things but the important one for the description here is the size of the span containing the glyphs for the string Hello World .

As yet another example consider then a change notification where the child span is modified to contain The Quick Brown Fox instead of Hello World . Clearly the span is going to get larger as there is now more text in the span. Clearly the parent paragraph that is primarily sized according the size of the span is now also going to get larger. Thus the span may not be formatted according to the single element means in this case.

Generally impacts may include parent child impacts and child parent impacts. In implementations these impacts may be numerous and not limited to the inheritance and sizing examples provided above for illustration only.

Returning to evaluation block this block represents determining whether the layer specified in the message is an effective layer in the reformatting process. The DVD Specification defines which layers are effective or have precedence in particularly circumstances. If the layer specified in the message is not an effective layer the process flow may take No branch to the end state . On the other hand if the layer specified in the message is an effective layer then the process flow may take Yes branch to evaluation block .

Block represents determining whether the current node being examined is set to inherit at least some of its attributes from another node. For example the current node may be a child node that inherits at least some of its attributes from a parent node. As another example the current node may be a parent node at least one of whose attributes are based on attributes of its children. Generally the change message when it is a set message includes the value that is being set. One special type of value is the inherit value.

From evaluation block if the current node is not set to inherit from another node then the process flow may take No branch to block which represents using a style value as specified in the incoming message . Afterwards the process flow may proceed to the end state .

From evaluation block if the current node is set to inherit from another node then the process flow may take Yes branch to block which represents disabling single element formatting for the current node as well as any parent or child nodes of the current node. Because the current node is inheriting from other nodes any changes resulting from reformatting may tend to cascade throughout at least part of the tree and in this case single element formatting may not be appropriate. Afterwards the process flow may proceed to block which was described above.

If the process flow reaches evaluation block after passing through block then block will have disabled single element formatting. In this event the process flow may take branch to block . In turn block may include ascertaining how much the changes resulting from the inheritance relationship of block cascades through the tree.

Having described the process flows for reactions to the change notification messages with the discussion now proceeds to a description of process flows for performing per frame formatting now presented with .

Block represents evaluating whether the clocking signals result in any state or style changes within the tree structure representing the scene description. If no state or style changes result from the clocking signals the process flows may take No branch to end state . On the other hand if any state or style changes result from the clocking signals the process flows may take Yes branch to block .

Block represents evaluating whether any part of the tree structure has become dirty as a result from the state or style changes evaluated in block . Put differently block may include evaluating whether at least one element within the tree is to change because of the state or style changes. More specifically block may include traversing the tree to select a given element within the tree to be processed for any state or style changes.

If no element within the tree is to be changed the process flows may take No branch to the end state . On the other hand any element within the tree is to be changed the process flows may take Yes branch to block which represents evaluating whether the tree traversal is complete. If no elements within the tree remain for traversal the process flows may take No branch to end state . On the other hand if any elements within the tree remain for traversal the process flows may take Yes branch to block .

Block represents traversing the tree to access at least one next element remaining in the tree as a current element. Block represents determining or computing any changes to be made to the current element. These changes may be viewed as dirty steps as indicated in . Block represents performing any dirty steps on the current element. Afterwards the process flows may return to block to check for any additional elements remaining in the tree that remain for traversal and processing. Blocks and may be repeated for the various elements contained within a given markup tree.

Having described the process flows for performing per frame formatting with the discussion now proceeds to a more detailed description of traversing parent and child nodes of the markup trees now presented with .

Turning in more detail to the first pass represented in block block represents traversing a given parent node within the DOM tree. The process flows may begin with a root node of the DOM tree e.g. and traverse the tree from there. Afterwards the traversal may progress to parent nodes beneath the root node e.g. that have one or more child nodes beneath them.

Block represents creating a context at the current node by performing as much reformatting work as possible at the current node before proceeding to the child nodes of that current node.

Block represents determining whether any additional parent nodes remain for processing in the DOM tree. If so the process flows may take Yes branch to return to block to select a next parent node in the tree. Otherwise the process flows may take No branch . Branch completes the detailed processing for the first pass and begins the detailed processing for the second pass as shown in .

Turning to block in more detail block represents traversing the tree to access any child nodes under a given parent node. Block represents resolving details for processing the child nodes that are under the given parent node.

Evaluation block represents determining whether the given parent node has any additional child nodes beneath it that remain for processing. If so then processing may take Yes branch back to block to repeat the process with a next child node. If the given parent node has no additional child nodes beneath it then processing may take No branch to block which represents fully resolving details relating to the given parent node having resolved the details for all child nodes beneath the given parent node.

Having described the process flows for traversing parent and child nodes of the markup trees with the discussion now proceeds to a more detailed description of content markup references and overall iteration through markup trees.

Table 2 presented below illustrates an example separation of passes through the tree denoted as Pass 1 and Pass 2.

As described above in Pass 1 traverses downward through the parent nodes and establishes context for child nodes. During Pass 2 up child details are fully resolved allowing the parent details fully to resolve.

While the foregoing description is presented in the context of processing HD DVDs it is noted that the tools and techniques described herein may be suitable for processing other types of media or for processing markup of types other than those described herein.

Although the systems and methods have been described in language specific to structural features and or methodological acts it is to be understood that the system and method defined in the appended claims is not necessarily limited to the specific features or acts described. Rather the specific features and acts are disclosed as exemplary forms of implementing the claimed system and method.

In addition regarding certain data and process flow diagrams described and illustrated herein it is noted that the processes and sub processes depicted therein may be performed in orders other than those illustrated without departing from the spirit and scope of the description herein. Also while these data and process flows are described in connection with certain components herein it is noted that these data and process flows could be performed with other components without departing from the spirit and scope of the description herein.

