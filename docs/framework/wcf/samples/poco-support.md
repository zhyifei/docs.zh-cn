---
title: POCO 支持
ms.date: 03/30/2017
ms.assetid: 3846ca73-2819-4ca2-8367-dc739dde5a5b
ms.openlocfilehash: e94f6d9576ed96613d975a66c1965820002f94ce
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183415"
---
# <a name="poco-support"></a><span data-ttu-id="b9dd9-102">POCO 支持</span><span class="sxs-lookup"><span data-stu-id="b9dd9-102">POCO Support</span></span>
<span data-ttu-id="b9dd9-103">此示例演示对未标记的类型的序列化支持，未标记的类型是指尚未应用序列化属性的类型，有时称作“简单传统 CLR 对象 (POCO)”类型。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-103">This sample demonstrates the serialization support for unmarked types; that is, types to which serialization attributes have not been applied, sometimes referred to as Plain Old CLR Object (POCO) types.</span></span> <span data-ttu-id="b9dd9-104">推断<xref:System.Runtime.Serialization.DataContractSerializer>具有无参数构造函数的所有公共无标记类型的数据协定。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-104">The <xref:System.Runtime.Serialization.DataContractSerializer> infers a data contract for all public unmarked types that have a parameterless constructor.</span></span> <span data-ttu-id="b9dd9-105">数据协定允许您在服务中传入和传出结构化数据。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-105">Data contracts allow you to pass structured data to and from services.</span></span> <span data-ttu-id="b9dd9-106">有关未标记类型的详细信息，请参阅[可序列化类型](../../../../docs/framework/wcf/feature-details/serializable-types.md)。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-106">For more information about unmarked types, see [Serializable Types](../../../../docs/framework/wcf/feature-details/serializable-types.md).</span></span>  
  
 <span data-ttu-id="b9dd9-107">此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，但使用复数而不是原始数值类型。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-107">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), but uses complex numbers instead of primitive numeric types.</span></span> <span data-ttu-id="b9dd9-108">它还类似于[基本数据协定](../../../../docs/framework/wcf/samples/basic-data-contract.md)示例，只不过 不使用 和<xref:System.Runtime.Serialization.DataContractAttribute><xref:System.Runtime.Serialization.DataMemberAttribute>属性。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-108">It is also similar to the [Basic Data Contract](../../../../docs/framework/wcf/samples/basic-data-contract.md) sample, except that the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes are not used.</span></span>  
  
 <span data-ttu-id="b9dd9-109">服务是由 Internet 信息服务 (IIS) 承载的，客户端是一个控制台应用程序 (.exe)。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-109">The service is hosted by Internet Information Services (IIS) and the client is a console application (.exe).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9dd9-110">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-110">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="b9dd9-111">`ComplexNumber` 类在 `ServiceContract` 中使用。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-111">The `ComplexNumber` class is used in the `ServiceContract`.</span></span> <span data-ttu-id="b9dd9-112">`ComplexNumber` 类型没有 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-112">The `ComplexNumber` type does not have the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> attributes, as shown in the following sample code.</span></span> <span data-ttu-id="b9dd9-113">默认情况下，所有公共属性和字段均被序列化。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-113">By default, all public properties and fields are serialized.</span></span>  
  
```csharp
public class ComplexNumber  
{  
    public double Real;  
    public double Imaginary;  
    public ComplexNumber()  
    {  
        Real = double.MinValue;  
        Imaginary = double.MinValue;  
    }  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
}  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b9dd9-114">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="b9dd9-114">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="b9dd9-115">确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-115">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="b9dd9-116">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-116">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="b9dd9-117">要在单机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-117">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b9dd9-118">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-118">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b9dd9-119">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="b9dd9-119">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="b9dd9-120">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="b9dd9-120">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b9dd9-121">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="b9dd9-121">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a><span data-ttu-id="b9dd9-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9dd9-122">See also</span></span>

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [<span data-ttu-id="b9dd9-123">可序列化类型</span><span class="sxs-lookup"><span data-stu-id="b9dd9-123">Serializable Types</span></span>](../../../../docs/framework/wcf/feature-details/serializable-types.md)
