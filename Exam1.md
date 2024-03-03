# Exam 1 Study Guide

## Lesson 1: Introduction, History, and Internet Architecture

- What are the advantages and disadvantages of a layered architecture?
    <details>
        <summary>Click to reveal the answer</summary>

            Advantages:
                1. Scalability
                2. Modularity
                3. Flexibility
            Disadvantages: 
                4. Interdependencies between layers
                5. Duplication of functionality
                6. Abstraction introduces overhead
    </details><br>

- What are the differences and similarities between the OSI model and the five-layered Internet model?
    <details>
        <summary>Click to reveal the answer</summary>

            Similarities:
                - Layered, Hierarchical, Abstraction
            - Differences
                - In the five-layered internet model the application, presentation, and session 
                  layers are combined into a single layer, and this combined layer is called the 
                  application layer. The interface between the application layer and the transport 
                  layer is the sockets.

    </details><br>
- What are sockets?
    <details>
        <summary>Click to reveal the answer</summary>

            Sockets are a programming interface (API) used for network communication between 
            processes running on different devices, typically over a network. They provide a 
            mechanism for processes (applications or software components) to establish communication 
            channels and exchange data.
    </details><br>
- Describe each layer of the OSI model.
    <details>
        <summary>Click to reveal the answer</summary>

            1. Application: The services that this layer offers are multiple depending on the application that is implemented. E.g.g HTTP, SMTP, FTP, etc.
            2. Presentation: Formats the information that it receives from the layer below and delivers it to the application layer.
            3. Session: Responsible for the mechanism that manages the different transport streams that belong to the same session between end-user application processes
            4. Transport: Responsible for the end-to-end communication between end hosts.
            5. Network: Moves datagrams from one Internet host to another.
            6. Data Link: Moves the frames from one node (host or router) to the next node.
            7. Physical: Facilitates the interaction with the actual hardware and is responsible to transfer bits within a frame between two nodes that are connected through a physical link.
    </details><br>
- Provide examples of popular protocols at each layer of the five-layered Internet model.
    <details>
        <summary>Click to reveal the answer</summary>

          1. Application: HTTP/SMTP/FTP/DNS
          2. Presentation: Formatting a video stream or translating integers from big endian to little endian format.
          3. Session: In the case of a teleconference application, it is responsible to tie together the audio stream and the video stream.
          4. Transport: TCP/UDP
          5. Network: IP
          6. Data Link: Ethernet/WiFi
          7. Physical: Coaxial Cable / Fiber optics
    </details><br>
- What is encapsulation, and how is it used in a layered model?
    <details>
        <summary>Click to reveal the answer</summary>

            Encapsulation in a layered model involves adding protocol-specific headers to data as it 
            moves down the layers. Each layer adds its own header, creating a hierarchical 
            structure. This process prepares data for transmission across a network.
    </details><br>

- What is the end-to-end (e2e) principle?
    <details>
        <summary>Click to reveal the answer</summary>

            Specific application-level functions should ideally not be built into the lower levels 
            of the network core. Instead, intelligence should reside at the endpoints of the 
            communication system, allowing for flexibility and innovation.
    </details><br>

- What are the examples of a violation of e2e principle?
    <details>
        <summary>Click to reveal the answer</summary>

            Firewalls / Traffic Filters: Because they are intermediate devices that are operated 
            between two end hosts and they can drop the end hosts communication.

            Network Address Translation (NAT): Because hosts behind them are not globally 
            addressable or rout-able, preventing direct communication from hosts on the public Internet.
    </details><br>

- What is the EvoArch model?
    <details>
        <summary>Click to reveal the answer</summary>

            An abstract model for studying protocol stacks and their evolution.
    </details><br>

- Explain a round in the EvoArch model.
    <details>
        <summary>Click to reveal the answer</summary>

            1. We introduce new nodes, and we place them randomly within the layers.
            2. We examine all layers, from the top to the bottom, and we perform the following tasks:
                i. We connect the new nodes that we may have just introduced to that layer by 
                choosing substrates based on the generality probabilities of the layer below s(l−1) 
                and by choosing products for them based on the generality probability of the current layer s(l).
                ii. We update the value of each node at each layer l, given that we may have new nodes added to the same layer l.
                iii. We examine all nodes in order of decreasing value in that layer and remove the nodes that should die.
            3. Finally, we stop the execution of the model when the network reaches a given number of nodes.
    </details><br>

