# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## AIM :
to implement the silding window protocol

## ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
   
## PROGRAM :

### CLIENT :

```
NAME : Mohamed Hameem Sajith J
REG NO :212223240090

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
### SERVER :

```
NAME : Mohamed Hameem Sajith J
REG NO :212223240090

import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
   print(s.recv(1024).decode())
   s.send("acknowledgement recived from the server".encode())

```
## OUPUT :

### CLIENT :

![image](https://github.com/user-attachments/assets/44bdc0e2-7125-4233-afe0-894dd7a032f2)

### SERVER :

![image](https://github.com/user-attachments/assets/06460379-f41c-47ca-a7d1-6f907ff79a61)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
