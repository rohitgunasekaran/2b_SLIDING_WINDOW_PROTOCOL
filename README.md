# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
### NAME:G.ROHIT
### REGISTER NUMBER:212222240083

## AIM:
To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM:
## CLIENT:
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
 
# SERVER:
import socket    
s=socket.socket()   
s.connect(('localhost',8000))   
while True:    
 print(s.recv(1024).decode())    
 s.send("acknowledgement recived from the server".encode())

## OUPUT
### client:
 <img src="https://github.com/aaliyafathimaa/2b_SLIDING_WINDOW_PROTOCOL/assets/154801069/1ccde7bd-7b63-4d4e-8d3d-ed240a7d0fda.type" width="" height="">

### server:

 <img src="https://github.com/aaliyafathimaa/2b_SLIDING_WINDOW_PROTOCOL/assets/154801069/03ed98ce-a702-41e0-9ca6-78c5c11ad66b.type" width="" height="">


## RESULT:
Thus, python program to perform stop and wait protocol was successfully executed
