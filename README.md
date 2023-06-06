STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL
EXP: 1
DATE :08-03-2023
AIM :
To write a python program to perform stop and wait protocol
ALGORITHM :
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client otherwise it will sendNACK signal to client.
6. Stop the program
CLIENT PROGRAM :
import socket
s=socket.socket()
s.bind(('localhost',8080))
s.listen(5)
c,addr=s.accept()
while True:
	i=input("ENter a data:")
	c.send(i.encode())
	ack=c.recv(1024).decode()
	if ack:
		print(ack)
		continue
	else:
		c.close()
		break
SERVER PROGRAM :
import socket
s=socket.socket()
s.connect(('localhost',8080))
while True:
	print(s.recv(1024).decode())
	s.send("Recieved".encode())
CLIENT OUTPUT :
241374228-776252bb-9f63-4361-b551-55aa746effd5

SERVER OUTPUT :
241374231-6ff91ac9-c4d2-44f3-9ce9-c2195c6dab42

RESULT:
Thus, python program to perform stop and wait protocol was successfully executed.

