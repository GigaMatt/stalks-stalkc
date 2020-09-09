# CS 4375 - Operating Systems

## Homework 8

Listed below are the responses to the questions.

**Due to issues with screencapture on macOS Catalina (10.15.5 Beta 2), which is the native OS that the Windows and Linux VMs were running on, I could not take direct screenshots of the output. The terminal output from the Linux & Windows OS was copied & pasted directly into this file.**

### Questions

1. On a single host, start the server in one window and two clients in their own windows. Send alternating messages to the server. Try this on both Windows and Linux. Are there any differences?

The differences I noticed when running on Linux verses Windows is that the port numbers are different. However, both messages still appear.

Below is the input for stalkc.java **on Linux**:
```
(base) montoms1@ubuntu:~/Downloads$ java stalkc
Looking up address of localhost... got it!
Our own port is 43955
LEAN IN (For Graduates) By Sheryl Sandberg
New Waves: A Novel By Kevin Nguyen
```

Below is the output of stalks.java **on Linux**:
```
(base) montoms1@ubuntu:~/Downloads$ java stalks
message from <127.0.0.1,43955>
LEAN IN (For Graduates) By Sheryl Sandberg
message from <127.0.0.1,43955>
New Waves: A Novel By Kevin Nguyen
```

Below is the input for stalkc.java **on Windows**:
```
C:\Users\montoms1\Downloads>java stalkc
Looking up address of localhost... got it!
Our own port is 59047
Why was it so hard to install Java on Windows
Why does the Windows OS exist
It makes webOS seem elegant by comparison
```

Below is the output of stalks.java **on Windows**:
```
C:\Users\montoms1\Downloads>java stalks
message from <127.0.0.1,59047>
Why was it so hard to install Java on Windows
message from <127.0.0.1,59047>
Why does the Windows OS exist
message from <127.0.0.1,59047>
It makes webOS seem elegant by comparison
```

2. Invoke the client with the external IP address of the server.

Here, we see similar results to question 1; the difference is that we have a different port number and it uses the IP address.

Below is the input for stalkc.java:
```
(base) montoms1@ubuntu:~/Downloads$ java stalkc
Looking up address of 24.162.196.68... got it!
Our own port is 53795
VPN Phantom of the Opera
Oh hey there is an IP address now
I dislike remote learning
```

Below is the output of stalks.java:
```
(base) montoms1@ubuntu:~/Downloads$ java stalks
message from <24.162.196.68>
VPN Phantom of the Opera
message from <24.162.196.68>
Oh hey there is an IP address now
message from <24.162.196.68>
I dislike remote learning
```

3. Modify the server to return the message string received from the client back to the client with the string “SERVER: “ prepended. That is, if client1 sends a string “Hello.” to to the server, the server sends the string “SERVER: Hello.” back to the client. Modify the client to receive this message and display it.

In order to produce the output, **stalkc.java** needed to be modified such that the message from the "server" was sent back to the "client" as a String object (variable). Furthermore, **stalks.java** also needed modification, which included the addition of the DatagramSocket's ```send()``` function. Thi allowed the message to be sent from the "server" to the "client".

Below is the input for stalkc.java:
```
(base) montoms1@ubuntu:~/Downloads$ java stalkc
Looking up address of localhost... got it!
Our own port is 34880
HELLO FROM THE OTHER SIDE
SERVER: HELLO FROM THE OTHER SIDE

TikTok is life in a mood of depression
SERVER: TikTok is life in a mood of depression

I fly to LA tomorrow; laters EP
SERVER: I fly to LA tomorrow; laters EP
```

Below is the output of stalks.java:
```
(base) montoms1@ubuntu:~/Downloads$ java stalks
Response timed out!
message from <127.0.0.1,34880>
HELLO FROM THE OTHER SIDE
message from <127.0.0.1,34880>
TikTok is life in a mood of depression
message from <127.0.0.1,34880>
I fly to LA tomorrow; laters EP
```
