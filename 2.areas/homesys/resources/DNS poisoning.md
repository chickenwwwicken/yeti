Normally, a networked computer uses a DNS server provided by an ISP.
DNS servers are used in an organization's network to improve resolution response performance by caching previously obtained query results.

Poisoning attacks on a single DNS server can affect the users serviced directly by the compromised server or those serviced indirectly by its downstream servers if applicable.

To perform a cache poisoning attack, the attacker exploits flaws in the DNS software. 
A server should correctly validate DNS responses to ensure that they are from an authoritative source (for example by using DNSSEC) otherwise the server might end up caching the incorrect entries locally and serve them to other users that make the same request.

This attack can be used to redirect users from a website to another site of the attacker's choosing. 

For example, an attacker spoofs the IP address DNS entries for a target website on a given DNS server and replaces them with the IP address of a server under their control. 
The attacker then creates files on the server under their control with names matching those on the target server. 
These files usually contain malicious content, such as computer worms or viruses. 
A user whose computer has referenced the poisoned DNS server gets tricked into accepting content coming from a non-authentic server and unknowingly downloads malicious content. 

This technique can also be used for phishing attacks, where a fake version of a genuine website is created to gather personal details such as bank and credit/debt card details. 

Vulnerability of systems to DNS cache poisoning goes beyond its immediate effects
It can open users up to further risks such as phishing, malware injections, denial of service, and website hijacking due to system vulnerabilities. 

Various methods, ranging from the use of social engineering tactics to the exploitation of weaknesses present in the DNS server software, can lead to these attacks. 