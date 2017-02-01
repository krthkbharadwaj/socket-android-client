# socket-android-client
Android app to send and read the Hexadecimal bytes using TCP socket

A client side app to send commands in Hexadecimal and reading the Hexadecimal response.

Steps occur when establishing a TCP connection between two computers using sockets 
-----------------------------------------------------------------------------------
1. Import the java.net.Socket which is the responsible to establish a server connection using socket at client side
2. Client instantiates a Socket object, specifying the server name and the port number to connect to
3. The constructor of the Socket class attempts to connect the client to the specified server and the port number. If communication is established, the client now has a Socket object capable of communicating with the server.
4. A reference is returned to a new socket on the server that is connected to client socket
5. Client is now capable to communicate with server

Here the socket is created with hardcoded port.
Also the port can be given in IpGetter class like InetAddress serverAddress = InetAddress.getByName(ipNumber);
             
Socket socket = new Socket("localhost", 9000);

Create DataOutputStream object for sending messages to server.
DataOutputStream out = new DataOutputStream(socket.getOutputStream());

Create DataInputStream object for receiving messages from server.
DataInputStream in = new DataInputStream(socket.getInputStream());

To write the ouput to server, use the below command. msg contains the string/commands which need to be sent to server
out.write(msg);

To read the response from server, use read() method which takes 3 parameters
in.read(data, off, len);

You can refer the below link to know more about read()
https://developer.android.com/reference/java/io/BufferedInputStream.html#read(byte[], int, int)

data contains the response

Finally, do not forget to take of closing the output,input stream and socket

out.flush(); out.close(); in.close(); socket.close();

Thank you, Cheers !!






