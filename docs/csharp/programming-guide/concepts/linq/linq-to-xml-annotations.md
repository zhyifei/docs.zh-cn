---
title: "LINQ to XML 批注 3"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 54e7b9d0-07f5-488f-9065-b6e6b870f810
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: eadbc55ac6188fa3634745bf8bb222f07675a308
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="db12f-102">LINQ to XML 批注</span><span class="sxs-lookup"><span data-stu-id="db12f-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="db12f-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中的注释可将任意类型的任意对象与 XML 树中的任何 XML 组件相关联。</span><span class="sxs-lookup"><span data-stu-id="db12f-103">Annotations in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="db12f-104">若要向 XML 组件（例如 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XAttribute>）中添加批注，需调用 <xref:System.Xml.Linq.XObject.AddAnnotation%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="db12f-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="db12f-105">批注是按类型检索的。</span><span class="sxs-lookup"><span data-stu-id="db12f-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="db12f-106">请注意，批注不是 XML 信息集的一部分，不对它们进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="db12f-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db12f-107">方法</span><span class="sxs-lookup"><span data-stu-id="db12f-107">Methods</span></span>  
 <span data-ttu-id="db12f-108">处理批注时可以使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="db12f-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="db12f-109">方法</span><span class="sxs-lookup"><span data-stu-id="db12f-109">Method</span></span>|<span data-ttu-id="db12f-110">描述</span><span class="sxs-lookup"><span data-stu-id="db12f-110">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XObject.AddAnnotation%2A>|<span data-ttu-id="db12f-111">向 <xref:System.Xml.Linq.XObject> 的批注列表中添加对象。</span><span class="sxs-lookup"><span data-stu-id="db12f-111">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotation%2A>|<span data-ttu-id="db12f-112">从 <xref:System.Xml.Linq.XObject> 获取指定类型的第一个批注对象。</span><span class="sxs-lookup"><span data-stu-id="db12f-112">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.Annotations%2A>|<span data-ttu-id="db12f-113">获取 <xref:System.Xml.Linq.XObject> 的指定类型的批注集合。</span><span class="sxs-lookup"><span data-stu-id="db12f-113">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObject.RemoveAnnotations%2A>|<span data-ttu-id="db12f-114">从 <xref:System.Xml.Linq.XObject> 移除指定类型的批注。</span><span class="sxs-lookup"><span data-stu-id="db12f-114">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="db12f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db12f-115">See Also</span></span>  
 [<span data-ttu-id="db12f-116">高级 LINQ to XML 编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="db12f-116">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
