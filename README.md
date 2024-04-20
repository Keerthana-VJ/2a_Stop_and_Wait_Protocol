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
## CLIENT:
```
import socket 
s=socket.socket() 
s.bind(('localhost',8000))
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

## SERVER:
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```
## OUTPUT
## CLIENT:
<img width="409" alt="Screenshot 2024-04-20 211802" src="https://github.com/Keerthana-VJ/2a_Stop_and_Wait_Protocol/assets/149347704/572d6849-8977-4dd1-97e3-ca71774c1e3e">

## SERVER:
<img width="407" alt="Screenshot 2024-04-20 211819" src="https://github.com/Keerthana-VJ/2a_Stop_and_Wait_Protocol/assets/149347704/27a85155-27a9-4ecc-abac-3590c2af5dd9">

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
