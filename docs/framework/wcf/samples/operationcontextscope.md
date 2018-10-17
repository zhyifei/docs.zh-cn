---
title: OperationContextScope
ms.date: 03/30/2017
ms.assetid: 11c11108-8eb4-4d49-95a0-83285a812262
ms.openlocfilehash: 499d3e9824ede493043b996d581b079ec23938f8
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2018
ms.locfileid: "49371982"
---
# <a name="operationcontextscope"></a><span data-ttu-id="91549-102">OperationContextScope</span><span class="sxs-lookup"><span data-stu-id="91549-102">OperationContextScope</span></span>
<span data-ttu-id="91549-103">OperationContextScope 示例演示如何发送 Windows Communication Foundation (WCF) 调用使用标头上的额外信息。</span><span class="sxs-lookup"><span data-stu-id="91549-103">The OperationContextScope sample demonstrates how to send extra information on a Windows Communication Foundation (WCF) call using headers.</span></span> <span data-ttu-id="91549-104">在此示例中，服务器和客户端都是控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="91549-104">In this sample, both the server and client are console applications.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="91549-105">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="91549-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="91549-106">此示例演示客户端如何使用 <xref:System.ServiceModel.Channels.MessageHeader> 以 <xref:System.ServiceModel.OperationContextScope> 的方式发送额外的信息。</span><span class="sxs-lookup"><span data-stu-id="91549-106">The sample demonstrates how a client can send additional information as a <xref:System.ServiceModel.Channels.MessageHeader> using <xref:System.ServiceModel.OperationContextScope>.</span></span> <span data-ttu-id="91549-107"><xref:System.ServiceModel.OperationContextScope> 对象是通过将其范围设置为通道来创建的。</span><span class="sxs-lookup"><span data-stu-id="91549-107">An <xref:System.ServiceModel.OperationContextScope> object is created by scoping it to a channel.</span></span> <span data-ttu-id="91549-108">必须转换为远程服务的头可以添加到 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> 集合中。</span><span class="sxs-lookup"><span data-stu-id="91549-108">Headers that must be translated to the remote service can be added to the <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="91549-109">可以通过访问 <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> 在服务上检索添加到此集合中的头。</span><span class="sxs-lookup"><span data-stu-id="91549-109">Headers added to this collection can be retrieved on the service by accessing <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A>.</span></span> <span data-ttu-id="91549-110">它的调用是在多个通道进行的，添加到客户端的头然后将只应用于用来创建 <xref:System.ServiceModel.OperationContextScope> 的通道。</span><span class="sxs-lookup"><span data-stu-id="91549-110">Its calls are made on multiple channels and then the headers added to the client only apply to the channel that was used to create the <xref:System.ServiceModel.OperationContextScope>.</span></span>  
  
## <a name="messageheaderreader"></a><span data-ttu-id="91549-111">MessageHeaderReader</span><span class="sxs-lookup"><span data-stu-id="91549-111">MessageHeaderReader</span></span>  
 <span data-ttu-id="91549-112">这是从客户端接收消息，并尝试在 <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> 集合中查找头的示例服务。</span><span class="sxs-lookup"><span data-stu-id="91549-112">This is the sample service that receives a message from the client and tries to look up the header in the <xref:System.ServiceModel.OperationContext.IncomingMessageHeaders%2A> collection.</span></span> <span data-ttu-id="91549-113">客户端传递在头中发送的 GUID，服务则检索自定义头，如果存在自定义头，则将其与客户端作为自变量传递的 GUID 进行比较。</span><span class="sxs-lookup"><span data-stu-id="91549-113">The client passes the GUID that it sent in the header and the service retrieves the custom header and, if present, compares it with the GUID passed as the argument by the client.</span></span>  
  
```csharp
public bool RetrieveHeader(string guid)  
{  
     MessageHeaders messageHeaderCollection =   
             OperationContext.Current.IncomingMessageHeaders;  
     String guidHeader = null;  
  
     Console.WriteLine("Trying to check if IncomingMessageHeader " +  
               " collection contains header with value {0}", guid);  
     if (messageHeaderCollection.FindHeader(  
                       CustomHeader.HeaderName,   
                       CustomHeader.HeaderNamespace) != -1)  
     {  
          guidHeader = messageHeaderCollection.GetHeader<String>(  
           CustomHeader.HeaderName, CustomHeader.HeaderNamespace);  
     }  
     else  
     {  
          Console.WriteLine("No header was found");  
     }  
     if (guidHeader != null)  
     {  
          Console.WriteLine("Found header with value {0}. "+   
         "Does it match with GUID sent as parameter: {1}",   
          guidHeader, guidHeader.Equals(guid));  
      }  
  
      Console.WriteLine();  
      //Return true if header is present and equals the guid sent by  
      // client as argument  
      return (guidHeader != null && guidHeader.Equals(guid));  
}  
```  
  
