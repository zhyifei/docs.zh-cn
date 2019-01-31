---
title: 创建 XML 树 (C#)
ms.date: 07/20/2015
ms.assetid: bccc3e0a-c08c-468e-9d30-e075670fdace
ms.openlocfilehash: 64aed2a02f2f31036458ae878a3cbd21d9526d9b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515844"
---
# <a name="creating-xml-trees-c"></a><span data-ttu-id="39d32-102">创建 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="39d32-102">Creating XML Trees (C#)</span></span>
<span data-ttu-id="39d32-103">最常见的 XML 任务之一是构造 XML 树。</span><span class="sxs-lookup"><span data-stu-id="39d32-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="39d32-104">本节介绍多种创建 XML 树的方法。</span><span class="sxs-lookup"><span data-stu-id="39d32-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="39d32-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="39d32-105">In This Section</span></span>  
  
|<span data-ttu-id="39d32-106">主题</span><span class="sxs-lookup"><span data-stu-id="39d32-106">Topic</span></span>|<span data-ttu-id="39d32-107">说明</span><span class="sxs-lookup"><span data-stu-id="39d32-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="39d32-108">函数构造 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="39d32-108">Functional Construction (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="39d32-109">提供对 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中的功能构造的概述。</span><span class="sxs-lookup"><span data-stu-id="39d32-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="39d32-110">功能构造使您能在单条语句中创建全部或部分 XML 树。</span><span class="sxs-lookup"><span data-stu-id="39d32-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="39d32-111">本主题演示如何在构造 XML 树时嵌入查询。</span><span class="sxs-lookup"><span data-stu-id="39d32-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="39d32-112">在 C# 中创建 XML 树 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="39d32-112">Creating XML Trees in C# (LINQ to XML)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md)|<span data-ttu-id="39d32-113">演示如何在 C# 中创建树。</span><span class="sxs-lookup"><span data-stu-id="39d32-113">Shows how to create trees in C#.</span></span>|  
|[<span data-ttu-id="39d32-114">分析 XML (C#)</span><span class="sxs-lookup"><span data-stu-id="39d32-114">Parsing XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="39d32-115">演示如何从不同的源分析 XML。</span><span class="sxs-lookup"><span data-stu-id="39d32-115">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="39d32-116">在 <xref:System.Xml.XmlReader> 的上层，而后者用于分析 XML。</span><span class="sxs-lookup"><span data-stu-id="39d32-116">is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="39d32-117">如何：使用 XmlWriter 填充 XML 树 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="39d32-117">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="39d32-118">演示如何使用 <xref:System.Xml.XmlWriter> 填充 XML 树。</span><span class="sxs-lookup"><span data-stu-id="39d32-118">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="39d32-119">如何：使用 XSD 进行验证 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="39d32-119">How to: Validate Using XSD (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="39d32-120">演示如何使用 XSD 验证 XML 树。</span><span class="sxs-lookup"><span data-stu-id="39d32-120">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="39d32-121">XElement 和 XDocument 对象的有效内容</span><span class="sxs-lookup"><span data-stu-id="39d32-121">Valid Content of XElement and XDocument Objects</span></span>](../../../../csharp/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects3.md)|<span data-ttu-id="39d32-122">描述可以传递给构造函数的有效自变量，以及用于向元素和文档添加内容的方法。</span><span class="sxs-lookup"><span data-stu-id="39d32-122">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="39d32-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="39d32-123">See also</span></span>

- [<span data-ttu-id="39d32-124">编程指南 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="39d32-124">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
