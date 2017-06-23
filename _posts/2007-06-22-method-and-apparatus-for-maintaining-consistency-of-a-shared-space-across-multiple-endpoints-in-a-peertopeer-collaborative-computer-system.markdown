---

title: Method and apparatus for maintaining consistency of a shared space across multiple endpoints in a peer-to-peer collaborative computer system
abstract: In a peer-to-peer collaboration system, deltas containing data change commands are organized in a persistent data structure called a delta log. The delta log is organized into blocks, which are the largest division in the delta log. In turn, blocks contain groups, groups contain chains and chains contain deltas. Delta blocks are used to implement priority deltas that are used to limit the collection of data change commands that must be transferred. Within a block the deltas are organized by groups, each of which is a set of deltas organized into chains. The delta group in used to determine which deltas to purge. The chains are ordered by increasing creator ID of the endpoint that created the chain. Organizing the delta log in this fashion allows the log to be “walked” to detect convergence problems. To achieve causality-preservation, each delta has a list of dependencies representing other deltas that must be executed before the current delta can be executed. The dynamics manager uses the ability to do (execute) and undo commands to perform roll back and roll forward operations on deltas in order to achieve convergence.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=08073905&OS=08073905&RS=08073905
owner: Microsoft Corporation
number: 08073905
owner_city: Redmond
owner_country: US
publication_date: 20070622
---
