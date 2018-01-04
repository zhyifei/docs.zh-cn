---
title: "JSON 序列化"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2835b77c1844c74e04c9ccf7ddaaa4f9fb60dba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="json-serialization"></a><span data-ttu-id="0a4dc-102">JSON 序列化</span><span class="sxs-lookup"><span data-stu-id="0a4dc-102">JSON Serialization</span></span>
<span data-ttu-id="0a4dc-103">此示例演示如何使用 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 序列化和反序列化 JavaScript Object Notation (JSON) 格式的数据。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-103">This sample demonstrates how to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to serialize and deserialize data in the JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="0a4dc-104">此序列化引擎将 JSON 数据转换为 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 类型的实例，然后重新转换为 JSON 数据。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-104">This serialization engine converts JSON data into instances of [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types and back into JSON data.</span></span> <span data-ttu-id="0a4dc-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 支持同一类型，如 <xref:System.Runtime.Serialization.DataContractSerializer>。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="0a4dc-106">JSON 数据格式在编写异步 JavaScript 和 XML (AJAX) 样式的 Web 应用程序时特别有用。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="0a4dc-107">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 中的 AJAX 支持已经过优化，可通过 ScriptManager 控件与 ASP.NET AJAX 一起使用。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-107">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="0a4dc-108">有关如何使用的示例[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]与 ASP.NET AJAX，请参阅[AJAX 示例](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e)。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-108">For examples of how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/en-us/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0a4dc-109">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0a4dc-110">此示例使用 `Person` 数据协定演示序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  
  
```  
[DataContract]  
    class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
```  
  
 <span data-ttu-id="0a4dc-111">若要将 `Person` 类型的实例序列化为 JSON，首先创建 <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> 并使用 `WriteObject` 方法将 JSON 数据编写成流。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  
  
```  
Person p = new Person();  
//Set up Person object...  
MemoryStream stream1 = new MemoryStream();  
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
ser.WriteObject(stream1, p);  
```  
  
 <span data-ttu-id="0a4dc-112">内存流包含有效的 JSON 数据。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-112">The memory stream contains valid JSON data.</span></span>  
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="0a4dc-113">此示例演示从 JSON 数据反序列化为对象。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="0a4dc-114">然后重绕流并调用 `ReadObject`。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-114">You then rewind the stream and call `ReadObject`.</span></span>  
  
```  
Person p2 = (Person)ser.ReadObject(stream1);  
```  
  
 <span data-ttu-id="0a4dc-115">检查 `p2` 对象显示 JSON 数据已正确反序列化。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0a4dc-116">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0a4dc-117">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="0a4dc-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="0a4dc-118">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0a4dc-119">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="0a4dc-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0a4dc-120">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="0a4dc-120">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="0a4dc-121">生成解决方案 JsonSerialization.sln 中所述[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="0a4dc-122">运行生成的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="0a4dc-122">Run the resulting console application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a4dc-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a4dc-123">See Also</span></span>
