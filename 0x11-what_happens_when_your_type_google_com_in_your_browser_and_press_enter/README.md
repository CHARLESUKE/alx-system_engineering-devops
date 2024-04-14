  requested and that flows up the list of DNS servers until the SOA is reached,
  and if found an answer is returned.

Server IP address is still not known
------------------------------------
All Resolver server (which is usually your ISP — Internet Service Provider) must 
know how to locate the root servers. In a situation where the resolver is still
unable to identify IP address of ``https://www.google.com``, it locates the root server
which tells it how to locate the .COM TLD (Top-Level Domain) server. The resolver
saves this information, so it doesn’t have to ask the root server again. On contact
with the .COM TLD server, the server provides the authoritative name servers for 
``https://www.google.com``, if it doesn’t know the IP address. Yet again, the resolver
stores this new information. The authoritative name server is the ultimate authority
responsible for handling request of this type. The resolver gets the IP address, saves it,
and finally goes home to give the OS this information. 

Opening of a socket
-------------------
Once the browser receives the IP address of the destination server, it takes
