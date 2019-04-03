---
title: XAttribute 类概述 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 7781580a-9583-4a1b-ae1e-91c5936eb0b1
ms.openlocfilehash: 6b24f429a69067f6af1a61efe4102a5638db3031
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836111"
---
# <a name="xattribute-class-overview-visual-basic"></a><span data-ttu-id="fea53-102">XAttribute 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fea53-102">XAttribute Class Overview (Visual Basic)</span></span>
<span data-ttu-id="fea53-103">属性是与元素关联的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="fea53-103">Attributes are name/value pairs that are associated with an element.</span></span> <span data-ttu-id="fea53-104"><xref:System.Xml.Linq.XAttribute> 类表示 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="fea53-104">The <xref:System.Xml.Linq.XAttribute> class represents XML attributes.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="fea53-105">概述</span><span class="sxs-lookup"><span data-stu-id="fea53-105">Overview</span></span>  
 <span data-ttu-id="fea53-106">使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 中的属性，与使用元素非常相似。</span><span class="sxs-lookup"><span data-stu-id="fea53-106">Working with attributes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] is similar to working with elements.</span></span> <span data-ttu-id="fea53-107">它们的构造函数相似。</span><span class="sxs-lookup"><span data-stu-id="fea53-107">Their constructors are similar.</span></span> <span data-ttu-id="fea53-108">用于检索它们的集合的方法相似。</span><span class="sxs-lookup"><span data-stu-id="fea53-108">The methods that you use to retrieve collections of them are similar.</span></span> <span data-ttu-id="fea53-109">属性集合的 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式与元素集合的 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 查询表达式看起来非常相似。</span><span class="sxs-lookup"><span data-stu-id="fea53-109">A [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of attributes looks very similar to a [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expression for a collection of elements.</span></span>  
  
 <span data-ttu-id="fea53-110">将属性添加到元素中的顺序会保留下来。</span><span class="sxs-lookup"><span data-stu-id="fea53-110">The order in which attributes were added to an element is preserved.</span></span> <span data-ttu-id="fea53-111">也就是说，当循环访问属性时，所见到的属性顺序与它们的添加顺序相同。</span><span class="sxs-lookup"><span data-stu-id="fea53-111">That is, when you iterate through the attributes, you see them in the same order that they were added.</span></span>  
  
## <a name="the-xattribute-constructor"></a><span data-ttu-id="fea53-112">XAttribute 构造函数</span><span class="sxs-lookup"><span data-stu-id="fea53-112">The XAttribute Constructor</span></span>  
 <span data-ttu-id="fea53-113">下面的 <xref:System.Xml.Linq.XAttribute> 类构造函数是您将最常使用的构造函数之一：</span><span class="sxs-lookup"><span data-stu-id="fea53-113">The following constructor of the <xref:System.Xml.Linq.XAttribute> class is the one that you will most commonly use:</span></span>  
  
|<span data-ttu-id="fea53-114">构造函数</span><span class="sxs-lookup"><span data-stu-id="fea53-114">Constructor</span></span>|<span data-ttu-id="fea53-115">描述</span><span class="sxs-lookup"><span data-stu-id="fea53-115">Description</span></span>|  
|-----------------|-----------------|  
|`XAttribute(XName name, object content)`|<span data-ttu-id="fea53-116">创建一个 <xref:System.Xml.Linq.XAttribute> 对象。</span><span class="sxs-lookup"><span data-stu-id="fea53-116">Creates an <xref:System.Xml.Linq.XAttribute> object.</span></span> <span data-ttu-id="fea53-117">`name` 参数指定属性的名称；`content` 指定属性的内容。</span><span class="sxs-lookup"><span data-stu-id="fea53-117">The `name` argument specifies the name of the attribute; `content` specifies the content of the attribute.</span></span>|  
  
### <a name="creating-an-element-with-an-attribute"></a><span data-ttu-id="fea53-118">创建具有属性的元素</span><span class="sxs-lookup"><span data-stu-id="fea53-118">Creating an Element with an Attribute</span></span>  
 <span data-ttu-id="fea53-119">下面的代码演示一个包含 Visual Basic 中使用 XML 文本的属性的元素：</span><span class="sxs-lookup"><span data-stu-id="fea53-119">The following code shows an element that contains an attribute using XML literals in Visual Basic:</span></span>  
  
```vb  
Dim phone As XElement = <Phone Type="Home">555-555-5555</Phone>  
Console.WriteLine(phone)  
```  
  
 <span data-ttu-id="fea53-120">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="fea53-120">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>  
```  
  
### <a name="functional-construction-of-attributes"></a><span data-ttu-id="fea53-121">属性的函数构造</span><span class="sxs-lookup"><span data-stu-id="fea53-121">Functional Construction of Attributes</span></span>  
 <span data-ttu-id="fea53-122">可以构造与 <xref:System.Xml.Linq.XAttribute> 对象的构造一致的 <xref:System.Xml.Linq.XElement> 对象，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fea53-122">You can construct <xref:System.Xml.Linq.XAttribute> objects in-line with the construction of <xref:System.Xml.Linq.XElement> objects, as follows:</span></span>  
  
```vb  
Dim c As XElement = _  
    <Customers>  
        <Customer>  
            <Name>John Doe</Name>  
            <PhoneNumbers>  
                <Phone type="home">555-555-5555</Phone>  
                <Phone type="work">666-666-6666</Phone>  
            </PhoneNumbers>  
        </Customer>  
    </Customers>  
Console.WriteLine(c)  
```  
  
 <span data-ttu-id="fea53-123">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="fea53-123">This example produces the following output:</span></span>  
  
```xml  
<Customers>  
  <Customer>  
    <Name>John Doe</Name>  
    <PhoneNumbers>  
      <Phone type="home">555-555-5555</Phone>  
      <Phone type="work">666-666-6666</Phone>  
    </PhoneNumbers>  
  </Customer>  
</Customers>  
```  
  
### <a name="attributes-are-not-nodes"></a><span data-ttu-id="fea53-124">属性不是节点</span><span class="sxs-lookup"><span data-stu-id="fea53-124">Attributes Are Not Nodes</span></span>  
 <span data-ttu-id="fea53-125">属性与元素之间有些区别。</span><span class="sxs-lookup"><span data-stu-id="fea53-125">There are some differences between attributes and elements.</span></span> <span data-ttu-id="fea53-126"><xref:System.Xml.Linq.XAttribute> 对象不是 XML 树中的节点。</span><span class="sxs-lookup"><span data-stu-id="fea53-126"><xref:System.Xml.Linq.XAttribute> objects are not nodes in the XML tree.</span></span> <span data-ttu-id="fea53-127">它们是与 XML 元素关联的名称/值对。</span><span class="sxs-lookup"><span data-stu-id="fea53-127">They are name/value pairs associated with an XML element.</span></span> <span data-ttu-id="fea53-128">与文档对象模型 (DOM) 相比，这更加贴切地反映了 XML 结构。</span><span class="sxs-lookup"><span data-stu-id="fea53-128">In contrast to the Document Object Model (DOM), this more closely reflects the structure of XML.</span></span> <span data-ttu-id="fea53-129">虽然 <xref:System.Xml.Linq.XAttribute> 对象实际上不是 XML 树的节点，但使用 <xref:System.Xml.Linq.XAttribute> 对象与使用 <xref:System.Xml.Linq.XElement> 对象非常相似。</span><span class="sxs-lookup"><span data-stu-id="fea53-129">Although <xref:System.Xml.Linq.XAttribute> objects are not actually nodes in the XML tree, working with <xref:System.Xml.Linq.XAttribute> objects is very similar to working with <xref:System.Xml.Linq.XElement> objects.</span></span>  
  
 <span data-ttu-id="fea53-130">这一区别仅对编写在节点级使用 XML 树的代码的开发人员特别重要。</span><span class="sxs-lookup"><span data-stu-id="fea53-130">This distinction is primarily important only to developers who are writing code that works with XML trees at the node level.</span></span> <span data-ttu-id="fea53-131">许多开发人员不会关心这种区别。</span><span class="sxs-lookup"><span data-stu-id="fea53-131">Many developers will not be concerned with this distinction.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fea53-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="fea53-132">See also</span></span>

- [<span data-ttu-id="fea53-133">LINQ to XML 编程概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fea53-133">LINQ to XML Programming Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-programming-overview.md)
