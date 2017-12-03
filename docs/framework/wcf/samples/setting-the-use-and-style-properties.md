---
title: "设置 Use 和 Style 属性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c09a0600-116f-41cf-900a-1b7e4ea4e300
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f6a8e4b990c7ae9815c8792c0be456463b10660b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="setting-the-use-and-style-properties"></a><span data-ttu-id="b26ab-102">设置 Use 和 Style 属性</span><span class="sxs-lookup"><span data-stu-id="b26ab-102">Setting the Use and Style Properties</span></span>
<span data-ttu-id="b26ab-103">本示例演示如何使用 <xref:System.ServiceModel.XmlSerializerFormatAttribute> 和 <xref:System.ServiceModel.DataContractFormatAttribute> 的 Use 和 Style 属性。</span><span class="sxs-lookup"><span data-stu-id="b26ab-103">This sample demonstrates how to use the Use and Style properties on the <xref:System.ServiceModel.XmlSerializerFormatAttribute> and the <xref:System.ServiceModel.DataContractFormatAttribute>.</span></span> <span data-ttu-id="b26ab-104">这些属性影响如何格式化消息。</span><span class="sxs-lookup"><span data-stu-id="b26ab-104">These properties affect how messages are formatted.</span></span> <span data-ttu-id="b26ab-105">默认情况下，使用设置为 <xref:System.ServiceModel.OperationFormatStyle.Document> 的样式格式化消息正文。</span><span class="sxs-lookup"><span data-stu-id="b26ab-105">By default, the message body is formatted with the style set to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span> <span data-ttu-id="b26ab-106">可以在服务协定级别或在操作协定级别指定这些设置。</span><span class="sxs-lookup"><span data-stu-id="b26ab-106">These settings can be specified at either the service contract level or the operation contract level.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b26ab-107">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="b26ab-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b26ab-108"><xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> 样式属性确定如何设置服务的 WSDL 元数据格式。</span><span class="sxs-lookup"><span data-stu-id="b26ab-108">The <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> style property determines how the WSDL metadata for the service is formatted.</span></span> <span data-ttu-id="b26ab-109">可能的值为 <xref:System.ServiceModel.OperationFormatStyle.Document> 和 <xref:System.ServiceModel.OperationFormatStyle.Rpc>。</span><span class="sxs-lookup"><span data-stu-id="b26ab-109">Possible values are <xref:System.ServiceModel.OperationFormatStyle.Document>, and <xref:System.ServiceModel.OperationFormatStyle.Rpc>.</span></span> <span data-ttu-id="b26ab-110">RPC 意味着与操作交换的消息的 WSDL 表示形式包含参数，如同远程过程调用那样。</span><span class="sxs-lookup"><span data-stu-id="b26ab-110">RPC means that the WSDL representation of messages exchanged for an operation contains parameters as if it were a remote procedure call.</span></span> <span data-ttu-id="b26ab-111">下面是一个示例。</span><span class="sxs-lookup"><span data-stu-id="b26ab-111">The following is an example.</span></span>  
  
```xml  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
  <wsdl:part name="n1" type="xsd:double"/>  
  <wsdl:part name="n2" type="xsd:double"/>  
</wsdl:message>  
```  
  
 <span data-ttu-id="b26ab-112">将样式设置为 <xref:System.ServiceModel.OperationFormatStyle.Document> 意味着 WSDL 表示形式包含一个表示与操作交换的文档的元素，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="b26ab-112">Setting the style to <xref:System.ServiceModel.OperationFormatStyle.Document> means that the WSDL representation contains a single element that represents the document that is exchanged for an operation as shown in the following example.</span></span>  
  
