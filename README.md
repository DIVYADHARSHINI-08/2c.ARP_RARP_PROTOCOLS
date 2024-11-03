# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
```
Developed by: DIVYA DHARSHINI R
Reg no: 212223040042

Client :
import socket 
s=socket.socket() 
s.bind(('localhost',8000)) 
s.listen(5) 
c,addr=s.accept() 
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())

Server :
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
ip=input("Enter logical Address : ") 
s.send(ip.encode())
print("MAC Address",s.recv(1024).decode()) 
```
## OUPUT - ARP
![WhatsApp Image 2024-11-03 at 14 14 25_8edebb27](https://github.com/user-attachments/assets/4d6ec46d-6fb1-4f29-bf02-d84a76e20a1a)

![WhatsApp Image 2024-11-03 at 14 14 25_75b8ab3c](https://github.com/user-attachments/assets/b7ce3b51-30d2-4d57-9bd6-22753773254c)

## PROGRAM - RARP
```
Client : 
import socket 
s=socket.socket() 
s.bind(('localhost',9000)) 
s.listen(5) 
c,addr=s.accept() 
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"}; 
while True: 
            ip=c.recv(1024).decode() 
            try: 
                c.send(address[ip].encode()) 
            except KeyError: 
                c.send("Not Found".encode())

Server :
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
    ip=input("Enter MAC Address : ") 
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
![WhatsApp Image 2024-11-03 at 14 16 37_c66c7a9a](https://github.com/user-attachments/assets/64a8eba0-7a5c-4f27-82c8-8fd58e22a3a4)

![WhatsApp Image 2024-11-03 at 14 16 37_7c2d9eff](https://github.com/user-attachments/assets/52570b02-412e-4eed-8535-668cf43aa57c)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
