## UDPSocket

<span class="images">![](https://os-doc-builder.test.mbed.com/docs/development/mbed-os-api-doxy/class_u_d_p_socket.png)<span>UDPSocket class hierarchy</span></span>

The UDPSocket class provides the ability to send packets of data over UDP, using the `sendto` and `recvfrom` member functions. Packets can be lost or arrive out of order, so we suggest using a [TCPSocket](/docs/development/reference/tcpsocket.html) when you require guaranteed delivery.

The constructor takes in the NetworkStack pointer to open the socket on the specified NetworkInterface. If you do not pass in the constructor, then you must call `open` to initialize the socket.

UDP is a connectionless protocol. This allows you to send and receive packets to and from any remote adderesses. Therefore, `Socket::listen()` and `Socket::accept()` functions are not implemented on UDPSocket.

If you prefer to use `send()` and `recv()` functions and work only with one peer, UDPSocket does support the `Socket::connect()` function, which sets a permanent peer address to the socket. Setting the peer address starts filtering incoming packets, so they are accepted only from that specific address. You can reset the filtering and peer address by calling `connect()` with empty `SocketAddress`.

### UDPSocket class reference

[![View code](https://www.mbed.com/embed/?type=library)](http://os-doc-builder.test.mbed.com/docs/development/mbed-os-api-doxy/class_u_d_p_socket.html)

### UDPSocket Example

This UDP example reads the current UTC time by sending a request to the NIST Internet Time Service:

[![View code](https://www.mbed.com/embed/?url=https://os.mbed.com/teams/mbed_example/code/mbed-os-example-udp-sockets)](https://os.mbed.com/teams/mbed_example/code/mbed-os-example-udp-sockets/file/cf516d904427/main.cpp)

### Related content

- [TCPSocket](/docs/development/reference/tcpsocket.html) API reference.