- What are the ramifications of the hourglass shape of the internet?
    <details>
        <summary>Click to reveal the answer</summary>

            The lower and higher layers tend to see frequent innovations, while the protocols at the 
            waist of the hourglass appear to be “ossified” (rigid, hardened, or resistant to 
            change). Thus, many technologies that were not originally designed for the internet have 
            been modified so that they have versions that can communicate over the internet (such as 
            Radio over IP)
    </details><br>

- Repeaters, hubs, bridges, and routers operate on which layers?
    <details>
        <summary>Click to reveal the answer</summary>

            Repeaters and hubs operate on the physical layer (L1), bridges operate on the data link 
            layer (L2), and routers operate on the network layer (L3)
    </details><br>

- What is a bridge, and how does it “learn”?
    <details>
        <summary>Click to reveal the answer</summary>

            Bridges enable communication between hosts that are not directly connected. When the 
            bridge receives any frame, this is a “learning opportunity” to know which hosts are 
            reachable through which ports. This is because the bridge can view the port over which a 
            frame arrives and the source host.
    </details><br>

- What is a distributed algorithm?
    <details>
        <summary>Click to reveal the answer</summary>

            A distributed algorithm is a type of algorithm designed to solve a computational problem 
            that involves multiple independent entities or components, often referred to as nodes or 
            processes, that operate concurrently and communicate with each other through a network. 
            These entities collaborate to achieve a common goal or solve a particular problem by 
            exchanging information and coordinating their actions.
    </details><br>

- Explain the Spanning Tree Algorithm.
    <details>
        <summary>Click to reveal the answer</summary>

        It prevents loops in Ethernet networks by creating a loop-free logical topology. It works by 
        selecting a root bridge and then disabling redundant links, ensuring that only one path 
        exists between any two network nodes. This creates a tree-like structure where all nodes are 
        reachable without creating loops.
    </details><br>

- What is the purpose of the Spanning Tree Algorithm?
    <details>
        <summary>Click to reveal the answer</summary>

            The main purpose of the Spanning Tree Algorithm is to establish a single, loop-free path 
            through the network, ensuring that data frames can be forwarded without encountering 
            infinite loops.
    </details><br>

## Lesson 2: Transport and Application Layers

- What does the transport layer provide?
    <details>
        <summary>Click to reveal the answer</summary>

            End-to-end connection between two applications running on different hosts.
    </details><br>

- What is a packet for the transport layer called?
    <details>
        <summary>Click to reveal the answer</summary>

            A segment.
    </details><br>

- What are the two main protocols within the transport layer?
    <details>
        <summary>Click to reveal the answer</summary>

            TCP and UDP.
    </details><br>

- What is multiplexing, and why is it necessary?
    <details>
        <summary>Click to reveal the answer</summary>

            It enables multiple applications to use the network simultaneously. It's necessary 
            because the network layer lacks specificity about which processes on the host should receive incoming packets.
    </details><br>

- Describe the two types of multiplexing/de-multiplexing.
    <details>
        <summary>Click to reveal the answer</summary>

            Connection-less Multiplexing: Uses ports to allow multiple applications to share a 
            host's IP address without a predefined connection.

            Connection-oriented Multiplexing: Establishes a connection between sender and receiver 
            before data transfer, allowing data to be multiplexed based on ports within the 
            established connection.
    </details><br>

- What are the differences between UDP and TCP?
    <details>
        <summary>Click to reveal the answer</summary>

            Reliability: TCP yes, UDP no
            Connection Management: TCP Connection-oriented(3-way shake), UDP Connection-less
            Error Handling: TCP a lot, UDP just header checksum
    </details><br>

- When would an application layer protocol choose UDP over TCP?
    <details>
        <summary>Click to reveal the answer</summary>

            TCP: Use when reliability and in-order delivery are crucial
            UDP: Use for real-time applications requiring low delays and immediate data transfer
    </details><br>

- Explain the TCP Three-way Handshake.
    <details>
        <summary>Click to reveal the answer</summary>

            1. Client sends SYN packet.
            2. Server responds with SYN-ACK packet, acknowledging client's SYN and sending its own SYN.
            3. Client acknowledges server's SYN, completing the handshake.
    </details><br>

