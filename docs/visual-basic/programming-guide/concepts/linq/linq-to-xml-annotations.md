---
title: LINQ to XML Annotations2
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ca84af7cd750529eadb9d0967f4d5570b7038a07
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="2932a-102">LINQ to XML 批注</span><span class="sxs-lookup"><span data-stu-id="2932a-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="2932a-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中的注释可将任意类型的任意对象与 XML 树中的任何 XML 组件相关联。</span><span class="sxs-lookup"><span data-stu-id="2932a-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="2932a-104">若要向 XML 组件（例如 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XAttribute>）中添加批注，需调用 <xref:System.Xml.Linq.XObject.AddAnnotation%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="2932a-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="2932a-105">批注是按类型检索的。</span><span class="sxs-lookup"><span data-stu-id="2932a-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="2932a-106">请注意，批注不是 XML 信息集的一部分，不对它们进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="2932a-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2932a-107">方法</span><span class="sxs-lookup"><span data-stu-id="2932a-107">Methods</span></span>  
 <span data-ttu-id="2932a-108">处理批注时可以使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="2932a-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="2932a-109">方法</span><span class="sxs-lookup"><span data-stu-id="2932a-109">Method</span></span>|<span data-ttu-id="2932a-110">描述</span><span class="sxs-lookup"><span data-stu-id="2932a-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="2932a-111">向 <xref:System.Xml.Linq.XObject> 的批注列表中添加对象。</span><span class="sxs-lookup"><span data-stu-id="2932a-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="2932a-112">从 <xref:System.Xml.Linq.XObject> 获取指定类型的第一个批注对象。</span><span class="sxs-lookup"><span data-stu-id="2932a-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="2932a-113">获取 <xref:System.Xml.Linq.XObject> 的指定类型的批注集合。</span><span class="sxs-lookup"><span data-stu-id="2932a-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="2932a-114">从 <xref:System.Xml.Linq.XObject> 移除指定类型的批注。</span><span class="sxs-lookup"><span data-stu-id="2932a-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2932a-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2932a-115">See Also</span></span>  
 [<span data-ttu-id="2932a-116">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2932a-116">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
