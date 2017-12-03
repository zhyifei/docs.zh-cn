---
title: "XMLSerializer 错误"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b9330173461509bed7128f461a05a6a35b26f43f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="xmlserializer-faults"></a><span data-ttu-id="eb580-102">XMLSerializer 错误</span><span class="sxs-lookup"><span data-stu-id="eb580-102">XmlSerializer Faults</span></span>
<span data-ttu-id="eb580-103"><xref:System.Xml.Serialization.XmlSerializer> 错误协定示例演示如何使用 <xref:System.Xml.Serialization.XmlSerializer> 将错误信息从服务传达到客户端。</span><span class="sxs-lookup"><span data-stu-id="eb580-103">The <xref:System.Xml.Serialization.XmlSerializer> fault contract sample demonstrates how to communicate error information from a service to a client using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="eb580-104">示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，使用的一些其他代码添加到服务，以将内部异常转换为错误。</span><span class="sxs-lookup"><span data-stu-id="eb580-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="eb580-105">客户端试图执行除数为零的运算以在服务上强制产生错误情况。</span><span class="sxs-lookup"><span data-stu-id="eb580-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="eb580-106">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="eb580-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="eb580-107">已将计算器协定修改为包括 <xref:System.ServiceModel.FaultContractAttribute>，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="eb580-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span> <span data-ttu-id="eb580-108">另外，<xref:System.ServiceModel.XmlSerializerFormatAttribute> 还用于使用 <xref:System.Xml.Serialization.XmlSerializer> 启用序列化</span><span class="sxs-lookup"><span data-stu-id="eb580-108">Also, the <xref:System.ServiceModel.XmlSerializerFormatAttribute> is used to enable serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="eb580-109">对于此属性 (Attribute)，<xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> 属性 (Property) 设置为 `true`，它指示序列化程序使用 <xref:System.Xml.Serialization.XmlSerializer> 读取和写入错误。</span><span class="sxs-lookup"><span data-stu-id="eb580-109">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> property is set to `true` on this attribute, which instructs the serializer to use the <xref:System.Xml.Serialization.XmlSerializer> for reading and writing faults.</span></span>  
  
```  
[XmlSerializerFormat(SupportFaults=true)]  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
  
    [OperationContract]  
    int Subtract(int n1, int n2);  
  
    [OperationContract]  
    int Multiply(int n1, int n2);  
  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="eb580-110">客户端代理生成代码，你必须将应用**/UseSerializerForFaults**标志切换为[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="eb580-110">When generating code for the client proxy, you must apply the **/UseSerializerForFaults** flag to [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="eb580-111">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="eb580-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="eb580-112">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="eb580-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="eb580-113">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="eb580-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="eb580-114">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="eb580-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="eb580-115">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="eb580-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="eb580-116">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="eb580-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="eb580-117">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="eb580-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="eb580-118">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="eb580-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## <a name="see-also"></a><span data-ttu-id="eb580-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eb580-119">See Also</span></span>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>
