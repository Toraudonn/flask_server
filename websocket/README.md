# Websocket with Flask

History:

For the most part, back then web was built around the idea of client's requesting data and the server fulfilling the requests.
In 2005 when AJAX was introduced, it became possible for the client-server relationship to be more __bidirectional__.

Web applications had grown up alot and were now consuming more data than ever before.
The biggest thing holding them back was the traditional HTTP model of client initiated transactions.
To overcome this a number of different stratigies were devised to allow servers to push data to the client.
One was to solve this issue was with the use of _long-polling_.
This involves keeping HTTP connection open until the server has some data to push down to the client.

The problem with these types of solutions is that they carry the overhead of HTTP. Everytime you make an HTTP request, a bunch of headers and cookie data are transferred to the server. This can add up to a reasonably large amount of data that needs to be transferred, which in turn increases latency. Reducing latency is crucial to keep things running smoothly in a demanding application such as realtime multiplayer game.

> ... The worst part is that a lot of these headers and cookies aren't actually needed to fulfill the client's request.

What we really need is a way of creating a persistent, low latency connection that can support transactions initiated by either the client or server.
This is what WebSockets provide!


## How WebSockets Work


