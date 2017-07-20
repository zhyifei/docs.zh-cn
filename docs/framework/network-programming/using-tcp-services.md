---
title: "使用 TCP 服务 | Microsoft Docs"
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
  - "从 Internet 请求数据，TCP"
  - "接收数据，TCP"
  - "TcpClient 类，关于 TcpClient 类"
  - "数据请求，TCP"
  - "应用程序协议，TCP"
  - "网络资源，TCP"
  - "发送数据，TCP"
  - "TCP"
  - "协议，TCP"
  - "Internet，TCP"
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: 11
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# 使用 TCP 服务
使用TCP， <xref:System.Net.Sockets.TcpClient> 选件类请求Internet资源的数据。  使用TCP， **TcpClient** 方法和属性中提取创建的 <xref:System.Net.Sockets.Socket> 详细信息请求和收到的数据。  由于与远程计算机的连接表示为流，数据可以读取和写入的流处理技术的.NET Framework。  
  
 TCP协议建立与远程发送和接收数据包的连接的终结点然后使用的连接。  TCP负责确保数据包发送给终结点并按正确的顺序组合而成，当到达时。  
  
 若要生成TCP连接，必须知道网络设备的地址承载所需的服务时，且必须知道服务使用传达的TCP端口。  internet指定号码适当\(Iana\)定义常用的服务的端口号\(请参见www.iana.org\/assignments\/port\-numbers\)。  services未在Iana列表可以具有在1,024到65,535范围内的端口号。  
  
 下面的示例演示如何设置 **TcpClient** 连接位于TCP端口13的一个时间服务器。  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeClient  
    Private const portNum As Integer = 13  
    Private const hostName As String = "host.contoso.com"  
  
    ' Entry point  that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Try  
            Dim client As New TcpClient(hostName, portNum)  
  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim bytes(1024) As Byte  
            Dim bytesRead As Integer = ns.Read(bytes, 0, bytes.Length)  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes, 0, bytesRead))  
  
        Catch e As Exception  
            Console.WriteLine(e.ToString())  
        End Try  
  
        client.Close()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeClient  
  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeClient {  
    private const int portNum = 13;  
    private const string hostName = "host.contoso.com";  
  
    public static int Main(String[] args) {  
        try {  
            TcpClient client = new TcpClient(hostName, portNum);  
  
            NetworkStream ns = client.GetStream();  
  
            byte[] bytes = new byte[1024];  
            int bytesRead = ns.Read(bytes, 0, bytes.Length);  
  
            Console.WriteLine(Encoding.ASCII.GetString(bytes,0,bytesRead));  
  
            client.Close();  
  
        } catch (Exception e) {  
            Console.WriteLine(e.ToString());  
        }  
  
        return 0;  
    }  
}  
```  
  
 <xref:System.Net.Sockets.TcpListener> 监视管理与客户端的连接传入请求的TCP端口然后创建 **套接字** 或 **TcpClient** 。  <xref:System.Net.Sockets.TcpListener.Start%2A> 方法允许侦听，并且， <xref:System.Net.Sockets.TcpListener.Stop%2A> 方法禁用听完端口。  <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> 方法接受传入连接请求并创建 **TcpClient** 处理请求，并且， <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> 方法接受传入连接请求并创建 **套接字** 处理请求。  
  
 下面的示例演示创建网络时服务器使用 **TcpListener** 监视TCP端口13。  当一个传入连接请求接受后，时间服务器响应与当前日期和时间从主机服务器。  
  
```vb  
Imports System  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class TcpTimeServer  
  
    Private const portNum As Integer = 13  
  
    ' Entry point that delegates to C-style main Private Function.  
    Public Overloads Shared Sub Main()  
        System.Environment.ExitCode = _  
            Main(System.Environment.GetCommandLineArgs())  
    End Sub  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
        Dim done As Boolean = False  
  
        Dim listener As New TcpListener(portNum)  
  
        listener.Start()  
  
        While Not done  
            Console.Write("Waiting for connection...")  
            Dim client As TcpClient = listener.AcceptTcpClient()  
  
            Console.WriteLine("Connection accepted.")  
            Dim ns As NetworkStream = client.GetStream()  
  
            Dim byteTime As Byte() = _  
                Encoding.ASCII.GetBytes(DateTime.Now.ToString())  
  
            Try  
                ns.Write(byteTime, 0, byteTime.Length)  
                ns.Close()  
                client.Close()  
            Catch e As Exception  
                Console.WriteLine(e.ToString())  
            End Try  
        End While  
  
        listener.Stop()  
  
        Return 0  
    End Function 'Main  
End Class 'TcpTimeServer  
```  
  
```csharp  
using System;  
using System.Net.Sockets;  
using System.Text;  
  
public class TcpTimeServer {  
  
    private const int portNum = 13;  
  
    public static int Main(String[] args) {  
        bool done = false;  
  
        TcpListener listener = new TcpListener(portNum);  
  
        listener.Start();  
  
        while (!done) {  
            Console.Write("Waiting for connection...");  
            TcpClient client = listener.AcceptTcpClient();  
  
            Console.WriteLine("Connection accepted.");  
            NetworkStream ns = client.GetStream();  
  
            byte[] byteTime = Encoding.ASCII.GetBytes(DateTime.Now.ToString());  
  
            try {  
                ns.Write(byteTime, 0, byteTime.Length);  
                ns.Close();  
                client.Close();  
            } catch (Exception e) {  
                Console.WriteLine(e.ToString());  
            }  
        }  
  
        listener.Stop();  
  
        return 0;  
    }  
  
}  
```  
  
## 请参阅  
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)