---
title: 在 C# 中创建 XML 树 (LINQ to XML)
ms.date: 08/31/2018
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
ms.openlocfilehash: 3bac7b62d04c9690cdd08d1993b64db33c4e6ab8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54503157"
---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a><span data-ttu-id="581cc-102">在 C# 中创建 XML 树 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="581cc-102">Creating XML trees in C# (LINQ to XML)</span></span>
<span data-ttu-id="581cc-103">本节提供有关使用 C# 来创建 XML 树的信息。</span><span class="sxs-lookup"><span data-stu-id="581cc-103">This section provides information about creating XML trees in C#.</span></span>  
  
 <span data-ttu-id="581cc-104">有关使用 LINQ 查询结果作为 <xref:System.Xml.Linq.XElement> 内容的信息，请参阅[功能构造 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="581cc-104">For information about using the results of LINQ queries as the content for an <xref:System.Xml.Linq.XElement>, see [Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="constructing-elements"></a><span data-ttu-id="581cc-105">构造元素</span><span class="sxs-lookup"><span data-stu-id="581cc-105">Constructing elements</span></span>
 <span data-ttu-id="581cc-106">通过 <xref:System.Xml.Linq.XElement> 和 <xref:System.Xml.Linq.XAttribute> 构造函数的签名，可以将元素或属性的内容作为参数传递到构造函数。</span><span class="sxs-lookup"><span data-stu-id="581cc-106">The signatures of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors let you pass the contents of the element or attribute as arguments to the constructor.</span></span> <span data-ttu-id="581cc-107">由于其中一个构造函数使用可变数目的参数，因此可以传递任意数目的子元素。</span><span class="sxs-lookup"><span data-stu-id="581cc-107">Because one of the constructors takes a variable number of arguments, you can pass any number of child elements.</span></span> <span data-ttu-id="581cc-108">当然，这些子元素中的每一个都可以包含它们自己的子元素。</span><span class="sxs-lookup"><span data-stu-id="581cc-108">Of course, each of those child elements can contain their own child elements.</span></span> <span data-ttu-id="581cc-109">对任意元素，可以添加任意多个属性。</span><span class="sxs-lookup"><span data-stu-id="581cc-109">For any element, you can add any number of attributes.</span></span>  
  
 <span data-ttu-id="581cc-110">在添加 <xref:System.Xml.Linq.XNode>（包括 <xref:System.Xml.Linq.XElement>）或 <xref:System.Xml.Linq.XAttribute> 对象时，如果新内容没有父级，则直接将这些对象附加到 XML 树中。</span><span class="sxs-lookup"><span data-stu-id="581cc-110">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="581cc-111">如果新内容已经有父级，并且是另一 XML 树的一部分，则克隆新内容，并将新克隆的内容附加到 XML 树。</span><span class="sxs-lookup"><span data-stu-id="581cc-111">If the new content already is parented, and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span> <span data-ttu-id="581cc-112">本主题最后一个示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="581cc-112">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="581cc-113">若要创建 `contacts`<xref:System.Xml.Linq.XElement>，可以使用下面的代码：</span><span class="sxs-lookup"><span data-stu-id="581cc-113">To create a `contacts`<xref:System.Xml.Linq.XElement>, you could use the following code:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="581cc-114">如果正确缩进，则构造 <xref:System.Xml.Linq.XElement> 对象的代码十分类似于基础 XML 的结构。</span><span class="sxs-lookup"><span data-stu-id="581cc-114">If indented properly, the code to construct <xref:System.Xml.Linq.XElement> objects closely resembles the structure of the underlying XML.</span></span>  
  
## <a name="xelement-constructors"></a><span data-ttu-id="581cc-115">XElement 构造函数</span><span class="sxs-lookup"><span data-stu-id="581cc-115">XElement constructors</span></span>  
 <span data-ttu-id="581cc-116"><xref:System.Xml.Linq.XElement> 类使用下面的构造函数用于函数构造。</span><span class="sxs-lookup"><span data-stu-id="581cc-116">The <xref:System.Xml.Linq.XElement> class uses the following constructors for functional construction.</span></span> <span data-ttu-id="581cc-117">请注意，对于 <xref:System.Xml.Linq.XElement>，存在其他一些构造函数，但是由于它们不用于函数构造，因此没有在此列出。</span><span class="sxs-lookup"><span data-stu-id="581cc-117">Note that there are some other constructors for <xref:System.Xml.Linq.XElement>, but because they are not used for functional construction they are not listed here.</span></span>  
  
|<span data-ttu-id="581cc-118">构造函数</span><span class="sxs-lookup"><span data-stu-id="581cc-118">Constructor</span></span>|<span data-ttu-id="581cc-119">说明</span><span class="sxs-lookup"><span data-stu-id="581cc-119">Description</span></span>|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|<span data-ttu-id="581cc-120">创建 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="581cc-120">Creates an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="581cc-121">`name` 参数指定元素的名称；`content` 指定元素的内容。</span><span class="sxs-lookup"><span data-stu-id="581cc-121">The `name` parameter specifies the name of the element; `content` specifies the content of the element.</span></span>|  
|`XElement(XName name)`|<span data-ttu-id="581cc-122">创建一个 <xref:System.Xml.Linq.XElement>，其 <xref:System.Xml.Linq.XName> 初始化为指定名称。</span><span class="sxs-lookup"><span data-stu-id="581cc-122">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span>|  
|`XElement(XName name, params object[] content)`|<span data-ttu-id="581cc-123">创建一个 <xref:System.Xml.Linq.XElement>，其 <xref:System.Xml.Linq.XName> 初始化为指定名称。</span><span class="sxs-lookup"><span data-stu-id="581cc-123">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span> <span data-ttu-id="581cc-124">从参数列表的内容创建属性和/或子元素。</span><span class="sxs-lookup"><span data-stu-id="581cc-124">The attributes and/or child elements are created from the contents of the parameter list.</span></span>|  
  
 <span data-ttu-id="581cc-125">`content` 参数极其灵活。</span><span class="sxs-lookup"><span data-stu-id="581cc-125">The `content` parameter is extremely flexible.</span></span> <span data-ttu-id="581cc-126">它支持作为 <xref:System.Xml.Linq.XElement> 的有效子对象的任何类型的对象。</span><span class="sxs-lookup"><span data-stu-id="581cc-126">It supports any type of object that is a valid child of an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="581cc-127">下面的规则适用于在此参数中传递的不同类型的对象：</span><span class="sxs-lookup"><span data-stu-id="581cc-127">The following rules apply to different types of objects passed in this parameter:</span></span>  
  
-   <span data-ttu-id="581cc-128">字符串添加为文本内容。</span><span class="sxs-lookup"><span data-stu-id="581cc-128">A string is added as text content.</span></span>  
  
-   <span data-ttu-id="581cc-129"><xref:System.Xml.Linq.XElement> 添加为子元素。</span><span class="sxs-lookup"><span data-stu-id="581cc-129">An <xref:System.Xml.Linq.XElement> is added as a child element.</span></span>  
  
-   <span data-ttu-id="581cc-130"><xref:System.Xml.Linq.XAttribute> 添加为属性。</span><span class="sxs-lookup"><span data-stu-id="581cc-130">An <xref:System.Xml.Linq.XAttribute> is added as an attribute.</span></span>  
  
-   <span data-ttu-id="581cc-131"><xref:System.Xml.Linq.XProcessingInstruction>、<xref:System.Xml.Linq.XComment> 或 <xref:System.Xml.Linq.XText> 添加为子内容。</span><span class="sxs-lookup"><span data-stu-id="581cc-131">An <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, or <xref:System.Xml.Linq.XText> is added as child content.</span></span>  
  
-   <span data-ttu-id="581cc-132">枚举 <xref:System.Collections.IEnumerable>，并且这些规则递归应用于结果。</span><span class="sxs-lookup"><span data-stu-id="581cc-132">An <xref:System.Collections.IEnumerable> is enumerated, and these rules are applied recursively to the results.</span></span>  
  
-   <span data-ttu-id="581cc-133">对任何其他类型，调用其 `ToString` 方法，结果添加为文本内容。</span><span class="sxs-lookup"><span data-stu-id="581cc-133">For any other type, its `ToString` method is called and the result is added as text content.</span></span>  
  
### <a name="creating-an-xelement-with-content"></a><span data-ttu-id="581cc-134">创建包含内容的 XElement</span><span class="sxs-lookup"><span data-stu-id="581cc-134">Creating an XElement with content</span></span>  
 <span data-ttu-id="581cc-135">可以使用单个方法调用来创建一个包含简单内容的 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="581cc-135">You can create an <xref:System.Xml.Linq.XElement> that contains simple content with a single method call.</span></span> <span data-ttu-id="581cc-136">为此，请指定内容作为第二个参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="581cc-136">To do this, specify the content as the second parameter, as follows:</span></span>  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="581cc-137">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="581cc-137">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 <span data-ttu-id="581cc-138">可以将任意类型的对象作为内容进行传递。</span><span class="sxs-lookup"><span data-stu-id="581cc-138">You can pass any type of object as the content.</span></span> <span data-ttu-id="581cc-139">例如，下面的代码创建一个包含浮点数作为内容的元素：</span><span class="sxs-lookup"><span data-stu-id="581cc-139">For example, the following code creates an element that contains a floating point number as content:</span></span>  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="581cc-140">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="581cc-140">This example produces the following output:</span></span>  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 <span data-ttu-id="581cc-141">该浮点数被装箱并传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="581cc-141">The floating point number is boxed and passed in to the constructor.</span></span> <span data-ttu-id="581cc-142">装箱的数字转换为字符串，然后用作元素的内容。</span><span class="sxs-lookup"><span data-stu-id="581cc-142">The boxed number is converted to a string and used as the content of the element.</span></span>  
  
### <a name="creating-an-xelement-with-a-child-element"></a><span data-ttu-id="581cc-143">创建具有子元素的 XElement</span><span class="sxs-lookup"><span data-stu-id="581cc-143">Creating an XElement with a child element</span></span>  
 <span data-ttu-id="581cc-144">如果传递 <xref:System.Xml.Linq.XElement> 类的一个实例作为内容参数，则构造函数将创建一个具有子元素的元素：</span><span class="sxs-lookup"><span data-stu-id="581cc-144">If you pass an instance of the <xref:System.Xml.Linq.XElement> class for the content argument, the constructor creates an element with a child element:</span></span>  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 <span data-ttu-id="581cc-145">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="581cc-145">This example produces the following output:</span></span>  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a><span data-ttu-id="581cc-146">创建具有多个子元素的 XElement</span><span class="sxs-lookup"><span data-stu-id="581cc-146">Creating an XElement with multiple child elements</span></span>  
 <span data-ttu-id="581cc-147">可以传递多个 <xref:System.Xml.Linq.XElement> 对象作为内容。</span><span class="sxs-lookup"><span data-stu-id="581cc-147">You can pass in a number of <xref:System.Xml.Linq.XElement> objects for the content.</span></span> <span data-ttu-id="581cc-148">每个 <xref:System.Xml.Linq.XElement> 对象都作为子元素包含进来。</span><span class="sxs-lookup"><span data-stu-id="581cc-148">Each of the <xref:System.Xml.Linq.XElement> objects is included as a child element.</span></span>  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 <span data-ttu-id="581cc-149">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="581cc-149">This example produces the following output:</span></span>  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 <span data-ttu-id="581cc-150">将上面的示例进行扩展，可以创建整个 XML 树，如下所示：</span><span class="sxs-lookup"><span data-stu-id="581cc-150">By extending the above example, you can create an entire XML tree, as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),                                                   
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
Console.WriteLine(contacts);  
```  
  
 <span data-ttu-id="581cc-151">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="581cc-151">This example produces the following output:</span></span>  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  

### <a name="creating-an-xelement-with-an-xattribute"></a><span data-ttu-id="581cc-152">创建具有 XAttribute 的 XElement</span><span class="sxs-lookup"><span data-stu-id="581cc-152">Creating an XElement with an XAttribute</span></span>
 <span data-ttu-id="581cc-153">如果传递 <xref:System.Xml.Linq.XAttribute> 类的一个实例作为内容参数，则构造函数将创建一个具有属性的元素：</span><span class="sxs-lookup"><span data-stu-id="581cc-153">If you pass an instance of the <xref:System.Xml.Linq.XAttribute> class for the content argument, the constructor creates an element with an attribute:</span></span>

```csharp  
XElement phone = new XElement("Phone",  
    new XAttribute("Type", "Home"),  
    "555-555-5555");  
Console.WriteLine(phone);  
```  
  
 <span data-ttu-id="581cc-154">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="581cc-154">This example produces the following output:</span></span>  
  
```xml  
<Phone Type="Home">555-555-5555</Phone>
```   

### <a name="creating-an-empty-element"></a><span data-ttu-id="581cc-155">创建空元素</span><span class="sxs-lookup"><span data-stu-id="581cc-155">Creating an empty element</span></span>  
 <span data-ttu-id="581cc-156">若要创建空 <xref:System.Xml.Linq.XElement>，请不要将任何内容传递给构造函数。</span><span class="sxs-lookup"><span data-stu-id="581cc-156">To create an empty <xref:System.Xml.Linq.XElement>, you do not pass any content to the constructor.</span></span> <span data-ttu-id="581cc-157">下面的示例创建一个空元素：</span><span class="sxs-lookup"><span data-stu-id="581cc-157">The following example creates an empty element:</span></span>  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="581cc-158">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="581cc-158">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a><span data-ttu-id="581cc-159">附加与克隆</span><span class="sxs-lookup"><span data-stu-id="581cc-159">Attaching vs. cloning</span></span>  
 <span data-ttu-id="581cc-160">前面提到，在添加 <xref:System.Xml.Linq.XNode>（包括 <xref:System.Xml.Linq.XElement>）或 <xref:System.Xml.Linq.XAttribute> 对象时，如果新内容没有父级，则直接将这些对象附加到 XML 树。</span><span class="sxs-lookup"><span data-stu-id="581cc-160">As mentioned previously, when adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="581cc-161">如果新内容已经有父级，并且是另一 XML 树的一部分，则克隆新内容，并将新克隆的内容附加到 XML 树。</span><span class="sxs-lookup"><span data-stu-id="581cc-161">If the new content already is parented and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  

<span data-ttu-id="581cc-162">以下示例演示将有父级的元素添加到树中，以及将没有父级的元素添加到树中时的行为。</span><span class="sxs-lookup"><span data-stu-id="581cc-162">The following example demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>

```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  

// The example displays the following output:  
//    Child1 was cloned  
//    Child2 was attached  
```

## <a name="see-also"></a><span data-ttu-id="581cc-163">请参阅</span><span class="sxs-lookup"><span data-stu-id="581cc-163">See also</span></span>

- [<span data-ttu-id="581cc-164">创建 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="581cc-164">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
