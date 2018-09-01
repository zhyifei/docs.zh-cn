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
ms.openlocfilehash: 0540c52cf3e4cd7594f051c10832ea99cf58a34e
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43386455"
---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="c32b4-102">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="c32b4-102">Accessing XML in Visual Basic</span></span>
<span data-ttu-id="c32b4-103">Visual Basic 提供了用于访问和导航 XML 轴属性[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]结构。</span><span class="sxs-lookup"><span data-stu-id="c32b4-103">Visual Basic provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] structures.</span></span> <span data-ttu-id="c32b4-104">这些属性使用特殊语法，可以通过指定的 XML 名称来访问元素和属性。</span><span class="sxs-lookup"><span data-stu-id="c32b4-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="c32b4-105">下表列出了使你能够访问 XML 元素和属性在 Visual Basic 中的语言功能。</span><span class="sxs-lookup"><span data-stu-id="c32b4-105">The following table lists the language features that enable you to access XML elements and attributes in Visual Basic.</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="c32b4-106">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="c32b4-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="c32b4-107">属性说明</span><span class="sxs-lookup"><span data-stu-id="c32b4-107">Property description</span></span>|<span data-ttu-id="c32b4-108">示例</span><span class="sxs-lookup"><span data-stu-id="c32b4-108">Example</span></span>|<span data-ttu-id="c32b4-109">描述</span><span class="sxs-lookup"><span data-stu-id="c32b4-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="c32b4-110">*子轴*</span><span class="sxs-lookup"><span data-stu-id="c32b4-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="c32b4-111">获取所有`phone`元素的子元素的`contact`元素。</span><span class="sxs-lookup"><span data-stu-id="c32b4-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="c32b4-112">*attribute 轴*</span><span class="sxs-lookup"><span data-stu-id="c32b4-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="c32b4-113">获取所有`type`的属性`phone`元素。</span><span class="sxs-lookup"><span data-stu-id="c32b4-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="c32b4-114">*descendant 轴*</span><span class="sxs-lookup"><span data-stu-id="c32b4-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="c32b4-115">获取所有`name`的元素`contacts`元素，而不考虑它们在层次结构中深度。</span><span class="sxs-lookup"><span data-stu-id="c32b4-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="c32b4-116">*扩展索引器*</span><span class="sxs-lookup"><span data-stu-id="c32b4-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="c32b4-117">获取第一个`name`序列中的元素。</span><span class="sxs-lookup"><span data-stu-id="c32b4-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="c32b4-118">*value*</span><span class="sxs-lookup"><span data-stu-id="c32b4-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="c32b4-119">获取在序列中，第一个对象的字符串表示形式或`Nothing`如果序列为空。</span><span class="sxs-lookup"><span data-stu-id="c32b4-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="c32b4-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="c32b4-120">In This Section</span></span>  
 [<span data-ttu-id="c32b4-121">如何：访问 XML 子代元素</span><span class="sxs-lookup"><span data-stu-id="c32b4-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="c32b4-122">演示如何使用子代轴属性访问具有指定的名称并且包含指定的 XML 元素下的所有 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="c32b4-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="c32b4-123">如何：访问 XML 子元素</span><span class="sxs-lookup"><span data-stu-id="c32b4-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="c32b4-124">演示如何使用子轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 子元素。</span><span class="sxs-lookup"><span data-stu-id="c32b4-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="c32b4-125">如何：访问 XML 特性</span><span class="sxs-lookup"><span data-stu-id="c32b4-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="c32b4-126">演示如何使用特性轴属性访问某个 XML 元素中具有指定的名称的所有 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="c32b4-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="c32b4-127">如何：声明和使用 XML 命名空间前缀</span><span class="sxs-lookup"><span data-stu-id="c32b4-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="c32b4-128">演示如何声明 XML 命名空间前缀，并使用它来创建和访问 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="c32b4-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="c32b4-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="c32b4-129">Related Sections</span></span>  
 [<span data-ttu-id="c32b4-130">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="c32b4-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="c32b4-131">提供指向介绍各种 XML 访问属性的章节。</span><span class="sxs-lookup"><span data-stu-id="c32b4-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="c32b4-132">Visual Basic 中的 LINQ to XML 概述</span><span class="sxs-lookup"><span data-stu-id="c32b4-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="c32b4-133">介绍了使用[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="c32b4-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c32b4-134">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="c32b4-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="c32b4-135">提供介绍如何在 Visual Basic 中使用 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="c32b4-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c32b4-136">在 Visual Basic 中操控 XML</span><span class="sxs-lookup"><span data-stu-id="c32b4-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="c32b4-137">提供有关加载和修改 Visual Basic 中的 XML 部分的链接。</span><span class="sxs-lookup"><span data-stu-id="c32b4-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="c32b4-138">XML</span><span class="sxs-lookup"><span data-stu-id="c32b4-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="c32b4-139">提供指向介绍如何使用章节[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="c32b4-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>
