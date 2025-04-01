# 4.Switching::Midterm 1 notes

## <!-- Introduction to Switching Techniques - Basic Concepts -->

What is the problem with direct links (full mesh) among all end systems as the number of nodes grows?

***

Direct links (full mesh) among all end systems **does not scale** to a large number of nodes because the **number of links grows with $O(n^2)$**.

## <!-- Introduction to Switching Techniques - Solution to Scalability -->

What is the solution to the scalability problem of direct links in large networks?

***

The solution is to **introduce intermediate devices called switches** that allow the **sharing of the capacity of links by multiple data transfers**.

## <!-- Introduction to Switching Techniques - Function of Switches -->

What is the primary function of switches in a network?

***

Switches **forward “data”** -- in the past, a signal -- from the **source end-system to destination end system(s)**.

## <!-- Packet Switching Sub-types -->

What are the two main sub-types of packet switching?

***

The two main sub-types of packet switching are:

* **Datagram**
* **Virtual circuits**

## <!-- Datagram Packet Switching -->

Explain how packet forwarding works in the datagram sub-type of packet switching. Is packet order guaranteed? Is signaling required? Provide examples.

***

In datagram packet switching, packets are forwarded **based on the destination address**. Datagrams **may follow different paths** to the destination, and **packet order is not guaranteed**. **No signaling is required** to set up a path for datagrams. Examples include **IP, IPv6, ethernet, Fiber Channel**.

## <!-- Virtual Circuits Packet Switching -->

Explain how packet forwarding works in the virtual circuits sub-type of packet switching. Is a path established beforehand? What are the phases involved in switched virtual circuits (SVC)? Provide examples.

***

In virtual circuits packet switching, **a path (a virtual circuit) is previously established** before transmitting packets. Packet forwarding is based on **labels with a link-scope meaning**. Types include “switched” (SVC) and permanent (PVC). Phases for SVC are: **SET UP, DATA TRANSMISSION, VC RELEASE**. Examples include **X.25 (obsolete), Frame Relay (obsolete), ATM (fixed-size packets called cells), MPLS**.

## <!-- Switching Unit Granularity - Circuit Switching -->

What is the switching unit (granularity) for circuit switching with TDM and FDM, and what are some technologies under exploitation?

***

For circuit switching:

* With **TDM**, the switching unit is a **Timeslot (TDM channel)**, and   technologies include **CS Telephony*, SDH*, OTN (ODU switching)**.
* With **FDM**, the switching unit is a **wavelength**, and the technology is   **OTN (lambda switching)**.

## <!-- Switching Unit Granularity - Packet Switching -->

What is the switching unit (granularity) for packet switching with datagrams and virtual circuits, and what are some technologies under exploitation?

***

For packet switching:

* With **Datagrams**, the switching unit is a **Packet (L3) or Frame (L2)**,   and technologies include **IP, ethernet, FiberChannel, Infiniband, PCIExpress**.
* With **Virtual Circuits**, the switching unit is a **Frame or cell**, and   technologies include **MPLS, ATM***.

## <!-- Comparing PS and CS - Data Handling -->

How is data handled by switches in an ideal scenario for Packet Switching (PS) and TDM Circuit Switching (CS)?

***

In an ideal scenario:

* **Packet Switching (PS)** handles data **“per-packet”**.
* **TDM Circuit Switching (CS)** handles data **“per-byte”** switching.

## <!-- Comparing PS and CS - Store & Forward and Queueing -->

What are the implications of store & forward and queueing for Packet Switching (PS) and TDM Circuit Switching (CS)?

***

The sources pose these as questions for comparison, indicating they are key differentiating factors:

* **Implications of store & forward and queueing for PS: ?**
* **Implications of store & forward and queueing for TDM CS: ?**

## <!-- QoS Parameters -->

List some fundamental Quality of Service (QoS) parameters.

***

Some fundamental Quality of Service (QoS) parameters include:

* **Throughput (b/s and pps)**
* **Average delay, RTT**
* **Packet Loss Ratio**
* **Jitter (delay variation)**
* **Availability**

## <!-- Link QoS Parameters -->

What are some QoS parameters specific to a link?

***

QoS parameters specific to a link include:

* **BER (Bit Error Rate)**
* **PER (Packet Error Rate)**

## <!-- Circuit Switching QoS Parameters -->

What are some QoS parameters specific to Circuit Switching?

***

QoS parameters specific to Circuit Switching include:

* **Blocking probability**
* **Set-up delay**

## <!-- Throughput Types -->

What are the different types of throughput mentioned?

***

Different types of throughput mentioned are:

* **“instantaneous” rate**: rate in a relatively short time interval   (1ms-10ms-1s)
* **average rate**: rate over a longer period of time (transfer, 1min-…)
* **goodput**: the application level throughput, i.e., the number of useful   information bits delivered by the network to a certain destination per unit of time.

## <!-- Goodput Definition -->

Explain the concept of **Goodput**.

***

**Goodput** is the **application level throughput**, which is the **number of useful information bits** delivered by the network to a certain destination **per unit of time**.

## <!-- IPDV -->

What is IPDV and how is instantaneous IPDV calculated for two packets?

***

**IPDV** stands for **IP Packet Delay Variation**. Instantaneous IPDV for two packets (p1 and p2) is calculated as: `ipdv = delay(p1) - delay(p2)`.

## <!-- Availability (QoS) -->

Define Availability as a QoS parameter and provide the formula.

***

**Availability (A)** is the **fraction of time** that a circuit/system/link/network works according to its specification. The formula is:

$$ A = \frac{MTBF}{MTBF+MTTR} = 1 - U = 1 - \frac{MTTR}{MTBF+MTTR} $$

Where MTBF is Mean Time Between Failures and MTTR is Mean Time To Repair.

## <!-- Networked Application Taxonomy - Real-time vs. Elastic -->

Differentiate between Real-time and Elastic networked applications based on their tolerance to loss and delay.

***

* **Real-time applications** are typically **delay sensitive** and can be   **loss tolerant** or **loss intolerant** depending on the specific application (e.g., VoIP is delay sensitive and loss intolerant for quality, while streaming can tolerate some loss) [7-9].
* **Elastic applications** (e.g., file transfer, email) are typically **loss   intolerant but delay tolerant**.

## <!-- Internet QoS Today -->

What is the state of Internet QoS today?

***

Today, the Internet primarily operates on a **best-effort** service model.

## <!-- QoS Tools - Loss -->

What end-to-end and network tools are mentioned for addressing packet loss in QoS?

***

Tools for addressing packet loss include:

* **End-to-end:**
* **Retransmission**
* **FEC (Forward Error Correction)**
* **Time-bounded retransmission**
* **Network:**
* **Over-provisioning**

## <!-- QoS Tools - Delay -->

What end-to-end and network tools are mentioned for addressing delay in QoS?

***

Tools for addressing delay include:

* **End-to-end:**
* **Buffering**
* **Network:**
* **Over-provisioning**

## <!-- Multimedia Application Characteristics -->

What are the fundamental characteristics of multimedia applications regarding delay and loss?

***

Fundamental characteristics of multimedia applications:

* Typically **delay sensitive** (end-to-end delay, delay jitter)
* Generally **loss tolerant**: infrequent losses cause minor glitches
* They are the **antithesis of file transfer applications**, which are loss   intolerant but delay tolerant.

