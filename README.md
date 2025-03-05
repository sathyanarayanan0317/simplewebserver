# EX01 Developing a Simple Webserver
## Date:05.03.25

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
<head>
<title>Software Companies</title>
</head>
<body bgcolor="pink">
<table border="9" cellspacing="10" cellpadding="10" height="150" width="300" align="center">
<caption> <h3>Top Five Revenue Generating Sotware Companies </h3></caption>
<tr>
<th>Company</th>
<th>Sales(USD)</th>
<th>Nationality</th>
</tr>
<tr>
<th>Microsoft</th>
<th>57.9</th>
<th>USA</th>
</tr>
<tr>
<th>Oracle</th>
<th>21.0</th>
<th>USA</th>
</tr>
<tr>
<th>SAP</th>
<th>16.1</th>
<th>Germany</th>
</tr>
<tr>
<th>Computer Associates</th>
<th>4.2</th>
<th>USA</th>
</tr>
<tr>
<th>Electronic Arts</th>
<th>3.2</th>
<th>USA</th>
</tr>
</table>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
`````
## OUTPUT:
![Screenshot (2)](https://github.com/user-attachments/assets/0af4e6f4-bd63-4303-bc87-b0d4b99be6ab)
![Screenshot (1)](https://github.com/user-attachments/assets/bc0ba69d-ee14-43e0-a441-e9cb305f2782)




## RESULT:
The program for implementing simple webserver is executed successfully.
