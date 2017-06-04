---
title: "使用异步服务器套接字 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "应用程序协议，套接字"
  - "发送数据，套接字"
  - "Socket 类，异步服务器套接字"
  - "数据请求，套接字"
  - "套接字，异步服务器套接字"
  - "从 Internet 请求数据，套接字"
  - "服务器套接字"
  - "接收数据，套接字"
  - "异步服务器套接字"
  - "协议，套接字"
  - "Internet，套接字"
ms.assetid: 813489a9-3efd-41b6-a33f-371d55397676
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 11
---
# 使用异步服务器套接字
异步服务器套接字使用.NET Framework异步编程模型处理网络服务请求。  <xref:System.Net.Sockets.Socket> 选件类遵循标准.NET Framework异步模式;名称例如，同步 <xref:System.Net.Sockets.Socket.Accept%2A> 方法对应于异步 <xref:System.Net.Sockets.Socket.BeginAccept%2A> 和 <xref:System.Net.Sockets.Socket.EndAccept%2A> 方法。  
  
 异步服务器套接字需要一个方案开始接受来自网络、回调方法以处理连接请求和开始接收数据从网络和回调方法的连接请求结束接收数据。  所有这些方法都进一步本节讨论。  
  
 在下面的示例中，启动接受来自网络的连接请求，方法 `StartListening` 初始化 **套接字** 然后使用 **BeginAccept** 开始方法接受新连接。  ，在一个新的连接请求在套接字时，可以接受回调方法调用。  为获取将处理连接和传递该 **套接字** 到线程将处理请求的 **套接字** 实例负责。  接受回调方法实现 <xref:System.AsyncCallback> 委托;它返回void并采用类型 <xref:System.IAsyncResult>的单个参数。  下面的示例是接受回调方法的shell。  
  
```vb  
Sub acceptCallback(ar As IAsyncResult)  
    ' Add the callback code here.  
End Sub 'acceptCallback  
```  
  
```csharp  
void acceptCallback( IAsyncResult ar) {  
    // Add the callback code here.  
}  
```  
  
 **BeginAccept** 方法采用两个参数，指向接受回调方法和对象用于对回调方法传递状态信息的 **AsyncCallback** 委托。  在下面的示例中，收听的 **套接字** 传递给回调方法 *状态* 参数。  此示例创建一个 **AsyncCallback** 委托并启动接受来自网络的连接。  
  
```vb  
listener.BeginAccept( _  
    New AsyncCallback(SocketListener.acceptCallback),_  
    listener)  
```  
  
```csharp  
listener.BeginAccept(  
    new AsyncCallback(SocketListener.acceptCallback),   
    listener);  
```  
  
 来自系统的异步套接字使用线程池线程处理传入连接。  一个线程对接受连接负责，另一个线程用于处理每个传入连接，并且，另一个线程用于接收从连接的数据负责。  这些可以是同一线程，线程由线程池分配。  在下面的示例中，的，它在执行时无法继续时， <xref:System.Threading.ManualResetEvent?displayProperty=fullName> 选件类挂起主线程和信号的执行。  
  
 下面的示例演示在本地计算机上创建一个异步TCP\/IP套接字并启动接受连接的异步方法。  假定，有一个名为 `allDone`的全局 **ManualResetEvent** ，方法是名为 `SocketListener`的选件类的成员，并且，名为 `acceptCallback` 的回调方法中定义。  
  
```vb  
Public Sub StartListening()  
    Dim ipHostInfo As IPHostEntry = Dns.Resolve(Dns.GetHostName())  
    Dim localEP = New IPEndPoint(ipHostInfo.AddressList(0), 11000)  
  
    Console.WriteLine("Local address and port : {0}", localEP.ToString())  
  
    Dim listener As New Socket(localEP.Address.AddressFamily, _  
       SocketType.Stream, ProtocolType.Tcp)  
  
    Try  
        listener.Bind(localEP)  
        listener.Listen(10)  
  
        While True  
            allDone.Reset()  
  
            Console.WriteLine("Waiting for a connection...")  
            listener.BeginAccept(New _  
                AsyncCallback(SocketListener.acceptCallback), _  
                listener)  
  
            allDone.WaitOne()  
        End While  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
    Console.WriteLine("Closing the listener...")  
End Sub 'StartListening  
  
```  
  
```csharp  
public void StartListening() {  
    IPHostEntry ipHostInfo = Dns.Resolve(Dns.GetHostName());  
    IPEndPoint localEP = new IPEndPoint(ipHostInfo.AddressList[0],11000);  
  
    Console.WriteLine("Local address and port : {0}",localEP.ToString());  
  
    Socket listener = new Socket( localEP.Address.AddressFamily,  
        SocketType.Stream, ProtocolType.Tcp );  
  
    try {  
        listener.Bind(localEP);  
        listener.Listen(10);  
  
        while (true) {  
            allDone.Reset();  
  
            Console.WriteLine("Waiting for a connection...");  
            listener.BeginAccept(  
                new AsyncCallback(SocketListener.acceptCallback),   
                listener );  
  
            allDone.WaitOne();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
  
    Console.WriteLine( "Closing the listener...");  
}  
```  
  
 接受回调方法\(在前面的示例中的`acceptCallback` \)来终止主应用程序线程来继续处理，生成与客户端的连接并启动异步读取客户端的数据。  下面的示例是 `acceptCallback` 实现方法的第一部分。  方法信号的此部分主应用程序线程继续处理和生成与客户端的连接。  假定名为 `allDone`的全局 **ManualResetEvent** 。  
  
