---
title: "在 Visual Basic 中访问 XML |Microsoft 文档"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], accessing XML
- Visual Basic code, XML
- accessing XML [Visual Basic], axis properties
- XML [Visual Basic], axis properties
- XML [Visual Basic], accessing
ms.assetid: c47f88b2-3cbc-4bb1-b4b9-be60f71ffc6a
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: fe096d3686adc2386235944b59b51fb7442dd096
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="accessing-xml-in-visual-basic"></a><span data-ttu-id="fa40d-102">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="fa40d-102">Accessing XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="fa40d-103">提供用于访问和导航 XML 轴属性[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]结构。</span><span class="sxs-lookup"><span data-stu-id="fa40d-103"> provides XML axis properties for accessing and navigating [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] structures.</span></span> <span data-ttu-id="fa40d-104">这些属性使用特殊语法来使您能够通过指定的 XML 名称来访问元素和属性。</span><span class="sxs-lookup"><span data-stu-id="fa40d-104">These properties use a special syntax to enable you to access elements and attributes by specifying the XML names.</span></span>  
  
 <span data-ttu-id="fa40d-105">下表列出了可用于访问 XML 元素和属性中的语言功能[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="fa40d-105">The following table lists the language features that enable you to access XML elements and attributes in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span>  
  
### <a name="xml-axis-properties"></a><span data-ttu-id="fa40d-106">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="fa40d-106">XML Axis Properties</span></span>  
  
|<span data-ttu-id="fa40d-107">属性说明</span><span class="sxs-lookup"><span data-stu-id="fa40d-107">Property description</span></span>|<span data-ttu-id="fa40d-108">示例</span><span class="sxs-lookup"><span data-stu-id="fa40d-108">Example</span></span>|<span data-ttu-id="fa40d-109">说明</span><span class="sxs-lookup"><span data-stu-id="fa40d-109">Description</span></span>|  
|--------------------------|-------------|-----------------|  
|<span data-ttu-id="fa40d-110">*子轴*</span><span class="sxs-lookup"><span data-stu-id="fa40d-110">*child axis*</span></span>|`contact.<phone>`|<span data-ttu-id="fa40d-111">获取所有`phone`元素属于的子元素`contact`元素。</span><span class="sxs-lookup"><span data-stu-id="fa40d-111">Gets all `phone` elements that are child elements of the `contact` element.</span></span>|  
|<span data-ttu-id="fa40d-112">*attribute 轴*</span><span class="sxs-lookup"><span data-stu-id="fa40d-112">*attribute axis*</span></span>|`phone.@type`|<span data-ttu-id="fa40d-113">获取所有`type`属性`phone`元素。</span><span class="sxs-lookup"><span data-stu-id="fa40d-113">Gets all `type` attributes of the `phone` element.</span></span>|  
|<span data-ttu-id="fa40d-114">*子代轴*</span><span class="sxs-lookup"><span data-stu-id="fa40d-114">*descendant axis*</span></span>|`contacts...<name>`|<span data-ttu-id="fa40d-115">获取所有`name`元素`contacts`元素，而不考虑深度顺序层次结构中。</span><span class="sxs-lookup"><span data-stu-id="fa40d-115">Gets all `name` elements of the `contacts` element, regardless of how deep in the hierarchy they occur.</span></span>|  
|<span data-ttu-id="fa40d-116">*扩展索引器*</span><span class="sxs-lookup"><span data-stu-id="fa40d-116">*extension indexer*</span></span>|`contacts...<name>(0)`|<span data-ttu-id="fa40d-117">获取第一个`name`从序列的元素。</span><span class="sxs-lookup"><span data-stu-id="fa40d-117">Gets the first `name` element from the sequence.</span></span>|  
|<span data-ttu-id="fa40d-118">*值*</span><span class="sxs-lookup"><span data-stu-id="fa40d-118">*value*</span></span>|`contacts...<name>.Value`|<span data-ttu-id="fa40d-119">获取在序列中，第一个对象的字符串表示或`Nothing`如果序列为空。</span><span class="sxs-lookup"><span data-stu-id="fa40d-119">Gets the string representation of the first object in the sequence, or `Nothing` if the sequence is empty.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="fa40d-120">本节内容</span><span class="sxs-lookup"><span data-stu-id="fa40d-120">In This Section</span></span>  
 [<span data-ttu-id="fa40d-121">如何：访问 XML 子代元素</span><span class="sxs-lookup"><span data-stu-id="fa40d-121">How to: Access XML Descendant Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-descendant-elements.md)  
 <span data-ttu-id="fa40d-122">演示如何使用子代轴属性来访问所有 XML 元素具有指定的名称并且包含在指定的 XML 元素之下。</span><span class="sxs-lookup"><span data-stu-id="fa40d-122">Shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under a specified XML element.</span></span>  
  
 [<span data-ttu-id="fa40d-123">如何：访问 XML 子元素</span><span class="sxs-lookup"><span data-stu-id="fa40d-123">How to: Access XML Child Elements</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-child-elements.md)  
 <span data-ttu-id="fa40d-124">演示如何使用子轴属性来访问在一个 XML 元素具有指定的名称的所有 XML 子元素。</span><span class="sxs-lookup"><span data-stu-id="fa40d-124">Shows how to use a child axis property to access all XML child elements that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="fa40d-125">如何：访问 XML 特性</span><span class="sxs-lookup"><span data-stu-id="fa40d-125">How to: Access XML Attributes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-access-xml-attributes.md)  
 <span data-ttu-id="fa40d-126">演示如何使用特性轴属性来访问在一个 XML 元素具有指定的名称的所有 XML 特性。</span><span class="sxs-lookup"><span data-stu-id="fa40d-126">Shows how to use an attribute axis property to access all XML attributes that have a specified name in an XML element.</span></span>  
  
 [<span data-ttu-id="fa40d-127">如何：声明和使用 XML 命名空间前缀</span><span class="sxs-lookup"><span data-stu-id="fa40d-127">How to: Declare and Use XML Namespace Prefixes</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-declare-and-use-xml-namespace-prefixes.md)  
 <span data-ttu-id="fa40d-128">演示如何声明 XML 命名空间前缀，并使用它来创建和访问 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="fa40d-128">Shows how to declare an XML namespace prefix and use it to create and access XML elements.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="fa40d-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="fa40d-129">Related Sections</span></span>  
 [<span data-ttu-id="fa40d-130">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="fa40d-130">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="fa40d-131">提供指向介绍各种 XML 访问属性的章节。</span><span class="sxs-lookup"><span data-stu-id="fa40d-131">Provides links to sections describing the various XML access properties.</span></span>  
  
 [<span data-ttu-id="fa40d-132">LINQ to XML 在 Visual Basic 中的概述</span><span class="sxs-lookup"><span data-stu-id="fa40d-132">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="fa40d-133">提供介绍如何使用[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="fa40d-133">Provides an introduction to using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="fa40d-134">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="fa40d-134">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="fa40d-135">提供介绍如何在 Visual Basic 中使用 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="fa40d-135">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="fa40d-136">在 Visual Basic 中操作 XML</span><span class="sxs-lookup"><span data-stu-id="fa40d-136">Manipulating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)  
 <span data-ttu-id="fa40d-137">提供有关加载和修改 Visual Basic 中的 XML 部分的链接。</span><span class="sxs-lookup"><span data-stu-id="fa40d-137">Provides links to sections about loading and modifying XML in Visual Basic.</span></span>  
  
 [<span data-ttu-id="fa40d-138">XML</span><span class="sxs-lookup"><span data-stu-id="fa40d-138">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="fa40d-139">提供指向介绍如何使用章节[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="fa40d-139">Provides links to sections describing how to use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>
