3c.CREATION FOR FILE TRANSFER USING TCP SOCKETS
AIM
To write a python program for creating File Transfer using TCP Sockets Links

ALGORITHM:
Import the necessary python modules.
Create a socket connection using socket module.
Send the message to write into the file to the client file.
Open the file and then send it to the client in byte format.
In the client side receive the file from server and then write the content into it.
PROGRAM
server.py

import socket

server = socket.socket()

server.bind(("127.0.0.1", 5555))

server.listen(1)
print("Server waiting for connection...")

client, addr = server.accept()
print("Connected to:", addr)

filename = input("Enter file name to send: ")

with open(filename, "rb") as file:
    data = file.read()
    client.send(data)

print("File sent successfully")

client.close()
server.close()
client.py

import socket

client = socket.socket()

client.connect(("127.0.0.1", 5555))

save_name = input("Enter name to save file: ")

data = client.recv(1000000)

with open(save_name, "wb") as file:
    file.write(data)

print("File received successfully")

client.close()
OUPUT
server

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/2e600cc0-d51d-48a0-955f-0e71b6f2ac5a" />

client

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/7b52914d-5f44-4ae3-9ba1-0d742c0d9969" />


RESULT

Thus, the python program for creating File Transfer using TCP Sockets Links was successfully created and executed.
