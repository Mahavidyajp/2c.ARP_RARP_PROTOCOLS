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
## CLIENT
```
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
 ```
## SERVER
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```
## OUPUT - ARP
## CLIENT

![image](https://github.com/Mahavidyajp/2c.ARP_RARP_PROTOCOLS/assets/144870914/a03a00b4-1675-4016-910d-d68011e22fba)

## SERVER

![image](https://github.com/Mahavidyajp/2c.ARP_RARP_PROTOCOLS/assets/144870914/a8289a7d-c570-4b45-894f-93401b2136ff)

## PROGRAM - RARP
## CLIENT
```
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
```
## SERVER
```
import socket 
s=socket.socket() 
s.connect(('localhost',9000)) 
while True: 
    ip=input("Enter MAC Address : ") 
    s.send(ip.encode()) 
    print("Logical Address",s.recv(1024).decode())
```
## OUPUT -RARP
## CLIENT

![image](https://github.com/Mahavidyajp/2c.ARP_RARP_PROTOCOLS/assets/144870914/f53c5fd0-cc57-4779-978c-84cae0e58b3b)

## SERVER

![image](https://github.com/Mahavidyajp/2c.ARP_RARP_PROTOCOLS/assets/144870914/dcc24490-2630-4107-9cbf-adc5b0b04dc0)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
