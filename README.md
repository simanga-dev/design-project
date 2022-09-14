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

T

### Assumption and dependencies


### Assumption and dependencies
The system need a web browser to connect to the dashborad. This is by design. A web browser is cross plarform
by default. that mean weather you are using Windoes, Mac or Linux you can still access the apllication system

The system assume you know how to connect to the internet. and you know how to use the internet

#### Relatable software

The system is related in most way to a car tracking system, The difference us a
car does not need a solar power since it can get power from the car while when
the livestock you have to supplier solar panel


*Describe any global limitations or constraints that have a significant impact
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
system to consume less power as possible, especially on the ESP32. A lot have been done
to make sure that the power consumption is low such as making sure that the bluethroat
module is turned off, and only use the wife module, and lower than the CPU clock rate.
I also made the CPU to do one job and one job only to make it last longer on a single
battery charge

The design of the tracking hardware is design to be resisted to hash weather condition, to be
robust. I made sure it does not fall easy when attached to the livestock. I also choose to make the
box/ case to package the ESP32 black. This will make sure that is became invisible as possible to the
livestock or not fool the livestock to think that is food


### Development Methods

The development of the project is develope using two wellknow developmne mthods in the
software indusry, which is **Agile development methodology** and **DevOps deployment methodology**
Those mothods was adapted after the first Software Development Life Cycle was applied.
The first step. Agile development methodlogy was used because it focuse strongly on user experience
and input. This make the softwarre highl responsive to changes while developing the softeware and also
get the system up and fuctional quickly to meet the user needs. DevOps deployment methodlogy was to make
sure that I get the application up and running quick, using things such as continues deliverance, git,
github.

#### Planning
The first step on the development of the livestock monitoring system was to draft steps and
calculating labor cost and material costs, creating timetable with target goals and creating a
structure that can be followed when developing the system

#### Creating
On this stage I focus more on packages the ESP32 to the case, connect the ESP to the wifi,
carefully soldering the sysrtem componets on the veroboard, esureing neat circuit is buit and ther are
no short circut that may cause blowing of the components

#### Developing
At this stage is where I swithch to following Agile development methodoloy, since it is
a software problems. I developed a NodeJS sever using JavaScript and a framework called
Node JS.

#### Deployment
I use git to deploy the application to the cloud. push the changes to git so that the system
can get the changes when made to the master branch. Tested the changes if the meet the user
needs that I define or proposed

#### Architectural Strategies
The hardware is pcackage on a black case of about 50CM to 20cm and 10cm hight. The case
for the hardware is light in weight and most of the livestock such as cattle and cow, sheep wont
fellt the case weight. The decision I don;t want to strain wight of the livestock that it
will affect their growth

On the drawing board, I wanted a flexible solar pane to use it as belt, that will
serve to purpose, Charge the battery inside the case and also hold the case in place.
dute to avaialbility I only able to find a hard solar panel that can charge up to 6V.
This will affect the design, The finel pacakge, The case and all wont look nice but it will
be enought to do a demostraction

##### *Tehchnologies used*

The hardware, ESP32 bing specif is programmed using the C++ nad curl libray was used theat allow
the ESP32 to communicate with the server over the internet. C++ is the starndard programming language when
it come to developing low level system, It can integrate very well with hardware. It made sense to
use C++ although is not the only language since we have language such as C# and Rust
C++ turnes out to even have more advantage since we also want to consume less power and it can be
optimise to maximsie the speed of the CPU. Curl, is a open source libray used in most C++ code base when
need to connect to the internet it is also light witht, it does not consume to much power

The server, is developed with the Javascrip programming langaude using a framewrok called Express.
running on a node server(the application). JavaSCrip it has replace PHP when you want to create a qick
server. It has most security feature and the is available resources online for librayies for
absolute anything you might want to do. The server is hosted on linode, a cloud base company that
offer most clound services. This is to make sure you can connect to sever from anywhre
arround the world

future plan for the application is to collect more data from the livestock such as temperature,
location and display the infomation in to the dashborad. Research on maximazing power efficient so that
the system can last longer on a single charge if the solar pannel can not charge the battery in a
rainy weather.


The user interact with the system via a beb browser. If they know how to user a web browser
They will know how to use the system. The input to the system is the signal sent from the case
to the server and the output will be the dashboard where we display the information about
the livestock

Describe any design decisions and/or strategies that affect the overall
organization of the system and its higher-level structures. These strategies
should provide insight into the key abstractions and mechanisms used in the
system architecture. Describe the reasoning employed for each decision and/or
strategy (possibly referring to previously stated design goals and principles)
and how any design goals or priorities were balanced or traded-off. Such
decisions might concern (but are not limited to) things like the following:


