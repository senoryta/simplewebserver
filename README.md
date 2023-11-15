# EX01 Developing a Simple Webserver

## Date: 19-09-2023

## AIM:
To develop a simple webserver to serve html pages.


## DESIGN STEPS:
### Step 1: 
HTML content creation
### Step 2:
Design of webserver workflow
### Step 3:
Implementation using Python code
### Step 4:
Serving the HTML pages.
### Step 5:
Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Webserver</title>
</head>
<body>
    <h1>Top 5 Revenue Companies</h1>
    <ol>
        <li>WalMart</li>
        <li>Amazon</li>
        <li>Saudi Armaco</li>
        <li>SinoPec</li>
        <li>PetroChina</li>
    </ol>
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
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```

## OUTPUT:
![Screenshot (326)](https://github.com/selvasachein/simplewebserver/assets/103128410/5a6f931f-1840-407e-89ba-d5594ab1ab31)
![Screenshot (325)](https://github.com/selvasachein/simplewebserver/assets/103128410/d551f38c-60b9-4e2d-b456-8b4efc9a552d)


## RESULT:
The program for implementing simple webserver is executed successfully.
