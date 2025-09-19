# EX01 Developing a Simple Webserver

# Date:18.09.2025
# AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.


# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```

from http.server import HTTPServer, BaseHTTPRequestHandler
content ='''<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Suite</title>
</head>
<body>

    <h1 align="center" style="font-size:28px;">TCP/IP Protocol Suite</h1>
    <h3 align="center" style="font-size:20px;">Name: VARSHINI K M | Reference Number: 25018756</h3>
    <hr>

    <table border="1" width="85%" align="center" cellspacing="0" cellpadding="10">
        <tr>
            <td>
                <h2 style="color:blue;">Layer 4: Application Layer</h2>
                <p style="font-size:18px;">
                    This is the top layer of the TCP/IP model. It allows the user to access services such as browsing, emails,
                    remote login, and file transfers. Applications directly interact with this layer.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> <b>HTTP</b>, <b>RDP</b>, <b>DHCP</b>, <b>DNS</b>, <b>X Windows</b>, <b>Telnet</b>, 
                    <b>SMTP</b>, <b>SSH</b>, <b>TFTP</b>, <b>SNMP</b>, <b>FTP</b>
                </p>
            </td>
        </tr>

        <tr>
            <td>
                <h2 style="color:blue;">Layer 3: Transport Layer</h2>
                <p style="font-size:18px;">
                    This layer manages end-to-end communication between devices. It ensures complete and reliable delivery 
                    of data, or in some cases fast delivery without reliability.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> <b>TCP</b>, <b>UDP</b>
                </p>
            </td>
        </tr>

        <tr>
            <td>
                <h2 style="color:blue;">Layer 2: Internet Layer</h2>
                <p style="font-size:18px;">
                    This layer decides how data is addressed, packaged, and routed across networks. It allows
                    data to travel from one device to another across multiple networks.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> <b>ICMP</b>, <b>IGMP</b>, <b>ARP</b>, <b>IPv4</b>, <b>IPv6</b>
                </p>
            </td>
        </tr>

        <tr>
            <td>
                <h2 style="color:blue;">Layer 1: Network Access Layer</h2>
                <p style="font-size:18px;">
                    This is the lowest layer. It deals with the physical transfer of data over different media like 
                    cables, fiber optics, or wireless. It also handles how data is formatted for transmission.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> <b>Ethernet</b>, <b>FDDI</b>, <b>X.25</b>, <b>Frame Relay</b>, <b>Token Ring</b>
                </p>
            </td>
        </tr>
    </table>

</body>
</html>
'''
class MyServer (BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response (200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())
print("This is my webserver") 
server_address = ('',8000)
httpd = HTTPServer (server_address, MyServer)
httpd.serve_forever()

```
# OUTPUT:
![alt text](<Screenshot 2025-09-18 231101.png>)

![alt text](<Screenshot 2025-09-18 231330.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.