## <!-- Streaming Stored Multimedia - Initial Delay -->

For stored streaming multimedia, what is a generally acceptable initial delay?

***

For stored streaming multimedia, a **5-second initial delay is generally OK** .

## <!-- Streaming Stored Multimedia - Command Effect Delay -->

For stored streaming multimedia, what is an acceptable delay until a command (pause, rewind, etc.) takes effect?

***

For stored streaming multimedia, a delay of **1-2 seconds until a command effect is generally OK**.

## <!-- Real-Time Interactive Multimedia Requirements -->

What are the key requirements for real-time interactive multimedia applications?

***

Key requirements for real-time interactive multimedia applications include:

* **Guaranteed rate**
* **End-to-end delay requirements** (e.g., audio: < 150 msec good, < 400 msec   OK)

## <!-- Network QoS Mechanisms -->

What are the two main ways to provide QoS in networks?

***

The two main ways to provide QoS are:

* To **introduce mechanisms at the network level** to guarantee the QoS.
* To **use application-level techniques** to mitigate (as best possible)   effects of delay, loss, etc..

## <!-- Network QoS Mechanisms - Packet Scheduling -->

What is a key network QoS mechanism for managing the order in which packets are sent?

***

A key network QoS mechanism is **Packet Scheduling**.

## <!-- Work-Conserving Scheduling Algorithms -->

List some examples of **work-conserving** packet scheduling algorithms.

***

Examples of **work-conserving** packet scheduling algorithms include:

* **FCFS (First-Come, First-Served)**
* **PQ (Priority Queueing)**
* **RR (Round Robin), WRR (Weighted Round Robin)**
* **GPS (Generalized Processor Sharing), Bitwise-RR (theoretical)**
* **WFQ (Weighted Fair Queuing), PGPS (Packet-by-packet GPS)**
* **DRR (Deficit Round Robin)**
* **Virtual Clock**
* **Delay-EDD (Earliest Due Date)**
* **CBQ (Class-Based Queueing)**
* **Worst-case Fair WFQ (WF2Q)**
* **SCFQ (Self-Clocked Fair Queueing)**
* **Start Time FQ**
* **Core State FQ**

## <!-- Non-Work-Conserving Scheduling Algorithms -->

List some examples of **non-work-conserving** packet scheduling algorithms.

***

Examples of **non-work-conserving** packet scheduling algorithms include:

* **Jitter-EDD**
* **Stop-and-Go**
* **HRR (Hierarchical RR)**
* **Rate-Controlled Static priority**

## <!-- Goals of Scheduling Algorithms -->

What are some general goals of packet scheduling algorithms?

***

General goals of packet scheduling algorithms include:

* **Fairness**
* **Traffic Control**:
* **Rate (avg, peak, mbs)**
* **QoS**: (absolute or relative)
* **Delay**
* **Jitter**
* **Loss**

## <!-- Work-Conserving vs. Non-Work-Conserving -->

Briefly describe the difference between “Non-work-conserving” and “Work-conserving” scheduling algorithms.

***

* **Work-conserving** scheduling algorithms will always transmit a packet if   there is one available. They never leave the link idle if there is traffic to send.
* **Non-work-conserving** scheduling algorithms may leave the link idle even if   there are packets waiting to be sent, for example, to control jitter by enforcing specific transmission times or slotting.

## <!-- Priority Queueing Operation -->

How does Priority Queueing (PQ) work? Which priority class is served first? What are the potential implications?

***

In Priority Queueing (PQ), **priority class i is served only if all lines j < i are empty**. The **highest priority class has the least delay, highest throughput, and lowest loss**. A potential implication is the **starvation of lower priority classes** if higher priority queues are always busy.  Packets within a given priority queue are served on a **First Come First Served (FCFS)** basis.

## <!-- Max-min Fair Sharing Objective -->

What is the objective of max-min fair sharing?

***

The objective of **max-min fair sharing** is to **maximize the share of the sessions that demand fewer resources**. It allocates the smallest of all demands from all flows first and then distributes remaining resources equally among competing flows.

## <!-- GPS Scheduling Guarantees - Bandwidth -->

What is the bandwidth guarantee provided by GPS scheduling under the assumption of token bucket traffic generation?

***

Under the assumption that traffic is generated by a token bucket (ri, bi), GPS scheduling provides a guarantee for the assigned bandwidth if $r_i < A ⋅ w_i = R_i$, where $r_i$ is the token bucket rate, $A$ is the total available bandwidth, $w_i$ is the weight assigned to flow $i$, and $R_i$ is the guaranteed reserved rate for flow $i$.

## <!-- GPS Scheduling Guarantees - Delay -->

What is the queuing delay guarantee provided by GPS scheduling?

***

GPS scheduling provides a guarantee for the queuing delay, which **depends directly on the assigned bandwidth ($R_i$)**, as it determines the time it takes to empty the buffer.

## <!-- WFQ as an Emulation of GPS -->

What is WFQ and how does it relate to GPS?

***

**WFQ (Weighted Fair Queuing)** is a **work-conserving algorithm** that allows the **emulation of GPS in a discrete environment** (packet-by-packet version of GPS). It attempts to implement a Bitwise round robin by selecting the packet whose processing would have been completed first under GPS and sending it.

## <!-- Deficit Round Robin (DRR) -->

Briefly describe the Deficit Round Robin (DRR) scheduling algorithm.

***

Deficit Round Robin (DRR) maintains a **deficit counter (DC)** for each queue, initialized to zero. In each round, each active queue receives a **quantum** (a certain number of bits to be served). The deficit counter is incremented by the quantum. Packets are dequeued as long as their size is less than or equal to the deficit counter, and the deficit counter is decreased by the packet size . If a queue becomes empty, its deficit counter is reset. Queues that still have packets after a round retain their remaining deficit for the next round.

## <!-- Network QoS Mechanisms - Queue Management Objective -->

What is the objective of a packet buffer in queue management? What happens if the buffer is always full?

***

The objective of a packet buffer is **absorbing transient packet bursts**.  If the buffer is always full, **packet dropping** occurs.

## <!-- Packet Dropping Strategies -->

What are the two main categories of packet dropping strategies?

***

The two main categories of packet dropping strategies are:

* **Forced dropping**: occurs due to **buffer overflow**.
* **Preventive dropping**: occurs **before overflow**, often based on a   threshold.

## <!-- RED Queue Management -->

Explain the Random Early Detection (RED) queue management technique. How does it calculate the drop probability? What are its effects?

***

**Random Early Detection (RED)** drops packets with a **probability that depends on the average queue size**. The **average queue length (AvQLen)** is calculated using an **exponentially weighted moving average (EWMA)**: $AvQLen(t) = (1-w)⋅AvQLen(t-1) + w ⋅QLen(t)$. The **packet drop probability (Pdrop)** is calculated based on where the average queue length lies between a minimum threshold (minth) and a maximum threshold (maxth): $P_{drop} = Maxp ⋅ (AvQLen(t) - minth) / (maxth - minth)$. Effects of RED include avoiding permanent overflow, reducing average latency, absorbing instantaneous bursts, lowering loss, spreading losses over multiple sources, and reducing synchronization.

## <!-- WRED -->

What is WRED and how does it relate to RED?

***

