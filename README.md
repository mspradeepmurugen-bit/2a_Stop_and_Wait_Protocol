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
```
import socket

s = socket.socket()
s.bind(('localhost', 8000))
s.listen(1)

print("Waiting for connection...")
conn, addr = s.accept()
print("Connected to", addr)

while True:
    data = conn.recv(1024).decode()
    if not data:
        break

    print("Frame received:", data)
    conn.send("ACK".encode())

conn.close()
```
```
import socket

s = socket.socket()
s.connect(('localhost', 8000))

n = int(input("Enter number of frames: "))

for i in range(n):
    msg = input("Enter frame: ")
    s.send(msg.encode())

    ack = s.recv(1024).decode()
    print("Received:", ack)

s.close()
```
## OUTPUT
<img width="1344" height="282" alt="Screenshot 2026-05-13 081837" src="https://github.com/user-attachments/assets/ea9f7ac8-af8f-4a43-b62b-dc2789113903" />
<img width="1457" height="336" alt="Screenshot 2026-05-13 081852" src="https://github.com/user-attachments/assets/b4e7997e-f4f6-4995-a36c-910e4d3e4779" />

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
