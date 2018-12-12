# HTTP Communication Method Between Server and Client device
#### *art of Web service*

- Polling
- Comet (Streaming)
- Long-Polling
- SSE (Server-Send Event)
- WebSocket

---

## Polling
Send request from client-side every time slice.
Polling cause too many requests and resourse using after request get in server.

---

## Comet
Server always keep request connection by Keep-Alive when client open request, then server could keep push data to client.  
Methods:
- Client keep updating data by checking **readyState === '3'** when **onreadystatechange**.
- Or use tricky iframe method
>- Comet may cause too many IO in the same time, so need Non-blocking IO Server.
>- Some info of Disconnect problem in proxy is searched from internet.  

---

## Long-Polling
Client set timeout parameter of Keeo-Alive in header. 
If request timeout or get response is end from server, call function of sending request again.  
Server side need to set some service like timer in order to make sure response is not close and keep checking if need to end connection now.

---

## Server-Send Event
Add event listener in client, waiting for server emit.
In client side, we use EventSource API: create EventSource object with event-name, then addEventListener.  
In server, we send event by add "Content-Type:text/event-stream" to http header.  
>Browsers like IE and Edge are not support.

---

## WebSocket
A Duplicate Way. A Real Time Communication Type.  
Create Connet at first, then we can send and add event for receive message in both client and server.  
>- Browsers like down version from IE9 are not support. Even through IE11 also has some problem, for example "Security Error" which cause by using localhost or create more then 6 connections. By the way, It's not necessary to create so many connections at the same time.
>- Some info of Disconnect problem in proxy is searched from internet.  

---

ref:  
1.[Polling vs SSE vs WebSocket— How to choose the right one](https://codeburst.io/polling-vs-sse-vs-websocket-how-to-choose-the-right-one-1859e4e13bd9)  
2.[Comet (programming) Wiki](https://en.wikipedia.org/wiki/Comet_(programming))  
3.[Browser 與 Server 持續同步的作法介紹 (Polling, Comet, Long Polling, WebSocket)](http://josephj.com/entry.php?id=358)