## <a name="messageheaderclient"></a><span data-ttu-id="91549-114">MessageHeaderClient</span><span class="sxs-lookup"><span data-stu-id="91549-114">MessageHeaderClient</span></span>  
 <span data-ttu-id="91549-115">这是使用由生成的代理的客户端实现[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)与远程服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="91549-115">This is the client implementation that uses the proxy generated by [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to communicate with the remote service.</span></span> <span data-ttu-id="91549-116">它首先创建 `MessageHeaderReaderClient` 的两个代理对象。</span><span class="sxs-lookup"><span data-stu-id="91549-116">It first creates two proxy objects of `MessageHeaderReaderClient`.</span></span>  
  
```csharp
//Create two clients to the remote service.  
MessageHeaderReaderClient client1 = new MessageHeaderReaderClient();  
MessageHeaderReaderClient client2 = new MessageHeaderReaderClient();  
```  
  
 <span data-ttu-id="91549-117">客户端然后创建 OperationContextScope 并将其范围设置为 `client1`。</span><span class="sxs-lookup"><span data-stu-id="91549-117">Client then creates an OperationContextScope and scopes it to `client1`.</span></span> <span data-ttu-id="91549-118">它将 <xref:System.ServiceModel.Channels.MessageHeader> 添加到 <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> 中，并在两个客户端上都进行一次调用。</span><span class="sxs-lookup"><span data-stu-id="91549-118">It adds a <xref:System.ServiceModel.Channels.MessageHeader> to <xref:System.ServiceModel.OperationContext.OutgoingMessageHeaders%2A> and invokes one call on both clients.</span></span> <span data-ttu-id="91549-119">它可确保仅在发送时的标头`client1`而不是在`client2`通过检查的返回值`RetrieveHeader`调用。</span><span class="sxs-lookup"><span data-stu-id="91549-119">It ensures that the header is sent only on `client1` and not on `client2` by checking the return value from the `RetrieveHeader` call.</span></span>  
  
```csharp
using (new OperationContextScope(client1.InnerChannel))  
{  
    //Create a new GUID that is sent as the header.  
    String guid = Guid.NewGuid().ToString();  
  
    //Create a MessageHeader for the GUID we just created.  
    MessageHeader customHeader = MessageHeader.CreateHeader(CustomHeader.HeaderName, CustomHeader.HeaderNamespace, guid);  
  
    //Add the header to the OutgoingMessageHeader collection.  
    OperationContext.Current.OutgoingMessageHeaders.Add(customHeader);  
  
    //Now call RetreieveHeader on both the proxies. Since the OperationContextScope is tied to   
    //client1's InnerChannel, the header should only be added to calls made on that client.  
    //Calls made on client2 should not be sending the header across even though the call  
    //is made in the same OperationContextScope.  
    Console.WriteLine("Using client1 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: True", client1.RetrieveHeader(guid));  
  
    Console.WriteLine();  
    Console.WriteLine("Using client2 to send message");  
    Console.WriteLine("Did server retrieve the header? : Actual: {0}, Expected: False", client2.RetrieveHeader(guid));  
}  
```  
  
 <span data-ttu-id="91549-120">此示例是自承载的。</span><span class="sxs-lookup"><span data-stu-id="91549-120">This sample is self-hosted.</span></span> <span data-ttu-id="91549-121">下面提供了运行示例的示例输出：</span><span class="sxs-lookup"><span data-stu-id="91549-121">The following sample output from running the sample is provided:</span></span>  
  
```console  
Prompt> Service.exe  
The service is ready.  
Press <ENTER> to terminate service.  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
Found header with value 2239da67-546f-42d4-89dc-8eb3c06215d8. Does it match with GUID sent as parameter: True  
  
Trying to check if IncomingMessageHeader collection contains header with value 2239da67-546f-42d4-89dc-8eb3c06215d8  
No header was found  
  
Prompt>Client.exe  
Using client1 to send message  
Did server retrieve the header? : Actual: True, Expected: True  
  
Using client2 to send message  
Did server retrieve the header? : Actual: False, Expected: False  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="91549-122">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="91549-122">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="91549-123">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="91549-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="91549-124">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="91549-124">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="91549-125">若要在单或跨计算机配置中运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="91549-125">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="91549-126">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="91549-126">The samples may already be installed on your machine.</span></span> <span data-ttu-id="91549-127">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="91549-127">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="91549-128">如果此目录不存在，请转到[Windows Communication Foundation (WCF) 和.NET Framework 4 的 Windows Workflow Foundation (WF) 示例](https://go.microsoft.com/fwlink/?LinkId=150780)若要下载所有 Windows Communication Foundation (WCF) 和[!INCLUDE[wf1](../../../../includes/wf1-md.md)]示例。</span><span class="sxs-lookup"><span data-stu-id="91549-128">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="91549-129">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="91549-129">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\OperationContextScope`  
  
## <a name="see-also"></a><span data-ttu-id="91549-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="91549-130">See Also</span></span>
