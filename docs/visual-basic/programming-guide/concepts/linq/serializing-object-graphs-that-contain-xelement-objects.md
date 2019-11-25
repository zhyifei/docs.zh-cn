---
title: 序列化包含 XElement 对象的对象图
ms.date: 07/20/2015
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
ms.openlocfilehash: caf594fc23eee15cc79cfad47e62a057518f62dd
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349370"
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="be57e-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be57e-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="be57e-103">本主题介绍序列化对象图的功能，其中对象图包含对类型为 <xref:System.Xml.Linq.XElement> 的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="be57e-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="be57e-104">为便于执行这种类型的序列化，<xref:System.Xml.Linq.XElement> 实现了 <xref:System.Xml.Serialization.IXmlSerializable> 接口。</span><span class="sxs-lookup"><span data-stu-id="be57e-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="be57e-105">请注意，只有 <xref:System.Xml.Linq.XElement> 类才实现序列化。</span><span class="sxs-lookup"><span data-stu-id="be57e-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="be57e-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="be57e-106">In This Section</span></span>  
  
|<span data-ttu-id="be57e-107">主题</span><span class="sxs-lookup"><span data-stu-id="be57e-107">Topic</span></span>|<span data-ttu-id="be57e-108">描述</span><span class="sxs-lookup"><span data-stu-id="be57e-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="be57e-109">如何：使用 XmlSerializer 进行序列化 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be57e-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="be57e-110">演示如何使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="be57e-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="be57e-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be57e-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="be57e-112">演示如何使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="be57e-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="be57e-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="be57e-113">See also</span></span>

- [<span data-ttu-id="be57e-114">Advanced LINQ to XML Programming (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be57e-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
