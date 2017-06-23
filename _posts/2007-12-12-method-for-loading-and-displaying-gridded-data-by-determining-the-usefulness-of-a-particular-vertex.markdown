---

title: Method for loading and displaying gridded data by determining the usefulness of a particular vertex
abstract: Method, computer executable program and apparatus for displaying massive amounts of potentially non-uniform gridded data through the use of view dependant refinement. An initial minimal representation is created. A view dependant refinement criterion is then used to ascertain the perceived quality. If necessary, refinements and decimations to the current representation are performed. The representation is then provided to graphics hardware for display.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08077177&OS=08077177&RS=08077177
owner: 
number: 08077177
owner_city: 
owner_country: 
publication_date: 20071212
---
This patent application claims the priority benefit of the filing date of a provisional application Ser. No. 60 879 211 filed in the United States Patent and Trademark Office on Dec. 15 2006.

The invention described herein may be manufactured and used by or for the Government for governmental purposes without the payment of any royalty thereon.

There exists a need to display high resolution terrain data e.g. Digital Terrain Elevation Data DTED from global to high resolution scales. To a limited extent this type of task has been accomplished using free distribution applications such as Google Earth . Specifically what is needed is a method for loading and managing massive gridded datasets of the type available from the National Geospatial Intelligence Agency NGA and the US Geological Survey USGS .

Brute force computing methods for loading or displaying such voluminous data at the global level exceed the current capabilities of modern processing hardware. The only way to achieve the desired visual quality and interactive speed is to use real time algorithms that vary the quality of the displayed content. Such algorithms would necessarily feature 1 a data structure for storing manipulating and processing of vertex information and 2 intelligent processing of the information contained within the data structure.

The ability to view terrain with such a large number of vertices is an important research area where several in core and out of core techniques have been developed. However these prior art techniques require an expensive pre processing stage which decimates the statistical accuracy of the original incoming data. Therefore an urgent need exists because the volume and resolution of terrain data is growing faster than our ability to display it.

One object of the present invention is to provide a method for storing manipulating and processing of vertex information.

Another object of the present invention is to provide an algorithm based method that intelligently processes the information contained within a data structure.

The invention disclosed herein provides a data structure and algorithm based method for loading and or displaying gridded datasets by adaptively loading data from an external data store and providing this information to a modern graphic processing unit in an acceptable form. In particular the present invention uses independent view refinement criteria for determining the usefulness of a particular vertex of the gridded data retrieves that data from some backing store and inserts that data into the Circular Linked List of Geometrical Relationship CLLGR data structure. When all necessary refinements have been completed it dispatches the vertex information as a list of triangle fans for visualization. These refinements can be adaptive such that more data may be fetched to satisfy the view refinement criteria but a redraw occurs due to the desire to provide the user with a more responsive system. The data maybe be procedurally generated as is the case for fractally generated terrain or displaying of the WGS84 reference ellipsoid or can be read from memory if the desired data has already been provided to a cache or can be loaded from some other persistent storage device like a modern hard disk drive or can be fetched from some web service or other network capable infrastructure.

An embodiment of the present invention provides a view refinement method and method for an out of core of the loading of NGA s DTED. The embodiment uses a screen projected node width approximation for ascertaining whether refinements or simplifications of the CLLGR are required. The loaded information is then projected into a user specified coordinate system that converts the source latitude and longitude tuples into geocentric vertex information. Two available projections comprise a flat earth projection and a World Geodetic 1984 WGS84 projection however there is no limitation to the types of projections that are possible.

The method of the present invention resembles a Quadtree structure where each IndexNode has an up down left and right pointer to another IndexNode. Each tree node consists of a center IndexNode denoted as V and eight immediate neighbors see Each TreeNode has zero or four children. An IndexNode is a structure which maintains unique mappings to other IndexNodes and has a Vertex for its Cartesian based information. A TreeNode is a collection of linked IndexNodes that encode some spatial relationship and potentially child TreeNodes.

With the assumption that the decimation process is performed at the TreeNode that is required to meet the view refinement criteria and that it has children the decimation process can be described in simplified form. see 

It is within the scope of the present invention that it be modified to allow use of non uniformly gridded data. Non quad tree representations can also be employed allowing for different refinement processes. Non view dependent criteria can also be employed.

The present invention creates a forest of Triangle Fans from gridded data by using an independent refinement criteria further enabling the display of real time 3D depictions of larger than in core memory datasets on modern graphics hardware. In particular the present invention employs a continuous level of detail algorithm to display massive amounts of terrain data effectively.