**WRED (Weighted RED)** is an extension of RED that **allows differentiation of packet drop probability between traffic classes**. It is used in the DiffServ model.

## <!-- QoS Contract - Traffic Contract Specification -->

What is the purpose of a Traffic Contract?

***

The objective of a Traffic Contract is **specification**.

## <!-- QoS Contract Models for Source Traffic -->

List the two main models for source traffic in a QoS contract mentioned.

***

The two main models for source traffic mentioned are:

* **Leaky Bucket**
* **Token Bucket**

## <!-- Leaky Bucket Model -->

Describe the Leaky Bucket model for traffic shaping. What are its key parameters and effects?

***

The Leaky Bucket model aims to **send data at regular intervals** to the network. It operates with a **credit to send n data bytes in a T_tick time interval**, ensuring the **data rate never exceeds r (bytes/s) = n / T_tick**. It allows for **buffering up to a limited amount of b bytes (bucket size)** . As a shaper, it **transforms an impulsive input into a regular flow** and **may add delay**.

## <!-- Token Bucket Model -->

Describe the Token Bucket model for traffic shaping. What are its key parameters and effects?

***

The Token Bucket model uses a **“Credit” system based on tokens**. Tokens are generated periodically at a **rate “r”**. A packet can be sent **if enough tokens are in the bucket**. Sending below the average rate allows for **accumulation of tokens**, up to a **maximum number “b” (bucket size)**.  It allows for **modeling bursty traffic** but **limits the size of a burst**. A **peak rate “p”** can be defined to limit the speed at which the bucket is emptied. As a shaper, it **smooths traffic** while allowing some bursts and **may add delay**.

## <!-- Traffic Conditioning Objective -->

What is the objective of traffic conditioning? What are the roles of a policer and a shaper?

***

The objective of **traffic conditioning** is to **enforce a Traffic Contract**.

* A **Policer** (typically on the operator side) checks for compliance.   Non-conformant traffic can be discarded or marked.
* A **Shaper** (typically on the client side) delays traffic to bring it into   compliance with the profile.

## <!-- Leaky Bucket as Policer/Marker -->

How can a Leaky Bucket be used as a policer or marker?

***

As a dropper/marker, a Leaky Bucket **drops packets if the bucket is full** when traffic arrives exceeding the rate.

## <!-- Token Bucket as Policer/Marker -->

How can a Token Bucket be used as a policer or marker?

***

As a dropper/marker, a Token Bucket will **drop or mark packets if there is no credit (not enough tokens) available** when they arrive.

## <!-- SR-TCM -->

What is SR-TCM and what are its key components?

***

**SR-TCM (Single Rate Three Color Marker)** uses **two token buckets**: **Committed (C)** and **Excess (E)**, with maximum burst sizes **CBS** and **EBS** respectively. Both buckets are filled with tokens at the same rate **CIR (Committed Information Rate)**. However, the E bucket only increments every Tclock if the C bucket is full. It can mark packets as green, yellow, or red based on token availability.

## <!-- Centralized Admission Control -->

Briefly describe centralized admission control. What are its potential drawbacks?

***

**Centralized Admission Control** uses a **central server (bandwidth broker, PCE, SDN controller)** to decide whether to accept new flows. Potential drawbacks include being **not very robust** and resolving contention only at the signaling phase.

## <!-- Distributed Admission Control -->

Briefly describe distributed admission control. What are its requirements and potential issues?

***

**Distributed Admission Control** involves **each node deciding locally** whether to accept a new flow and reserve resources. It **requires reservation protocols (e.g., RSVP)**. It is considered **more robust and scalable** but can still face **contention problems at the signaling phase**.

## <!-- DiffServ Model - PHBs -->

Does the DiffServ architecture standardize services or PHBs?

***

The DiffServ architecture **standardizes PHBs (Per Hop Behaviors)**, **NOT services**. It also does not standardize the PHB implementation. Services can be defined using the PHBs.

## <!-- DiffServ Domain -->

What is a DiffServ Domain?

***

A **DS Domain** is a **network with a set of routers with the same policies** .

## <!-- Qualitative DiffServ Service Examples -->

Provide examples of qualitative types of service in DiffServ. How can they be checked?

***

Examples of qualitative types of service in DiffServ include:

* **Transport of low latency traffic**
* **Transport of low loss traffic** They can **only be checked by comparison**.

## <!-- Quantitative DiffServ Service Examples -->

Provide examples of quantitative types of service in DiffServ. How can they be verified?

***

Examples of quantitative types of service in DiffServ include:

* **90% of the traffic in a class will experience a delay of less than 50 ms**.
* **The loss of traffic in a given sample will be less than 5%**.
* **The class makes use of at least 20% of the link capacity; the spare   capacity of the link is shared in a fair manner**.  They **can be verified, without needing comparisons**.

## <!-- DiffServ Terminology - SLA -->

What does SLA stand for in the context of DiffServ?

***

**SLA** stands for **Service Level Agreement**. It's a legal service contract with general terms and conditions.

## <!-- DiffServ Terminology - SLS -->

What does SLS stand for in the context of DiffServ?

***

**SLS** stands for **Service Level Specification** or **DiffServ’s TCA (Traffic Conditioning Agreement)**. It includes technical terms and conditions on how client traffic will be treated, such as DSCPs and PHBs.

## <!-- DiffServ Terminology - PHB -->

What does PHB stand for in the context of DiffServ?

***

**PHB** stands for **Per Hop Behaviour**. It describes the externally observable router behavior upon a given DSCP.

## <!-- DiffServ Terminology - DSCP -->

What is DSCP in the context of DiffServ? Where is it located?

***

**DSCP** stands for **DiffServ Code Points**. It is located in the **DS Field (Differentiated Services) in the packet header** [34-36]. Edge routers mark packets with DSCP stamps.

## <!-- DiffServ Router Functions -->

List the main functional modules of a DiffServ router.

***

The main functional modules of a DiffServ router are:

* **Classifier**
* **Marker**
* **Meter**
* **Shaper**
* **Discard (Dropper)**
* **Queue management**
* **Packet scheduling**
* **Admission Control**
* **Policing**

## <!-- DiffServ Classifier -->

What is the role of the Classifier in a DiffServ router? What are the types of classification?

***

The **Classifier** selects packets based on the values of one or more packet header fields. Types of classification include:

* **BA (Behavior Aggregate)**: based on the DSCP value in the DS byte (in the   core).
* **MF (Multi Field)**: based on multiple header fields (at the ingress/edge) .   Examples include <IPv6 source address, FlowID> and application-level bandwidth managers.

## <!-- DiffServ Marker -->

What is the role of the Marker in a DiffServ router?

***

The **Marker** inserts the appropriate **DSCP value in the DS byte** of a packet so that it receives appropriate service (PHB) in subsequent routers .

## <!-- DiffServ Meter -->

What is the role of the Meter in a DiffServ router?

***

The **Meter** compares the incoming flow with the negotiated traffic profile and can:

* Pass conforming packets.
* Pass violating packets to the shaper and dropper.
* Remark violating packets with a lower grade service using a different DSCP .
* Be used for accounting management.

## <!-- DiffServ Shaper -->

What is the role of the Shaper in a DiffServ router?

***

The **Shaper** may introduce **delay** to bring a flow into compliance with its profile. It typically has a limited buffer, and packets that don’t fit may be discarded. Shapers can accept bursts and then send traffic at an acceptable rate.

