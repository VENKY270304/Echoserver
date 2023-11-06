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
## Server Side:
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
## Client Side:
import socket


HOST = "127.0.0.1"  # The server's hostname or IP address
PORT = 65432  # The port used by the server


with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.connect((HOST, PORT))
    s.sendall(b"Hello, world")
    data = s.recv(1024)


print(f"Received {data!r}")

## OUTPUT:
## Server Output:

![Screenshot 2023-11-06 102627](https://github.com/VENKY270304/Echoserver/assets/124234106/047cb1be-2588-4f79-8b4e-85f655589243)##
## Client Output:

![264622529-3a51c91b-09de-4372-994d-53261cf632c1](https://github.com/VENKY270304/Echoserver/assets/124234106/ee774095-fa89-4fb7-afe5-7c6782d6462c)


## RESULT:
The program is executed successfully
