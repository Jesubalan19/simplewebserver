# EX01 Developing a Simple Webserver
## Date:28.02.2024

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
<title>Software Companies</title>
<head>
<body bgcolor="cyan">
<table border="3" cellspacing="4" cellpadding="12" align="center">
<caption>Top Five Revenue Generating Software Companies</caption>
<tr>
<th>Company</th>
<th>Revenue</th>
<th>Net worth</th>
<th>Rank</th>
</tr>
<tr>
<td>Amazon</td>
<td>$427.56 Billion</td>
<td>$1.82 Trillion</td>
<td>1</td>
</tr>
<tr>
<td>Apple</td>
<td>$335.85 Billion</td>
<td>$2.64 Trillion</td>
<td>2</td>
</tr>
<tr>
<td>Samsung</td>
<td>$221.1 Billion</td>
<td>$355 Billion</td>
<td>3</td>
</tr>
<tr>
<td>Google</td>
<td>$217.94 Billion</td>
<td>$1.72 Trillion</td>
<td>4</td>
</tr>
<tr>
<td>Microsoft</td>
<td>$168.95 Billion</td>
<td>$3.02 Trillion</td>
<td>5</td>
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
```

## OUTPUT:
![Alt text](<Screenshot 2024-03-12 114022.png>) 
![Alt text](<Screenshot 2024-03-12 113516.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.
