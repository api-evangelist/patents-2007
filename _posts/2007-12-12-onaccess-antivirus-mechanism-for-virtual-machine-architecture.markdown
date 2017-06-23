---

title: On-access anti-virus mechanism for virtual machine architecture
abstract: A tangible medium embodying instructions usable by a computer system to protect a plurality of guest virtual machines (VMs), which execute via virtualization software on a common host platform, from malicious code is described. A scan engine is configured to scan data for malicious code and determine a result of the scanning, wherein the result indicates whether malicious code is present in the data. A driver portion is configured for installation in an operating system of a target VM, which is one of the guest VMs. The driver portion intercepts an access request to a file, that originates within the target VM. The driver portion communicates information identifying a location of the data to be scanned by the scan engine without sending a copy of the data to the scan engine. The scan engine executes within the virtualization layer outside a context of the target VM.
url: http://patft.uspto.gov/netacgi/nph-Parser?Sect1=PTO2&Sect2=HITOFF&p=1&u=%2Fnetahtml%2FPTO%2Fsearch-adv.htm&r=1&f=G&l=50&d=PALL&S1=07797748&OS=07797748&RS=07797748
owner: VMware, Inc.
number: 07797748
owner_city: Palo Alto
owner_country: US
publication_date: 20071212
---
