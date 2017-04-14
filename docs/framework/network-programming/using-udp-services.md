---
title: "使用 UDP 服务 | Microsoft Docs"
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
  - "协议，UDP"
  - "网络资源，UDP"
  - "从 Internet 请求数据，UDP"
  - "UDP"
  - "接收数据，UDP"
  - "Internet，UDP"
  - "将消息广播到多个地址"
  - "数据请求，UDP"
  - "UdpClient 类，关于 UdpClient 类"
  - "发送数据，UDP"
  - "应用程序协议，UDP"
ms.assetid: d5c3477a-e798-454c-a890-738ba14c5707
caps.latest.revision: 15
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 13
---
# 使用 UDP 服务
使用UDP， <xref:System.Net.Sockets.UdpClient> 选件类与web服务通信。  使用UDP， <xref:System.Net.Sockets.UdpClient> 的属性和方法类将创建请求和接收的数据 <xref:System.Net.Sockets.Socket> 详细信息。  
  
 用户数据协议\(UDP\)是使一种最佳工作提供数据对远程主机的简单协议。  但是，在中，因为UDP协议\(ftp\)是未连接的协议， UDP数据进行发送给远程终结点不能保证到达，也不是它们确保达到其发送的同一序列。  使用UDP应用程序必须准备处理缺失，副本并不按顺序运行数据。  
  
 使用UDP，若要将数据发送运行，必须知道网络设备的网络地址承载需要和UDP端口号服务使用通信的服务。  internet指定号码适当\(Iana\)定义常用的服务的端口号\(请参见www.iana.org\/assignments\/port\-numbers\)。  services未在Iana列表可以具有在1,024到65,535范围内的端口号。  
  
 特定网络地址用于支持UDP在基于IP的网络的广播的消息。  下面的讨论使用在Internet例如使用的IP 4版地址族。  
  
 IP地址版本4使用32位指定网络地址。  对于使用255.255.255.0 netmask的选件类C地址，这些位分为四个八位字节。  在小数点表示，四个八位字节构成熟悉虚线四核表示形式，例如192.168.100.2。  前两个八位字节\(192.168在此示例中\)以形成网络号码，第三个八位字节\(100\)定义子网和\(2\)是宿主标识符的最终八位字节。  
  
 设置IP地址的所有位到一个或255.255.255.255，窗体有限广播地址。  发送UDP数据进行到此地址消息到本地网络段的所有虚拟机。  由于路由器从未转发" help " \(发送到该地址，在网络段的仅宿主接收广播的消息。  
  
 broadcasts可以处理到网络的特定部分通过将宿主标识符的所有位。  例如，发送的广播到IP地址确定的网络上的任何宿主从开始192.168.1，请使用该地址192.168.1.255。  
  
 下面的代码示例使用 <xref:System.Net.Sockets.UdpClient> 侦听UDP数据进行发送到在端口11,000上处理的广播地址192.168.1.255。  客户端收到消息字符串和消息写入到控制台。  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class UDPListener  
   Private Const listenPort As Integer = 11000  
  
   Private Shared Sub StartListener()  
      Dim done As Boolean = False  
      Dim listener As New UdpClient(listenPort)  
      Dim groupEP As New IPEndPoint(IPAddress.Any, listenPort)  
      Try  
         While Not done  
            Console.WriteLine("Waiting for broadcast")  
            Dim bytes As Byte() = listener.Receive(groupEP)  
            Console.WriteLine("Received broadcast from {0} :", _  
                groupEP.ToString())   
            Console.WriteLine( _  
                Encoding.ASCII.GetString(bytes, 0, bytes.Length))  
            Console.WriteLine()  
         End While  
      Catch e As Exception  
         Console.WriteLine(e.ToString())  
      Finally  
         listener.Close()  
      End Try  
   End Sub 'StartListener  
  
   Public Shared Function Main() As Integer  
      StartListener()  
      Return 0  
   End Function 'Main  
End Class 'UDPListener  
```  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Sockets;  
using System.Text;  
  
public class UDPListener   
{  
    private const int listenPort = 11000;  
  
    private static void StartListener()   
    {  
        bool done = false;  
  
        UdpClient listener = new UdpClient(listenPort);  
        IPEndPoint groupEP = new IPEndPoint(IPAddress.Any,listenPort);  
  
        try   
        {  
            while (!done)   
            {  
                Console.WriteLine("Waiting for broadcast");  
                byte[] bytes = listener.Receive( ref groupEP);  
  
                Console.WriteLine("Received broadcast from {0} :\n {1}\n",  
                    groupEP.ToString(),  
                    Encoding.ASCII.GetString(bytes,0,bytes.Length));  
            }  
  
        }   
        catch (Exception e)   
        {  
            Console.WriteLine(e.ToString());  
        }  
        finally  
        {  
            listener.Close();  
        }  
    }  
  
    public static int Main()   
    {  
        StartListener();  
  
        return 0;  
    }  
}  
```  
  
 使用端口11,000，下面的代码示例使用 <xref:System.Net.Sockets.UdpClient> 发送UDP数据进行到进程中的广播地址， 192.168.1.255。  客户端发送在命令行上指定的消息字符串。  
  
```vb  
Imports System  
Imports System.Net  
Imports System.Net.Sockets  
Imports System.Text  
  
Public Class Program  
  
    Overloads Public Shared Function Main(args() As [String]) As Integer  
      Dim s As New Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
          ProtocolType.Udp)  
      Dim broadcast As IPAddress = IPAddress.Parse("192.168.1.255")  
      Dim sendbuf As Byte() = Encoding.ASCII.GetBytes(args(0))  
      Dim ep As New IPEndPoint(broadcast, 11000)  
      s.SendTo(sendbuf, ep)  
      Console.WriteLine("Message sent to the broadcast address")  
   End Function 'Main  
End Class   
```  
  
```csharp  
using System;  
using System.Net;  
using System.Net.Sockets;  
using System.Text;  
  
class Program   
{  
    static void Main(string[] args)   
    {  
        Socket s = new Socket(AddressFamily.InterNetwork, SocketType.Dgram,  
            ProtocolType.Udp);  
  
        IPAddress broadcast = IPAddress.Parse("192.168.1.255");  
  
        byte[] sendbuf = Encoding.ASCII.GetBytes(args[0]);  
        IPEndPoint ep = new IPEndPoint(broadcast, 11000);  
  
        s.SendTo(sendbuf, ep);  
  
        Console.WriteLine("Message sent to the broadcast address");  
    }  
}  
```  
  
## 请参阅  
 <xref:System.Net.Sockets.UdpClient>   
 <xref:System.Net.IPAddress>   
 [TCP\/UDP](../../../docs/framework/network-programming/tcp-udp.md)