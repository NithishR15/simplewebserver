# EX01 Developing a Simple Webserver
## Date: 06.10.2023

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
<html>
       <title>Software Companies</title>
       <body>
       <table border="20"cellspacing="4">
       <captions> top five revenue generating software compaines</captions>
       <tr>
       <th> s.no </th>
       <th> company</th>
       <th> Revenue </th>
       </tr>
<tr>
<th>1</th>
<th>Microsoft</th>
<th>65.00billion</th>
</tr>
<tr>
<th>2</th>
<th>Oracle</th>
<th>60billion</th>
</tr>
<tr>
<th>3</th>
<th>IBM</th>
<th>34</th>
</tr>
<tr>
<th>4</th>
<th>SAP</th>
<th>6.9billion</th>
</tr>
<tr>
<th>5</th>
<th>symantec</th>
<th>5</th>
</tr>
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
```
## OUTPUT:
![Alt text](<Screenshot (2).png>)

![Alt text](<Screenshot (3).png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