- Explain the TCP connection tear down.
    <details>
        <summary>Click to reveal the answer</summary>

            1. Client sends FIN packet to server.
            2. Server acknowledges receipt of FIN and initiates closing.
            3. Server sends FIN packet to client, indicating connection closure.
            4. Client acknowledges server's FIN, completing the teardown process.
    </details><br>

- What is Automatic Repeat Request or ARQ?
    <details>
        <summary>Click to reveal the answer</summary>

            It is how TCP achieves reliability. If no ack is received within a timeout, the sender 
            assumes loss and re-sends.
    </details><br>

- What is Stop and Wait ARQ?
    <details>
        <summary>Click to reveal the answer</summary>

            The sender waits (until time-out) for an acknowledgment after sending a packet.
    </details><br>

- What is Go-back-N?
    <details>
        <summary>Click to reveal the answer</summary>

            1. Receiver sends ACK for the most recently received in-order packet.
            2. Sender retransmits all packets from the most recent in-order packet.
            3. Out-of-order received packets are discarded.
    </details><br>

- What is selective ACKing?
    <details>
        <summary>Click to reveal the answer</summary>

            1. TCP employs selective ACKing to avoid unnecessary retransmissions.
            2. Sender retransmits suspected error packets only, improving efficiency.
            3. Out-of-order packets are buffered until missing packets are received.
    </details><br>

- What is fast retransmit?
    <details>
        <summary>Click to reveal the answer</summary>

            Triggered when 3 duplicate ACKs are received, prompting immediate retransmission of the 
            suspected lost packet
    </details><br>

- What is transmission control, and why do we need to control it?
    <details>
        <summary>Click to reveal the answer</summary>

            Mechanisms in the transport layer for controlling transmission rates. 
    </details><br>

- What is flow control, and why do we need to control it?
    <details>
        <summary>Click to reveal the answer</summary>

            Mechanisms to control transmission rates to protect the receiver buffer from overflowing.
    </details><br>

- What is congestion control?
    <details>
        <summary>Click to reveal the answer</summary>

            Mechanisms to control transmission rate to prevent network congestion.
    </details><br>

- What are the goals of congestion control?
    <details>
        <summary>Click to reveal the answer</summary>

            Some properties of a good congestion control algorithm are:

            Efficiency (high throughput, or utilization)
            Fairness (Each user should have their fair share of the network bandwidth)
            Low delay
            Fast convergence (a flow should converge to its fair allocation fast)
    </details><br>

- What is network-assisted congestion control?
    <details>
        <summary>Click to reveal the answer</summary>

            Relies on the network layer to provide explicit congestion feedback to the sender.
    </details><br>

- What is end-to-end congestion control?
    <details>
        <summary>Click to reveal the answer</summary>

            Hosts infer congestion from network behavior and adjust transmission rates accordingly.
    </details><br>

- How does a host infer congestion?
    <details>
        <summary>Click to reveal the answer</summary>

            Packet delay and packet loss.
    </details><br>

- How does a TCP sender limit the sending rate?
    <details>
        <summary>Click to reveal the answer</summary>

            a TCP sender cannot send faster than the slowest component, which is either the network 
            or the receiving host.
    </details><br>

- Explain Additive Increase/Multiplicative Decrease (AIMD) in the context of TCP.
    <details>
        <summary>Click to reveal the answer</summary>

            Increase: Starts with a constant initial window and incrementally increases it by 1 
            packet every Round Trip Time (RTT).

            Decrease: Upon detecting congestion, TCP reduces the congestion window (cwnd) to half of 
            its previous value.
    </details><br>

- What is a slow start in TCP?
    <details>
        <summary>Click to reveal the answer</summary>

            The congestion window grows exponentially, starting with one packet and doubling after each Round Trip Time (RTT).
            AIMD good when sending host operates near network capacity.
            Slow-start good for new connections starting from scratch.
    </details><br>

- Is TCP fair in the case where connections have the same RTT? Explain.
    <details>
        <summary>Click to reveal the answer</summary>

            Yes because congestion control mechanisms ensure each connection shares available bandwidth fairly.
    </details><br>

- Is TCP fair in the case where two connections have different RTTs? Explain.
    <details>
        <summary>Click to reveal the answer</summary>

            No because connections with shorter RTT values increase their congestion window more 
            rapidly than those with longer RTT values.
    </details><br>

