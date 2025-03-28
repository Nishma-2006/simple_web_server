# EX01 Developing a Simple Webserver
# NISHMA SHERIN.K
# Date:28/03/2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<!doctype html>
<html>
    <body bgcolor="PURPLE">
        <table border="5" cellpadding="22" aling="center" bgcolor="cyan">
            <caption aling="center">LAPTOP CONFIGURATION </caption>
        
        <tr bgcolor="blue">
            <th>0</th><th>Frequency</th><th>3.40 GHz</th>
        </tr>
        <tr>
            <th>1</th><th>PROCESSOR</th><th>4 out-of-order cores</th>
        </tr>
        <tr>
            <th>2</th><th>L1 I/D Caches</th><th>64KB,8-Way,private</th>
        </tr>
        <TR>
            <th>3</th><th>L2 I/D Caches</th><th>256 KB,8-Way,private</th>
        </TR>
        <tr>
            <th>4</th><th>Coherence Protocol</th><th>MESI</th>
        </tr>
        <tr>
            <th>5</th><th>MEMORY</th><TH>DDR4-1600,4GB</TH>
            </tr>
            
        

        
            
        </table>


    </body>
        
    
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
# OUTPUT:
![Screenshot 2025-03-28 232754](https://github.com/user-attachments/assets/e7450b03-5b43-4fee-9e6b-e66d3d94ce3e)

# RESULT:
The program for implementing simple webserver is executed successfully.
