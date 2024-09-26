# EX01 Developing a Simple Webserver
## Date: 26-09-24

## AIM:
To develop a simple webserver to display the configuration details of my laptop.

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

content = '''
<!DOCTYPE html>
<html>
  <head>
    <title>Manisri latha 212223110025</title>
  </head>
  <body>
      <h1>My Laptop Configuration</h1>
      <h2>Manisri latha 212223110025</h2>
      <br>
      <table align="center" border="2" cellpadding="5">
        <tr>
          <th>Specifications</th>
          <th>Details</th>
        </tr>
        <tr>
          <td>Brand</td>
          <td>Samsung</td>
        </tr>
        <tr>
          <td>Model Name</td>
          <td>Galaxy Book 2</td>
        </tr>
        <tr>
          <td>Screen Size</td>
          <td>15.6</td>
        </tr>
        <tr>
          <td>Harddisk Size</td>
          <td>512 GB</td>
        </tr>
        <tr>
          <td>CPU Model</td>
          <td>Others</td>
        </tr>
        <tr>
          <td>RAM Memory Installed Size</td>
          <td>8 GB</td>
        </tr>
        <tr>
          <td>Operating System</td>
          <td>Windows 11 Home</td>
        </tr>
        <tr>
          <td>Special Feature</td>
          <td>Fingerprint Reader</td>
        </tr>
        <tr>
          <td>Graphics Card Description</td>
          <td>Integrated</td>
        </tr>
      </table>
  </body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("GET request received")
        self.send_response(200)
        self.send_header("Content-Type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is a web server")
server_address = ('', 8000)
httpd = HTTPServer(server_address, MyServer)
httpd.serve_forever()
```
## OUTPUT:
![Screenshot 2024-09-26 112934](https://github.com/user-attachments/assets/273db1ec-bc5f-4448-a219-caac9b585886)

![Screenshot 2024-09-26 112853](https://github.com/user-attachments/assets/633c1d0f-e713-49db-bd42-b619ab561cca)

## RESULT:
The program for implementing simple webserver is executed successfully.
