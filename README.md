# Ex. No:1b 			STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

## Aim: 
To implement socket programming date and time display from client to server using TCPSockets

## ALGORITHM :

## Server:

1.Create a server socket and bind it to port.

2.Listen for new connection and when a connection arrives, accept it.

3.Send server‟s date and time to the client.

4.Read client‟s IP address sent by the client.

5.Display the client details.

6.Repeat steps 2-5 until the server is terminated.

7.Close all streams.

8.Close the server socket.

9.Stop.

## Client:

1.Create a client socket and connect it to the server‟s port number.

2.Retrieve its own IP address using built-in function.

3.Send its address to the server.

4.Display the date & time sent by the server.

5.Close the input and output streams.

6.Close the client socket.

7.Stop.

## Program 
## Client Program:
```

```

## Server Program:
```
import socket
s = socket.socket()
host = socket.gethostname()
print(' Server will start on host : ',host) 
port = 8080
s.bind((host, port))
print()
print('Waiting for connection')
print()
s.listen(1)
conn, addr = s.accept()
print(addr, ' Has connected to the server') 
print()
while 1:
    message = input(str('>> '))
    message = message.encode()
    conn.send(message)
    print('Sent')
    print()
    incoming_message = conn.recv(1024)
    incoming_message = incoming_message.decode()
    print(' Client : ',incoming_message)
    print()         
```
## Client Program:
```
import socket
s = socket.socket()
host = input(str('Enter hostname or host IP : '))
port= 8080
s.connect((host, port))
print('Connected to chat server')
while 1:
    incoming_message = s.recv(1024)
    incoming_message = incoming_message.decode()
    print(' Server : ',incoming_message) 
    print()
    message = input(str('>> '))
    message = message.encode()
    s.send(message)
    print('Sent')
    print()
```

## Output:

<img width="1920" height="1080" alt="Screenshot 2026-05-26 181131" src="https://github.com/user-attachments/assets/339da017-811f-48f9-a373-318927f54907" />

<img width="1920" height="1080" alt="Screenshot 2026-05-26 181142" src="https://github.com/user-attachments/assets/9d55ce12-54b9-4420-99f9-05dc6ac4af74" />


## Result:

Thus, the program to implement socket programming date and time display from client to server
using TCP Sockets was successfully executed.