- Explain how TCP CUBIC works.
    <details>
        <summary>Click to reveal the answer</summary>

            TCP CUBIC employs a cubic growth function to optimize window size. Upon triple duplicate 
            ACK, indicating congestion, it halves the window size (Wmin). It then aggressively 
            increases the window until nearing Wmax, where the previous loss occurred. If no further 
            loss is detected, it gradually increases the window. Time since last loss event (not 
            ACK-based) contributes to fairness and is represented by the cubic function 
            W(t)=C(t−K)3+Wmax, where K is the time to increase W to Wmax.
    </details><br>

- Explain TCP throughput calculation.
    <details>
        <summary>Click to reveal the answer</summary>

            Throughput = TCP_Window_Size / RTT (TODO investigate this more)
    </details><br>

## Lesson 3: Intra-domain Routing

- What is the difference between forwarding and routing?
    <details>
        <summary>Click to reveal the answer</summary>

            Forwarding refers to transferring a packet from an incoming link to an outgoing link
            within a single router. Routing refers to how routers work together using routing 
            protocols to determine the best routes over which the packets travel from the source to 
            the destination router.
    </details><br>

- What is the main idea behind a link-state routing algorithm?
    <details>
        <summary>Click to reveal the answer</summary>

            The main idea behind a link-state routing algorithm is for each router in a network to 
            construct a map of the entire network by exchanging information about the state of their 
            links with other routers. With this information, routers calculate the shortest path to 
            reach each destination using algorithms like Dijkstra's algorithm. By maintaining 
            up-to-date knowledge of the network topology, routers can dynamically adapt to changes 
            and select optimal paths for forwarding packets.
    </details><br>

- What is an example of a link-state routing algorithm?
    <details>
        <summary>Click to reveal the answer</summary>

            Dijkstra's
    </details><br>

- Walk through an example of the link-state routing algorithm.
  - SEE NOTES

- What is the computational complexity of the link-state routing algorithm?
    <details>
        <summary>Click to reveal the answer</summary>

            O(n^2)
    </details><br>

- What is the main idea behind the distance vector routing algorithm?
    <details>
        <summary>Click to reveal the answer</summary>

            The main idea behind the distance vector routing algorithm is for routers to iteratively 
            exchange routing information with neighboring routers, sharing their routing tables 
            containing the distance and direction to reach each destination. Routers use this 
            information to update their own routing tables, continually refining their understanding 
            of the network topology and selecting the shortest paths to each destination based on 
            the accumulated information.
    </details><br>

- Walk through an example of the distance vector algorithm.
  - SEE NOTES

- When does the count-to-infinity problem occur in the distance vector algorithm?
    <details>
        <summary>Click to reveal the answer</summary>

            When there is a routing loop in the network, causing routers to incorrectly perceive the 
            distance to a destination as shorter than it actually is. This incorrect information 
            propagates through the network, leading to a situation where routers continuously 
            increment their distance estimates until they reach infinity.
    </details><br>

- How does poison reverse solve the count-to-infinity problem?
    <details>
        <summary>Click to reveal the answer</summary>

            Nodes advertise infinity back along the path that caused the routing loop. By poisoning 
            the route with infinity, nodes inform their neighbors that the route is unreachable, 
            preventing them from inadvertently selecting it as a valid path.

            This technique will solve the problem with 2 nodes, however poisoned reverse will not 
            solve the problem with 3 or more nodes that are not directly connected!!!
    </details><br>

- What is the Routing Information Protocol (RIP)?
    <details>
        <summary>Click to reveal the answer</summary>

            A distance vector routing algorithm where routing information is exchanged among routers 
            to determine the best path to each destination, using hop count as its metric. RIP 
            operates through periodic updates and has versions including RIPv1 and RIPv2, with the 
            latter offering enhancements such as sub-netting and authentication support.
    </details><br>

- What is the Open Shortest Path First (OSPF) protocol?
    <details>
        <summary>Click to reveal the answer</summary>

            A link-state routing protocol which calculates the shortest path to each destination 
            based on a map of the entire network topology. OSPF routers exchange link-state 
            advertisements (LSAs) to build and maintain a database of the network topology. OSPF 
            uses Dijkstra's algorithm to calculate the shortest paths and assigns costs to links 
            based on metrics like bandwidth or delay. It is widely used in larger networks due to 
            its scalability and support for hierarchical design.
    </details><br>

