# Echoserver
Echo server and client using python socket

# AIM:

To develop a simple webserver to serve html programming pages.

## DESIGN STEPS:

### Step 1:

Design of echo server and client using python socket

### Step 2:

Implementation using Python code

### Step 3:

Testing the server and client 

## PROGRAM:
```
Name : Vineesh.M
Reg no: 212221230122
```

### server code
```py
# echo-server.py
import socket

HOST = "127.0.0.1"  # Standard loopback interface address (localhost)
PORT = 65432  # Port to listen on (non-privileged ports are > 1023)

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind((HOST, PORT))
    s.listen()
    conn, addr = s.accept()
    with conn:
        print(f"Connected by {addr}")
        while True:
            data = conn.recv(1024)
            if not data:
                break
            conn.sendall(data)
```

### server code
```py
# echo-client.py

import socket

HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)

print(f"Received {data!r}")
```

## OUTPUT:
### Server side:

![1](https://github.com/Vineesh-AI-DS/Echoserver/assets/93427254/04a87f19-e326-436c-93ea-b1ac08aafdbb)

### Client Side :
![2](https://github.com/Vineesh-AI-DS/Echoserver/assets/93427254/1b4ea11d-8953-436b-b5bc-a16f426b13c5)


## RESULT:
The program is executed successfully
