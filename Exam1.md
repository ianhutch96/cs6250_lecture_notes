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

- What is the Open Shortest Path First (OSPF) protocol?

- How does a router process advertisements?

- What is hot potato routing?

## Lesson 4: AS Relationships and Inter-domain Routing

- Describe the relationships between ISPs, IXPs, and CDNs.

- What is an AS?

- What kind of relationship does AS have with other parties?

- What is BGP?

- How does an AS determine what rules to import/export?

- What were the original design goals of BGP? What was considered later?

- What are the basics of BGP?

- What is the difference between iBGP and eBGP?

- What is the difference between iBGP and IGP-like protocols (RIP or OSPF)?

- How does a router use the BGP decision process to choose which routes to import?

- What are the 2 main challenges with BGP? Why?

- What is an IXP?

- What are four reasons for IXP's increased popularity?

- Which services do IXPs provide?

- How does a route server work?

## Lesson 5: Router Design and Algorithms (Part 1)

- What are the basic components of a router?

- Explain the forwarding (or switching) function of a router.

- The switching fabric moves the packets from input to output ports. What are the functionalities performed by the input and output ports?

- What is the purpose of the router’s control plane

- What tasks occur in a router

- List and briefly describe each type of switching. Which, if any, can send multiple packets across the fabric in parallel

- What are two fundamental problems involving routers, and what causes these problems

- What are the bottlenecks that routers face, and why do they occur

- Convert between different prefix notations (dot-decimal, slash, and masking)

- What is CIDR, and why was it introduced

- Name 4 takeaway observations around network traffic characteristics. Explain their consequences

- Why do we need multibit tries

- What is prefix expansion, and why is it needed

- Perform a prefix lookup given a list of pointers for unibit tries, fixed-length multibit ties, and variable-length multibit tries

- Perform a prefix expansion. How many prefix lengths do old prefixes have? What about new prefixes

- What are the benefits of variable-stride versus fixed-stride multibit tries?

## Lesson 6: Router Design and Algorithms (Part 2)

- Why is packet classification needed?

- What are three established variants of packet classification?

- What are the simple solutions to the packet classification problem?

- How does fast searching using set-pruning tries work?

- What’s the main problem with the set pruning tries?

- What is the difference between the pruning approach and the backtracking approach for packet classification with a trie?

- What’s the benefit of a grid of tries approach?

- Describe the “Take the Ticket” algorithm.

- What is the head-of-line problem?

- How is the head-of-line problem avoided using the knockout scheme?

- How is the head-of-line problem avoided using parallel iterative matching?

- Describe FIFO with tail drop.

- What are the reasons for making scheduling decisions more complex than FIFO?

- Describe Bit-by-bit Round Robin scheduling.

- Bit-by-bit Round Robin provides fairness; what’s the problem with this method?

- Describe Deficit Round Robin (DRR).

- What is a token bucket shaping?

- In traffic scheduling, what is the difference between policing and shaping?

- How is a leaky bucket used for traffic policing and shaping?