## <!-- DiffServ Discard/Dropper -->

What is the role of the Discard or Dropper in a DiffServ router?

***

The **Dropper** performs a **policing function** by simply **dropping packets that are out of profile**. It can be considered a special instance of a shaper with no buffer.

## <!-- Assured Forwarding (AF) PHB Goal -->

What is the service goal of the Assured Forwarding (AF) PHB in a DS domain?

***

The service goal of AF PHB is to **offer different levels of forwarding guarantee to clients that have subscribed to the service**, for example, gold, silver, bronze services.

## <!-- Assured Forwarding (AF) Classes and Discard Priorities -->

How many independent AF classes are defined, and how many packet discard priorities are there within each class? How are these implemented?

***

There are **4 independent AF classes**. Within each class, there are **3 packet discard priorities**. Discard priorities are typically implemented using **WRED** at points of congestion.

## <!-- Expedited Forwarding (EF) PHB Goal -->

What is the goal of the Expedited Forwarding (EF) PHB? What type of traffic is it often used for?

***

The goal of the Expedited Forwarding (EF) PHB is to provide a **virtual wire** with low loss, low delay, and low jitter. It is often used for **delay-sensitive traffic like Voice over IP**. It aims for an abstracted link with a guaranteed minimum bandwidth.

## <!-- IntServ Service Types -->

What are the three end-to-end reservation service types specified by RFC2210?

***

The three end-to-end reservation service types are:

* **Guaranteed service (GS)**
* **Controlled load service (CL)**
* **Best-effort service**

## <!-- IntServ - Guaranteed Service -->

What type of applications is the Guaranteed Service (GS) in IntServ intended to support? What are its key requirements? How does it compare to DiffServ PHBs?

***

Guaranteed service (GS) is intended to support **inelastic applications** with **low-delay, low-jitter, low-loss, assured bandwidth requirements**, such as VoIP and video. Such applications are typically supported with an **EF PHB** where DiffServ is deployed.

## <!-- IntServ - Controlled Load Service -->

What type of applications is the Controlled Load service (CL) in IntServ intended to support? What does it aim to provide? How does it compare to DiffServ PHBs?

***

Controlled load service (CL) is intended to support **elastic applications with assured bandwidth requirements**. It provides a **QoS closely approximating the QoS that same flow would receive from an unloaded network element**, but uses capacity (admission) control to assure this even when the network element is overloaded. Such applications are typically supported with an **AF PHB** where DiffServ is deployed.

## <!-- IntServ - Best-Effort Service -->

How is the Best-effort service defined in the context of IntServ? How does it compare to DiffServ PHBs?

***

Best-effort service in IntServ is defined as the service that flows receive that have **neither had a successful GS or CL reservation established**.  It is analogous to the service that would be supported with the **default PHB** where DiffServ is deployed.

## <!-- IntServ - RSVP Objectives -->

What is RSVP and what are some of its key objectives and characteristics?

***

**RSVP (Resource reSerVation Protocol)** is a **node-to-node signaling protocol** for making **dynamic reservations**. Key objectives and characteristics include:

* **Multicast-aware**: allows reservation aggregation.
* **Receiver-oriented**: reservations are initiated by the receiver.   Heterogeneous receivers can make different reservations for the same multicast flow.
* **Routing Protocol independent**: separate signaling but designed to follow   the routing. Allows for topology changes.
* **Network protocol independent**: supports IPv4, IPv6, ATM.
* Aims to **load the network minimally**.

## <!-- RSVP - Path Message -->

What is the purpose of an RSVP Path message? Where does it originate and how does it travel? What information does it carry?

***

The RSVP **Path message** is sent by the **source** towards the destination . It follows the **same path as the data flow**. Its purpose is to **identify/characterize the flow and alert routers to wait for reservations coming upstream**. It carries information such as the **source and destination IP addresses** and the **address of the previous router’s output interface (phop)**.

## <!-- RSVP - Resv Message -->

What is the purpose of an RSVP Resv message? Where does it originate and how does it travel? What information does it carry?

***

The RSVP **Resv message** is sent by the **receiver** towards the source.  It follows the **reverse path of the Path message**. Its purpose is to **describe the desired reservation**. It carries information about the **flow specification (FLOW_SPEC)**, including parameters like bandwidth requirements.

## <!-- RSVP - Soft State -->

Explain the concept of 'Soft State' in the context of RSVP. What are the implications?

***

The **Soft State philosophy** in RSVP means that a **reservation has a limited lifetime**. The reservation request **must be refreshed periodically** by sending Path messages from the source and Resv messages from the destination, as if requesting new reservations. This mechanism allows the network to be dynamic and automatically tear down reservations if a flow stops or if routes change without explicit teardown signaling.

## <!-- IntServ Problems -->

List some of the problems associated with IntServ that hindered its widespread deployment.

***

Problems associated with IntServ include:

* **Complexity**
* **Scalability**: "per-flow" reservation problems, requiring classification,   resource management, and signaling per flow.
* **Soft-state**: while dynamic, it introduces significant signaling overhead .
* **Constrained semantics for the service models**: only "guaranteed" and   "controlled load" were well-defined.
* **Slow deployment**: poor coexistence with "no QoS" environments, requiring   changes in all routers for it to work.

## <!-- Packet Forwarding Devices - Definition -->

What is a packet forwarding device?

***

A **packet forwarding device** is an element that **receives packets and processes them with the aim of getting them to the destination**.

## <!-- Types of Packet Forwarding Devices -->

List some examples of packet forwarding devices.

***

Examples of packet forwarding devices include:

* The **Internet access router at home**
* An **Ethernet switch** on a campus or office
* A **core router of the Internet**
* A **data center switch**
* Devices with additional functionality like **firewall, load balancer,   bandwidth manager, NAT**

## <!-- Classification of Packet Forwarding Devices by Layer -->

How are packet forwarding devices classified based on the network layer at which they perform forwarding?

***

Packet forwarding devices are classified as:

* **Switches (or bridges)** when they use **L2 (Layer 2)** information, for   example, Ethernet.
* **Routers** when they use **L3 (Layer 3)** information, for example, IPv4 or   IPv6.

Most devices already support multiple functionalities (L2/L3 forwarding, ACLs, MPLS, etc.).

## <!-- Elements of a Packet Forwarding Device -->

List the key elements of a packet forwarding device.

***

Key elements of a packet forwarding device include:

* **Ports**
* **Decision logic**
* **Buffers**
* **Fabric (Switching Fabric)**
* **Scheduling**
* **Control and Management**

## <!-- Function of Ports in a PFD -->

What is the function of ports in a packet forwarding device?

***

**Ports** are where **packets are sent and received** over a packet forwarding device. They can have different speeds and use different transmission media.

## <!-- Function of Decision Logic in a PFD -->

What is the function of the decision logic in a packet forwarding device? What is a common way it is implemented?

***

The **decision logic** processes the packets, typically the header fields, and **decides what to do with them** (e.g., forward, drop, mark). It often involves a sequence of **rule table lookup operations known as a pipeline**. It needs to work at wire speed.

## <!-- Function of Buffers in a PFD -->

What is the function of buffers in a packet forwarding device? Where can they be located?

***
 **Buffers** store packets temporarily:

