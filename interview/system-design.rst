System Design
===============


- Reverse Proxy
  
  - A proxy server is a go‑between or intermediary server that forwards requests for content from multiple clients to different servers across the Internet. 
    A reverse proxy server is a type of proxy server that typically sits behind the firewall in a private network and directs client requests to the appropriate backend server. 
    A reverse proxy provides an additional level of abstraction and control to ensure the smooth flow of network traffic between clients and servers.
  
  |
  - Common Uses
  
   
    - **Load balancing** – A reverse proxy server can act as a “traffic cop,” sitting in front of your backend servers and distributing client requests across a group of servers in a manner that maximizes speed and capacity utilization while ensuring no one server is overloaded, which can degrade performance. If a server goes down, the load balancer redirects traffic to the remaining online servers.
    
    |
    - **Web acceleration** – Reverse proxies can compress inbound and outbound data, as well as cache commonly requested content, both of which speed up the flow of traffic between clients and servers. They can also perform additional tasks such as SSL encryption to take load off of your web servers, thereby boosting their performance.
    
    |
    - **Security and anonymity** – By intercepting requests headed for your backend servers, a reverse proxy server protects their identities and acts as an additional defense against security attacks. It also ensures that multiple servers can be accessed from a single record locator or URL regardless of the structure of your local area network.

  |
  - Reference
  
    - `Nginx <https://www.nginx.com/resources/glossary/reverse-proxy-server/>`_