```xml  
<wsdl:message name="IUseAndStyleCalculator_Add_InputMessage">  
  <wsdl:part name="parameters" element="tns:Add"/>  
</wsdl:message>  
```  
  
 <span data-ttu-id="b26ab-113"><xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> 属性确定消息的格式。</span><span class="sxs-lookup"><span data-stu-id="b26ab-113">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property determines the format of the message.</span></span> <span data-ttu-id="b26ab-114">可能的值为 <xref:System.ServiceModel.OperationFormatUse.Literal> 和 <xref:System.ServiceModel.OperationFormatUse.Encoded>；默认值为 <xref:System.ServiceModel.OperationFormatUse.Literal>。</span><span class="sxs-lookup"><span data-stu-id="b26ab-114">Possible values are <xref:System.ServiceModel.OperationFormatUse.Literal> and <xref:System.ServiceModel.OperationFormatUse.Encoded>; the default value is <xref:System.ServiceModel.OperationFormatUse.Literal>.</span></span> <span data-ttu-id="b26ab-115">文本表示该消息是 WSDL 中的一个架构文本实例，如下面的“文档/文本”示例所示。</span><span class="sxs-lookup"><span data-stu-id="b26ab-115">Literal means that the message is a literal instance of the schema in the WSDL as shown in the following Document/ Literal example.</span></span>  
  
```xml  
<Add xmlns="http://Microsoft.ServiceModel.Samples">  
  <n1>100</n1>  
  <n2>15.99</n2>  
</Add>  
```  
  
 <span data-ttu-id="b26ab-116">编码表明 WSDL 中的架构是根据 SOAP 1.1 第 5 节中的规则进行编码的抽象规范。</span><span class="sxs-lookup"><span data-stu-id="b26ab-116">Encoded means that the schemas in the WSDL are abstract specifications that are encoded according to the rules found in SOAP 1.1 section 5.</span></span> <span data-ttu-id="b26ab-117">下面是一个 RPC/编码示例。</span><span class="sxs-lookup"><span data-stu-id="b26ab-117">The following is an RPC/Encoded example.</span></span>  
  
