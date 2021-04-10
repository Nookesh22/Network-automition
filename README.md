 **Aim of the project**
 **********
Deploy nginx on webservers and haproxy on load-balancer.
The load-balancer should be able to successfully load balance the client requests.
Serve a simple web page deployed on web servers through load-balancer depending upon the balance.
Setup
***********


**Required network to be created**
***************
(Internet)---> HAProxy	
		+--->A	|--
		+--->B	| |---> (Internal Private Network (10.0.1.0/27)	
		+--->C	|--
(Internet) --->	Bastion
****************


**Deployment of nginx into webservers and haproxy load balancer into haproxy server**

***************
Deploy nginx servers to targeted webserver hosts and required php packages also to targeted webserver hosts.
Configure nginx servers on webserver hosts, restart the servers.
Deploy haproxy to targeted load balancer hosts.
Configuration file for haproxy written initially using Jinja2 templating engine, which renders the dynamic information of hosts. Here, it renders the hosts ip addresses. All templates rendered using Jinja2 templating engine are placed under templates directory.
Restart haproxy servers.
***************




**Command to run the playbook**
*********
ansible-playbook -i hosts site.yaml
*********
