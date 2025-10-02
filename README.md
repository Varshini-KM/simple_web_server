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
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #d8bfd8; /* greyish violet */
        }

        h1 {
            color: darkblue;
        }

        h3 {
            color: #222;
        }

        table {
            border-collapse: collapse;
            margin: 20px auto;
            width: 85%;
        }

        td {
            padding: 15px;
            border-radius: 10px;
        }

        .application {
            background-color: #e0f7fa;
        }

        .transport {
            background-color: #fce4ec;
        }

        .internet {
            background-color: #fff9c4;
        }

        .network {
            background-color: #e8f5e9;
        }

        .application h2 {
            color: #00796b;
        }

        .transport h2 {
            color: #c2185b;
        }

        .internet h2 {
            color: #f57f17;
        }

        .network h2 {
            color: #2e7d32;
        }
    </style>
</head>
<body>

    <h1 align="center" style="font-size:28px;">TCP/IP Protocol Suite</h1>
    <h3 align="center" style="font-size:20px;">Name: VARSHINI K M | Reference Number: 25018756</h3>
    <hr>

    <table cellspacing="0" cellpadding="10">
        <tr>
            <td class="application">
                <h2>Layer 4: Application Layer</h2>
                <p style="font-size:18px;">
                    This is the top layer of the TCP/IP model. It allows the user to access services such as browsing, emails,
                    remote login, and file transfers. Applications directly interact with this layer.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> HTTP, RDP, DHCP, DNS, X Windows, Telnet, SMTP, SSH, TFTP, SNMP, FTP
                </p>
            </td>
        </tr>

        <tr>
            <td class="transport">
                <h2>Layer 3: Transport Layer</h2>
                <p style="font-size:18px;">
                    This layer manages end-to-end communication between devices. It ensures complete and reliable delivery 
                    of data, or in some cases fast delivery without reliability.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> TCP, UDP
                </p>
            </td>
        </tr>

        <tr>
            <td class="internet">
                <h2>Layer 2: Internet Layer</h2>
                <p style="font-size:18px;">
                    This layer decides how data is addressed, packaged, and routed across networks. It allows
                    data to travel from one device to another across multiple networks.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> ICMP, IGMP, ARP, IPv4, IPv6
                </p>
            </td>
        </tr>

        <tr>
            <td class="network">
                <h2>Layer 1: Network Access Layer</h2>
                <p style="font-size:18px;">
                    This is the lowest layer. It deals with the physical transfer of data over different media like 
                    cables, fiber optics, or wireless. It also handles how data is formatted for transmission.
                </p>
                <p style="font-size:18px;">
                    <b>Protocols:</b> Ethernet, FDDI, X.25, Frame Relay, Token Ring
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
![alt text](<Screenshot 2025-10-02 223358.png>)
![alt text](<Screenshot 2025-10-02 234659.png>)
# RESULT:
The program for implementing simple webserver is executed successfully.
