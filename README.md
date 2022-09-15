# Design Documentation

### Introduction

The following document outline all design documentation of the smart livestock monitoring
System. This document is separated in section, you can jump to any specific section you want to learn more
about related to the livestock monitoring system. You are advice to read this document if you want to
learn more about the design principle and choices of the livestock monitoring system. The information on this document will
enable you to not only understand the system but will tell you how to trouble shoot the system if anything went
wrong and also extend the functionality of the system if you so choose to.

##### *scope*
The document will cover design consideration, Assumptions, goals and guideline. It will give you enough information
about Architectural strategies, System architectural and Functional flow of the livestock monitoring system.

##### *Audience*
The design documentation is for anyone who want to learn more about the livestock monitoring system,
How it is design from ground up and how they can extend the system to solve other problem. This document it also
good for any engineers who want to replicate the system on their own.

### Overviews

The smart livestock monitoring system track livestock using ESP32 Micro controller. One ESP32 per
each livestock that contain a unique identify (UID) that will enable the system to count the total
livestock at a given time. A web sever connect to a database take the information sends sends by
the Micro controller and store it to a database.

The Micro controller is  being package to a case with a battery. The band that
cover the animal is a solar panel that charge the
battery so that it does not die quick. The case is that package the microcontroller is strong enough
to resist hard weather condition

### Design considerations

The first issue that need to be solved on the design consideration is the power
supply for the Micro controller. We need to make sure that the battery last
longer and became rechargeable over the life span of the livestock

The second is weather condition, The device need to withstand harsh weather
condition since livestock can be farmed outside

The third design issue is the wight of the device, We need the device to be light as possible that it
does not affect the growth of the livestock.

### Assumption and dependencies

The livestock monitoring system is developed with the assumption its users
have access to a web browser. Weather that be a phone or computer, few of the
popular web browser include Chrome, Firefox and Brave. This is by design, A web
browser is cross-platform by default, that mean weather you are using a
Windows, Mac or Linux you can still access the system.

We also developed the system under the assumption that where the livestock
is being kept the is internet connection, or at least we can install one. The
Micro controller need internet access to be able to send data that we need to
monitor the livestock and for the most part we assume that our users know how
to access the internet and can be able to read chart

#### Relatable software

The system is related in most way to a car tracking system, The difference is a
car does not need a solar power since it can get power from the car while
the livestock monitoring system  you need creative way to supplier power to the
system

#### Related software and hardware

The system is related in most way to a car tracking system, The difference is a
car does not need a solar power since it can get power from the car while
the livestock monitoring system  you need creative way to supplier power to the
system


#### General Constraints

Describe any global limitations or constraints that have a significant impact
on the design of the system's software (and describe the associated impact).
Such constraints may be imposed by any of the following (the list is not
exhaustive):

- Hardware or software environment
- End-user environment
- Availability or volatility of resources
- Other requirements described in the requirements specification




### Goals and guidelines
The development of livestock tracking system follows the Unix philosophy that
emphasis building simple, compact, clear, modular, and extensible code that can
be easily maintain and repurposed by developer other than its creator

While developing the system, the main focus was power consumption, I wanted the
system to consume less power as possible. A lot have been done on the Micro controller
to make sure that the power consumption is low as possible, such as making sure that the bluetooth
module is turned off, and only use the wife module, and lower than the CPU clock rate.
I also made the CPU to do one job and one job only to make it last longer on a single
The design of the tracking hardware is design to be resisted to hash weather condition, to be
robust. I made sure it does not fall easy when attached to the livestock. I also choose to make the
box/ case to package the ESP32 black. This will make sure that is became invisible as possible to the
livestock or not fool the livestock to think that is food


### Development Methods

The development of the project is developed using two well known development methods in the
software industry, which is **Agile development methodology** and **DevOps deployment methodology**
Those methods was adapted after the first Software Development Life Cycle was applied.
The first step. Agile development methodology was used because it focus strongly on user experience
and input. This make the software high responsive to changes while developing the software and also
get the system up and factional quickly to meet the user needs. DevOps deployment methodology was to make
sure that I get the application up and running quick, using things such as continues deliverance, git,
Github.

#### Planning

The first step on the development of the livestock monitoring system was to draft steps and
calculating labor cost and material costs, creating timetable with target goals and creating a
structure that can be followed when developing the system

#### Creating
On this stage I focus more on packing the ESP32 to the case, connect the ESP to the WI-FI,
carefully soldering the system components on the veroboard, ensuring neat circuit is built and the are
no short circuit that may cause blowing of the components

#### Developing
At this stage is where I switch to following Agile development methodology, since it is
a software problems. I developed a NodeJS sever using JavaScript and a framework called
Express.

#### Deployment
I use git to deploy the application to the cloud. push the changes to git so that the system
can get the changes when made to the master branch. Tested the changes if the meet the user
needs that I define or proposed

#### Architectural Strategies