The present invention exists in an Application Programmer s Interface form where it facilitates the visualization of unmodified global terrain information from the National Geospatial Intelligence Agency NGA in real time on a variety of platforms. It is currently distributed with the JView API and being used on Macintosh Linux and Windows computers that range from low end Toshiba tough books up to high end visualization workstations. The highest end system that it has been tested consists of two Sony SRX 105 projectors driven from an 8 dual core processor computer from BOXX technologies with 32 GB of memory and two NVidia Quadro Plex IV s driving the display at 7680 pixels by 2160 pixels.

Referring to the data structures of the present invention are defined as TreeNodes and IndexNodes. TreeNodes contain nine IndexNodes designated as V through V. A particular task can involve one or more TreeNodes. IndexNodes V through V are directly addressable by each TreeNode and represent the possible raw or un projected vertex information. For example an IndexNode could store the latitude longitude and altitude of a spot on the Earth but to generate the actual vertex data a projection needs to be applied to the data stored in the IndexNode. Alternatively IndexNodes could also store the post projection data. This decision is based heavily on its projected use.

Referring to a first TreeNode share edges with a second TreeNode to form the finished geometry by sharing the IndexNodes labeled A D G C F and I. This creates the lowest quality version for this case. Each TreeNode directly accesses nine IndexNodes but due to the sharing of some IndexNodes there are only twelve unique IndexNodes.

Before displaying a particular level of refinement a view refinement step can be taken first. This step essentially determines whether the current representation as stored by the tree of TreeNodes and IndexNodes satisfies the criteria. For this case the assumptions made that one TreeNode failed the check and required refinement.

Referring to depicts the initial state and corresponding data structures and the first step of view refinement process of the TreeNode see that failed the check. Step creates four TreeNode children.

Referring to depicts the second and third steps of view refinement process and corresponding data structures. Step creates up to sixteen new IndexNodes. If an IndexNode already exists that satisfies the geometric relationship then the previously created IndexNode must be shared by these new IndexNodes. This is identical to the requirements for the TreeNodes as specified in . In this example the assumption is that no previously created IndexNodes satisfy the geometric relationship so sixteen new IndexNodes are created. Step assigns the newly created IndexNodes to their respective TreeNodes. Notice that the sharing of IndexNodes is pervasive through this algorithm and is the basis for efficiency and effectiveness of the present invention.

Referring to depicts the fourth and fifth steps of view refinement process and corresponding data structures. Step assigns the four newly created TreeNodes to the TreeNode that failed the view criteria. Step then links the new IndexNodes together.

Referring to shows that after IndexNode connections are created the ability to create a cycle by traversing about the IndexNodes is preserved.

Referring to following all necessary view refinements the process of creating the triangle fans to be sent to the graphics card is commenced. The process commences for all TreeNodes that do not have children. For each TreeNode data is transformed from the IndexNode into the desired coordinate system and then added to a list of vertices referred to as the vertex list for the triangle fan. That IndexNode s top link is followed . That new IndexNode s data is transformed into the desired coordinate system and added to the vertex list .

Still referring to for each of the top first half left side bottom side right side and top second half the respective IndexNode s left link bottom link right link top link and left link is traversed. Also for each link traversed respective transformed IndexNode s data is added to the vertex draw list. If it is determined that an IndexNode has a bottom link it is traversed otherwise the IndexNode s left link is traversed . This process continues until all directly accessible IndexNodes for a particular TreeNode have been traversed at which point the process ceases . This may result in more than nine vertices being stored since a neighbor may have refined.

Referring to after applying the display process explained in to the data structure depicted in the resultant triangle fans as shown would be generated. Each individual fan is shaded with a different pattern. Since there are five TreeNodes that do not have children 5 triangle fans are created. The triangle fans avoid T junctions by the fact that the IndexNodes are shared and thus neighbors that require additional levels of refinement are effectively inserting IndexNodes for multiple TreeNodes without the need for direct knowledge of their siblings.

Referring to and when a current representation exceeds the desired goal the present invention will perform the opposite of view refinement that is it will decimate the representation by first unlinking 16 Index Nodes and decimating and clearing i.e. removing children tree nodes. The corresponding data structure is shown during the decimation process.

While the preferred embodiments have been described and illustrated it should be understood that various substitutions equivalents adaptations and modifications of the invention may be made thereto by those skilled in the art without departing from the spirit and scope of the invention. Accordingly it is to be understood that the present invention has been described by way of illustration and not limitation.

