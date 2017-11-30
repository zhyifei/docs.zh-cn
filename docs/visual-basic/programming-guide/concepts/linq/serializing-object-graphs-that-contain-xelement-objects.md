---
title: "序列化对象图包含 XElement 对象 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 44a30e3c79eb1f68f968e83c50a55f24da9275cb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="0ba83-102">序列化对象图包含 XElement 对象 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ba83-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="0ba83-103">本主题介绍序列化对象图的功能，其中对象图包含对类型为 <xref:System.Xml.Linq.XElement> 的对象的引用。</span><span class="sxs-lookup"><span data-stu-id="0ba83-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="0ba83-104">为便于执行这种类型的序列化，<xref:System.Xml.Linq.XElement> 实现了 <xref:System.Xml.Serialization.IXmlSerializable> 接口。</span><span class="sxs-lookup"><span data-stu-id="0ba83-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="0ba83-105">请注意，只有 <xref:System.Xml.Linq.XElement> 类才实现序列化。</span><span class="sxs-lookup"><span data-stu-id="0ba83-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0ba83-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="0ba83-106">In This Section</span></span>  
  
|<span data-ttu-id="0ba83-107">主题</span><span class="sxs-lookup"><span data-stu-id="0ba83-107">Topic</span></span>|<span data-ttu-id="0ba83-108">描述</span><span class="sxs-lookup"><span data-stu-id="0ba83-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0ba83-109">如何： 使用 XmlSerializer (Visual Basic) 进行序列化</span><span class="sxs-lookup"><span data-stu-id="0ba83-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="0ba83-110">演示如何使用 <xref:System.Xml.Serialization.XmlSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="0ba83-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="0ba83-111">如何： 使用 DataContractSerializer (Visual Basic) 进行序列化</span><span class="sxs-lookup"><span data-stu-id="0ba83-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="0ba83-112">演示如何使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化。</span><span class="sxs-lookup"><span data-stu-id="0ba83-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0ba83-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0ba83-113">See Also</span></span>  
 [<span data-ttu-id="0ba83-114">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0ba83-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