The hardware is packaged on a black case of about 50cm to 20cm and 10cm hight. The case
for the hardware is light in weight and most of the livestock such as cattle and cow, sheep would not
feel the case weight. The decision I do not want to strain wight of the livestock that it end up
affect their growth

On the drawing board, I wanted a flexible solar pane to be used  as belt, that will
serve two purposes, Charge the battery inside the case and also hold the case in place
due to availability I only able to find a hard solar panel that can charge up to 6V.
This will affect the design, The final package, The case and all would look nice, but it will
be good enough to do a demonstration

##### *Tehchnologies used*

The hardware, ESP32 Micro controller it is programmed using the C++ programming
language and the curl library was used to allow the ESP32 to communicate with
the server over the internet. C++ is the standard programming language when it
come to programming low level system, It can integrate very well with hardware.
Made sense to use C++ although is not the only language since we have
language such as C# and Rust. C++ turned out to even have more advantage since
we also want to consume less power and it can be optimize to maximise the speed
of the CPU. Curl, is a open source library used in most C++ code base when need
to connect to the internet it is also light libra, it does not consume too much
power

The server, is developed with the JavaScript programming language using a
framework called Express. Running on a node server(the application). JavaScript
it has replaced PHP when you want to create a quick server. It has most security
feature and the is more resources online for libraries for absolute
anything you might want to do. The server is hosted on Linode, a cloud base
company that offer most cloud services. This is to make sure you can connect
to sever from anywhere around the world

Future plan for the application is to collect more data from the livestock such as temperature,
location and display the information in to the dashboard. Research on maximizing power efficient so that
the system can last longer on a single charge if the solar panel can not charge the battery in a
rainy weather.

The user interact with the system via a web browser. If they know how to user a web browser
They will know how to use the system. The input to the system is the signal sent from the case
to the server and the output will be the dashboard where we display the information about
the livestock

##### *Communication mechanisms*
The following diagrame display communication flow of the ESP32 and the server
```
<digram>
```

#### Subsystem Architecture

The system does not contain complicated componentes, everything is simple as it
archieve a specific things. This is by design, Thanks to the Unix philosophy. The
whole purpose of the system is to count livestock remotely

#### *ESP32(hardware)*
For the system to be able to count livestock, E=each esp32 micro controller
get atatched to the livestock. The ESP32 the sends request to a remote server
with a uniquer UUID to identify the livestock. The request is being constantly send
to the server at an interval time rate


#### *Node Js (Server Application)*
The Server application is connect to a Maria database and listening to HTTP request,
when a POST request is being made with UID, It gets save to the database with the time
stamp. The Server also expose a Web Socket to stream the total number of unique ID that are in the database.
When a client is connected to that socket, the total number its get send to the client

#### *Web Application (Client dashborad)*
The Web applicaton connect to the server using web socket to listen to the datat bieng screaed from
the server which represent the number of unique ID from the databas


### Detailed System Design

Most components described in the System Architecture section will require a
more detailed discussion. Other lower-level components and subcomponents may
need to be described as well. Each subsection of this section will refer to or
contain a detailed description of a system software component. The discussion
provided should cover the following software component attributes:

#### Classification
The kind of component, such as a subsystem, module, class, package, function, file etc.

Definition

The specific purpose and semantic meaning of the component. This may need to
refer back to the requirements specification.

#### Responsibilities
The primary responsibilities and/or behavior of this component. What does this
component accomplish? What roles does it play? What kinds of services does it
provide to its clients? For some components, this may need to refer back to the
requirements specification.

#### Constraints

Any relevant assumptions, limitations, or constraints for this component. This
should include constraints on timing, storage, or component state, and might
include rules for interacting with this component (encompassing preconditions,
post-conditions, invariants, other constraints on input or output values and
local or global values, data formats and data access, synchronization,
exceptions, etc.)

#### Composition

A description of the use and meaning of the subcomponents that are a part of
this component

#### Resources


#### Interface/Exports

Much of the information that appears in this section is not necessarily
expected to be kept separate from the source code. In fact, much of the
information can be gleaned from the source itself (especially if it is
adequately commented). This section should not copy or reproduce information
that can be easily obtained from reading the source code (this would be an
unwanted and unnecessary duplication of effort and would be very difficult to
keep up-to-date).

It is recommended that most of this information be contained
in the source (with appropriate comments for each component, subsystem, module,
and subroutine). Hence, it is expected that this section will largely consist
of references to or excerpts of annotated diagrams and source code. Any
referenced diagrams or source code excerpts should be provided at any design
reviews.

### Functional Flow
Provide a detailed description of the different system functions. For each
function provide an activity diagram, process flow table and a status flow
table.

Process Flow Table: In this table you list the processes in that function and a description explaining the process

Status Flow Table: In this table you list the different statuses and add a description to explain the status.

### Conclusion
blah blah
### Glossary

An ordered list of defined terms and concepts used throughout the document.

### Bibliography

A list of referenced and/or related publications.
