---
title: 序列化包含 XElement 对象的对象图 (C#)
ms.date: 07/20/2015
ms.assetid: fcbc3951-3cc4-4d0f-9259-e97549ed68f0
ms.openlocfilehash: 2e82165421d31ec234de4806b59565fa675217ef
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45698138"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-c"></a><span data-ttu-id="db044-102">序列化包含 XElement 对象的对象图 (C#)</span><span class="sxs-lookup"><span data-stu-id="db044-102">Serializing Object Graphs that Contain XElement Objects (C#)</span></span>
<span data-ttu-id="db044-103">本主题介绍序列化对象图的功能，其中对象图包含对类型为 <xref:System.Xml.Linq.XElement> 的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="db044-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="db044-104">为便于执行这种类型的序列化，<xref:System.Xml.Linq.XElement> 实现了 <xref:System.Xml.Serialization.IXmlSerializable> 接口。</span><span class="sxs-lookup"><span data-stu-id="db044-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="db044-105">请注意，只有 <xref:System.Xml.Linq.XElement> 类才实现序列化。</span><span class="sxs-lookup"><span data-stu-id="db044-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="db044-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="db044-106">In This Section</span></span>  
  
|<span data-ttu-id="db044-107">主题</span><span class="sxs-lookup"><span data-stu-id="db044-107">Topic</span></span>|<span data-ttu-id="db044-108">描述</span><span class="sxs-lookup"><span data-stu-id="db044-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="db044-109">如何：使用 XmlSerializer 进行序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="db044-109">How to: Serialize Using XmlSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="db044-110">演示如何使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="db044-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="db044-111">如何：使用 DataContractSerializer 进行序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="db044-111">How to: Serialize Using DataContractSerializer (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="db044-112">演示如何使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="db044-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db044-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="db044-113">See Also</span></span>

- [<span data-ttu-id="db044-114">高级 LINQ to XML 编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="db044-114">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
