---
title: "LINQ to XML 在 Visual Basic 中的概述 |Microsoft 文档"
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
- LINQ to XML [Visual Basic], about LINQ to XML
- LINQ [Visual Basic], LINQ to XML
ms.assetid: 01c62a79-6d58-468e-84fb-039c05947701
caps.latest.revision: 17
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
ms.openlocfilehash: cab0c219fe62064c62af4bd93e445107d73974db
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="overview-of-linq-to-xml-in-visual-basic"></a><span data-ttu-id="43590-102">Visual Basic 中的 LINQ to XML 概述</span><span class="sxs-lookup"><span data-stu-id="43590-102">Overview of LINQ to XML in Visual Basic</span></span>
[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="43590-103">提供了对支持[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]通过 XML 文本和 XML 轴属性。</span><span class="sxs-lookup"><span data-stu-id="43590-103"> provides support for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] through XML literals and XML axis properties.</span></span> <span data-ttu-id="43590-104">这使您可以使用熟悉、 便利的语法，在中使用 XML 您[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]代码。</span><span class="sxs-lookup"><span data-stu-id="43590-104">This enables you to use a familiar, convenient syntax for working with XML in your [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] code.</span></span> <span data-ttu-id="43590-105">*XML 文本*使您能够在您的代码中直接包含 XML。</span><span class="sxs-lookup"><span data-stu-id="43590-105">*XML literals* enable you to include XML directly in your code.</span></span> <span data-ttu-id="43590-106">*XML 轴属性*使您能够访问子节点、 子代节点和属性的 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="43590-106">*XML axis properties* enable you to access child nodes, descendant nodes, and attributes of an XML literal.</span></span> <span data-ttu-id="43590-107">有关详细信息，请参阅[XML 文本概述](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)和[在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="43590-107">For more information, see [XML Literals Overview](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md) and [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="43590-108">内存中 XML 编程 API，专门用于充分利用[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="43590-108"> is an in-memory XML programming API designed specifically to take advantage of [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)].</span></span> <span data-ttu-id="43590-109">尽管可以调用[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]Api 直接，只[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]可用于声明 XML 文本和直接访问 XML 轴属性。</span><span class="sxs-lookup"><span data-stu-id="43590-109">Although you can call the [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] APIs directly, only [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enables you to declare XML literals and directly access XML axis properties.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="43590-110">在 ASP.NET 页中的声明性代码中不支持 XML 文本和 XML 轴属性。</span><span class="sxs-lookup"><span data-stu-id="43590-110">XML literals and XML axis properties are not supported in declarative code in an ASP.NET page.</span></span> <span data-ttu-id="43590-111">若要使用 Visual Basic XML 功能，请将代码放在 ASP.NET 应用程序中的代码隐藏页。</span><span class="sxs-lookup"><span data-stu-id="43590-111">To use Visual Basic XML features, put your code in a code-behind page in your ASP.NET application.</span></span>  
  
 <span data-ttu-id="43590-112">![视频链接](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo")相关的视频演示，请参阅[如何开始使用 LINQ to XML？](http://go.microsoft.com/fwlink/?LinkId=143034)和[如何实现创建 Excel 电子表格使用 LINQ to XML？](http://go.microsoft.com/fwlink/?LinkId=143536)。</span><span class="sxs-lookup"><span data-stu-id="43590-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For related video demonstrations, see [How Do I Get Started with LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143034) and [How Do I Create Excel Spreadsheets using LINQ to XML?](http://go.microsoft.com/fwlink/?LinkId=143536).</span></span>  
  
## <a name="creating-xml"></a><span data-ttu-id="43590-113">创建 XML</span><span class="sxs-lookup"><span data-stu-id="43590-113">Creating XML</span></span>  
 <span data-ttu-id="43590-114">有两种方法来创建 XML 树的[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]。</span><span class="sxs-lookup"><span data-stu-id="43590-114">There are two ways to create XML trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)].</span></span> <span data-ttu-id="43590-115">您可以声明 XML 文本直接在代码中，也可以使用[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]Api 以创建树。</span><span class="sxs-lookup"><span data-stu-id="43590-115">You can declare an XML literal directly in code, or you can use the [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] APIs to create the tree.</span></span> <span data-ttu-id="43590-116">这两个进程都使代码能够反映最终 XML 树的结构。</span><span class="sxs-lookup"><span data-stu-id="43590-116">Both processes enable the code to reflect the final structure of the XML tree.</span></span> <span data-ttu-id="43590-117">例如，下面的代码示例创建一个 XML 元素︰</span><span class="sxs-lookup"><span data-stu-id="43590-117">For example, the following code example creates an XML element:</span></span>  
  
 <span data-ttu-id="43590-118">[!code-vb[VbXmlSamples #&5;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="43590-118">[!code-vb[VbXmlSamples#5](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_1.vb)]</span></span>  
  
 <span data-ttu-id="43590-119">有关详细信息，请参阅[在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="43590-119">For more information, see [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md).</span></span>  
  
## <a name="accessing-and-navigating-xml"></a><span data-ttu-id="43590-120">访问和导航 XML</span><span class="sxs-lookup"><span data-stu-id="43590-120">Accessing and Navigating XML</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="43590-121">提供用于访问和导航 XML 结构的 XML 轴属性。</span><span class="sxs-lookup"><span data-stu-id="43590-121"> provides XML axis properties for accessing and navigating XML structures.</span></span> <span data-ttu-id="43590-122">这些属性，您可以通过指定的 XML 子元素名称来访问 XML 元素和属性。</span><span class="sxs-lookup"><span data-stu-id="43590-122">These properties enable you to access XML elements and attributes by specifying the XML child element names.</span></span> <span data-ttu-id="43590-123">或者，您可以显式调用[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]用于导航和查找元素和属性的方法。</span><span class="sxs-lookup"><span data-stu-id="43590-123">Alternatively, you can explicitly call the [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] methods for navigating and locating elements and attributes.</span></span> <span data-ttu-id="43590-124">例如，下面的代码示例使用 XML 轴属性来引用的属性和 XML 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="43590-124">For example, the following code example uses XML axis properties to refer to the attributes and child elements of an XML element.</span></span> <span data-ttu-id="43590-125">此代码示例使用[!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)]查询以检索子元素并输出为 XML 元素，从而有效地执行转换。</span><span class="sxs-lookup"><span data-stu-id="43590-125">The code example uses a [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] query to retrieve child elements and output them as XML elements, effectively performing a transform.</span></span>  
  
 <span data-ttu-id="43590-126">[!code-vb[VbXmlSamples #&8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="43590-126">[!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_2.vb)]</span></span>  
  
 <span data-ttu-id="43590-127">有关详细信息，请参阅[在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="43590-127">For more information, see [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md).</span></span>  
  
## <a name="xml-namespaces"></a><span data-ttu-id="43590-128">XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="43590-128">XML Namespaces</span></span>  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]<span data-ttu-id="43590-129">使您能够通过使用指定为全局的 XML 命名空间别名`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="43590-129"> enables you to specify an alias to a global XML namespace by using the `Imports` statement.</span></span> <span data-ttu-id="43590-130">下面的示例演示如何使用`Imports`语句导入的 XML 命名空间︰</span><span class="sxs-lookup"><span data-stu-id="43590-130">The following example shows how to use the `Imports` statement to import an XML namespace:</span></span>  
  
 <span data-ttu-id="43590-131">[!code-vb[VbXMLSamples #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="43590-131">[!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_3.vb)]</span></span>  
  
 <span data-ttu-id="43590-132">访问 XML 轴属性和声明的 XML 文档和元素的 XML 文本时，可以使用 XML 命名空间别名。</span><span class="sxs-lookup"><span data-stu-id="43590-132">You can use an XML namespace alias when you access XML axis properties and declare XML literals for XML documents and elements.</span></span>  
  
 <span data-ttu-id="43590-133">您可以检索<xref:System.Xml.Linq.XNamespace>对象使用的特定命名空间前缀[GetXmlNamespace 运算符](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md)。</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="43590-133">You can retrieve an <xref:System.Xml.Linq.XNamespace> object for a particular namespace prefix by using the [GetXmlNamespace Operator](../../../../visual-basic/language-reference/operators/getxmlnamespace-operator.md).</span></span>  
  
 <span data-ttu-id="43590-134">有关详细信息，请参阅[Imports 语句 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="43590-134">For more information, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md).</span></span>  
  
### <a name="using-xml-namespaces-in-xml-literals"></a><span data-ttu-id="43590-135">在 XML 文本中使用 XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="43590-135">Using XML Namespaces in XML Literals</span></span>  
 <span data-ttu-id="43590-136">下面的示例演示如何创建<xref:System.Xml.Linq.XElement>使用全局命名空间的对象`ns`:</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="43590-136">The following example shows how to create an <xref:System.Xml.Linq.XElement> object that uses the global namespace `ns`:</span></span>  
  
 <span data-ttu-id="43590-137">[!code-vb[VbXMLSamples #&2;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="43590-137">[!code-vb[VbXMLSamples#2](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_4.vb)]</span></span>  
  
 <span data-ttu-id="43590-138">[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]编译器将转换成等效的代码，用于使用 XML 命名空间的 XML 表示法包含 XML 命名空间别名的 XML 文本`xmlns`属性。</span><span class="sxs-lookup"><span data-stu-id="43590-138">The [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] compiler translates XML literals that contain XML namespace aliases into equivalent code that uses the XML notation for using XML namespaces, with the `xmlns` attribute.</span></span> <span data-ttu-id="43590-139">在编译时上, 一节示例中的代码将产生与下面的示例实质上是相同的可执行代码︰</span><span class="sxs-lookup"><span data-stu-id="43590-139">When compiled, the code in the previous section's example produces essentially the same executable code as the following example:</span></span>  
  
 <span data-ttu-id="43590-140">[!code-vb[VbXMLSamples #&3;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="43590-140">[!code-vb[VbXMLSamples#3](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_5.vb)]</span></span>  
  
### <a name="using-xml-namespaces-in-xml-axis-properties"></a><span data-ttu-id="43590-141">使用 XML 命名空间中 XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="43590-141">Using XML Namespaces in XML Axis Properties</span></span>  
 <span data-ttu-id="43590-142">XML 文本声明的 XML 命名空间不可用于在 XML 轴属性中使用。</span><span class="sxs-lookup"><span data-stu-id="43590-142">XML namespaces declared in XML literals are not available for use in XML axis properties.</span></span> <span data-ttu-id="43590-143">但是，全局命名空间可以用于 XML 轴属性。</span><span class="sxs-lookup"><span data-stu-id="43590-143">However, global namespaces can be used with the XML axis properties.</span></span> <span data-ttu-id="43590-144">使用冒号分隔 XML 命名空间前缀和本地元素名称。</span><span class="sxs-lookup"><span data-stu-id="43590-144">Use a colon to separate the XML namespace prefix from the local element name.</span></span> <span data-ttu-id="43590-145">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="43590-145">Following is an example:</span></span>  
  
 <span data-ttu-id="43590-146">[!code-vb[VbXMLSamples #&4;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="43590-146">[!code-vb[VbXMLSamples#4](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/overview-of-linq-to-xml_6.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43590-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43590-147">See Also</span></span>  
 <span data-ttu-id="43590-148">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="43590-148">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="43590-149"> [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span><span class="sxs-lookup"><span data-stu-id="43590-149"> [Creating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md) </span></span>  
<span data-ttu-id="43590-150"> [在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md) </span><span class="sxs-lookup"><span data-stu-id="43590-150"> [Accessing XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md) </span></span>  
<span data-ttu-id="43590-151"> [在 Visual Basic 中操作 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span><span class="sxs-lookup"><span data-stu-id="43590-151"> [Manipulating XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)</span></span>
