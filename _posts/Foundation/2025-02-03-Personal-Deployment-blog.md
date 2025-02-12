**Personal Deployment Blog** 

**Big Idea 4 - Comuting Systems and Networks | AWS Deployment**


<button><a href="https://apclassroom.collegeboard.org/103/home?unit=4">AP CLASSROOM</a></button>



<u>Prerequisits</u>


 - test server
 
 Needs working frontend-to-backend test server that works locally in order for 
 
 deployment.


 - Subdomain

 Setup DNS endpoint through AWS Route 53.


```yml
Server: https://flask2025.nighthawkcodingsociety.com/
Domain: nighthawkcodingsociety.com
Subdomain: flask2025
```
 
- Port 

Select a unique port in the backend (main.py) Ours 

is 8102

if __name__ == "__main__":
      # change name for testing
      app.run(debug=True, host="0.0.0.0", port="8102")


also change port in dockerfile, docker compose yml, and nginx file

in backend


Also change port in frontend under assets 


export var pythonURI;
  if (location.hostname === "localhost" || location.hostname === "127.0.0.1") {
      pythonURI = "http://localhost:8102";  // Same URI for localhost or 127.0.0.1
  } else {
      pythonURI = "https://frostbyte.stu.nighthawkcodingsociety.com";
  }







- AWS


AWS deployment refers to the process of releasing an application 

or infrastructure to run on Amazon Web Services (AWS) cloud 

platform. AWS provides a broad set of cloud services like 

computing power, storage, networking, databases, machine 

learning, and much more. 



after logging in to AWS click on EC2 and then instances


- Dockerfile 


Make sure your Dockerfile and docker-compose.yml match the 

port you discovered with docker ps on AWS EC2. then test 

docker-compose up or sudo docker-compose up

After it’s done building, type in http://localhost:8102 in your browser



- Server setup 

In the AWS EC2 terminal;

cd ~

Clone backend repo: git clone 

github.com/server/project.git my_unique_name

Navigate to your repo: cd my_unique_name

Build your site: docker-compose up -d --build

Test your site: curl localhost:8---


- Route 53 DNS


Route 53 DNS Setup:


Record name	Type	Value/Route traffic to

projectUniqueName	CNAME	csp.nighthawkcodingsociety.com

projectUniqueName	CNAME	csa.nighthawkcodingsociety.com


- Nginx setup


Create an nginx config file (change projectUniqueName to make 

you unique config file, suggest using your registered domain): 

sudo nano projectUniqueName


servserver {
        listen 80;
        listen [::]:80;
        server_name frostbyte.stu.nighthawkcodingsociety.com;

        location / {
                proxy_pass http://localhost:8102;

                # Preflighted requests
                if ($request_method = OPTIONS) {
                add_header "Access-Control-Allow-Credentials" "true" always;
                add_header "Access-Control-Allow-Origin"  "https://nighthawkcoders.github.io" always;
                add_header "Access-Control-Allow-Methods" "GET, POST, PUT, DELETE, OPTIONS, HEAD" always;
                add_header "Access-Control-Allow-MaxAge" 600 always;
                add_header "Access-Control-Allow-Headers" "Authorization, Origin, X-Origin, X-Requested-With, Content-Type, Accept" always;
                return 204;
                }
        }
}



activate configuration. Create a symbolic link 

(change projectUniqueName to your nginx config file name): cd /etc/nginx/

sites-enabled, then sudo ln -s /etc/nginx/sites-available/projectUniqueName 

/etc/nginx/sites-enabled


Validate by running: sudo nginx -t


Restart nginx by running sudo systemctl restart nginx


Test domain name on desktop browser now 



- Certbog Config 

run this in terminal: sudo certbot --nginx


ideal outcome -->


Saving debug log to /var/log/letsencrypt/letsencrypt.log
Plugins selected: Authenticator nginx, Installer nginx

Which names would you like to activate HTTPS for?
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
...

28: cars.nighthawkcodingsociety.com

29: dolphin.nighthawkcodingsociety.com

30: saakd.nighthawkcodingsociety.com
...
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Select the appropriate numbers separated by commas and/or spaces, or leave input

blank to select all options shown (Enter 'c' to cancel): # ENTER YOUR CORRESPONDING NUMBER

