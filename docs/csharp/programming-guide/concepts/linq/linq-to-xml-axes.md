---
title: "LINQ to XML 轴 (C#)"
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
ms.assetid: 3f7d54ff-b608-43a1-9e2d-e70668b72df8
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
ms.openlocfilehash: 65d64b6082942d702444305d7dfed4d05444b59e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="linq-to-xml-axes-c"></a><span data-ttu-id="fe711-102">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-102">LINQ to XML Axes (C#)</span></span>
<span data-ttu-id="fe711-103">创建 XML 树或将 XML 文档加载到 XML 树之后，可以进行查询，从而查找元素和属性并检索它们的值。</span><span class="sxs-lookup"><span data-stu-id="fe711-103">After you have created an XML tree or loaded an XML document into an XML tree, you can query it to find elements and attributes and retrieve their values.</span></span>  
  
 <span data-ttu-id="fe711-104">在编写查询之前，必须了解 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 轴。</span><span class="sxs-lookup"><span data-stu-id="fe711-104">Before you can write any queries, you must understand the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] axes.</span></span> <span data-ttu-id="fe711-105">有两类轴方法：第一类，是调用单个 <xref:System.Xml.Linq.XElement> 对象、<xref:System.Xml.Linq.XDocument> 对象或 <xref:System.Xml.Linq.XNode> 对象的方法。</span><span class="sxs-lookup"><span data-stu-id="fe711-105">There are two kinds of axis methods: First, there are the methods that you call on a single <xref:System.Xml.Linq.XElement> object, <xref:System.Xml.Linq.XDocument> object, or <xref:System.Xml.Linq.XNode> object.</span></span> <span data-ttu-id="fe711-106">这些方法对单个对象操作，返回 <xref:System.Xml.Linq.XElement>、<xref:System.Xml.Linq.XAttribute> 或 <xref:System.Xml.Linq.XNode> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="fe711-106">These methods operate on a single object and return a collection of <xref:System.Xml.Linq.XElement>, <xref:System.Xml.Linq.XAttribute>, or <xref:System.Xml.Linq.XNode> objects.</span></span> <span data-ttu-id="fe711-107">第二类，是对集合操作并返回集合的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="fe711-107">Second, there are extension methods that operate on collections and return collections.</span></span> <span data-ttu-id="fe711-108">这些扩展方法可以：枚举源集合，在集合的每一项上调用适当的轴方法，将结果串联起来。</span><span class="sxs-lookup"><span data-stu-id="fe711-108">The extension methods enumerate the source collection, call the appropriate axis method on each item in the collection, and concatenate the results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fe711-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="fe711-109">In This Section</span></span>  
  
|<span data-ttu-id="fe711-110">主题</span><span class="sxs-lookup"><span data-stu-id="fe711-110">Topic</span></span>|<span data-ttu-id="fe711-111">描述</span><span class="sxs-lookup"><span data-stu-id="fe711-111">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="fe711-112">LINQ to XML 轴概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-112">LINQ to XML Axes Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)|<span data-ttu-id="fe711-113">介绍轴的定义，并说明如何在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询的上下文中使用轴。</span><span class="sxs-lookup"><span data-stu-id="fe711-113">Defines axes, and explains how they are used in the context of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] queries.</span></span>|  
|[<span data-ttu-id="fe711-114">如何：检索元素集合 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-114">How to: Retrieve a Collection of Elements (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-elements-linq-to-xml.md)|<span data-ttu-id="fe711-115">介绍 <xref:System.Xml.Linq.XContainer.Elements%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fe711-115">Introduces the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="fe711-116">此方法检索元素的子元素集合。</span><span class="sxs-lookup"><span data-stu-id="fe711-116">This method retrieves a collection of the child elements of an element.</span></span>|  
|[<span data-ttu-id="fe711-117">如何：检索元素的值 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-117">How to: Retrieve the Value of an Element (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-element-linq-to-xml.md)|<span data-ttu-id="fe711-118">演示如何获取元素的值。</span><span class="sxs-lookup"><span data-stu-id="fe711-118">Shows how to get the values of elements.</span></span>|  
|[<span data-ttu-id="fe711-119">如何：筛选元素名称 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-119">How to: Filter on Element Names (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-filter-on-element-names-linq-to-xml.md)|<span data-ttu-id="fe711-120">演示如何在使用轴时筛选元素名称。</span><span class="sxs-lookup"><span data-stu-id="fe711-120">Shows how to filter on element names when using axes.</span></span>|  
|[<span data-ttu-id="fe711-121">如何：链接轴方法调用 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-121">How to: Chain Axis Method Calls (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-chain-axis-method-calls-linq-to-xml.md)|<span data-ttu-id="fe711-122">演示如何将调用链接到轴方法。</span><span class="sxs-lookup"><span data-stu-id="fe711-122">Shows how to chain calls to axes methods.</span></span>|  
|[<span data-ttu-id="fe711-123">如何：检索单个子元素 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-123">How to: Retrieve a Single Child Element (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md)|<span data-ttu-id="fe711-124">演示在给定子元素标记名的情况下，如何检索元素的单个子元素。</span><span class="sxs-lookup"><span data-stu-id="fe711-124">Shows how to retrieve a single child element of an element, given the tag name of the child element.</span></span>|  
|[<span data-ttu-id="fe711-125">如何：检索特性的集合 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-125">How to: Retrieve a Collection of Attributes (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-collection-of-attributes-linq-to-xml.md)|<span data-ttu-id="fe711-126">介绍 <xref:System.Xml.Linq.XElement.Attributes%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="fe711-126">Introduces the <xref:System.Xml.Linq.XElement.Attributes%2A> method.</span></span> <span data-ttu-id="fe711-127">此方法检索元素的属性。</span><span class="sxs-lookup"><span data-stu-id="fe711-127">This method retrieves the attributes of an element.</span></span>|  
|[<span data-ttu-id="fe711-128">如何：检索单个特性 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-128">How to: Retrieve a Single Attribute (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-attribute-linq-to-xml.md)|<span data-ttu-id="fe711-129">演示在给定属性名称的情况下，如何检索元素的单个属性。</span><span class="sxs-lookup"><span data-stu-id="fe711-129">Shows how to retrieve a single attribute of an element, given the attribute name.</span></span>|  
|[<span data-ttu-id="fe711-130">如何：检索特性的值 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-130">How to: Retrieve the Value of an Attribute (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-value-of-an-attribute-linq-to-xml.md)|<span data-ttu-id="fe711-131">演示如何获取属性的值。</span><span class="sxs-lookup"><span data-stu-id="fe711-131">Shows how to get the values of attributes.</span></span>|  
|[<span data-ttu-id="fe711-132">如何：检索元素的浅表值 (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-132">How to: Retrieve the Shallow Value of an Element (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-the-shallow-value-of-an-element.md)|<span data-ttu-id="fe711-133">演示如何检索元素的浅值。</span><span class="sxs-lookup"><span data-stu-id="fe711-133">Shows how to retrieve the shallow value of an element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="fe711-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="fe711-134">See Also</span></span>  
 <span data-ttu-id="fe711-135">[扩展方法](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span><span class="sxs-lookup"><span data-stu-id="fe711-135">[Extension Methods](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md) </span></span>  
 [<span data-ttu-id="fe711-136">编程指南 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="fe711-136">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