##### *Communication mechanisms*
The following diagrame display communication flow of the ESP32 and the server
```
digram
```


- Use of a particular type of product (programming language, database, library, etc. ...)
- Reuse of existing software components to implement various parts/features of the system
- Future plans for extending or enhancing the software
- User interface paradigms (or system input and output models)
- Hardware and/or software interface paradigms
- Error detection and recovery
- Memory management policies
- External databases and/or data storage management and persistence
- Distributed data or control over a network
- Generalized approaches to control
- Concurrency and synchronization
- Mijanagement of other resources

Each significant strategy employed should probably be discussed in its own
subsection, or (if it is complex enough) in a separate design document (with an
appropriate reference here of course). Make sure that when describing a design
decision that you also discuss any other significant alternatives that were
considered, and your reasons for rejecting them (as well as your reasons for
accepting the alternative you finally chose). Sometimes it will be most
effective to employ the "pattern format" for describing a strategy.

#### System Architecture(1page)
This section should provide a high-level overview of how the functionality and
responsibilities of the system were partitioned and then assigned to subsystems
or components. Don't go into too much detail about the individual components
themselves (there is a subsequent section for detailed component descriptions).
The main purpose here is to gain a general understanding of how and why the
system was decomposed, and how the individual parts work together to provide
the desired functionality.

At the top-most level, describe the major responsibilities that the software
must undertake and the various roles that the system (or portions of the
system) must play. Describe how the system was broken down into its
components/subsystems (identifying each top-level component/subsystem and the
roles/responsibilities assigned to it). Describe how the higher-level
components collaborate with each other in order to achieve the required
results. Don't forget to provide some sort of rationale for choosing this
particular decomposition of the system (perhaps discussing other proposed
decompositions and why they were rejected). Feel free to make use of design
patterns, either in describing parts of the architecture (in pattern format),
or for referring to elements of the architecture that employ them.

If there are any diagrams, models, flowcharts, documented scenarios or
use-cases of the system behavior and/or structure, they may be included here
(unless you feel they are complex enough to merit being placed in the Detailed
System Design section). Diagrams that describe a particular component or
subsystem should be included within the particular subsection that describes
that component or subsystem.

Note:

 This section (and its subsections) really applies only to newly developed (or
 yet-to-be developed) portions of the system. If there are parts of the system
 that already existed before this development effort began, then you only need
 to describe the pre-existing parts that the new parts of the system depend
 upon, and only in enough detail sufficient to describe the relationships and
 interactions between the old parts and the new parts. Pre-existing parts that
 are modified or enhanced need to be described only to the extent that is
 necessary for the reader to gain a sufficient understanding of the nature of
 the changes that were made.

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


If a particular component is one which merits a more detailed discussion than
what was presented in the System Architecture section, provide that more
detailed discussion in a subsection of the System Architecture section (or it
may even be more appropriate to describe the component in its own design
document). If necessary, describe how the component was further divided into
subcomponents, and the relationships and interactions between the subcomponents
(similar to what was done for top-level components in the System Architecture
section).

If any subcomponents are also deemed to merit further discussion, then describe
them in a separate subsection of this section (and in a similar fashion).
Proceed to go into as many levels/subsections of discussion as needed in order
for the reader to gain a high-level understanding of the entire system or
subsystem (but remember to leave the gory details for the Detailed System
Design section).

If this component is very large and/or complex, you may want to consider
documenting its design in a separate document and simply including a reference
to it in this section. If this is the option you choose, the design document
for this component should have an organizational format that is very similar
(if not identical to) this document.

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

A description of any and all resources that are managed, affected, or needed by
this entity. Resources are entities external to the design such as memory,
processors, printers, databases, or a software library. This should include a
discussion of any possible race conditions and/or deadlock situations, and how
they might be resolved.

#### Processing

A description of precisely how this components goes about performing the duties
necessary to fulfill its responsibilities. This should encompass a description
of any algorithms used; changes of state; relevant time or space complexity;
concurrency; methods of creation, initialization, and cleanup; and handling of
exceptional conditions.

#### Interface/Exports

The set of services (resources, data, types, constants, subroutines, and
exceptions) that are provided by this component. The precise definition or
declaration of each such element should be present, along with comments or
annotations describing the meanings of values, parameters, etc. .... For each
service element described, include (or provide a reference) in its discussion a
description of its important software component attributes (Classification,
Definition, Responsibilities, Constraints, Composition, Uses, Resources,
Processing, and Interface).

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
