# Load Balancing

Load balancing allows us to distribute incoming network traffic across multiple resources, ensuring high availability and reliability by directing requests to resources that are online. This offers the flexibility to add or remove resources based on demand.

## Why Load Balancing?

Modern high-traffic websites often need to handle hundreds of thousands or even millions of concurrent requests. To meet this demand cost-effectively, adding more servers is generally the best practice. A load balancer sits in front of these servers and routes client requests across all available servers. This ensures no single server is overworked, and if one server goes down, the load balancer redirects traffic to others. It also automatically begins sending requests to new servers as they are added.

## Workload Distribution

Load balancing provides several common variations for distributing traffic:

- **Host-based**: Distributes requests based on the hostname.
- **Path-based**: Uses the full URL, not just the hostname, to distribute requests.
- **Content-based**: Distributes requests based on content, such as the value of a parameter.

## Layers of Load Balancing

Load balancers generally operate at one of two levels:

- **Network Layer (Layer 4)**: Works at the network transport layer, using IP addresses for routing. These load balancers typically cannot perform content-based routing and often involve high-speed hardware.
  
- **Application Layer (Layer 7)**: Operates at the application layer, performing content-based routing by reading requests in their entirety. This allows for more informed traffic management.

## Types of Load Balancers

### Software Load Balancers
- Easier to deploy and more cost-effective.
- Flexible but may require more effort to configure.
- Commonly available as installable solutions or as managed cloud services.

### Hardware Load Balancers
- Physical devices that can handle large volumes of traffic.
- More expensive and less flexible.
- Require regular maintenance and firmware updates.

### DNS Load Balancing
- Distributes traffic across multiple servers based on domain names.
- Less reliable due to its inability to detect server or network outages.

## Routing Algorithms

Commonly used routing algorithms include:

- **Round-robin**: Distributes requests in rotation across servers.
- **Weighted Round-robin**: Accounts for differing server capacities using weights.
- **Least Connections**: Directs new requests to the server with the fewest active connections.
- **Least Response Time**: Combines the fastest response time and fewest connections to route requests.
- **Least Bandwidth**: Sends requests to the server with the least traffic (in Mbps).
- **Hashing**: Routes requests based on a defined key (e.g., client IP address or request URL).

## Advantages of Load Balancing

- **Scalability**: Allows easy addition of resources as demand grows.
- **Redundancy**: Increases fault tolerance by using multiple servers.
- **Flexibility**: Can adapt to varying load conditions.
- **Efficiency**: Distributes traffic effectively to avoid overloading any one resource.

## Redundant Load Balancers

Load balancers themselves can become a single point of failure. To mitigate this, a second or additional load balancers can be set up in cluster mode. In the event of a failure, a passive load balancer can take over.

## Features of Load Balancers

- **Autoscaling**: Adjusts resources based on demand.
- **Sticky Sessions**: Ensures the same user is connected to the same resource for session continuity.
- **Health Checks**: Monitors the health of resources and removes unhealthy ones from the pool.
- **Persistent Connections**: Supports long-lasting connections, such as WebSocket connections.
- **Encryption**: Manages encrypted connections (TLS/SSL).
- **Certificates**: Handles client and server certificates.
- **Compression**: Compresses responses to save bandwidth.
- **Caching**: Application-layer load balancers may cache responses for efficiency.
- **Logging**: Records request and response metadata for auditing and analysis.
- **Request Tracing**: Assigns unique IDs to requests for monitoring and troubleshooting.
- **Redirects**: Redirects requests based on the requested path.
- **Fixed Response**: Sends static responses for certain requests (e.g., error messages).

## Examples of Load Balancing Solutions

- **Amazon Elastic Load Balancing**
- **Azure Load Balancing**
- **Google Cloud Platform (GCP) Load Balancing**
- **DigitalOcean Load Balancer**
- **Nginx**
- **HAProxy**