* **At the input** until a decision is made.
* **At the output** until they are sent.  Buffers can be **shared or per   port**. Buffering increases delay.

## <!-- Function of Fabric in a PFD -->

What is the function of the fabric (switching fabric) in a packet forwarding device?

***

The **fabric (switching fabric)** is responsible for **moving the packets from the input port to the output port** within the packet forwarding device.

## <!-- Function of Scheduling in a PFD -->

What is the function of scheduling in a packet forwarding device? Where is it commonly done?

***

**Scheduling** decides **when to send a packet** to enforce Quality of Service (QoS). It is commonly linked to buffers and **done at the egress (output) port**.

## <!-- Function of Control/Management in a PFD -->

What are the typical functions of the control and management plane in a packet forwarding device?

***

The control and management plane typically:

* **Configures the PFD** (tables, buffers, etc.).
* **Handles control plane protocols** like BGP.
* **Keeps statistics on performance (Telemetry)**.
* In SDN, most functionality is offloaded to a central controller.

## <!-- Virtual Routers -->

What are virtual routers and where are they typically used? What are some technologies used to achieve good performance?

***

**Virtual Routers** are **implemented in software** and used in **Virtual Environments**. Technologies used to achieve good performance (latency, pps) include:

* **Data Plane Development Kit (DPDK)**
* **Open Data Plane (ODP)**
* **Vector Packet Processing (VPP)**

## <!-- Performance of Routers - Throughput vs. PPS -->

How is the performance of a router typically stated? Why is packets per second (pps) often more important than throughput in b/s?

***

The performance of a router is stated in terms of **throughput (b/s)**. However, since routers forward packets, **packets per second (pps)** is often more important because the processing is done per packet. Throughput depends on the packet size, so a higher b/s rate with large packets might not indicate the ability to handle a high rate of small packets.

## <!-- Formula for Throughput (T) -->

What is the formula relating throughput (T), number of ports (P), and line rate (R)?

***

$T = P × R$

## <!-- Formula relating Line Rate (R), Packet Size (S), and PPS (Ps) -->

What is the formula relating line rate (R), packet size (S), and packets per second (Ps)? What is a commonly used smallest packet size for calculation?

***

$R = S × Ps$. A commonly used smallest packet size for worst-case pps calculation is **64 Bytes** (often considering TCP ACK).

## <!-- Factors Contributing to Processing Complexity in Routers -->

List some factors that contribute to the processing complexity in routers.

***

Factors contributing to processing complexity include:

* Simple **Ethernet switching** vs. complex tasks.
* Looking up in **large routing tables** (Internet scale).
* Performing **Access Control List (ACL) checks** against many rules.
* **Tracking existing connections** as in NAT.
* Performing **classification on many packet fields** as in SDN.
* The combination of several of these tasks.

## <!-- Trade-off between Flexibility and Speed in Router Processing -->

What is the general trade-off between flexibility and speed in packet processing for routers (hardware vs. software)?

***

In general:

* **Hardware** implementations (e.g., ASICs) are **fast** but **not very   flexible**.
* **Software** implementations are **flexible** but generally **slower** .

## <!-- Benefits of Modularity in Routers -->

What are the benefits of modularity in large network devices?

***

Modularity helps with:

* **Reliability and availability** (redundant modules, module swap)
* **Capacity growth** (adding ports)
* **Adding new features**
* Impacts **cost**.

## <!-- Factors Driving Cost of Routers -->

What are some key factors that drive the cost of routers?

***

The cost of routers is driven by:

* **Research and Development**
* **Bill of Materials (BoM)**
* **Marketing and sales**
* **Integration** to lower costs (System on Chip - SoC).

## <!-- Packet Flow in a Router - General Stages -->

What are the general stages of packet flow in a router?

***

General stages of packet flow in a router include:

* **Ingress packet processing** at the input network interface [63-65].
* Interaction with the **Forwarding Engine** to determine the next hop.
* Temporary storage in **Buffer Memory**.
* Transfer to the appropriate egress card via the **Backplane Interface** .
* **Egress packet processing** at the output network interface.
* Transmission over the output interface.

## <!-- Packet Context in a Router -->

What is a "packet context" in a router and what is its purpose?

***

A **packet context** is a **data structure (an “internal packet”)** that serves as a **scratch pad for carrying information between different stages of packet processing** inside the router. It stores information such as ingress/egress interface details, L2/L3 headers, next-hop information, etc. .

## <!-- Fast Path vs. Slow Path in a Router -->

Differentiate between the Fast Path and the Slow Path of packet processing in a router. Provide examples of tasks for each.

***

* **Fast Path (Time-critical)**: Deals with the **majority of packets** and   needs to be highly optimized for high forwarding rates (implemented in hardware in high-performance routers). Examples:
* **Header processing**: packet validation, TTL and checksum calculation .
* **Forwarding**: destination address lookup, packet classification, buffering,   queue management, and scheduling.
* **Slow Path (Non–time-critical)**: Handles **management, control, and error   handling** (typically implemented in software on the Route Processor) [68, 69]. Examples:
* **Routing protocol updates**.
* **Processing packets for router management** (e.g., SNMP, Telnet).
* **Handling exceptions and errors**.

## <!-- Memory Organization in Routers - Pools -->

Explain the concept of memory pools for packet queuing in routers. What is the problem they aim to solve and a potential issue?

***

To optimize memory usage for queuing packets, memory can be organized in **pools**, where **a pool is a large array of memory blocks of the same size** (often derived from the MTU). The problem they aim to solve is efficient allocation and deallocation of memory for packets. A potential issue is that **packets are normally smaller than the link’s MTU**, leading to wasted space if only one large pool size is used.

## <!-- Memory Organization in Routers - Public vs. Private Buffers -->

Explain the concept of public vs. private buffers in router memory organization. What problem does this solve?

***

To prevent one interface from monopolizing all buffer capacity and causing starvation for others, some buffers are assigned for the **exclusive use of each interface (private buffers)**. The remaining buffers are organized as **public buffers / system buffers** and are **shared among all interfaces** .

## <!-- Hardware-Aided Switching - Examples -->

List some examples of hardware components used to accelerate packet switching in high-performance routers.

***

Examples of hardware components used for hardware-aided switching include:

* **Custom ASICs (Application-Specific Integrated Circuits)**
* **Network Processors (NPs)**
* **Ternary Content Addressable Memories (TCAMs) / Search Processors**
* **FPGAs (Field-Programmable Gate Arrays)**

## <!-- Switching Fabric - Need for Control -->

Why is it important to control the switching fabric in a router?

***

It is important to control the switching fabric to **calculate and establish the connections** between input and output ports so that packets can be forwarded correctly.

## <!-- Switching Fabric - Challenge of Variable Packet Sizes -->

What is a challenge posed by variable packet sizes in controlling the switching fabric? What is a common solution?

***

Variable packet sizes make it complex to calculate connections because **each cross-point will be available at a different time** (when a packet finishes transmission through the fabric). This leads to **high complexity of control** . A common solution is to use a **fixed-size switching unit** where packets are split into **chunks or cells**, and decisions are taken at fixed intervals, simplifying scheduling. However, this requires additional circuitry for **segmentation and reassembly (SAR)**.

## <!-- Switch Fabrics - Shared Medium (Bus) - Limits and Advantages -->