- How does a router process advertisements?
    <details>
        <summary>Click to reveal the answer</summary>

            When a router receives link-state update packets containing LSAs from a neighboring 
            router, it processes them by first storing the LSAs in its link-state database to form a 
            consistent view of the network topology. Then, using this information, the router 
            calculates the shortest path using the shortest path first (SPF) algorithm. The 
            resulting shortest path is stored in the Forwarding Information Base (FIB), which is 
            used to determine the next hop for incoming data packets and forward them to the 
            appropriate outgoing interface card.
    </details><br>

- What is hot potato routing?
    <details>
        <summary>Click to reveal the answer</summary>

            A technique of choosing a path within the network, by choosing the closest egress point 
            based on intra-domain path cost (Interior Gateway Protocol/IGP cost).
    </details><br>

## Lesson 4: AS Relationships and Inter-domain Routing

- Describe the relationships between ISPs, IXPs, and CDNs.
    <details>
        <summary>Click to reveal the answer</summary>

            ISPs connect users to the internet, IXPs facilitate the exchange of traffic between ISPs 
            and networks, and CDNs enhance content delivery by strategically distributing it across 
            networks.
    </details><br>

- What is an AS?
    <details>
        <summary>Click to reveal the answer</summary>

            A network or group of networks that operate under a single administrative domain, 
            typically managed by a single entity such as an internet service provider (ISP) or a 
            large organization.
    </details><br>

- What kind of relationship does AS have with other parties?
    <details>
        <summary>Click to reveal the answer</summary>

            Provider-Customer: The provider forwards the customer's traffic to destinations found in 
            the provider's routing table (including the opposite direction of the traffic).
            Peering: Two ASes share a subset of routing tables, typically limited to their 
            respective customers. This agreement remains viable unless traffic exchange becomes 
            highly asymmetric.
    </details><br>

- What is BGP?
    <details>
        <summary>Click to reveal the answer</summary>

            Stands for Border Gateway Protocol; It's a standardized exterior gateway protocol 
            designed to exchange routing and reachability information among autonomous systems (AS) 
            on the internet.
    </details><br>

- How does an AS determine what rules to import/export?
    <details>
        <summary>Click to reveal the answer</summary>

            An AS determines what rules to import/export through the configuration of its Border 
            Gateway Protocol (BGP) policies.
    </details><br>

- What were the original design goals of BGP? What was considered later?
    <details>
        <summary>Click to reveal the answer</summary>

            Scalability, Security, Cooperation, express routing policies.
    </details><br>

- What are the basics of BGP?
    <details>
        <summary>Click to reveal the answer</summary>

            A pair of routers, known as BGP peers, exchange routing information over a semi-
            permanent TCP port connection called a BGP session. To begin a BGP session, a router 
            will send an OPEN message to another router. Then the sending and receiving routers will 
            send each other announcements from their routing tables. After BGP peers establish a 
            session, they can exchange BGP messages to provide reachability information and enforce 
            routing policies. We have two types of BGP messages: UPDATE messages convey route 
            changes, KEEPALIVE messages maintain session connectivity between peers.
    </details><br>

- What is the difference between iBGP and eBGP?
    <details>
        <summary>Click to reveal the answer</summary>

            A BGP session between a pair of routers in two different ASes is called an external BGP 
            (eBGP) session, and a BGP session between routers that belong to the same AS is called 
            an internal BGP (iBGP) session.
    </details><br>

- What is the difference between iBGP and IGP-like protocols (RIP or OSPF)?
    <details>
        <summary>Click to reveal the answer</summary>

            IGP-like protocols are used to establish paths between the internal routers of an AS 
            based on specific costs within the AS. In contrast, iBGP is only used to disseminate 
            external routes within the AS.
    </details><br>

- How does a router use the BGP decision process to choose which routes to import?
    <details>
        <summary>Click to reveal the answer</summary>

            When a router receives advertisements, it first applies the import policies to exclude 
            routes from further consideration. Then the router implements the decision process to 
            select the best routes that reflect the policy in place. Next, the newly selected routes 
            are installed in the forwarding table.
    </details><br>

- What are the 2 main challenges with BGP? Why?
    <details>
        <summary>Click to reveal the answer</summary>

            Scalability: The growth in the number of internet routes, the size of routing tables, 
            and the number of BGP peers strain the computational resources and memory capacity of 
            routers.
            Misconfigurations
    </details><br>

