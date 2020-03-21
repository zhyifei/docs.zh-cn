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
# <a name="datacontractjsonserializer-sample"></a><span data-ttu-id="6e41c-102">数据合同Jon序列化器样品</span><span class="sxs-lookup"><span data-stu-id="6e41c-102">DataContractJsonSerializer sample</span></span>

> [!NOTE]
> <span data-ttu-id="6e41c-103">此示例用于<xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>。</span><span class="sxs-lookup"><span data-stu-id="6e41c-103">This sample is for <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span> <span data-ttu-id="6e41c-104">对于大多数涉及序列化和反序列化 JSON 的方案，我们建议[在系统中使用 API。](../../../standard/serialization/system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="6e41c-104">For most scenarios that involve serializing and deserializing JSON, we recommend the APIs in the [System.Text.Json namespace](../../../standard/serialization/system-text-json-overview.md).</span></span>

<span data-ttu-id="6e41c-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 支持同一类型，如 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="6e41c-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="6e41c-106">JSON 数据格式在编写异步 JavaScript 和 XML (AJAX) 样式的 Web 应用程序时特别有用。</span><span class="sxs-lookup"><span data-stu-id="6e41c-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="6e41c-107">Windows 通信基础 （WCF） 中的 AJAX 支持经过优化，可通过脚本管理器控件与ASP.NET AJAX 一起使用。</span><span class="sxs-lookup"><span data-stu-id="6e41c-107">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="6e41c-108">有关如何将 Windows 通信基础 （WCF） 与 ASP.NET AJAX 一起使用的示例，请参阅[AJAX 示例](ajax.md)。</span><span class="sxs-lookup"><span data-stu-id="6e41c-108">For examples of how to use Windows Communication Foundation (WCF) with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
<span data-ttu-id="6e41c-109">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="6e41c-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
<span data-ttu-id="6e41c-110">此示例使用 `Person` 数据协定演示序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="6e41c-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

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

 <span data-ttu-id="6e41c-111">若要将 `Person` 类型的实例序列化为 JSON，首先创建 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 并使用 `WriteObject` 方法将 JSON 数据编写成流。</span><span class="sxs-lookup"><span data-stu-id="6e41c-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="6e41c-112">内存流包含有效的 JSON 数据。</span><span class="sxs-lookup"><span data-stu-id="6e41c-112">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="6e41c-113">此示例演示从 JSON 数据反序列化为对象。</span><span class="sxs-lookup"><span data-stu-id="6e41c-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="6e41c-114">然后重绕流并调用 `ReadObject`。</span><span class="sxs-lookup"><span data-stu-id="6e41c-114">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="6e41c-115">检查 `p2` 对象显示 JSON 数据已正确反序列化。</span><span class="sxs-lookup"><span data-stu-id="6e41c-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6e41c-116">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="6e41c-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6e41c-117">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="6e41c-117">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6e41c-118">如果此目录不存在，请转到[Windows 通信基础 （WCF） 和 Windows 工作流基础 （WF） 示例 .NET 框架 4](https://www.microsoft.com/download/details.aspx?id=21459)以下载[!INCLUDE[wf1](../../../../includes/wf1-md.md)]所有 Windows 通信基础 （WCF） 和示例。</span><span class="sxs-lookup"><span data-stu-id="6e41c-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6e41c-119">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="6e41c-119">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6e41c-120">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="6e41c-120">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="6e41c-121">生成解决方案 Json 序列化.sln，如[构建 Windows 通信基础示例](../../../../docs/framework/wcf/samples/building-the-samples.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="6e41c-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="6e41c-122">运行生成的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="6e41c-122">Run the resulting console application.</span></span>  