```vb  
Public Sub acceptCallback(ar As IAsyncResult)  
    allDone.Set()  
  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Additional code to read data goes here.  
End Sub 'acceptCallback  
```  
  
```csharp  
public void acceptCallback(IAsyncResult ar) {  
    allDone.Set();  
  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Additional code to read data goes here.    
}  
```  
  
 读取客户端套接字的数据将要求值在异步调用之间的状态对象。  下面的示例实现接收一个字符串的状态对象从该远程客户端。  它包含客户端套接字、一个数据缓冲区接收的数据和 <xref:System.Text.StringBuilder> 的字段创建的客户端发送的数据字符串。  将这些字段在状态对象授予的值跨多个保持调用读取客户端套接字的数据。  
  
```vb  
Public Class StateObject  
    Public workSocket As Socket = Nothing  
    Public BufferSize As Integer = 1024  
    Public buffer(BufferSize) As Byte  
    Public sb As New StringBuilder()  
End Class 'StateObject  
```  
  
```csharp  
public class StateObject {  
    public Socket workSocket = null;  
    public const int BufferSize = 1024;  
    public byte[] buffer = new byte[BufferSize];  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 启动首先接收数据从客户端套接字 `acceptCallback` 方案的一部分初始化 `StateObject` 选件类的实例并调用 <xref:System.Net.Sockets.Socket.BeginReceive%2A> 方法开始读取客户端套接字的数据异步。  
  
 下面的示例演示完整 `acceptCallback` 方法。  假定，有一个名为 `allDone,` 的全局 **ManualResetEvent**`StateObject` 选件类中定义，并且， `readCallback` 方法在选件类中定义名为 `SocketListener`。  
  
```vb  
Public Shared Sub acceptCallback(ar As IAsyncResult)  
    ' Get the socket that handles the client request.  
    Dim listener As Socket = CType(ar.AsyncState, Socket)  
    Dim handler As Socket = listener.EndAccept(ar)  
  
    ' Signal the main thread to continue.  
    allDone.Set()  
  
    ' Create the state object.  
    Dim state As New StateObject()  
    state.workSocket = handler  
    handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
        AddressOf AsynchronousSocketListener.readCallback, state)  
End Sub 'acceptCallback  
  
```  
  
```csharp  
public static void acceptCallback(IAsyncResult ar) {  
    // Get the socket that handles the client request.  
    Socket listener = (Socket) ar.AsyncState;  
    Socket handler = listener.EndAccept(ar);  
  
    // Signal the main thread to continue.  
    allDone.Set();  
  
    // Create the state object.  
    StateObject state = new StateObject();  
    state.workSocket = handler;  
    handler.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
        new AsyncCallback(AsynchronousSocketListener.readCallback), state);  
}  
```  
  
 需要为异步套接字服务器执行最终的方法是返回客户端发送的数据的读取的回调方法。  与接受回调方法，该方法读取的回调方法是 **AsyncCallback** 委托。  此方法读取客户端套接字的一个或多个字节到数据区域然后再次调用 **BeginReceive** 方法，直到客户端发送的数据完成。  对于所有消息从客户端读取，该字符串在控制台中显示，并处理与客户端的服务器套接字连接已关闭。  
  
 下面的示例执行 `readCallback` 方法。  假定， `StateObject` 选件类中定义的。  
  
```vb  
Public Shared Sub readCallback(ar As IAsyncResult)  
    Dim state As StateObject = CType(ar.AsyncState, StateObject)  
    Dim handler As Socket = state.workSocket  
  
    ' Read data from the client socket.   
    Dim read As Integer = handler.EndReceive(ar)  
  
    ' Data was read from the client socket.  
    If read > 0 Then  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, read))  
        handler.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf readCallback, state)  
    Else  
        If state.sb.Length > 1 Then  
            ' All the data has been read from the client;  
            ' display it on the console.  
            Dim content As String = state.sb.ToString()  
            Console.WriteLine("Read {0} bytes from socket." + _  
                ControlChars.Cr + " Data : {1}", content.Length, content)  
        End If  
    End If  
End Sub 'readCallback  
  
```  
  
```csharp  
public static void readCallback(IAsyncResult ar) {  
    StateObject state = (StateObject) ar.AsyncState;  
    Socket handler = state.WorkSocket;  
  
    // Read data from the client socket.  
    int read = handler.EndReceive(ar);  
  
    // Data was read from the client socket.  
    if (read > 0) {  
        state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,read));  
        handler.BeginReceive(state.buffer,0,StateObject.BufferSize, 0,  
            new AsyncCallback(readCallback), state);  
    } else {  
        if (state.sb.Length > 1) {  
            // All the data has been read from the client;  
            // display it on the console.  
            string content = state.sb.ToString();  
            Console.WriteLine("Read {0} bytes from socket.\n Data : {1}",  
               content.Length, content);  
        }  
        handler.Close();  
    }  
}  
```  
  
## 请参阅  
 [使用同步服务器套接字](../../../docs/framework/network-programming/using-a-synchronous-server-socket.md)   
 [异步服务器套接字示例](../../../docs/framework/network-programming/asynchronous-server-socket-example.md)   
 [Threading](../../../docs/standard/threading/index.md)   
 [使用套接字侦听](../../../docs/framework/network-programming/listening-with-sockets.md)