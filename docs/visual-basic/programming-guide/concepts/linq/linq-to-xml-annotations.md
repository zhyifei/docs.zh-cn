---
title: "LINQ to XML Annotations2 |Microsoft 文档"
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
ms.assetid: c3e8b3ff-fceb-4428-b0ca-1ed6f128aac8
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 97f5386630ba687e4401ee0cfb70f7170e273a53
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="linq-to-xml-annotations"></a><span data-ttu-id="62745-102">LINQ to XML 批注</span><span class="sxs-lookup"><span data-stu-id="62745-102">LINQ to XML Annotations</span></span>
<span data-ttu-id="62745-103">中的批注[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]使您能够将任意类型的任意对象与 XML 树中的任何 XML 组件相关联。</span><span class="sxs-lookup"><span data-stu-id="62745-103">Annotations in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] enable you to associate any arbitrary object of any arbitrary type with any XML component in an XML tree.</span></span>  
  
 <span data-ttu-id="62745-104">若要将批注添加到 XML 组件，比如<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>，您调用<xref:System.Xml.Linq.XObject.AddAnnotation%2A>方法。</xref:System.Xml.Linq.XObject.AddAnnotation%2A> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="62745-104">To add an annotation to an XML component, such as an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute>, you call the <xref:System.Xml.Linq.XObject.AddAnnotation%2A> method.</span></span> <span data-ttu-id="62745-105">批注是按类型检索的。</span><span class="sxs-lookup"><span data-stu-id="62745-105">You retrieve annotations by type.</span></span>  
  
 <span data-ttu-id="62745-106">请注意，批注不是 XML 信息集的一部分，不对它们进行序列化和反序列化。</span><span class="sxs-lookup"><span data-stu-id="62745-106">Note that annotations are not part of the XML infoset; they are not serialized or deserialized.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62745-107">方法</span><span class="sxs-lookup"><span data-stu-id="62745-107">Methods</span></span>  
 <span data-ttu-id="62745-108">处理批注时可以使用以下方法：</span><span class="sxs-lookup"><span data-stu-id="62745-108">You can use the following methods when working with annotations:</span></span>  
  
|<span data-ttu-id="62745-109">方法</span><span class="sxs-lookup"><span data-stu-id="62745-109">Method</span></span>|<span data-ttu-id="62745-110">描述</span><span class="sxs-lookup"><span data-stu-id="62745-110">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="62745-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></xref:System.Xml.Linq.XObject.AddAnnotation%2A></span><span class="sxs-lookup"><span data-stu-id="62745-111"><xref:System.Xml.Linq.XObject.AddAnnotation%2A></span></span>|<span data-ttu-id="62745-112">将对象添加到<xref:System.Xml.Linq.XObject>。</xref:System.Xml.Linq.XObject>的批注列表</span><span class="sxs-lookup"><span data-stu-id="62745-112">Adds an object to the annotation list of an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="62745-113"><xref:System.Xml.Linq.XObject.Annotation%2A></xref:System.Xml.Linq.XObject.Annotation%2A></span><span class="sxs-lookup"><span data-stu-id="62745-113"><xref:System.Xml.Linq.XObject.Annotation%2A></span></span>|<span data-ttu-id="62745-114">从<xref:System.Xml.Linq.XObject>。</xref:System.Xml.Linq.XObject>中获取指定类型的第一个批注对象</span><span class="sxs-lookup"><span data-stu-id="62745-114">Gets the first annotation object of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="62745-115"><xref:System.Xml.Linq.XObject.Annotations%2A></xref:System.Xml.Linq.XObject.Annotations%2A></span><span class="sxs-lookup"><span data-stu-id="62745-115"><xref:System.Xml.Linq.XObject.Annotations%2A></span></span>|<span data-ttu-id="62745-116">获取指定类型的批注的集合<xref:System.Xml.Linq.XObject>。</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="62745-116">Gets a collection of annotations of the specified type for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="62745-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span><span class="sxs-lookup"><span data-stu-id="62745-117"><xref:System.Xml.Linq.XObject.RemoveAnnotations%2A></span></span>|<span data-ttu-id="62745-118">从<xref:System.Xml.Linq.XObject>。</xref:System.Xml.Linq.XObject>中删除指定类型的批注</span><span class="sxs-lookup"><span data-stu-id="62745-118">Removes the annotations of the specified type from an <xref:System.Xml.Linq.XObject>.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="62745-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62745-119">See Also</span></span>  
 [<span data-ttu-id="62745-120">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="62745-120">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
