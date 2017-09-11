---
title: "序列化包含 XElement 对象 (Visual Basic 中) 的对象图 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c0cc5c92-5ca3-44b1-98dd-371601df721b
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ce026e68aa95e6d02b46f9b985ee9ee3a268efb3
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="serializing-object-graphs-that-contain-xelement-objects-visual-basic"></a><span data-ttu-id="6267b-102">序列化包含 XElement 对象 (Visual Basic 中) 的对象图</span><span class="sxs-lookup"><span data-stu-id="6267b-102">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>
<span data-ttu-id="6267b-103">本主题介绍序列化对象图包含对类型为<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement>的对象的引用的功能</span><span class="sxs-lookup"><span data-stu-id="6267b-103">This topic introduces the capability of serializing object graphs that contain references to objects of type <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="6267b-104">为便于这种类型的序列化时，<xref:System.Xml.Linq.XElement>实现<xref:System.Xml.Serialization.IXmlSerializable>接口。</xref:System.Xml.Serialization.IXmlSerializable> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6267b-104">To facility this type of serializing, <xref:System.Xml.Linq.XElement> implements the <xref:System.Xml.Serialization.IXmlSerializable> interface.</span></span>  
  
 <span data-ttu-id="6267b-105">请注意，只能<xref:System.Xml.Linq.XElement>类实现序列化。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="6267b-105">Note that only the <xref:System.Xml.Linq.XElement> class implements serialization.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6267b-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="6267b-106">In This Section</span></span>  
  
|<span data-ttu-id="6267b-107">主题</span><span class="sxs-lookup"><span data-stu-id="6267b-107">Topic</span></span>|<span data-ttu-id="6267b-108">描述</span><span class="sxs-lookup"><span data-stu-id="6267b-108">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="6267b-109">如何︰ 使用 XmlSerializer (Visual Basic 中) 进行序列化</span><span class="sxs-lookup"><span data-stu-id="6267b-109">How to: Serialize Using XmlSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-xmlserializer.md)|<span data-ttu-id="6267b-110">演示如何使用<xref:System.Xml.Serialization.XmlSerializer>。</xref:System.Xml.Serialization.XmlSerializer>进行序列化</span><span class="sxs-lookup"><span data-stu-id="6267b-110">Demonstrates how to serialize using <xref:System.Xml.Serialization.XmlSerializer>.</span></span>|  
|[<span data-ttu-id="6267b-111">如何︰ 使用 DataContractSerializer (Visual Basic 中) 进行序列化</span><span class="sxs-lookup"><span data-stu-id="6267b-111">How to: Serialize Using DataContractSerializer (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-serialize-using-datacontractserializer.md)|<span data-ttu-id="6267b-112">演示如何使用<xref:System.Runtime.Serialization.DataContractSerializer>。</xref:System.Runtime.Serialization.DataContractSerializer>进行序列化</span><span class="sxs-lookup"><span data-stu-id="6267b-112">Demonstrates how to serialize using <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6267b-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6267b-113">See Also</span></span>  
 [<span data-ttu-id="6267b-114">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6267b-114">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
