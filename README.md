# Developing a Simple Webserver
## AIM:
To develop a simple webserver to display top five programing languages
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
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1 style="color:pink">TOP FIVE PROGRAMING LANGUAGES</h1>

<h1 style="color:yellow">1.javascript</h1>
<p style="color:black">designed by : brendan eich of netscape initially;others have also contributed to EMAscript standard.</p>

<p>JAVASCRIPT,often abbreviated as JS,is a programming 
*it conforms to the EMCAscript specification
*JS is high level,often just-in-time compiled and multi paradigm
*it has dynamic typing,prototype-based object- orientation and first class functions.</p>
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


## OUTPUT:


## RESULT:
