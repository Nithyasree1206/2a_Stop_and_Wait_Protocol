# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
 server:
 ~~~
 import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(5)

c, addr = s.accept()

while True:
    i = input("Enter a data: ")
    c.send(i.encode())

    ack = c.recv(1024).decode()

    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
~~~
client:
~~~
import socket

s = socket.socket()
s.connect(('localhost', 8000))

while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
 ~~~
## OUTPUT

<img width="467" height="114" alt="server" src="https://github.com/user-attachments/assets/229acbd7-916d-4531-811f-d14fde4a1c15" />

<img width="494" height="118" alt="cn" src="https://github.com/user-attachments/assets/00730437-0493-413b-86b9-cf354f00354a" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
