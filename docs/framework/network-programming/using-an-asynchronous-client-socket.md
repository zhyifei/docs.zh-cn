---
title: "使用异步客户端套接字 | Microsoft Docs"
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
  - "数据请求，套接字"
  - "异步客户端套接字"
  - "Socket 类，异步客户端套接字"
  - "从 Internet 请求数据，套接字"
  - "套接字，异步客户端套接字"
  - "接收数据，套接字"
  - "协议，套接字"
  - "Internet，套接字"
  - "客户端套接字"
ms.assetid: fd85bc88-e06c-467d-a30d-9fd7cffcfca1
caps.latest.revision: 14
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 12
---
# 使用异步客户端套接字
异步客户端套接字不会应用程序，当等待网络操作完成。  相反，那么，当应用程序在原始线程时，继续运行它使用标准.NET Framework异步编程模型处理在一个线程的网络连接。  异步套接字对于大量使用网络或不能等待网络操作在继续操作之前完成的应用程序需要的。  
  
 <xref:System.Net.Sockets.Socket> 选件类采用异步方法的.NET Framework命名模式;例如，同步 <xref:System.Net.Sockets.Socket.Receive%2A> 方法对应于异步 <xref:System.Net.Sockets.Socket.BeginReceive%2A> 和 <xref:System.Net.Sockets.Socket.EndReceive%2A> 方法。  
  
 异步操作需要回调方法返回操作的结果。  如果应用程序不需要知道该结果，则不需要回调方法。  本节中的代码示例演示如何使用方法启动连接到网络设备和回调方法完成连接、方法启动发送数据和回调方法完成发送和方法添加到接收数据的开头和回调方法以接收数据的末尾。  
  
 异步回该系统套接字使用多个线程池线程处理网络连接。  一个线程以启动发送或接收负责数据;其他线程仅使用网络设备的连接并发送或接收数据。  在下面的示例中，的，它在执行时无法继续时， <xref:System.Threading.ManualResetEvent?displayProperty=fullName> 选件类的实例用于挂起主线程和信号的执行。  
  
 在下面的示例中，连接异步套接字到网络设备， `Connect`方法初始化 **套接字** 然后调用 [BeginConnect](frlrfsystemnetsocketssocketclassconnecttopic) 方法，并传递表示网络设备，连接回调方法，并且，状态对象的远程终结点\(客户端 **套接字**\)，用于将在异步之间的状态信息调用。  该示例实现 `Connect` 方法来指定的 **套接字** 到指定的终点。  假定名为 `connectDone`的全局 **ManualResetEvent** 。  
  
```vb  
Public Shared Sub Connect(remoteEP As EndPoint, client As Socket)  
    client.BeginConnect(remoteEP, _  
       AddressOf ConnectCallback, client)  
  
    connectDone.WaitOne()  
End Sub 'Connect  
```  
  
```csharp  
public static void Connect(EndPoint remoteEP, Socket client) {  
    client.BeginConnect(remoteEP,   
        new AsyncCallback(ConnectCallback), client );  
  
   connectDone.WaitOne();  
}  
```  
  
 连接回调方法 `ConnectCallback` 实现 <xref:System.AsyncCallback> 委托。  它连接到远程计算机，如果远程计算机可用然后信号应用程序线程时连接通过设置 **ManualResetEvent**`connectDone`完成。  下面的代码执行 `ConnectCallback` 方法。  
  
```vb  
Private Shared Sub ConnectCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete the connection.  
        client.EndConnect(ar)  
  
        Console.WriteLine("Socket connected to {0}", _  
            client.RemoteEndPoint.ToString())  
  
        ' Signal that the connection has been made.  
        connectDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ConnectCallback  
  
```  
  
```csharp  
private static void ConnectCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete the connection.  
        client.EndConnect(ar);  
  
        Console.WriteLine("Socket connected to {0}",  
            client.RemoteEndPoint.ToString());  
  
        // Signal that the connection has been made.  
        connectDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 示例方案 `Send` 输入指定的数据以ASCII格式并将其发送异步到指定的套接字表示的网络设备。  下面的示例执行 `Send` 方法。  
  
```vb  
Private Shared Sub Send(client As Socket, data As [String])  
    ' Convert the string data to byte data using ASCII encoding.  
    Dim byteData As Byte() = Encoding.ASCII.GetBytes(data)  
  
    ' Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None, _  
        AddressOf SendCallback, client)  
End Sub 'Send  
  
```  
  
```csharp  
private static void Send(Socket client, String data) {  
    // Convert the string data to byte data using ASCII encoding.  
    byte[] byteData = Encoding.ASCII.GetBytes(data);  
  
    // Begin sending the data to the remote device.  
    client.BeginSend(byteData, 0, byteData.Length, SocketFlags.None,  
        new AsyncCallback(SendCallback), client);  
}  
```  
  
 发送回调方法 `SendCallback` 实现 <xref:System.AsyncCallback> 委托。  ，当网络设备准备收到时，它发送数据。  下面的示例演示 `SendCallback` 方法的实现。  假定名为 `sendDone`的全局 **ManualResetEvent** 。  
  
```vb  
Private Shared Sub SendCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the socket from the state object.  
        Dim client As Socket = CType(ar.AsyncState, Socket)  
  
        ' Complete sending the data to the remote device.  
        Dim bytesSent As Integer = client.EndSend(ar)  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent)  
  
        ' Signal that all bytes have been sent.  
        sendDone.Set()  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'SendCallback  
  
