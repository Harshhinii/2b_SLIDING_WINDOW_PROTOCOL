# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
   while(i<len(l)):
        st+=s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
           print(ack)
           i+=s
```
```
server:
import socket
s=socket.socket()
s.connect(('localhost',8000)
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
CLIENT:
![Screenshot 2024-03-06 202642](https://github.com/Harshhinii/2b_SLIDING_WINDOW_PROTOCOL/assets/148633023/971a1418-664c-4187-8fb3-4f0e77dafdd8)

SERVER:
![Screenshot 2024-03-06 202652](https://github.com/Harshhinii/2b_SLIDING_WINDOW_PROTOCOL/assets/148633023/0b39cd6e-50b5-4708-8f02-c1d2a7e78db1)


## RESULT
Thus, python program to perform IMPLEMENTATION OF SLIDING WINDOW PROTOCOL was successfully executed
