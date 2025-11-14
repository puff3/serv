# .serv

`.serv` is a single-file Python program that provides an encrypted
terminal-based chat system. One user runs the chat **host**, and other
users connect as **clients**. All messages are encrypted using a shared
session key generated when the host starts.

This tool is lightweight, cross-platform, and requires only Python 3.


## Features

- Encrypted messaging between host and clients
- Simple terminal UI
- Allows multiple users to connect
- Users can change their nickname at any time
- Extremely small, single-file design


## Requirements

You need:

- **Python 3.8 or newer**
- The Python `cryptography` package

Install the dependency with:

pip install cryptography


## Usage

### Start a Host

python3 .serv host --port 9009


If no port is given, the default is used.

The host will generate a session key automatically and begin listening
for incoming clients.


### Connect as a Client

python3 .serv connect <host-ip> <port>


Example:

python3 .serv connect 127.0.0.1 9009


## Chat Commands

There is **only one command** inside the chat for now:

### **Change your nickname**

/nick newname


Example:

/nick Alice


All other input is treated as a normal chat message.


## Notes

- Messages are encrypted using Fernet from the `cryptography` library.
- If clients are on the internet rather than the same LAN, port
  forwarding may be required.
- To stop the program, press `Ctrl+C`.
