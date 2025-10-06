# 2a_Stop_and_Wait_Protocol
## NAME : Reena K
## REGISTER NO : 212224040272
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
## SERVER
```
import socket 
s=socket.socket() 
s.bind(('localhost',8080))

s.listen(5) 
c,addr=s.accept() 
while True: 
    i=input("Enter a data: ") 
    c.send(i.encode()) 
    ack=c.recv(1024).decode() 
    if ack: 
        print(ack) 
        continue 
    else: 
        c.close() 
        break 
```
## CLIENT
```
import socket 
s=socket.socket() 
s.connect(('localhost',8080)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT

## server

<img width="589" height="191" alt="Screenshot 2025-10-06 161840" src="https://github.com/user-attachments/assets/deffbdfe-0ae2-40db-a442-f4cf1642463b" />

## client 

<img width="660" height="316" alt="Screenshot 2025-10-06 161829" src="https://github.com/user-attachments/assets/b67cf28a-8768-4bae-9ba9-2b9a2fd95cb5" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
