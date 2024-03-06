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

# echo-server.py

Server code:

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
            
Client code:

# echo-client.py


import socket


HOST = "127.0.0.1"  # The server's hostname or IP address

PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:

    s.connect((HOST, PORT))
    
    s.sendall(b"Hello, world")
    
    data = s.recv(1024)


print(f"Received {data!r}")

## OUTPUT:
Server side:
![image](https://github.com/Manjupriya1207/Echoserver/assets/113583090/950ff60b-8547-4161-b691-c2ab60f4af56)

Client side:
![image](https://github.com/Manjupriya1207/Echoserver/assets/113583090/fcf98369-cd04-4adb-be1f-afecf6317bcd)


## RESULT:
The program is executed successfully