What are the physical speed limit and an advantage of a shared medium (bus) switching fabric?

***

* **Physical limit of speed of bus**: approximately **NxR** (N = number of   ports, R = line rate). Address filters and output buffers must operate at this speed.
* **Advantage**: **Natural implementation of multicast and broadcast**.

## <!-- Switch Fabrics - Shared Memory - Limits and Advantages -->

What is the physical speed limit and an advantage of a shared memory switching fabric?

***

* **Physical limit of access time of RAM**: needs to read/write at a speed of   **2N times the speed of ports (2NR)**.
* **Advantage**: **Efficient use of memory** due to statistical sharing of   output buffers. Requires minimum memory for a target loss rate.

## <!-- Head-of-Line (HOL) Blocking -->

What is Head-of-Line (HOL) blocking in input-buffered switches?

***

**Head-of-Line (HOL) blocking** occurs in input-buffered switches when a **packet at the front of an input queue is blocked from reaching its desired output port** (because the output port is busy), and this **blocking delays other packets behind it in the same input queue**, even if those packets are destined for different, available output ports [77-79].

## <!-- Virtual Output Queuing (VOQ) -->

What is Virtual Output Queuing (VOQ) and how does it aim to solve HOL blocking?

***

**Virtual Output Queuing (VOQ)** is a technique where **each input port maintains a separate queue for each output interface**. By decoupling the queuing for different output ports at the input, a packet destined for an available output is not blocked by a packet at the front of the same input queue that is destined for a busy output. This helps to mitigate the HOL blocking problem.

## <!-- Switch Fabrics - Crossbar Switch - Output-Queued - Advantages and Disadvantages -->

What are the advantages and disadvantages of an Output-Queued Crossbar Switch?

***

**Advantages of Output-Queued Crossbar Switch:**

* **No Head-of-line (HOL) blocking**: achieves **100% performance**.
* **No input traffic scheduling is required**.

**Disadvantages of Output-Queued Crossbar Switch:**

* The **crossbar and memory need to run at RxN** (speed-up = N, where N is the   number of ports).
* **Less scalable architecture**.

## <!-- Switch Fabrics - Crossbar Switch - Input-Queued - Need for Speed-Up -->

Why do Input-Buffered switch fabrics sometimes need a speed-up factor greater than 1? What is a Combined Input-Output Queued (CIOQ) switch?

***

Input-buffered switches can experience output contention (multiple inputs needing the same output) and HOL blocking (even with VOQ, if multiple packets at the same input are destined for different free outputs, one might have to wait). To mitigate these and approach 100% throughput, the **switch fabric speed is often increased by a factor S times faster than the line rate (speed-up)**. A **Combined Input-Output Queued (CIOQ) crossbar switch** uses both input and output buffering and often incorporates a speed-up factor (typically between 2 and 5, theoretically up to N).

## <!-- Switch Fabrics - Distributed Output-Buffered - Advantages and Disadvantages -->

What are the advantages and disadvantages of a Distributed Output-Buffered Switch?

***

**Advantages of Distributed Output-Buffered Switch:**

* **Switch fabric (N-buses), AF and buffers run at line-speed R** - no need to   speed-up.
* **Optimal throughput: 100%**.
* **Better latency control (QoS guarantees)**.

**Disadvantages of Distributed Output-Buffered Switch:**

* **Cost**: **Quadratic N^2 growth of buffers**.
* **Modularity**: **limit to number of ports N**.

## <!-- Switching Fabric Control Algorithm Requirements -->

What are some key requirements for switching fabric control algorithms in input-queued switches with VOQ?

***

Requirements for switching fabric control algorithms include:

* **Simple to implement**
* **Fast**
* **Fair**
* **Starvation free** (no endless waiting in VOQ)
* **High throughput**

## <!-- Parallel Iterative Matching (PIM) - Basic Steps -->

Outline the basic steps of the Parallel Iterative Matching (PIM) algorithm for controlling a switch fabric.

***

PIM involves three steps repeated iteratively with free inputs and outputs:

1. **Request**: Each input sends a request to every output for which it has a queued cell.
2. **Grant**: If an output receives multiple requests, it chooses one randomly and notifies each input whether its request was granted.
3. **Accept**: If an input receives multiple grants, it chooses one randomly .

The algorithm stops when no new matching can be found.

## <!-- Round-Robin Matching (RRM) - Basic Steps -->

Outline the basic steps of the Round-Robin Matching (RRM) algorithm for controlling a switch fabric. How does it differ from PIM?

***

RRM involves three steps per iteration, using round-robin selection instead of random:

1. **Request**: Each input sends a request to every output for which it has a queued cell.
2. **Grant**: If an output receives multiple requests, it chooses the first one starting from the highest priority element (marked by its grant pointer, gj), which is updated to the next input after the granted one.
3. **Accept**: If an input receives multiple grants, it chooses the first one starting from the highest priority element (marked by its accept pointer, ai), which is updated to the next output after the accepted one.

The algorithm finishes when there are no new connections in an iteration.  It differs from PIM in its deterministic selection process based on pointers instead of random selection.

## <!-- iSLIP Algorithm - Basic Steps and Key Difference from RRM -->

Outline the basic steps of the iSLIP algorithm for controlling a switch fabric. What is a key difference from RRM that aims to prevent starvation?

***

iSLIP has four steps per iteration with not assigned inputs and outputs:

1. **Request**: Each input sends a request to every output for which it has a queued cell.
2. **Grant**: If an output receives multiple requests, it chooses the first one starting from the highest priority element (gj).
3. **Accept**: If an input receives multiple grants, it accepts the first one starting from the highest priority element (ai). The ai pointer is updated to the next output only in the first iteration of a successful match.
4. **Update**: The gj pointers of the outputs that granted a request that was accepted are updated. The gj pointer is updated to the next input only in the first iteration of a successful grant.

A key difference from RRM that aims to prevent starvation is that **gj pointers are updated only if their grants are accepted**, and the selected pair effectively gets the minimum priority in the next round.

## <!-- Decision Logic in Routers - Introduction -->

What is the role of decision logic in routers? How is the process often structured?

***

The **decision logic analyzes packets** and, based on a set of rules, **decides what actions to take** on each packet. In most cases, the process can be structured as a **sequence of table lookups**.

## <!-- Packet Parsing in Routers -->

What is the first step in the decision-making process for a router upon receiving a packet?

***

The first step is **packet parsing**, where **relevant information is extracted from the packet headers**. This extracted information is then used for subsequent decision-making processes like table lookups.

## <!-- Table Lookup Examples in Routers -->

List some traditional examples of table lookups performed by routers.

***

Traditional examples of table lookups include:

* **Ethernet switching**
* **IP routing**
* **ACLs (Access Control Lists)**

These can be generalized into a table lookup operation on arbitrary packet header fields.

## <!-- Ethernet Switching - Key and Match Type -->

What is the key used for Ethernet switching table lookups, and what type of match is typically performed?

***

The key for Ethernet switching is the **destination MAC address (48 bits)** . The match type is an **exact match bit by bit**.

## <!-- IP Routing - Key and Match Type -->

What is the key used for IP routing table lookups, and what type of match is performed?

***

The key for IP routing is the **destination IP address (32 bits in IPv4, 128 in IPv6)**. The match type is **Longest Prefix Match (LPM)**.

