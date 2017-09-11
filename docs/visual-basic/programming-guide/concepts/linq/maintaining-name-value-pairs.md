---
title: "维护名称 / 值对 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 57ac2072-d9f5-432b-84f0-a889c62fd813
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 30e40c73430f385815b7a08a2507343db0fafd4f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="maintaining-namevalue-pairs-visual-basic"></a><span data-ttu-id="6e31e-102">维护名称/值对 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6e31e-102">Maintaining Name/Value Pairs (Visual Basic)</span></span>
<span data-ttu-id="6e31e-103">很多应用程序都必须维护需要保存为名称/值对的信息。</span><span class="sxs-lookup"><span data-stu-id="6e31e-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="6e31e-104">此信息可能是配置信息或全局设置。</span><span class="sxs-lookup"><span data-stu-id="6e31e-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="6e31e-105"> 包含一些方法，能轻松保存一组名称/值对。</span><span class="sxs-lookup"><span data-stu-id="6e31e-105"> contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="6e31e-106">可以将这些信息保存为属性，也可以保存为一组子元素。</span><span class="sxs-lookup"><span data-stu-id="6e31e-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="6e31e-107">将信息保存为属性和保存为子元素之间的区别在于属性具有约束，对于一个元素，只能有一个属性具有特定的名称。</span><span class="sxs-lookup"><span data-stu-id="6e31e-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="6e31e-108">而这种限制不适用于子元素。</span><span class="sxs-lookup"><span data-stu-id="6e31e-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="6e31e-109">SetAttributeValue 与 SetElementValue</span><span class="sxs-lookup"><span data-stu-id="6e31e-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="6e31e-110">两种方法中有助于保存名称/值对是<xref:System.Xml.Linq.XElement.SetAttributeValue%2A>和<xref:System.Xml.Linq.XElement.SetElementValue%2A>。</xref:System.Xml.Linq.XElement.SetElementValue%2A> </xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="6e31e-111">这两种方法具有相似的语义。</span><span class="sxs-lookup"><span data-stu-id="6e31e-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="6e31e-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A>可以添加、 修改或删除元素的属性。</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
-   <span data-ttu-id="6e31e-113">如果调用<xref:System.Xml.Linq.XElement.SetAttributeValue%2A>具有不存在的属性名称，该方法创建新的属性并将其添加到指定的元素。</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="6e31e-114">如果调用<xref:System.Xml.Linq.XElement.SetAttributeValue%2A>现有属性的名称，并指定一些内容，该属性的内容会用替换为指定的内容。</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="6e31e-115">如果调用<xref:System.Xml.Linq.XElement.SetAttributeValue%2A>对现有的同名属性，并指定内容为空，则移除该属性从其父级。</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="6e31e-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A>可以添加、 修改或删除元素的子元素。</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
-   <span data-ttu-id="6e31e-117">如果调用<xref:System.Xml.Linq.XElement.SetElementValue%2A>与不存在的子元素的名称，该方法创建一个新元素，并将其添加到指定的元素。</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
-   <span data-ttu-id="6e31e-118">如果调用<xref:System.Xml.Linq.XElement.SetElementValue%2A>现有元素的名称，并指定一些内容，该元素的内容会用替换为指定的内容。</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
-   <span data-ttu-id="6e31e-119">如果调用<xref:System.Xml.Linq.XElement.SetElementValue%2A>了一个名为现有的元素，并指定内容为空，从其父级中移除该元素。</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e31e-120">示例</span><span class="sxs-lookup"><span data-stu-id="6e31e-120">Example</span></span>  
 <span data-ttu-id="6e31e-121">下面的示例创建一个没有属性的元素。</span><span class="sxs-lookup"><span data-stu-id="6e31e-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="6e31e-122">然后，它使用<xref:System.Xml.Linq.XElement.SetAttributeValue%2A>方法来创建和维护名称/值对的列表。</xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22)  
root.SetAttributeValue("Left", 20)  
root.SetAttributeValue("Bottom", 122)  
root.SetAttributeValue("Right", 300)  
root.SetAttributeValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
  
' Replace the value of Top.  
root.SetAttributeValue("Top", 10)  
Console.WriteLine(root)  
  
' Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="6e31e-123">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="6e31e-123">This example produces the following output:</span></span>  
  
```  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="6e31e-124">示例</span><span class="sxs-lookup"><span data-stu-id="6e31e-124">Example</span></span>  
 <span data-ttu-id="6e31e-125">下面的示例创建一个没有子元素的元素。</span><span class="sxs-lookup"><span data-stu-id="6e31e-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="6e31e-126">然后，它使用<xref:System.Xml.Linq.XElement.SetElementValue%2A>方法来创建和维护名称/值对的列表。</xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```vb  
' Create an element with no content.  
Dim root As XElement = <Root/>  
  
' Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22)  
root.SetElementValue("Left", 20)  
root.SetElementValue("Bottom", 122)  
root.SetElementValue("Right", 300)  
root.SetElementValue("DefaultColor", "Color.Red")  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Replace the value of Top.  
root.SetElementValue("Top", 10)  
Console.WriteLine(root)  
Console.WriteLine("----")  
  
' Remove DefaultColor.  
root.SetElementValue("DefaultColor", Nothing)  
Console.WriteLine(root)  
  
```  
  
 <span data-ttu-id="6e31e-127">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="6e31e-127">This example produces the following output:</span></span>  
  
```  
<Root>  
  <Top>22</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
  <DefaultColor>Color.Red</DefaultColor>  
</Root>  
----  
<Root>  
  <Top>10</Top>  
  <Left>20</Left>  
  <Bottom>122</Bottom>  
  <Right>300</Right>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="6e31e-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e31e-128">See Also</span></span>  
 <span data-ttu-id="6e31e-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-129"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A></span></span>   
 <span data-ttu-id="6e31e-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></xref:System.Xml.Linq.XElement.SetElementValue%2A></span><span class="sxs-lookup"><span data-stu-id="6e31e-130"><xref:System.Xml.Linq.XElement.SetElementValue%2A></span></span>   
<span data-ttu-id="6e31e-131"> [修改 XML 树 (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span><span class="sxs-lookup"><span data-stu-id="6e31e-131"> [Modifying XML Trees (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)</span></span>
