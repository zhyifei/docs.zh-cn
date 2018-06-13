---
title: 在 Visual Basic 中访问 XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
ms.openlocfilehash: b000b3f6846f800b2a96ce10cdd408a355f78a81
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33649589"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="fab90-102">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="fab90-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="fab90-103">Visual Basic 提供用于访问和导航 XML 轴属性[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]结构。</span><span class="sxs-lookup"><span data-stu-id="fab90-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="fab90-104">这些属性使用特殊语法，可以通过指定的 XML 名称来访问元素和属性。</span><span class="sxs-lookup"><span data-stu-id="fab90-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="fab90-105">下表列出可用于访问 XML 元素和属性在 Visual Basic 中的语言功能。</span><span class="sxs-lookup"><span data-stu-id="fab90-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="fab90-106">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="fab90-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="fab90-107">属性说明</span><span class="sxs-lookup"><span data-stu-id="fab90-107">Property description</span></span>|<span data-ttu-id="fab90-108">示例</span><span class="sxs-lookup"><span data-stu-id="fab90-108">Example</span></span>|<span data-ttu-id="fab90-109">描述</span><span class="sxs-lookup"><span data-stu-id="fab90-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="fab90-110">*子轴*</span><span class="sxs-lookup"><span data-stu-id="fab90-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="fab90-111">获取所有`phone`是中的子元素的元素`contact`元素。</span><span class="sxs-lookup"><span data-stu-id="fab90-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="fab90-112">*属性轴*</span><span class="sxs-lookup"><span data-stu-id="fab90-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="fab90-113">获取所有`type`属性`phone`元素。</span><span class="sxs-lookup"><span data-stu-id="fab90-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="fab90-114">*子代轴*</span><span class="sxs-lookup"><span data-stu-id="fab90-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="fab90-115">获取所有`name`元素`contacts`元素，而不考虑如何深层他们发生层次结构中。</span><span class="sxs-lookup"><span data-stu-id="fab90-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="fab90-116">*扩展索引器*</span><span class="sxs-lookup"><span data-stu-id="fab90-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="fab90-117">获取第一个`name`从序列的元素。</span><span class="sxs-lookup"><span data-stu-id="fab90-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="fab90-118">*value*</span><span class="sxs-lookup"><span data-stu-id="fab90-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="fab90-119">序列中获取的字符串表示形式的第一个对象或`Nothing`如果序列为空。</span><span class="sxs-lookup"><span data-stu-id="fab90-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="fab90-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="fab90-120">In This Section</span></span>  
 [<span data-ttu-id="fab90-121">如何：访问 XML 子代元素</span><span class="sxs-lookup"><span data-stu-id="fab90-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="fab90-122">演示如何使用子代轴属性来访问具有指定的名称和指定的 XML 元素下包含的所有 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="fab90-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="fab90-123">如何：访问 XML 子元素</span><span class="sxs-lookup"><span data-stu-id="fab90-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="fab90-124">演示如何使用子轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 子元素。</span><span class="sxs-lookup"><span data-stu-id="fab90-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="fab90-125">如何：访问 XML 特性</span><span class="sxs-lookup"><span data-stu-id="fab90-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="fab90-126">演示如何使用特性轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 特性。</span><span class="sxs-lookup"><span data-stu-id="fab90-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="fab90-127">如何：声明和使用 XML 命名空间前缀</span><span class="sxs-lookup"><span data-stu-id="fab90-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="fab90-128">演示如何声明 XML 命名空间前缀，并使用它来创建和访问 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="fab90-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fab90-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="fab90-129">Related Sections</span></span>  
 [<span data-ttu-id="fab90-130">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="fab90-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="fab90-131">提供指向介绍各种 XML 访问属性的章节。</span><span class="sxs-lookup"><span data-stu-id="fab90-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="fab90-132">Visual Basic 中的 LINQ to XML 概述</span><span class="sxs-lookup"><span data-stu-id="fab90-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="fab90-133">提供介绍了如何使用[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="fab90-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="fab90-134">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="fab90-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="fab90-135">提供在 Visual Basic 中使用 XML 文本的说明。</span><span class="sxs-lookup"><span data-stu-id="fab90-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="fab90-136">在 Visual Basic 中操控 XML</span><span class="sxs-lookup"><span data-stu-id="fab90-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="fab90-137">提供指向有关加载和修改 Visual Basic 中的 XML 的章节。</span><span class="sxs-lookup"><span data-stu-id="fab90-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="fab90-138">XML</span><span class="sxs-lookup"><span data-stu-id="fab90-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="fab90-139">提供指向介绍如何使用章节[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="fab90-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