Cert not yet due for renewal

You have an existing certificate that has exactly the same domains or certificate name you requested and isn't close to expiry.

(ref: /etc/letsencrypt/renewal/nighthawkcodingsociety.com-0001.conf)

What would you like to do?
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
1: Attempt to reinstall this existing certificate

2: Renew & replace the cert (limit ~5 per 7 days)
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

Select the appropriate number [1-2] then [enter] 

(press 'c' to cancel): 2

Renewing an existing certificate

Performing the following challenges:

http-01 challenge for nighthawkcodingsociety.com

http-01 challenge for csa.nighthawkcodingsociety.com

http-01 challenge for cso.nighthawkcodingsociety.com

http-01 challenge for flm.nighthawkcodingsociety.com

Waiting for verification...

Cleaning up challenges

Deploying Certificate to VirtualHost /etc/nginx/sites-enabled/nighthawk_society

Deploying Certificate to VirtualHost /etc/nginx/sites-enabled/nighthawk_csa

Deploying Certificate to VirtualHost /etc/nginx/sites-enabled/nighthawk_csp

Deploying Certificate to VirtualHost /etc/nginx/sites-enabled/nighthawk_flm

Please choose whether or not to redirect HTTP traffic to HTTPS, removing HTTP access.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
1: No redirect - Make no further changes to the webserver configuration.

2: Redirect - Make all requests redirect to secure HTTPS access. Choose this for

new sites, or if you're confident your site works on HTTPS. You can undo this

change by editing your web server's configuration.
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Select the appropriate number [1-2] then [enter] (press 'c' to cancel): 2

Traffic on port 80 already redirecting to ssl in /etc/nginx/sites-enabled/nighthawk_society

Traffic on port 80 already redirecting to ssl in /etc/nginx/sites-enabled/nighthawk_csa

Traffic on port 80 already redirecting to ssl in /etc/nginx/sites-enabled/nighthawk_csp

Traffic on port 80 already redirecting to ssl in /etc/nginx/sites-enabled/nighthawk_flm

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -
Your existing certificate has been successfully renewed, and the new certificate

has been installed.

The new certificate covers the following domains:

https://nighthawkcodingsociety.com, 

https://csa.nighthawkcodingsociety.com, 

https://csp.nighthawkcodingsociety.com, and

https://flm.nighthawkcodingsociety.com,

You should test your configuration at:

https://www.ssllabs.com/ssltest/analyze.html?d=nighthawkcodingsociety.com

https://www.ssllabs.com/ssltest/analyze.html?d=csa.nighthawkcodingsociety.com

https://www.ssllabs.com/ssltest/analyze.html?d=csp.nighthawkcodingsociety.com

https://www.ssllabs.com/ssltest/analyze.html?d=flm.nighthawkcodingsociety.com
- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

IMPORTANT NOTES:

 - Congratulations! Your certificate and chain have been saved at:

   /etc/letsencrypt/live/nighthawkcodingsociety.com-0001/fullchain.pem

   Your key file has been saved at:

   /etc/letsencrypt/live/nighthawkcodingsociety.com-0001/privkey.pem

   Your cert will expire on 2022-03-06. To obtain a new or tweaked

   version of this certificate in the future, simply run certbot again

   with the "certonly" option. To non-interactively renew *all* of

   your certificates, run "certbot renew"

 - If you like Certbot, please consider supporting our work by:


   Donating to ISRG / Let's Encrypt:   https://letsencrypt.org/donate

   Donating to EFF:                    https://eff.org/donate-le




- Changing code in VS code


steps:  git pull before making changes, run main, commit changes,

locally, Before updating deployment start Docker Desktop app 

and test your Web Application, after Docker is done building, 

type in http://localhost:8--- in your browser, If all goes well, 

sync change from UI or git push from terminal. 



- Pulling Changes into AWS EC2 deployment


cd ~/my_unique_name


docker-compose down

Test Server in browser using https://, it should be down 

(502 Bad Gateway in browser)


git pull


Rebuild your docker container: docker-compose up -d --build

Test Server in browser using https://, sll updates should 

be up and running on internet.



- Optional, Troubleshooting checks on AWS EC2


Try to curl: curl localhost:8--- (replace ‘8—’ with your port number)

Verify home pages is yours


