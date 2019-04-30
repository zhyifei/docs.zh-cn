---
title: 自定义绑定传输和编码
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: d293ccb45a3af85ca5ca23fec9e3c01a55564581
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62003348"
---
# <a name="custom-binding-transport-and-encoding"></a><span data-ttu-id="137ff-102">自定义绑定传输和编码</span><span class="sxs-lookup"><span data-stu-id="137ff-102">Custom Binding Transport and Encoding</span></span>
<span data-ttu-id="137ff-103">自定义绑定由离散绑定元素的有序列表定义。</span><span class="sxs-lookup"><span data-stu-id="137ff-103">A custom binding is defined by an ordered list of discrete binding elements.</span></span> <span data-ttu-id="137ff-104">本示例演示如何使用各种传输和消息编码元素配置自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="137ff-104">This sample demonstrates how to configure a custom binding with various transport and message encoding elements.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="137ff-105">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="137ff-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="137ff-106">此示例基于[自托管](../../../../docs/framework/wcf/samples/self-host.md)，并已修改为三个终结点配置为使用自定义绑定支持 HTTP、 TCP 和 NamedPipe 传输。</span><span class="sxs-lookup"><span data-stu-id="137ff-106">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md), and has been modified to configure three endpoints to support HTTP, TCP, and NamedPipe transports with custom bindings.</span></span> <span data-ttu-id="137ff-107">并对客户端配置进行了类似修改，将客户端代码更改为能与这三个终结点中的每一个进行通信。</span><span class="sxs-lookup"><span data-stu-id="137ff-107">The client configuration was similarly modified, and the client code changed to communicate with each of the three endpoints.</span></span>  
  
 <span data-ttu-id="137ff-108">本示例演示如何配置支持特定传输和消息编码的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="137ff-108">The sample demonstrates a how to configure a custom binding that supports a particular transport and message encoding.</span></span> <span data-ttu-id="137ff-109">这是通过为 `binding` 元素配置传输和消息编码而实现的。</span><span class="sxs-lookup"><span data-stu-id="137ff-109">This is accomplished by configuring a transport and a message encoding for the `binding` element.</span></span> <span data-ttu-id="137ff-110">绑定元素的顺序十分重要中定义自定义绑定，因为每个表示通道堆栈中的层 (请参阅[自定义绑定](../../../../docs/framework/wcf/extending/custom-bindings.md))。</span><span class="sxs-lookup"><span data-stu-id="137ff-110">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="137ff-111">本示例配置三个自定义绑定：使用文本编码的 HTTP 传输、使用文本编码的 TCP 传输和使用二进制编码的 NamedPipe 传输。</span><span class="sxs-lookup"><span data-stu-id="137ff-111">This sample configures three custom bindings: an HTTP transport with text encoding, a TCP transport with text encoding, and a NamedPipe transport with a binary encoding.</span></span>  
  
 <span data-ttu-id="137ff-112">服务配置按如下所示定义自定义绑定：</span><span class="sxs-lookup"><span data-stu-id="137ff-112">The service configuration defines the custom bindings as follows:</span></span>  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding   
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="137ff-113">运行示例时，操作请求和响应将显示在服务和客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="137ff-113">When you run the sample, the operation requests and responses are displayed in both the service and client console window.</span></span> <span data-ttu-id="137ff-114">客户端将逐一与三个终结点进行通信，首先访问 HTTP，接着是 TCP，最后为 NamedPipe。</span><span class="sxs-lookup"><span data-stu-id="137ff-114">The client communicates with each of the three endpoints, accessing first HTTP, then TCP, and finally NamedPipe.</span></span> <span data-ttu-id="137ff-115">在每个控制台窗口中按 Enter 可以关闭服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="137ff-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="137ff-116">`namedPipeTransport` 绑定不支持计算机到计算机的操作。</span><span class="sxs-lookup"><span data-stu-id="137ff-116">The `namedPipeTransport` binding does not support machine-to-machine operations.</span></span> <span data-ttu-id="137ff-117">它仅用于同一计算机上的通信。</span><span class="sxs-lookup"><span data-stu-id="137ff-117">It is used only for communication on the same machine.</span></span> <span data-ttu-id="137ff-118">因此，当在跨计算机的方案中运行示例时，应注释掉客户端代码文件中的以下行：</span><span class="sxs-lookup"><span data-stu-id="137ff-118">Therefore, when running the sample in a cross-machine scenario, comment out the following lines in the client code file:</span></span>  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
>  <span data-ttu-id="137ff-119">如果使用 Svcutil.exe 为此示例重新生成配置，请确保在客户端配置中修改终结点名称以与客户端代码匹配。</span><span class="sxs-lookup"><span data-stu-id="137ff-119">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="137ff-120">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="137ff-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="137ff-121">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="137ff-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="137ff-122">若要生成C#， C++，或 Visual Basic.NET 版本的解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="137ff-122">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="137ff-123">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="137ff-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="137ff-124">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="137ff-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="137ff-125">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="137ff-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="137ff-126">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="137ff-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="137ff-127">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="137ff-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
