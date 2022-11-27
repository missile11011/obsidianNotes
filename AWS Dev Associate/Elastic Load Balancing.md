ELB directs and distribute traffic to multiple targets ex. EC2. Traffic can be distribute accross one or multiple AZ within the same region. Ensures that traffic is sent to healthy targets. Thes's a single point of accesss to the application. Only one subnet for each AZ for each ELB. ELB can be internet facing(public) ro internal(private). They're four kinds of load balancers Classic (CLB), Application (ALB), Network (NLB), and Gateway (GLB). CLB it outdated and provides the basics at OSI Layer 4 and 7. ALB sue OSI layer 7 routes based on request. NLB USE OSI Layer 4 routes connection on IP protocol data. GLB use OSI Layer 4 and 7 placed in front of things like firewalls and IDS/IPS. Perfect Forward Security(PFS) adds protection for encryted data by creating random session keys. ALB balces to multiple HTTP applications across machines and to multiple application on the same machine.
<font class="h3">ELB Security Groups:</font> controls the ports and protocols that can rach the fornt0end listener. Also need to allow the ports for health checks ports and back-end listener.
<font class="h3">Security Groups Configuration for Elastic Load Balancer</font>
Inbound Internet-facing:
<table>
	<tb>
	<tr>
		<th>Source</th>
		<th>Protocol</th>
		<th>Port Range</th>
	</tr>
	<tr>
		<td>0.0.0.0/0</td>
		<td>TCP</td>
		<td>Listner</td>
	</tr>
	</tb>
</table>
Outbound Internet-facing:
<table>
	<tb>
		<tr>
			<th>Destenation</th>
			<th>Protocol</th>
			<th>Port Range</th>
		</tr>
		<tr>
			<td>Instance Security Group</td>
			<td>TCP</td>
			<td>Instance Listner</td>
		</tr>
		<tr>
			<td>Instance Security Group</td>
			<td>TCP</td>
			<td>Health Check</td>
		</tr>
	</tb>
</table>
Inbound Internal use:
<table>
	<tb>
	<tr>
		<th>Source</th>
		<th>Protocol</th>
		<th>Port Range</th>
	</tr>
	<tr>
		<td>VPC CIDR</td>
		<td>TCP</td>
		<td>Listner</td>
	</tr>
	</tb>
</table>
Outbound Internal use:
<table>
	<tb>
		<tr>
			<th>Destenation</th>
			<th>Protocol</th>
			<th>Port Range</th>
		</tr>
		<tr>
			<td>Instance Security Group</td>
			<td>TCP</td>
			<td>Instance Listner</td>
		</tr>
		<tr>
			<td>Instance Security Group</td>
			<td>TCP</td>
			<td>Health Check</td>
		</tr>
	</tb>
</table>

<font class="h3">Target Groups:</font> are groups for targets and are used with ALB, NLB, and GLB. The targets can be EC2 instnaces, ECS containers, IP addresses, Lambda function and other Load Balancers. A target group can only be linked to one Load Balancer. Target groups are region based just like Elastic Load Balancer. You can't mix types of targets within the targets group like EC2, IP or Lambda.
<font class="h3">Application Load Balancer</font> 
Application Load Balancer uses OSI Layer 7 to opperate to route traffic to EC2, containers, and IP address targets. Use ALB for HTTP/HTTPS application. ALB supports Server Name  Indication(SNI) to allow multiple sites to a single server listiner. IP address can be targets for application hosted on AWS or for back-end instances/servers as targets. It's required to enable two AZ or more for ALB. Can be intergated with [[Amazon Cognito]].
<font class="h3">Network Load Balancer</font>
Network Load Balancer uses OSI Layer 4, routes to EC2, containers, and IP addresses based on IP protocol data. Can handle millions of requests per second to support volatile traffic with low latency. NLB has one static IP/Elastic IPO for each AZ. Supports loning running connections idel for WebSocket applications.
### Gateway Load Balancer ###
uses the GENEVE protocol. Opperates at the third layer of the OSI. GLB deploy, scale, and manage virtual appliances. For example firwalls, intrusion detection, prevention system, and deep packet inspection. It's a transparent gateway so all entry and exit traffic goes throuh one point. The targets are EC2, IP addresses. The GENEVE protocol is on <font class="highlight-y">port 6081</font>.
### Sticky Sessions###
Sticky sessions makes the Load Balancers to attach it's self to a user session and allows all requests are sent to the same target. Keeps user data exchange to targets low. Sticky sessions uses cookies.
### Cross Zone Load Balancer###
Calssic, Application, Network, Gateway Load Balncers can be enabled except for for Application Load Balancers it's always on. <font class="highlight-y">All Load Balncers destributes traffic evenly to all targets across AZ</font>
### SSL Certification###
encrytpes traffic in transit SSL(Secure Sockets Layer)and TLS(Tarnsport Layer Security) is the newer version. TLS are mainly used but SSL certifcates for one web server use SNI(Server Name Indication). SNI work for ALB and NLB new generation. <font class="Use ACM"</font>




#AWS #AWS-compute #aws-developer-associate