---
title: 数据合同Jon序列化器样品
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: d3456582d73640f1802c17d7f29f4931a6f920b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79144625"
---
# <a name="datacontractjsonserializer-sample"></a>数据合同Jon序列化器样品

> [!NOTE]
> 此示例用于<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>。 对于大多数涉及序列化和反序列化 JSON 的方案，我们建议[在系统中使用 API。](../../../standard/serialization/system-text-json-overview.md)

<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 支持同一类型，如 <xref:System.Runtime.Serialization.DataContractSerializer>。 JSON 数据格式在编写异步 JavaScript 和 XML (AJAX) 样式的 Web 应用程序时特别有用。 Windows 通信基础 （WCF） 中的 AJAX 支持经过优化，可通过脚本管理器控件与ASP.NET AJAX 一起使用。 有关如何将 Windows 通信基础 （WCF） 与 ASP.NET AJAX 一起使用的示例，请参阅[AJAX 示例](ajax.md)。  
  
本主题的最后介绍了此示例的设置过程和生成说明。  
  
此示例使用 `Person` 数据协定演示序列化和反序列化。  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 若要将 `Person` 类型的实例序列化为 JSON，首先创建 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 并使用 `WriteObject` 方法将 JSON 数据编写成流。  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 内存流包含有效的 JSON 数据。
  
```json  
{"age":42,"name":"John"}  
```  
  
 此示例演示从 JSON 数据反序列化为对象。 然后重绕流并调用 `ReadObject`。  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 检查 `p2` 对象显示 JSON 数据已正确反序列化。  
  
> [!IMPORTANT]
> 您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> 如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。 此示例位于以下目录：  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>设置、生成和运行示例  
  
1. 生成解决方案 Json 序列化.sln，如[构建 Windows 通信基础示例](../../../../docs/framework/wcf/samples/building-the-samples.md)中所述。  
  
2. 运行生成的控制台应用程序。  
