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
## SERVER
~~~
import socket
s = socket.socket()
s.bind(('localhost', 9999))
s.listen(1)
print("Server listening...")
conn, addr = s.accept()
print(f"Connected to {addr}")

while True:
    frames = conn.recv(1024).decode()
    if not frames:
        break

    print(f"Received frames: {frames}")
    ack_message = f"ACK for frames: {frames}"
    conn.send(ack_message.encode())

conn.close()  
s.close()
~~~
## CLIENT
~~~
import socket
s = socket.socket()
s.bind(('localhost', 9999))
s.listen(1)
print("Server listening...")
conn, addr = s.accept()
print(f"Connected to {addr}")

while True:
    frames = conn.recv(1024).decode()
    if not frames:
        break

    print(f"Received frames: {frames}")
    ack_message = f"ACK for frames: {frames}"
    conn.send(ack_message.encode())

conn.close()  
s.close()
~~~
## OUTPUT
## SERVER
~~~
<img width="1358" height="189" alt="Screenshot 2026-02-14 111501" src="https://github.com/user-attachments/assets/54dbe786-7fb9-4775-99a5-7a1a6da5b582" />

~~~
## CLIENT
~~~
<img width="1416" height="211" alt="Screenshot 2026-02-14 111407" src="https://github.com/user-attachments/assets/865b3c68-8653-410e-be43-4b3c0c2a3088" />

~~~
## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