- What is an IXP?
    <details>
        <summary>Click to reveal the answer</summary>

            IXPs are physical infrastructures that provide the means for ASes to interconnect and 
            directly exchange traffic with one another
    </details><br>

- What are four reasons for IXP's increased popularity?
    <details>
        <summary>Click to reveal the answer</summary>

            1. They serve as interconnection hubs handling massive traffic volumes
            2. IXPs play a vital role in mitigating DDoS attacks
            3. They offer real-world infrastructures for research
            4. IXPs are active marketplaces and technology innovation hubs
    </details><br>

- Which services do IXPs provide?
    <details>
        <summary>Click to reveal the answer</summary>
            1. Public peering
            2. Private peering
            3. Route servers and SLAs
            4. Remote peering through sellers
            5. Mobile peering
            6. DDoS protection
    </details><br>

- How does a route server work?
    <details>
        <summary>Click to reveal the answer</summary>

            It collects and shares routing information from its peers or participants of the IXP 
            that connect to the RS. It executes its own BGP decision process and re-advertises the 
            resulting information (e.g., best route selection) to all RS's peer routers. A typical 
            routing daemon maintains a Routing Information Base (RIB), which contains all BGP paths 
            that it receives from its peers - the Master RIB. In addition, the route server also 
            maintains AS-specific RIBs to keep track of the individual BGP sessions they maintain 
            with each participant AS.
    </details><br>

## Lesson 5: Router Design and Algorithms (Part 1)

- What are the basic components of a router?
    <details>
        <summary>Click to reveal the answer</summary>

            Forwarding / switching function (Data plane)
            Switching fabricR
            Routing Table
            I/O ports
            Control plane functions (CPU / Remote controller)
    </details><br>

- Explain the forwarding (or switching) function of a router.
    <details>
        <summary>Click to reveal the answer</summary>

            Moves the packets from input to output ports and makes the connections between the input and the output ports.
    </details><br>

- The switching fabric moves the packets from input to output ports. What are the functionalities performed by the input and output ports?
    <details>
        <summary>Click to reveal the answer</summary>

            Input: Physically terminate the incoming links to the router, Decapsulate the packets in 
            the data link processing unit, and most importantly, perform the lookup function. The 
            input ports consult the forwarding table to ensure that each packet is forwarded to the 
            appropriate output port through the switch fabric.
            Output: Receive and queue packets from the switching fabric and then send them to the 
            outgoing link.
    </details><br>

- What is the purpose of the router’s control plane
    <details>
        <summary>Click to reveal the answer</summary>

            Implementing the routing protocols, maintaining the routing tables, and computing the 
            forwarding table. All these functions are implemented in software in the routing processor.
    </details><br>

- What tasks occur in a router
    <details>
        <summary>Click to reveal the answer</summary>

            Time sensitive: Lookup, switching, scheduling
            Less time sensitive: HW validation & checksum, route processing, protocol processing
    </details><br>

- List and briefly describe each type of switching. Which, if any, can send multiple packets across the fabric in parallel
    <details>
        <summary>Click to reveal the answer</summary>

            1. Switching via memory: Incoming packets are stored temporarily in the router's memory 
               before being forwarded. Each packet is individually processed and forwarded.
            3. Switching via bus: A shared bus to interconnect the router's input and output ports.
               Packets are forwarded one at a time through the bus.
            5. Switching via interconnection network (crossbar). Packets can be forwarded across the 
               fabric in parallel.
    </details><br>

- What are two fundamental problems involving routers, and what causes these problems
    <details>
        <summary>Click to reveal the answer</summary>

            - Bandwidth and Internet population scaling, caused by: increasing number of devices/traffic
            - Services at high speeds
    </details><br>

- What are the bottlenecks that routers face, and why do they occur
    <details>
        <summary>Click to reveal the answer</summary>

            Limited compute resources: Implementing complex protocols / 
            Speed of interfaces: high volume of traffic
            Routing table size: Increases lookup time
    </details><br>

- Convert between different prefix notations (dot-decimal, slash, and masking)
  - SEE NOTES

- What is CIDR, and why was it introduced
    <details>
        <summary>Click to reveal the answer</summary>

            CIDR stands for Classless Inter-Domain Routing. It was introduced to address the inefficient allocation of IP addresses under the older addressing scheme.
    </details><br>

