<h2>Exercise 2: Analyze a HTTP Authentication</h2>

<h3>Objectives</h3>
- ...
<br />
- ...
<br />
- ...
<br />
- ...

<h3>Step 1: Initiate a Basic HTTP Authentication</h3>
To capture HTTP traffic, I'll set the capture filter to port 80, as HTTP typically operates on this port. Using a non-private web server accessible to the public, I'll navigate to an HTTP page where I'll input both the correct and incorrect passwords. Upon entering the correct password, "password," I anticipate receiving an authentication message. 
<br />
<img src="https://github.com/Yagoobz/AnalyzingHTTPAuthentication/assets/145611184/7057eed6-56bd-4a90-a25f-d2293cb50b55" height="30%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://github.com/Yagoobz/AnalyzingHTTPAuthentication/assets/145611184/6f19eacd-7f9a-418b-bbe0-3a69d1452274" height="30%" width="70%" alt="Disk Sanitization Steps"/>

<h3>Step 2: Analyze Packets in Wireshark</h3>
All communications sent thus far have remained unencrypted. Initially, an authentication request was made, resulting in a 401 unauthorized response, indicating denial. However, in the subsequent request, a "200 OK" response was received, signifying successful authentication. This transparency poses a security risk as it exposes all actions undertaken during the process.
<br />
<img src="https://github.com/Yagoobz/AnalyzingHTTPAuthentication/assets/145611184/97362f77-ad7f-424f-b351-21d6765fbffc" height="30%" width="70%" alt="Disk Sanitization Steps"/>
<br />
Recognizing the inherent insecurity, I resolved to uncover the username and incorrect password transmitted to the web server. This involved clicking on the initial packet, expanding the "Hypertext Transfer Protocol" section, and further expanding "Authorization," revealing the username and incorrect password. Subsequently, repeating the process for the "200 OK" packet unveiled both the username and, this time, the correct password.
<br />
<img src="https://github.com/Yagoobz/AnalyzingHTTPAuthentication/assets/145611184/7057eed6-56bd-4a90-a25f-d2293cb50b55" height="30%" width="70%" alt="Disk Sanitization Steps"/>
<br />
<img src="https://github.com/Yagoobz/AnalyzingHTTPAuthentication/assets/145611184/6f19eacd-7f9a-418b-bbe0-3a69d1452274" height="30%" width="70%" alt="Disk Sanitization Steps"/>

