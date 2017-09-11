---
title: "LINQ to XML 编程概述 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 2dfa9b6f-5890-461d-b81c-316853c7f320
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: bc22991f53920b045280d3e74b9b8dd73e63c944
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-xml-programming-overview-c"></a><span data-ttu-id="0650a-102">LINQ to XML 编程概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-102">LINQ to XML Programming Overview (C#)</span></span>
<span data-ttu-id="0650a-103">这些主题提供有关 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 类的高级概述信息，以及有关三个最重要类的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0650a-103">These topics provide high-level overview information about the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes, as well as detailed information about three of the most important classes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0650a-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="0650a-104">In This Section</span></span>  
  
|<span data-ttu-id="0650a-105">主题</span><span class="sxs-lookup"><span data-stu-id="0650a-105">Topic</span></span>|<span data-ttu-id="0650a-106">描述</span><span class="sxs-lookup"><span data-stu-id="0650a-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0650a-107">函数编程与过程编程 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-107">Functional vs. Procedural Programming (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-vs-procedural-programming-linq-to-xml.md)|<span data-ttu-id="0650a-108">总览介绍编写 LINQ to XML 应用程序的两种主要方法。</span><span class="sxs-lookup"><span data-stu-id="0650a-108">Provides a high level view of the two principle approaches to writing LINQ to XML applications.</span></span>|  
|[<span data-ttu-id="0650a-109">LINQ to XML 类概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-109">LINQ to XML Classes Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-classes-overview.md)|<span data-ttu-id="0650a-110">提供 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 类的概述。</span><span class="sxs-lookup"><span data-stu-id="0650a-110">Provides an overview of the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] classes.</span></span>|  
|[<span data-ttu-id="0650a-111">XElement 类概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-111">XElement Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xelement-class-overview.md)|<span data-ttu-id="0650a-112">介绍 <xref:System.Xml.Linq.XElement> 类，该类表示 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="0650a-112">Introduces the <xref:System.Xml.Linq.XElement> class, which represents XML elements.</span></span> <span data-ttu-id="0650a-113"><xref:System.Xml.Linq.XElement> 是 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 类层次结构中的基础类之一。</span><span class="sxs-lookup"><span data-stu-id="0650a-113"><xref:System.Xml.Linq.XElement> is one of the fundamental classes in the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] class hierarchy.</span></span>|  
|[<span data-ttu-id="0650a-114">XAttribute 类概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-114">XAttribute Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xattribute-class-overview.md)|<span data-ttu-id="0650a-115">介绍 <xref:System.Xml.Linq.XAttribute> 类，该类表示 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="0650a-115">Introduces the <xref:System.Xml.Linq.XAttribute> class, which represents XML attributes.</span></span>|  
|[<span data-ttu-id="0650a-116">XDocument 类概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-116">XDocument Class Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/xdocument-class-overview.md)|<span data-ttu-id="0650a-117">介绍 <xref:System.Xml.Linq.XDocument> 类，该类表示 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="0650a-117">Introduces the <xref:System.Xml.Linq.XDocument> class, which represents XML documents.</span></span>|  
|[<span data-ttu-id="0650a-118">如何：生成 LINQ to XML 示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-118">How to: Build LINQ to XML Examples (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-build-linq-to-xml-examples.md)|<span data-ttu-id="0650a-119">包含生成 LINQ to XML 示例所需的 `Using` 指令。</span><span class="sxs-lookup"><span data-stu-id="0650a-119">Contains the `Using` directives that are required to build the LINQ to XML examples.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0650a-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="0650a-120">See Also</span></span>  
 [<span data-ttu-id="0650a-121">编程指南 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0650a-121">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