- Name 4 takeaway observations around network traffic characteristics. Explain their consequences
    <details>
        <summary>Click to reveal the answer</summary>

            1. Caching solutions will not work efficiently
            2. Lookup speed in memory is very important.
            3. Need a stable routing protocol.
            4. A vital trade-off is memory usage. Fast+Expensive or Slow+Cheap
    </details><br>

- Why do we need multibit tries
    <details>
        <summary>Click to reveal the answer</summary>

            To reduce the number of memory accesses required to perform a lookup.
    </details><br>

- What is prefix expansion, and why is it needed
    <details>
        <summary>Click to reveal the answer</summary>

            The process of increasing the size of a routing prefix in CIDR notation to encompass a 
            larger range of IP addresses. It's needed to efficiently allocate IP addresses and 
            accommodate network growth while minimizing the number of routing table entries.
    </details><br>

- Perform a prefix lookup given a list of pointers for unibit tries, fixed-length multibit ties, and variable-length multibit tries
  - SEE NOTES

- Perform a prefix expansion. How many prefix lengths do old prefixes have? What about new prefixes
  - SEE NOTES

- What are the benefits of variable-stride versus fixed-stride multibit tries?
    <details>
        <summary>Click to reveal the answer</summary>

            Variable-stride offers more efficient memory utilization and faster lookup times 
            compared to fixed-stride. This is because variable-stride adjusts the length of each 
            stride dynamically based on the distribution of prefixes in the routing table. 
    </details><br>

## Lesson 6: Router Design and Algorithms (Part 2)

- Why is packet classification needed?
    <details>
        <summary>Click to reveal the answer</summary>

            Networks require quality-of-service and security guarantees for their traffic. Packet 
            forwarding based on the longest prefix matching of destination IP addresses is 
            insufficient. We need to handle packets based on multiple criteria such as TCP flags, 
            source addresses, and so on.
    </details><br>

- What are three established variants of packet classification?
    <details>
        <summary>Click to reveal the answer</summary>

          1. Firewalls
          2. Resource reservation protocols
          3. Routing based on traffic type
    </details><br>

- What are the simple solutions to the packet classification problem?
    <details>
        <summary>Click to reveal the answer</summary>

            Linear search, caching, and passing labels.
    </details><br>

- How does fast searching using set-pruning tries work?
    <details>
        <summary>Click to reveal the answer</summary>

            Fast searching using set-pruning tries involves efficiently searching for prefixes in a 
            routing table by eliminating unnecessary comparisons through set-based pruning. This 
            method organizes prefixes into sets based on common prefixes and utilizes a trie 
            structure to represent these sets. During a search, the trie is traversed, and sets of 
            prefixes are pruned based on their matching prefixes, reducing the number of comparisons 
            required. This pruning technique accelerates the search process, leading to faster 
            lookup times and improved routing performance.
    </details><br>

- What’s the main problem with the set pruning tries?
    <details>
        <summary>Click to reveal the answer</summary>

            The main problem with set pruning tries is the potential increase in memory consumption. 
            While set pruning tries can improve search efficiency by reducing the number of 
            comparisons needed during lookup, they may require additional memory to store the 
            set-based pruning information.
    </details><br>

- What is the difference between the pruning approach and the backtracking approach for packet classification with a trie?
    <details>
        <summary>Click to reveal the answer</summary>

            The pruning approach optimizes trie traversal by eliminating irrelevant subsets of rules 
            early in the process, while the backtracking approach explores all possible paths in the 
            trie without pruning, potentially requiring more computational resources but ensuring 
            completeness in classification.
    </details><br>

- What’s the benefit of a grid of tries approach?
    <details>
        <summary>Click to reveal the answer</summary>

            We can reduce the wasted time in the backtracking search by using pre-computation. When 
            there is a failure point in a source trie, we pre-compute a switch pointer. Switch 
            pointers take us directly to the next possible source trie containing a matching rule.
    </details><br>

- Describe the “Take the Ticket” algorithm.
    <details>
        <summary>Click to reveal the answer</summary>

            Each output line maintains a distributed queue for all input lines that want to send 
            packets to it. When an input line intends to send a packet to a specific output line, it 
            requests a ticket. Then, the input line waits for the ticket to be served. At that 
            point, the input line connects to the output line, the crosspoint is turned on, and the 
            input line sends the packet.
    </details><br>

