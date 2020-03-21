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
# <a name="poco-support"></a>POCO 支持
此示例演示对未标记的类型的序列化支持，未标记的类型是指尚未应用序列化属性的类型，有时称作“简单传统 CLR 对象 (POCO)”类型。 推断<xref:System.Runtime.Serialization.DataContractSerializer>具有无参数构造函数的所有公共无标记类型的数据协定。 数据协定允许您在服务中传入和传出结构化数据。 有关未标记类型的详细信息，请参阅[可序列化类型](../../../../docs/framework/wcf/feature-details/serializable-types.md)。  
  
 此示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，但使用复数而不是原始数值类型。 它还类似于[基本数据协定](../../../../docs/framework/wcf/samples/basic-data-contract.md)示例，只不过 不使用 和<xref:System.Runtime.Serialization.DataContractAttribute><xref:System.Runtime.Serialization.DataMemberAttribute>属性。  
  
 服务是由 Internet 信息服务 (IIS) 承载的，客户端是一个控制台应用程序 (.exe)。  
  
> [!NOTE]
> 本主题的最后介绍了此示例的设置过程和生成说明。  
  
 `ComplexNumber` 类在 `ServiceContract` 中使用。 `ComplexNumber` 类型没有 <xref:System.Runtime.Serialization.DataContractAttribute> 和 <xref:System.Runtime.Serialization.DataMemberAttribute> 属性，如下面的示例代码所示。 默认情况下，所有公共属性和字段均被序列化。  
  
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
  
### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 确保已为 Windows[通信基础示例执行一次性设置过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。  
  
2. 若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。  
  
3. 要在单机或跨计算机配置中运行示例，请按照[运行 Windows 通信基础示例中的](../../../../docs/framework/wcf/samples/running-the-samples.md)说明操作。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\POCO`  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>
- [可序列化类型](../../../../docs/framework/wcf/feature-details/serializable-types.md)
