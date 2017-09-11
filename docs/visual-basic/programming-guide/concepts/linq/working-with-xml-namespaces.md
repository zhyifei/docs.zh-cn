---
title: "使用 XML 命名空间 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 428bf4b0-e348-4ffd-986b-d905d5a0e7fa
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 4ddbc7a241fa8dee886fb0aeb5951f1ee622efb5
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="working-with-xml-namespaces-visual-basic"></a><span data-ttu-id="52d81-102">使用 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52d81-102">Working with XML Namespaces (Visual Basic)</span></span>
<span data-ttu-id="52d81-103">本部分中的主题介绍如何[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]支持命名空间。</span><span class="sxs-lookup"><span data-stu-id="52d81-103">The topics in this section describe how [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] supports namespaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="52d81-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="52d81-104">In This Section</span></span>  
  
|<span data-ttu-id="52d81-105">主题</span><span class="sxs-lookup"><span data-stu-id="52d81-105">Topic</span></span>|<span data-ttu-id="52d81-106">描述</span><span class="sxs-lookup"><span data-stu-id="52d81-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="52d81-107">命名空间概述 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="52d81-107">Namespaces Overview (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)|<span data-ttu-id="52d81-108">本主题介绍命名空间、<xref:System.Xml.Linq.XName>类和<xref:System.Xml.Linq.XNamespace>类。</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="52d81-108">This topic introduces namespaces, the <xref:System.Xml.Linq.XName> class, and the <xref:System.Xml.Linq.XNamespace> class.</span></span>|  
|[<span data-ttu-id="52d81-109">如何︰ 创建包含命名空间 (LINQ to XML) 的文档 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52d81-109">How to: Create a Document with Namespaces (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-document-with-namespaces.md)|<span data-ttu-id="52d81-110">演示如何创建包含命名空间的文档。</span><span class="sxs-lookup"><span data-stu-id="52d81-110">Shows how to create documents with namespaces.</span></span>|  
|[<span data-ttu-id="52d81-111">如何︰ 控制 Namespace 前缀 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="52d81-111">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-control-namespace-prefixes-linq-to-xml.md)|<span data-ttu-id="52d81-112">演示如何通过声明全局命名空间来控制命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="52d81-112">Shows how to control namespace prefixes by declaring global namespaces.</span></span>|  
|[<span data-ttu-id="52d81-113">在 Visual Basic 中的默认命名空间的范围</span><span class="sxs-lookup"><span data-stu-id="52d81-113">Scope of Default Namespaces in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/scope-of-default-namespaces.md)|<span data-ttu-id="52d81-114">演示为默认命名空间中的 XML 编写查询的适当方式。</span><span class="sxs-lookup"><span data-stu-id="52d81-114">Demonstrates the appropriate way to write queries for XML in the default namespace.</span></span>|  
|[<span data-ttu-id="52d81-115">使用全局命名空间 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="52d81-115">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-global-namespaces-linq-to-xml.md)|<span data-ttu-id="52d81-116">说明在 Visual Basic 中，并使用它们的原因中的全局命名空间的语义。</span><span class="sxs-lookup"><span data-stu-id="52d81-116">Explains the semantics of global namespaces in Visual Basic, and reasons for using them.</span></span>|  
|[<span data-ttu-id="52d81-117">如何︰ 编写针对命名空间 (Visual Basic 中) 中的 XML 的查询</span><span class="sxs-lookup"><span data-stu-id="52d81-117">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-queries-on-xml-in-namespaces.md)|<span data-ttu-id="52d81-118">演示如何在 Visual Basic LINQ to XML 查询中指定 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="52d81-118">Demonstrates how to specify XML namespaces in Visual Basic LINQ to XML queries.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="52d81-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52d81-119">See Also</span></span>  
 [<span data-ttu-id="52d81-120">编程指南 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="52d81-120">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