## <!-- Access Control List (ACL) - Key Fields -->

What are some typical fields used as part of the key for Access Control List (ACL) lookups? What type of matching can be involved?

***

Typical fields used in ACL lookups include the **5-tuple**:

* Source IP address
* Source L4 port
* Destination IP address
* Destination L4 port
* Protocol

Matching can involve **exact matches and wildcards** on several fields, as well as flags and port ranges.

## <!-- Decision Pipeline in Routers -->

What is the decision pipeline in a router? Can it be changed?

***

The **decision pipeline** is the **sequence of table lookups** that a router performs on a packet. The pipeline can be **fixed or configurable**, allowing changes to the number and types of tables involved in processing.

## <!-- Implementation of Decision Logic - Main Options for a Single Table -->

What are the main hardware-based and memory/data structure-based options for implementing a single table in decision logic?

***

Main options for a single table implementation include:

* **Hardware-based:**
* **Content Addressable Memory (CAM)** for exact match
* **Ternary Content Addressable Memory (TCAM)** for exact match and wildcard   bits (used for LPM and ACLs)
* **Memory/Data Structure-based:**
* **Standard memories (SRAM or DRAM) combined with a data structure** (e.g.,   hashing, tries)

## <!-- CAM vs. TCAM - Key Difference -->

What is the key difference between CAM and TCAM? What type of matching does each support?

***

The key difference is the type of matching they support:

* **CAM (Content Addressable Memory)** supports **exact match** using binary   '0' and '1' bits.
* **TCAM (Ternary Content Addressable Memory)** supports **exact match** ('0',   '1') **and wildcard ('x') bits**, allowing for prefix matching (LPM) and flexible rule matching (ACLs).

## <!-- Advantages of CAMs/TCAMs -->

What is a primary advantage of using CAMs/TCAMs for table lookups?

***

A primary advantage is that they **provide the result in one memory access** as the comparison is done in hardware within the memory itself.

## <!-- Disadvantages of CAMs/TCAMs -->

What are some disadvantages of using CAMs/TCAMs for table lookups?

***

Disadvantages include:

* **Large area and power consumption** compared to SRAM.
* **Not available in some platforms** like general-purpose computers or FPGAs .
* **Limited ability to support very large tables**.
* **Limited flexibility** as they cannot be easily reused to store   data/actions.

## <!-- Data Structures for Table Lookup - Advantages -->

What are some advantages of using standard memories with data structures for table lookups compared to CAMs/TCAMs?

***

Advantages include:

* They can use **standard SRAM or DRAM memories**.
* The **same memory can be reused for other purposes if needed**, offering more   flexibility.
* Potentially **better scalability** for very large tables (depending on the   data structure).
* Often more suitable for software-based implementations and certain hardware   platforms like FPGAs.

## <!-- Exact Match Lookup with Hashing - Potential Issue -->

What is a potential issue with using hashing with separate chaining for exact match lookups?

***

A potential issue is that **collisions force us to perform several memory accesses per lookup**, and the number of accesses depends on the occupancy and is **not constant**.

## <!-- Cuckoo Hashing - Key Property -->

What is a key property of cuckoo hashing that makes it attractive for exact match lookups?

***

Cuckoo hashing provides a **constant and known worst-case number of memory accesses** for lookups.

## <!-- Longest Prefix Match (LPM) Implementation Approaches -->

What are some approaches mentioned for implementing Longest Prefix Match (LPM)?

***

Approaches mentioned include:

* Implementing LPM as a **sequence of exact match lookups** (potentially using   caching).
* Using a **binary search on prefix lengths**.
* Using **Tries** (binary or multibit).

## <!-- Trie Data Structure for LPM - Basic Concept -->

Explain the basic concept of using a Trie for Longest Prefix Match (LPM).

***

A **trie** is a **tree-based structure** that organizes IP prefixes on a digital basis by using the bits of the prefixes to direct the branching from the root. Each node on level k represents all addresses starting with the same k bits as the path to that node. Nodes corresponding to prefixes contain forwarding information. The longest prefix match is found by traversing the trie based on the bits of the destination address and keeping track of the most specific prefix node visited.

## <!-- Binary Trie - Potential Drawbacks -->

What are potential drawbacks of using binary (1-bit) tries for LPM?

***

Potential drawbacks of binary tries include:

* **Long sequences of one-child nodes may exist**, requiring inspection of bits   even when no branching decision is needed, leading to potentially longer search times.
* **One-child nodes consume memory**.
* Worst-case **lookup time of O(W)** (W is address length) and **memory   requirement O(NW)** (N is number of entries).

## <!-- Path-Compressed Tries - Basic Idea and Benefits -->

What is the basic idea behind path-compressed tries, and what are the benefits?

***

**Path-compression** techniques remove unnecessary one-branch nodes in a binary trie. The basic idea is to store information (e.g., number of skipped bits) in the remaining nodes to allow correct search operations.  Benefits include:

* **Reduced search time** as the search jumps directly to bits where a   significant decision is to be made.
* **Reduced memory consumption** by eliminating one-child nodes.
* Storage requirements can be reduced to **O(N)**.

## <!-- Multibit Tries - Basic Concept and Trade-offs -->

Explain the basic concept of multibit tries for LPM. What are the key trade-offs involved?

***

A **multibit trie** inspects **multiple bits (K, the stride)** of the IP address at each level of the trie, rather than just one bit as in a binary trie . Each node in a K-bit trie has up to 2^K pointers. Prefixes that are not a multiple of K in length may need to be expanded. Key trade-offs involved are between:

* **Search speed**: Larger strides (K) lead to a smaller height of the trie and   thus **faster lookups (O(W/K))**.
* **Memory consumption**: Larger strides increase the number of pointers per   node, potentially leading to a **higher memory requirement (O(2^KNW/K))** .
* **Update complexity**: Prefix expansion with larger strides can make updates   more complex.

## <!-- Typical Multibit Trie Structure in Hardware -->

What is a typical multibit trie structure used in hardware for core network routers?

***

A typical structure uses a **two-level multibit trie with fixed strides**: often **24 bits at the first level and 8 bits at the second level**. The first level is often implemented as a large table. This approach aims to find the longest prefix match in a maximum of two memory accesses, optimizing for the common case where prefixes are 24 bits or less.

## <!-- HOL Blocking Solution in Input-Queued Crossbar Switches -->

Explain how to solve the HOL Blocking in Input-queued (IQ) crossbar switches.

***

HOL blocking in IQ crossbar switches can be significantly mitigated using **Virtual Output Queuing (VOQ)**. In VOQ, each input port maintains a separate queue for each output port. This prevents a blocked packet at the head of a queue (waiting for a busy output) from delaying other packets in the same input queue that are destined for different, available outputs. To effectively utilize VOQ and achieve high throughput, a **scheduling algorithm** is needed to determine which input-output connections to establish in each time slot. Algorithms like **iSLIP** and **RRM** are used for this purpose. Additionally, **increasing the speed of the switching fabric (speed-up)** can also help to reduce the impact of output contention, which can still cause some queuing even with VOQ.

## <!-- Concept of Marker in DiffServ Router -->

Explain the concept of **Marker** in a model of a DiffServ router. Which other elements take part in traffic conditioning?

***

