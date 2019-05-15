---
title: 维护名称-值对 (C#)
ms.date: 07/20/2015
ms.assetid: 7b04b0f1-af64-42eb-8737-83f8861b5915
ms.openlocfilehash: 4577ff032eaf25e519e687a0eea969bf76ca3540
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64596956"
---
# <a name="maintaining-namevalue-pairs-c"></a><span data-ttu-id="59b0a-102">维护名称/值对 (C#)</span><span class="sxs-lookup"><span data-stu-id="59b0a-102">Maintaining Name/Value Pairs (C#)</span></span>
<span data-ttu-id="59b0a-103">很多应用程序都必须维护需要保存为名称/值对的信息。</span><span class="sxs-lookup"><span data-stu-id="59b0a-103">Many applications have to maintain information that is best kept as name/value pairs.</span></span> <span data-ttu-id="59b0a-104">此信息可能是配置信息或全局设置。</span><span class="sxs-lookup"><span data-stu-id="59b0a-104">This information might be configuration information or global settings.</span></span> [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="59b0a-105">包含一些方法，能轻松保存一组名称/值对。</span><span class="sxs-lookup"><span data-stu-id="59b0a-105">contains some methods that make it easy to keep a set of name/value pairs.</span></span> <span data-ttu-id="59b0a-106">可以将这些信息保存为属性，也可以保存为一组子元素。</span><span class="sxs-lookup"><span data-stu-id="59b0a-106">You can either keep the information as attributes or as a set of child elements.</span></span>  
  
 <span data-ttu-id="59b0a-107">将信息保存为属性和保存为子元素之间的区别在于属性具有约束，对于一个元素，只能有一个属性具有特定的名称。</span><span class="sxs-lookup"><span data-stu-id="59b0a-107">One difference between keeping the information as attributes or as child elements is that attributes have the constraint that there can be only one attribute with a particular name for an element.</span></span> <span data-ttu-id="59b0a-108">而这种限制不适用于子元素。</span><span class="sxs-lookup"><span data-stu-id="59b0a-108">This limitation does not apply to child elements.</span></span>  
  
## <a name="setattributevalue-and-setelementvalue"></a><span data-ttu-id="59b0a-109">SetAttributeValue 与 SetElementValue</span><span class="sxs-lookup"><span data-stu-id="59b0a-109">SetAttributeValue and SetElementValue</span></span>  
 <span data-ttu-id="59b0a-110">两种有助于保存名称/值对的方法是 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> 和 <xref:System.Xml.Linq.XElement.SetElementValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="59b0a-110">The two methods that facilitate keeping name/value pairs are <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> and <xref:System.Xml.Linq.XElement.SetElementValue%2A>.</span></span> <span data-ttu-id="59b0a-111">这两种方法具有相似的语义。</span><span class="sxs-lookup"><span data-stu-id="59b0a-111">These two methods have similar semantics.</span></span>  
  
 <span data-ttu-id="59b0a-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> 可以添加、修改或移除元素的属性。</span><span class="sxs-lookup"><span data-stu-id="59b0a-112"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A> can add, modify, or remove attributes of an element.</span></span>  
  
- <span data-ttu-id="59b0a-113">如果使用不存在的属性的名称调用 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>，则该方法会创建一个新属性并将该属性添加到指定的元素中。</span><span class="sxs-lookup"><span data-stu-id="59b0a-113">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an attribute that does not exist, the method creates a new attribute and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="59b0a-114">如果使用现有属性的名称调用 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>，并指定一些内容，则会用指定内容替换属性的内容。</span><span class="sxs-lookup"><span data-stu-id="59b0a-114">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute and with some specified content, the contents of the attribute are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="59b0a-115">如果使用现有属性的名称调用 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>，并指定内容为空，则会从该属性的父级移除该属性。</span><span class="sxs-lookup"><span data-stu-id="59b0a-115">If you call <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> with a name of an existing attribute, and specify null for the content, the attribute is removed from its parent.</span></span>  
  
 <span data-ttu-id="59b0a-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> 可以添加、修改或移除元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="59b0a-116"><xref:System.Xml.Linq.XElement.SetElementValue%2A> can add, modify, or remove child elements of an element.</span></span>  
  
- <span data-ttu-id="59b0a-117">如果使用不存在的子元素的名称调用 <xref:System.Xml.Linq.XElement.SetElementValue%2A>，则该方法会创建一个新元素并将该新元素添加到指定的元素中。</span><span class="sxs-lookup"><span data-stu-id="59b0a-117">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of a child element that does not exist, the method creates a new element and adds it to the specified element.</span></span>  
  
- <span data-ttu-id="59b0a-118">如果使用现有元素的名称调用 <xref:System.Xml.Linq.XElement.SetElementValue%2A>，并指定一些内容，则会用指定内容替换元素的内容。</span><span class="sxs-lookup"><span data-stu-id="59b0a-118">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element and with some specified content, the contents of the element are replaced with the specified content.</span></span>  
  
- <span data-ttu-id="59b0a-119">如果使用现有元素的名称调用 <xref:System.Xml.Linq.XElement.SetElementValue%2A>，并指定内容为空，则会从该元素的父级移除该元素。</span><span class="sxs-lookup"><span data-stu-id="59b0a-119">If you call <xref:System.Xml.Linq.XElement.SetElementValue%2A> with a name of an existing element, and specify null for the content, the element is removed from its parent.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59b0a-120">示例</span><span class="sxs-lookup"><span data-stu-id="59b0a-120">Example</span></span>  
 <span data-ttu-id="59b0a-121">下面的示例创建一个没有属性的元素。</span><span class="sxs-lookup"><span data-stu-id="59b0a-121">The following example creates an element with no attributes.</span></span> <span data-ttu-id="59b0a-122">之后使用 <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> 方法创建一个名称/值对列表并维护该列表。</span><span class="sxs-lookup"><span data-stu-id="59b0a-122">It then uses the <xref:System.Xml.Linq.XElement.SetAttributeValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as attributes.  
root.SetAttributeValue("Top", 22);  
root.SetAttributeValue("Left", 20);  
root.SetAttributeValue("Bottom", 122);  
root.SetAttributeValue("Right", 300);  
root.SetAttributeValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
  
// Replace the value of Top.  
root.SetAttributeValue("Top", 10);  
Console.WriteLine(root);  
  
// Remove DefaultColor.  
root.SetAttributeValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="59b0a-123">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="59b0a-123">This example produces the following output:</span></span>  
  
```xml  
<Root Top="22" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" DefaultColor="Color.Red" />  
<Root Top="10" Left="20" Bottom="122" Right="300" />  
```  
  
## <a name="example"></a><span data-ttu-id="59b0a-124">示例</span><span class="sxs-lookup"><span data-stu-id="59b0a-124">Example</span></span>  
 <span data-ttu-id="59b0a-125">下面的示例创建一个没有子元素的元素。</span><span class="sxs-lookup"><span data-stu-id="59b0a-125">The following example creates an element with no child elements.</span></span> <span data-ttu-id="59b0a-126">之后使用 <xref:System.Xml.Linq.XElement.SetElementValue%2A> 方法创建一个名称/值对列表并维护该列表。</span><span class="sxs-lookup"><span data-stu-id="59b0a-126">It then uses the <xref:System.Xml.Linq.XElement.SetElementValue%2A> method to create and maintain a list of name/value pairs.</span></span>  
  
```csharp  
// Create an element with no content.  
XElement root = new XElement("Root");  
  
// Add a number of name/value pairs as elements.  
root.SetElementValue("Top", 22);  
root.SetElementValue("Left", 20);  
root.SetElementValue("Bottom", 122);  
root.SetElementValue("Right", 300);  
root.SetElementValue("DefaultColor", "Color.Red");  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Replace the value of Top.  
root.SetElementValue("Top", 10);  
Console.WriteLine(root);  
Console.WriteLine("----");  
  
// Remove DefaultColor.  
root.SetElementValue("DefaultColor", null);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="59b0a-127">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="59b0a-127">This example produces the following output:</span></span>  
  
```xml  
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
  
## <a name="see-also"></a><span data-ttu-id="59b0a-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="59b0a-128">See also</span></span>

- <xref:System.Xml.Linq.XElement.SetAttributeValue%2A>
- <xref:System.Xml.Linq.XElement.SetElementValue%2A>
- [<span data-ttu-id="59b0a-129">修改 XML 树 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="59b0a-129">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