- What is the head-of-line problem?
    <details>
        <summary>Click to reveal the answer</summary>

            When the entire queue is blocked by the progress of the head of the queue.
    </details><br>

- How is the head-of-line problem avoided using the knockout scheme?
    <details>
        <summary>Click to reveal the answer</summary>

            The knockout scheme avoids the head-of-line problem by dropping or "knocking out" 
            packets that encounter blocked output ports, allowing subsequent packets to continue 
            forwarding without waiting.
    </details><br>

- How is the head-of-line problem avoided using parallel iterative matching?
    <details>
        <summary>Click to reveal the answer</summary>

            The head-of-line problem is avoided using parallel iterative matching by concurrently 
            processing multiple packets against different rules or prefixes in the classification 
            database. This allows packets to progress independently, preventing congestion or delays 
            caused by a single stalled packet.
    </details><br>

- Describe FIFO with tail drop.
    <details>
        <summary>Click to reveal the answer</summary>

            Packets enter a router on input links which are then looked up using the address lookup 
            component – which gives the router an output link number. The switching system within 
            the router then places the packet in the corresponding output port. This port is a FIFO 
            queue. If the output link buffer is full, incoming packets to the tail of the queue are 
            dropped.
    </details><br>

- What are the reasons for making scheduling decisions more complex than FIFO?
    <details>
        <summary>Click to reveal the answer</summary>

            1. Router support for congestion
            2. Fair sharing of links among competing flows
            3. Providing QoS guarantees to flows
    </details><br>

- Describe Bit-by-bit Round Robin scheduling.
    <details>
        <summary>Click to reveal the answer</summary>

            Bit-by-bit Round Robin scheduling works by allocating transmission slots to different 
            input ports in a round-robin fashion, processing one bit at a time from each input port 
            in sequential order. This ensures fair access to the output port among input ports and 
            prevents a single input port from monopolizing the output. Each input port is given a 
            turn to transmit one bit of its packet, and the process repeats cyclically. This 
            scheduling method helps distribute traffic evenly across input ports and avoids the 
            head-of-line blocking problem by allowing all input ports to progress simultaneously.
    </details><br>

- Bit-by-bit Round Robin provides fairness; what’s the problem with this method?
    <details>
        <summary>Click to reveal the answer</summary>

            It can suffer from inefficiency and reduced throughput because packets are processed one 
            bit at a time, which may not fully utilize the available bandwidth of the output port.
    </details><br>

- Describe Deficit Round Robin (DRR).
    <details>
        <summary>Click to reveal the answer</summary>

            DRR is a scheduling algorithm that allocates bandwidth fairly among multiple queues. 
            Each queue is assigned a deficit counter, determining its priority for transmission. 
            During each round, the scheduler deducts a fixed amount from the deficit counter of 
            active queues and transmits packets until the deficit is exhausted or the queue becomes 
            empty. Unused deficit is carried over to the next round, ensuring fair allocation of 
            bandwidth while allowing bursts of traffic.
    </details><br>

- What is a token bucket shaping?
    <details>
        <summary>Click to reveal the answer</summary>

            Token bucket shaping regulates data flow by associating a token bucket with each traffic 
            flow. Tokens are added to the bucket at a fixed rate. When a packet arrives, it is 
            transmitted if enough tokens are available; otherwise, it is delayed. This method 
            smooths bursts of traffic and enforces a sustainable transmission rate, aiding in 
            managing network congestion.
    </details><br>

- In traffic scheduling, what is the difference between policing and shaping?
    <details>
        <summary>Click to reveal the answer</summary>

            Policing imposes strict rate limits and may result in packet loss when limits are 
            exceeded, while shaping buffers traffic to enforce rate limits more gently, avoiding 
            immediate packet drops.
    </details><br>

- How is a leaky bucket used for traffic policing and shaping?
    <details>
        <summary>Click to reveal the answer</summary>

            A leaky bucket is used for traffic policing and shaping by controlling the rate of 
            outgoing traffic. In policing, incoming packets are compared against the bucket's 
            capacity, and excess packets are either dropped or marked. In shaping, outgoing packets 
            are transmitted at a controlled rate determined by the bucket's leak rate, smoothing 
            traffic flow to conform to a specified rate limit.
    </details><br>