The **Marker** in a DiffServ router is responsible for **inserting the appropriate DSCP (DiffServ Code Point) value into the DS byte of a packet**. This DSCP value determines the PHB (Per-Hop Behavior) the packet will receive in subsequent DiffServ-aware routers.

Other elements that take part in **traffic conditioning** in a DiffServ router include:

* **Meter**: Compares the traffic flow against a defined traffic profile (part   of the SLS).
* **Shaper**: Delays packets to bring the flow into compliance with the traffic   profile.
* **Policer (often implemented by a Meter and Dropper)**: Enforces the traffic   profile by dropping or remarking non-conforming packets.

The meter, marker, shaper, and dropper are collectively known as traffic conditioners.

## <!-- Main Packet Dropping Strategies in QoS -->

Identify the main Packet dropping strategies in QoS.

***

The main packet dropping strategies in QoS are:

* **Forced Dropping**: This occurs when a buffer overflows because it cannot   accommodate any more incoming packets.
* **Preventive Dropping**: This strategy involves dropping packets *before* a   buffer becomes completely full. Techniques like **Random Early Detection (RED)** and its weighted variant **WRED** fall under this category. These methods drop packets probabilistically based on the average queue length or other factors to avoid congestion and improve network performance [20-22].

## <!-- Compare Fast Path and Slow Path of Packet Processing in a Router -->

Compare the ‘Fast Path’ and the ‘Slow Path’ of the packet processing of a router, including examples of the tasks of each one.

***

The **Fast Path** and **Slow Path** are two distinct processing pipelines within a router.

**Fast Path:**

* **Purpose**: Handles the **majority of data packets** that require high-speed   forwarding. It is highly optimized for performance and is typically implemented in hardware (e.g., ASICs).
* **Speed**: Designed to operate at **gigabit/s or even terabit/s** rates to   avoid becoming a bottleneck.
* **Tasks (Examples)**:
* **Header processing**: Parsing packet headers, validating packet integrity   (e.g., checksum), decrementing TTL.
* **Forwarding**: Performing destination address lookup in the forwarding table   to determine the next hop and outgoing interface, packet classification for QoS, basic packet filtering.
* **Packet buffering**: Temporarily storing packets before forwarding .
* **Queue management and scheduling**: Determining the order in which packets   are sent out based on QoS policies.

**Slow Path:**

* **Purpose**: Handles **non-time-critical tasks**, such as control plane   functions, management, and exception handling. It typically involves more complex processing and is usually implemented in software running on the router's control processor.
* **Speed**: Performance is less critical than the fast path as it deals with a   smaller volume of traffic or less time-sensitive operations.
* **Tasks (Examples)**:
* **Routing protocol processing**: Running routing protocols (e.g., OSPF, BGP),   updating the routing table.
* **Router management**: Handling SNMP, Telnet, SSH access for configuration   and monitoring.
* **Exception handling**: Processing packets that cannot be handled by the fast   path (e.g., packets with errors, packets for the router's IP address, packets requiring special processing like IP options).
* **Generating control packets**: Sending out routing protocol updates,   responding to management requests.
* **Building and maintaining the forwarding table**: Populating the fast path's   forwarding table based on the routing table maintained by the slow path.

In essence, the fast path is the workhorse responsible for the rapid transit of data packets, while the slow path is the control center managing the router's overall operation and handling less frequent but necessary tasks.

## <!-- What are CAMs and TCAMs? Explain the concept of ‘wildcard’ -->

What are CAMs and TCAMs? Explain the concept of ‘wildcard’.

***

**CAMs (Content Addressable Memories)** and **TCAMs (Ternary Content Addressable Memories)** are specialized types of memory used in routers and switches for high-speed table lookups, particularly in the decision logic for tasks like Ethernet switching, IP routing, and Access Control Lists (ACLs) .

**CAMs:**

* They store key-value pairs. When a key is presented to the CAM, it compares   the input key against all stored keys in parallel and, if a match is found, returns the associated value (e.g., an output port number).
* CAMs support **exact matching** using binary values ('0' and '1').

**TCAMs:**

* TCAMs are an extension of CAMs that offer more flexibility in matching.  Like   CAMs, they perform parallel searches based on an input key.
* The key difference is that TCAMs support three possible states for each bit:   **'0', '1', and 'X' (don't care or wildcard)**.

**Concept of ‘wildcard’:** The **wildcard ('X')** in a TCAM allows for **flexible pattern matching**. When a bit in a stored key is set to 'X', it will match either a '0' or a '1' in the corresponding bit of the input key. This is crucial for implementing functionalities like:

* **Longest Prefix Match (LPM) in IP routing**: IP routing tables contain   prefixes of varying lengths (e.g., 192.168.1.0/24). A TCAM can store these prefixes, with the less significant bits covered by wildcards. When a destination IP address needs to be looked up, the TCAM will find all matching prefixes, and the longest (most specific) match is then selected. For example, the prefix 192.168.1.0/24 in binary would have the last 8 bits as wildcards in the TCAM.
* **Access Control Lists (ACLs)**: ACL rules often specify conditions based on   source/destination IP addresses, port numbers, and protocols. TCAMs can store these rules, using wildcards to represent "any" value for certain fields or parts of fields. For instance, a rule might block traffic from any IP address to a specific port; the source IP address field in the TCAM entry would use wildcards.

In summary, CAMs provide fast exact matching, while TCAMs extend this capability by adding wildcard support, enabling more complex and flexible pattern matching essential for advanced routing and security features in network devices.

## <!-- Explain what means that IntServ (Integrated Services Internet) is ‘Soft State’ -->

Explain what means that IntServ (Integrated Services Internet) is ‘Soft State’.

***

The term **‘Soft State’** in the context of IntServ (Integrated Services Internet) refers to the mechanism by which resource reservations are maintained in the network. Unlike ‘hard state’ systems where a reservation remains in place indefinitely until explicitly torn down, **soft state reservations have a limited lifetime and require periodic refreshing** to remain active.

Here's a breakdown of what ‘soft state’ means for IntServ and its implications:

* **Limited Lifetime**: Each resource reservation established through the RSVP   (Resource ReSerVation Protocol) in IntServ has an associated timer.  When this timer expires, the reservation is automatically removed unless it is refreshed.
* **Periodic Refreshing**: To keep a reservation active, the sender (via Path   messages) and the receiver (via Resv messages) must periodically send refresh messages along the established path. These messages essentially restate the desire for the reservation.
* **Robustness to Failures**: The soft state approach provides a level of   robustness against network failures. If a router along the reservation path fails and recovers, or if a route changes, the lack of refresh messages will eventually lead to the expiration of the reservation on the affected segments. This automatic teardown avoids persistent, stale reservations in the network .
* **Adaptability**: Soft state allows reservations to be dynamically adjusted.   For example, a receiver could change the parameters of its reservation by sending a new Resv message, which effectively acts as a refresh with updated requirements.
* **Signaling Overhead**: A key aspect of soft state is the continuous need for   refresh messages. In networks with a large number of reservations or long paths, this periodic signaling can introduce a significant overhead.

In essence, the ‘soft state’ nature of IntServ means that reservations are not permanent and require ongoing signaling to be maintained. This design choice provides flexibility and resilience to network changes but comes with the trade-off of increased signaling traffic. The need for this continuous signaling was one of the factors that contributed to the scalability challenges of IntServ.