Run docker-compose ps

Perform check on your container, verify docker is up


Run docker ps

Perform checks on all containers and all images







**CollegeBoard Main Ideas**


Understanding Computing Systems

Components of a Computing System: A computing system is made up of hardware and software 

components that work together to perform tasks.

Hardware: Physical devices such as processors (CPU), memory (RAM), 

storage, input/output devices, etc.

Software: Programs and applications that tell the hardware what to do, 

such as operating systems, applications, and system software.

Operating Systems: Understand how the operating system manages hardware 

resources and provides an interface for users and other programs. Key tasks

 include memory management, process scheduling, file management, etc.



2. Computer Networks

Basic Network Types:

Local Area Network (LAN): A network that connects devices in a limited area, 

like a home or office.
Wide Area Network (WAN): A network that spans a larger geographical area, such as the internet.

Wireless Networks: Networks that allow devices to connect without physical cables, 

such as Wi-Fi and cellular networks.

Network Communication:

Data Transmission: Understanding how data is sent across networks in the form

 of packets and how devices communicate over these networks.
Protocols: Rules or standards that define how devices communicate. Examples include:
TCP/IP (Transmission Control Protocol/Internet Protocol) is fundamental for communication on the Internet.
HTTP/HTTPS for web browsing and communication between servers and clients.
DNS (Domain Name System) for translating domain names to IP addresses.
Wi-Fi, Bluetooth for local wireless communication.
3. Data Transmission and Networking Models
Packet Switching: Data is broken into smaller packets that are sent across the network independently and reassembled at the destination. This approach allows for efficient and flexible use of network resources.
Client-Server Model: In this model, clients (devices) send requests to servers (computers providing services) and receive responses.
Peer-to-Peer Networks (P2P): Devices act as both clients and servers, sharing resources directly without a central server.
Bandwidth and Latency:
Bandwidth refers to the amount of data that can be transmitted in a given time frame.
Latency refers to the delay before a transfer of data begins following an instruction.
Transmission Medium: The physical or wireless medium through which data travels, such as fiber optics, coaxial cables, or radio waves for wireless communication.
4. Internet and Its Impact
The Internet: A vast network of networks that connects millions of computing devices worldwide. The Internet is built on top of TCP/IP protocols and is essential for web browsing, email, and many modern applications.
The Web and Websites: The web is a collection of websites accessible over the internet, utilizing protocols like HTTP/HTTPS for communication.
Cloud Computing: A model where data and applications are stored on remote servers (the cloud) and accessed via the internet, offering flexibility and scalability.
5. Security and Privacy in Networks
Security Threats: Networks and computing systems are vulnerable to various security threats, such as:
Malware: Software designed to harm or exploit systems (viruses, worms, ransomware).
Phishing: Scams that trick individuals into revealing sensitive information.
Denial of Service (DoS) attacks: Attacks aimed at overwhelming a network or system to make it unavailable to users.
Encryption: Protecting data by converting it into an unreadable format using cryptography, ensuring privacy and security in communication.
SSL/TLS: Protocols for securing data transfer over the web (HTTPS).
Firewalls: Systems that monitor and control incoming and outgoing network traffic based on predetermined security rules.
6. Impact of Networks and Computing Systems
Global Connectivity: The internet connects the world, enabling global communication, collaboration, and access to resources.
Distributed Computing: Computing tasks are shared across multiple computers in a network (e.g., cloud computing, distributed databases).
Internet of Things (IoT): Refers to the interconnection of everyday physical devices (such as smart thermostats, wearables, etc.) via the internet, allowing them to collect and exchange data.
Ethical Considerations: The use of computing systems and networks raises important ethical questions regarding:
Privacy: Protecting users’ personal data.
Accessibility: Ensuring equitable access to technology and networks.
Digital Divide: Addressing inequalities in access to computing and network resources.
Key Concepts to Remember:
IP Address: A unique identifier for a device on a network.
HTTP vs HTTPS: HTTP is unencrypted, while HTTPS ensures encrypted communication over the web.
Network Topology: The physical or logical arrangement of devices in a network (e.g., star, bus, mesh).
Cloud Computing: A computing model where services are delivered over the internet, often in a scalable, on-demand way.
DNS: A system for translating human-readable domain names into machine-readable IP addresses.