```  
  
```csharp  
private static void SendCallback(IAsyncResult ar) {  
    try {  
        // Retrieve the socket from the state object.  
        Socket client = (Socket) ar.AsyncState;  
  
        // Complete sending the data to the remote device.  
        int bytesSent = client.EndSend(ar);  
        Console.WriteLine("Sent {0} bytes to server.", bytesSent);  
  
        // Signal that all bytes have been sent.  
        sendDone.Set();  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 读取客户端套接字的数据将要求值在异步调用之间的状态对象。  下面选件类是接收数据的示例状态对象从客户端套接字。  它包含客户端套接字的字段，接收数据的缓冲区和 <xref:System.Text.StringBuilder> 保存传入数据的字符串。  将这些字段在状态对象授予的值跨多个保持调用读取客户端套接字的数据。  
  
```vb  
Public Class StateObject  
    ' Client socket.  
    Public workSocket As Socket = Nothing   
    ' Size of receive buffer.  
    Public BufferSize As Integer = 256  
    ' Receive buffer.  
    Public buffer(256) As Byte   
    ' Received data string.  
    Public sb As New StringBuilder()  
End Class 'StateObject  
  
```  
  
```csharp  
public class StateObject {  
    // Client socket.  
    public Socket workSocket = null;  
    // Size of receive buffer.  
    public const int BufferSize = 256;  
    // Receive buffer.  
    public byte[] buffer = new byte[BufferSize];  
    // Received data string.  
    public StringBuilder sb = new StringBuilder();  
}  
```  
  
 示例 `Receive` 方法设置状态对象并调用 **BeginReceive** 方法读取客户端套接字的数据异步。  下面的示例执行 `Receive` 方法。  
  
```vb  
Private Shared Sub Receive(client As Socket)  
    Try  
        ' Create the state object.  
        Dim state As New StateObject()  
        state.workSocket = client  
  
        ' Begin receiving the data from the remote device.  
        client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
            AddressOf ReceiveCallback, state)  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'Receive  
  
```  
  
```csharp  
private static void Receive(Socket client) {  
    try {  
        // Create the state object.  
        StateObject state = new StateObject();  
        state.workSocket = client;  
  
        // Begin receiving the data from the remote device.  
        client.BeginReceive( state.buffer, 0, StateObject.BufferSize, 0,  
            new AsyncCallback(ReceiveCallback), state);  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
 接收回调方法 `ReceiveCallback` 实现 **AsyncCallback** 委托。  它接收来自网络设备的数据并生成消息字符串。  它读取一个或多个字节从网络的数据到数据区域然后再次调用 **BeginReceive** 方法，直到客户端发送的数据完成。  对于所有数据从客户端读取， `ReceiveCallback` 信号应用程序线程数据会通过设置 **ManualResetEvent** `sendDone`完成。  
  
 下面的代码示例执行 `ReceiveCallback`方法。  假定到名为 `receiveDone`的进行接收的字符串和全局 **ManualResetEvent** 负名为 `response` 的全局字符串。  服务器必须正常关闭客户端套接字网络关闭会话。  
  
```vb  
Private Shared Sub ReceiveCallback(ar As IAsyncResult)  
    Try  
        ' Retrieve the state object and the client socket   
        ' from the asynchronous state object.  
        Dim state As StateObject = CType(ar.AsyncState, StateObject)  
        Dim client As Socket = state.workSocket  
  
        ' Read data from the remote device.  
        Dim bytesRead As Integer = client.EndReceive(ar)  
  
        If bytesRead > 0 Then  
            ' There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer, 0, _  
                bytesRead))  
  
            '  Get the rest of the data.  
            client.BeginReceive(state.buffer, 0, state.BufferSize, 0, _  
                AddressOf ReceiveCallback, state)  
        Else  
            ' All the data has arrived; put it in response.  
            If state.sb.Length > 1 Then  
                response = state.sb.ToString()  
            End If  
            ' Signal that all bytes have been received.  
            receiveDone.Set()  
        End If  
    Catch e As Exception  
        Console.WriteLine(e.ToString())  
    End Try  
End Sub 'ReceiveCallback  
  
```  
  
```csharp  
private static void ReceiveCallback( IAsyncResult ar ) {  
    try {  
        // Retrieve the state object and the client socket   
        // from the asynchronous state object.  
        StateObject state = (StateObject) ar.AsyncState;  
        Socket client = state.workSocket;  
        // Read data from the remote device.  
        int bytesRead = client.EndReceive(ar);  
        if (bytesRead > 0) {  
            // There might be more data, so store the data received so far.  
            state.sb.Append(Encoding.ASCII.GetString(state.buffer,0,bytesRead));  
                //  Get the rest of the data.  
            client.BeginReceive(state.buffer,0,StateObject.BufferSize,0,  
                new AsyncCallback(ReceiveCallback), state);  
        } else {  
            // All the data has arrived; put it in response.  
            if (state.sb.Length > 1) {  
                response = state.sb.ToString();  
            }  
            // Signal that all bytes have been received.  
            receiveDone.Set();  
        }  
    } catch (Exception e) {  
        Console.WriteLine(e.ToString());  
    }  
}  
```  
  
## 请参阅  
 [使用同步客户端套接字](../../../docs/framework/network-programming/using-a-synchronous-client-socket.md)   
 [使用套接字侦听](../../../docs/framework/network-programming/listening-with-sockets.md)   
 [异步客户端套接字示例](../../../docs/framework/network-programming/asynchronous-client-socket-example.md)