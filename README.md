# Developing a Simple Webserver

# AIM:

To develop a program to display top 3 programming languages

## DESIGN STEPS:

### Step 1:

HTML content creation is done

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
<html>
<head>
</head>
<body>
<h1>welcome to the webserver</h1>
</body>
</html>
"""

class WebHandler(BaseHTTPRequestHandler):
     def do_GET(self):
         self.send_response(200)
         self.send_header('content-type','text/html;charset=utf-8')
         self.end_headers()
         self.wfile.write(content.encode())
         
server_address = ('',8080)
httpd = HTTPServer(server_address,WebHandler)
print("Web Server running....")
httpd.serve_forever() 

```
## OUTPUT:

### Server Side Output
![Server Side Output](./images/serveroutput.png)

### Client Side Output
![Client Side Output](./images/clientoutput.png)
## RESULT:
Thus the program is to display top 3 programming languages
