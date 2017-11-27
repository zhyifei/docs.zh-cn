---
title: "使用 TCP 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- requesting data from Internet, TCP
- receiving data, TCP
- TcpClient class, about TcpClient class
- data requests, TCP
- application protocols, TCP
- network resources, TCP
- sending data, TCP
- TCP
- protocols, TCP
- Internet, TCP
ms.assetid: d2811830-3bcb-495c-b82d-cda9cf919aad
caps.latest.revision: "11"
author: mcleblanc
ms.author: markl
manager: markl
ms.openlocfilehash: f560ae08c928e9f21def9f69950efbd72ccb6b88
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="using-tcp-services"></a><span data-ttu-id="b642a-102">使用 TCP 服务</span><span class="sxs-lookup"><span data-stu-id="b642a-102">Using TCP Services</span></span>
<span data-ttu-id="b642a-103"><xref:System.Net.Sockets.TcpClient> 类使用 TCP 从 Internet 资源请求数据。</span><span class="sxs-lookup"><span data-stu-id="b642a-103">The <xref:System.Net.Sockets.TcpClient> class requests data from an Internet resource using TCP.</span></span> <span data-ttu-id="b642a-104">TcpClient 的方法和属性会摘录为了通过 TCP 请求和接收数据而创建的 <xref:System.Net.Sockets.Socket> 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b642a-104">The methods and properties of **TcpClient** abstract the details for creating a <xref:System.Net.Sockets.Socket> for requesting and receiving data using TCP.</span></span> <span data-ttu-id="b642a-105">与远程设备的连接表示为流，因此可以使用 .NET Framework 流处理技术读取和写入数据。</span><span class="sxs-lookup"><span data-stu-id="b642a-105">Because the connection to the remote device is represented as a stream, data can be read and written with .NET Framework stream-handling techniques.</span></span>  
  
 <span data-ttu-id="b642a-106">TCP 协议与远程终结点建立连接，然后使用此连接发送和接收数据包。</span><span class="sxs-lookup"><span data-stu-id="b642a-106">The TCP protocol establishes a connection with a remote endpoint and then uses that connection to send and receive data packets.</span></span> <span data-ttu-id="b642a-107">TCP 负责确保将数据包发送到终结点，并在数据包到达时以正确的顺序对其进行汇编。</span><span class="sxs-lookup"><span data-stu-id="b642a-107">TCP is responsible for ensuring that data packets are sent to the endpoint and assembled in the correct order when they arrive.</span></span>  
  
 <span data-ttu-id="b642a-108">若要建立 TCP 连接，必须知道承载所需服务的网络设备地址以及该服务用于通信的 TCP 端口。</span><span class="sxs-lookup"><span data-stu-id="b642a-108">To establish a TCP connection, you must know the address of the network device hosting the service you need and you must know the TCP port that the service uses to communicate.</span></span> <span data-ttu-id="b642a-109">Internet 编号分配机构 (IANA) 定义公共服务的端口号（请参阅 www.iana.org/assignments/port-numbers）。</span><span class="sxs-lookup"><span data-stu-id="b642a-109">The Internet Assigned Numbers Authority (Iana) defines port numbers for common services (see www.iana.org/assignments/port-numbers).</span></span> <span data-ttu-id="b642a-110">不在 IANA 列表上的服务可使用 1,024 到 65,535 范围内的端口号。</span><span class="sxs-lookup"><span data-stu-id="b642a-110">Services not on the Iana list can have port numbers in the range 1,024 to 65,535.</span></span>  
  
 <span data-ttu-id="b642a-111">以下示例演示如何设置 TcpClient 以连接到 TCP 端口 13 上的时间服务器。</span><span class="sxs-lookup"><span data-stu-id="b642a-111">The following example demonstrates setting up a **TcpClient** to connect to a time server on TCP port 13.</span></span>  
  
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
  
 <span data-ttu-id="b642a-112"><xref:System.Net.Sockets.TcpListener> 用于监视 TCP 端口上的传入请求，然后创建一个 Socket 或 TcpClient 来管理与客户端的连接。</span><span class="sxs-lookup"><span data-stu-id="b642a-112"><xref:System.Net.Sockets.TcpListener> is used to monitor a TCP port for incoming requests and then create either a **Socket** or a **TcpClient** that manages the connection to the client.</span></span> <span data-ttu-id="b642a-113"><xref:System.Net.Sockets.TcpListener.Start%2A> 方法可使用侦听，而 <xref:System.Net.Sockets.TcpListener.Stop%2A> 方法禁用端口上的侦听。</span><span class="sxs-lookup"><span data-stu-id="b642a-113">The <xref:System.Net.Sockets.TcpListener.Start%2A> method enables listening, and the <xref:System.Net.Sockets.TcpListener.Stop%2A> method disables listening on the port.</span></span> <span data-ttu-id="b642a-114"><xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> 方法接受传入的连接请求并创建 TcpClient 处理请求，<xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> 方法接受传入的连接请求并创建 Socket 处理请求。</span><span class="sxs-lookup"><span data-stu-id="b642a-114">The <xref:System.Net.Sockets.TcpListener.AcceptTcpClient%2A> method accepts incoming connection requests and creates a **TcpClient** to handle the request, and the <xref:System.Net.Sockets.TcpListener.AcceptSocket%2A> method accepts incoming connection requests and creates a **Socket** to handle the request.</span></span>  
  
 <span data-ttu-id="b642a-115">以下示例演示如何使用 TcpListener 创建网络时间服务器以监视 TCP 端口 13。</span><span class="sxs-lookup"><span data-stu-id="b642a-115">The following example demonstrates creating a network time server using a **TcpListener** to monitor TCP port 13.</span></span> <span data-ttu-id="b642a-116">接受传入的连接请求时，时间服务器会使用主机服务器的当前日期和时间进行响应。</span><span class="sxs-lookup"><span data-stu-id="b642a-116">When an incoming connection request is accepted, the time server responds with the current date and time from the host server.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b642a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b642a-117">See Also</span></span>  
 
