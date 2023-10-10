# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Top five Revenue generating Software Companies</h1>
<ol>
<li>Microsoft</li>
<li>Infosys</li>
<li>google</li>
<li>IBM</li>
<li>amazon</li>
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
server_address = ('',8004)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever(

```

## OUTPUT:
![image](https://github.com/kavisree86/simplewebserver/assets/145759687/c5982c70-ad55-4ad7-8ae7-e2946c56a0e7)


## RESULT:
The program for implementing simple webserver is executed successfully.