```xml  
<q1:Add xmlns:q1="http://Microsoft.ServiceModel.Samples">  
  <n1 xsi:type="xsd:double" xmlns="">100</n1>  
  <n2 xsi:type="xsd:double" xmlns="">15.99</n2>  
</q1:Add>  
```  
  
 <span data-ttu-id="b26ab-118">WS-I 基本配置文件 1.0 禁止使用 <xref:System.ServiceModel.OperationFormatUse.Encoded>，只能在旧式服务需要时使用它。</span><span class="sxs-lookup"><span data-stu-id="b26ab-118">The WS-I Basic Profile 1.0 prohibits the use of <xref:System.ServiceModel.OperationFormatUse.Encoded> and you should only use it when required by legacy services.</span></span> <span data-ttu-id="b26ab-119">仅当使用 XmlSerializer 时，`Encoded` 消息格式才可用。</span><span class="sxs-lookup"><span data-stu-id="b26ab-119">The `Encoded` message format is only available when using the XmlSerializer.</span></span>  
  
 <span data-ttu-id="b26ab-120">若要允许你查看正在发送和接收的消息，此示例基于[跟踪和消息日志记录](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md)。</span><span class="sxs-lookup"><span data-stu-id="b26ab-120">To allow you to see the messages being sent and received, this sample is based on the [Tracing and Message Logging](../../../../docs/framework/wcf/samples/tracing-and-message-logging.md).</span></span> <span data-ttu-id="b26ab-121">已将服务配置和源代码修改为启用和使用跟踪和消息日志记录。</span><span class="sxs-lookup"><span data-stu-id="b26ab-121">The service configuration and source code have been modified to enable and utilize tracing and message logging.</span></span> <span data-ttu-id="b26ab-122">此外，<<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 已配置没有使用安全性，因此可以以不加密格式查看记录的消息。</span><span class="sxs-lookup"><span data-stu-id="b26ab-122">In addition, the <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> has been configured without security, so the logged messages can be viewed in an unencrypted format.</span></span> <span data-ttu-id="b26ab-123">应通过查看生成的跟踪日志 （System.ServiceModel.e2e 和 Message.log）[服务跟踪查看器工具 (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="b26ab-123">The resulting trace logs (System.ServiceModel.e2e and Message.log) should be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../../../../docs/framework/wcf/service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="b26ab-124">将跟踪配置为在 C:\LOGS 文件夹中创建。</span><span class="sxs-lookup"><span data-stu-id="b26ab-124">The traces are configured to be created in the C:\LOGS folder.</span></span> <span data-ttu-id="b26ab-125">请在运行示例之前创建该文件夹。</span><span class="sxs-lookup"><span data-stu-id="b26ab-125">Create the folder before running the sample.</span></span> <span data-ttu-id="b26ab-126">若要在跟踪查看器工具中查看消息内容，请选择**消息**中的左窗格和右窗格的工具。</span><span class="sxs-lookup"><span data-stu-id="b26ab-126">To view message contents in the Trace Viewer tool, select **Messages** in both the left and the right panes of the tool.</span></span>  
  
 <span data-ttu-id="b26ab-127">下面的代码显示服务协定，该协定的 <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> 属性设置为 <xref:System.ServiceModel.OperationFormatUse>，消息正文格式从默认的 <xref:System.ServiceModel.OperationFormatStyle> 更改为 <xref:System.ServiceModel.OperationFormatStyle.Document>。</span><span class="sxs-lookup"><span data-stu-id="b26ab-127">The following code shows the service contract with the <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> property set to <xref:System.ServiceModel.OperationFormatUse> and the format of the message body changed from the default <xref:System.ServiceModel.OperationFormatStyle> to <xref:System.ServiceModel.OperationFormatStyle.Document>.</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"),  
XmlSerializerFormat(Style = OperationFormatStyle.Rpc,   
                                 Use = OperationFormatUse.Encoded)]  
public interface IUseAndStyleCalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="b26ab-128">若要查看不同的 <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> 和 <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> 设置之间的差异，请在服务中修改这些设置、重新生成客户端、运行示例并用服务跟踪查看器工具检查 c:\logs\message.logs 文件。</span><span class="sxs-lookup"><span data-stu-id="b26ab-128">To see the difference between the different <xref:System.ServiceModel.XmlSerializerFormatAttribute.Use%2A> and <xref:System.ServiceModel.XmlSerializerFormatAttribute.Style%2A> settings, modify them in the service, regenerate the client, run the sample, and examine the c:\logs\message.logs file with the Service Trace Viewer tool.</span></span> <span data-ttu-id="b26ab-129">还可以通过查看 http://localhost/ServiceModelSamples/service.svc?wsdl 观察对元数据的影响。</span><span class="sxs-lookup"><span data-stu-id="b26ab-129">Also observe the impact on the metadata by viewing http://localhost/ServiceModelSamples/service.svc?wsdl.</span></span> <span data-ttu-id="b26ab-130">服务的元数据通常分为多页。</span><span class="sxs-lookup"><span data-stu-id="b26ab-130">The metadata for services is typically broken up into multiple pages.</span></span> <span data-ttu-id="b26ab-131">虽然 wsdl 主页包含 WSDL 绑定，但查看 http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0 可观察到消息定义。</span><span class="sxs-lookup"><span data-stu-id="b26ab-131">The main wsdl page contains the WSDL bindings, but view http://localhost/ServiceModelSamples/service.svc?wsdl=wsdl0 to observe the message definitions.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b26ab-132">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="b26ab-132">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="b26ab-133">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="b26ab-133">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b26ab-134">创建一个 C:\LOGS 目录，用于记录消息。</span><span class="sxs-lookup"><span data-stu-id="b26ab-134">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="b26ab-135">向用户授予对该目录的“网络服务”写权限。</span><span class="sxs-lookup"><span data-stu-id="b26ab-135">Give the user Network Service write permissions for this directory.</span></span>  
  
3.  <span data-ttu-id="b26ab-136">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b26ab-136">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
4.  <span data-ttu-id="b26ab-137">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="b26ab-137">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b26ab-138">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b26ab-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b26ab-139">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b26ab-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b26ab-140">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="b26ab-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b26ab-141">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b26ab-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\UseAndStyle`  
  
## <a name="see-also"></a><span data-ttu-id="b26ab-142">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b26ab-142">See Also</span></span>
