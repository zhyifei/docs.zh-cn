---
title: 如何：使用批注以 XSLT 样式转换 LINQ to XML 树 (C#)
ms.date: 07/20/2015
ms.assetid: 12a95902-a6b7-4a1e-ad52-04a518db226f
ms.openlocfilehash: 13b65b5b4e1926910ad68204fdffffd7020f07f2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43864347"
---
# <a name="how-to-use-annotations-to-transform-linq-to-xml-trees-in-an-xslt-style-c"></a><span data-ttu-id="90df6-102">如何：使用批注以 XSLT 样式转换 LINQ to XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="90df6-102">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (C#)</span></span>
<span data-ttu-id="90df6-103">使用批注可帮助进行 XML 树的转换。</span><span class="sxs-lookup"><span data-stu-id="90df6-103">Annotations can be used to facilitate transforms of an XML tree.</span></span>  
  
 <span data-ttu-id="90df6-104">有些 XML 文档“以文档为中心兼有混合内容”。</span><span class="sxs-lookup"><span data-stu-id="90df6-104">Some XML documents are "document centric with mixed content."</span></span> <span data-ttu-id="90df6-105">对于这样的文档，您不必知道元素的子节点的形状。</span><span class="sxs-lookup"><span data-stu-id="90df6-105">With such documents, you don't necessarily know the shape of child nodes of an element.</span></span> <span data-ttu-id="90df6-106">例如，包含文本的节点可能具有像下面这样的外观：</span><span class="sxs-lookup"><span data-stu-id="90df6-106">For instance, a node that contains text may look like this:</span></span>  
  
```xml  
<text>A phrase with <b>bold</b> and <i>italic</i> text.</text>  
```  
  
 <span data-ttu-id="90df6-107">任何给定的文本节点都可以具有任意数量的子 `<b>` 和 `<i>` 元素。</span><span class="sxs-lookup"><span data-stu-id="90df6-107">For any given text node, there may be any number of child `<b>` and `<i>` elements.</span></span> <span data-ttu-id="90df6-108">此方法可扩展到很多其他情况：如页面可以包含各种子元素（如规则段落、带项目符号的段落和位图）。</span><span class="sxs-lookup"><span data-stu-id="90df6-108">This approach extends to a number of other situations, such as pages that can contain a variety of child elements, such as regular paragraphs, bulleted paragraphs, and bitmaps.</span></span> <span data-ttu-id="90df6-109">表中的单元格可以包含文本，下拉列表或位图。</span><span class="sxs-lookup"><span data-stu-id="90df6-109">Cells in a table may contain text, drop down lists, or bitmaps.</span></span> <span data-ttu-id="90df6-110">以文档为中心的 XML 的一个主要特性是您不必知道任一特定元素将具有哪些子元素。</span><span class="sxs-lookup"><span data-stu-id="90df6-110">One of the primary characteristics of document centric XML is that you do not know which child element any particular element will have.</span></span>  
  
 <span data-ttu-id="90df6-111">如果在转换树中的元素时不必知道有关要转换元素的子级的太多信息，则这种方法（使用批注）就是一种有效的方法。</span><span class="sxs-lookup"><span data-stu-id="90df6-111">If you want to transform elements in a tree where you don't necessarily know much about the children of the elements that you want to transform, then this approach that uses annotations is an effective approach.</span></span>  
  
 <span data-ttu-id="90df6-112">这种方法摘要如下：</span><span class="sxs-lookup"><span data-stu-id="90df6-112">The summary of the approach is:</span></span>  
  
-   <span data-ttu-id="90df6-113">首先，用替换元素批注树中的元素。</span><span class="sxs-lookup"><span data-stu-id="90df6-113">First, annotate elements in the tree with a replacement element.</span></span>  
  
-   <span data-ttu-id="90df6-114">然后，循环访问整个树，创建一个新树，并用其批注替换树中的每个元素。</span><span class="sxs-lookup"><span data-stu-id="90df6-114">Second, iterate through the entire tree, creating a new tree where you replace each element with its annotation.</span></span> <span data-ttu-id="90df6-115">本示例在名为 `XForm` 的函数中实现迭代和创建新树。</span><span class="sxs-lookup"><span data-stu-id="90df6-115">This example implements the iteration and creation of the new tree in a function named `XForm`.</span></span>  
  
 <span data-ttu-id="90df6-116">具体地说，此方法包括：</span><span class="sxs-lookup"><span data-stu-id="90df6-116">In detail, the approach consists of:</span></span>  
  
-   <span data-ttu-id="90df6-117">执行一个或多个 LINQ to XML 查询，用这些查询返回要从一种形状转换为另一种形状的元素集。</span><span class="sxs-lookup"><span data-stu-id="90df6-117">Execute one or more LINQ to XML queries that return the set of elements that you want to transform from one shape to another.</span></span> <span data-ttu-id="90df6-118">对于查询中的每个元素，添加一个新 <xref:System.Xml.Linq.XElement> 对象作为该元素的批注。</span><span class="sxs-lookup"><span data-stu-id="90df6-118">For each element in the query, add a new <xref:System.Xml.Linq.XElement> object as an annotation to the element.</span></span> <span data-ttu-id="90df6-119">在转换的新树中会用此新元素替换批注的元素。</span><span class="sxs-lookup"><span data-stu-id="90df6-119">This new element will replace the annotated element in the new, transformed tree.</span></span> <span data-ttu-id="90df6-120">这是示例中所示的唯一需要编写的代码。</span><span class="sxs-lookup"><span data-stu-id="90df6-120">This is simple code to write, as demonstrated by the example.</span></span>  
  
-   <span data-ttu-id="90df6-121">作为批注添加的新元素可以包含新的子节点，它可以形成一个具有任意形状的子树。</span><span class="sxs-lookup"><span data-stu-id="90df6-121">The new element that is added as an annotation can contain new child nodes; it can form a sub-tree with any desired shape.</span></span>  
  
-   <span data-ttu-id="90df6-122">有一条特殊规则：如果新元素的子节点位于不同的命名空间，即专门为此建立的命名空间（在本示例中，此命名空间为 `http://www.microsoft.com/LinqToXmlTransform/2007`），则不会将该子元素复制到新树。</span><span class="sxs-lookup"><span data-stu-id="90df6-122">There is a special rule: If a child node of the new element is in a different namespace, a namespace that is made up for this purpose (in this example, the namespace is `http://www.microsoft.com/LinqToXmlTransform/2007`), then that child element is not copied to the new tree.</span></span> <span data-ttu-id="90df6-123">而如果命名空间是上面提到的特殊命名空间，并且元素的本地名称为 `ApplyTransforms`，则会迭代源树中该元素的子节点并将其复制到新树（但批注的子元素本身例外，它们将根据这些规则进行转换）。</span><span class="sxs-lookup"><span data-stu-id="90df6-123">Instead, if the namespace is the above mentioned special namespace, and the local name of the element is `ApplyTransforms`, then the child nodes of the element in the source tree are iterated, and copied to the new tree (with the exception that annotated child elements are themselves transformed according to these rules).</span></span>  
  
-   <span data-ttu-id="90df6-124">这有些类似于 XSL 中的转换规范。</span><span class="sxs-lookup"><span data-stu-id="90df6-124">This is somewhat analogous to the specification of transforms in XSL.</span></span> <span data-ttu-id="90df6-125">用于选择一组节点的查询类似于用于模板的 XPath 表达式。</span><span class="sxs-lookup"><span data-stu-id="90df6-125">The query that selects a set of nodes is analogous to the XPath expression for a template.</span></span> <span data-ttu-id="90df6-126">用于创建以批注形式保存的新 <xref:System.Xml.Linq.XElement> 的代码类似于 XSL 中的序列构造函数，`ApplyTransforms` 元素的功能类似于 XSL 中的 `xsl:apply-templates` 元素。</span><span class="sxs-lookup"><span data-stu-id="90df6-126">The code to create the new <xref:System.Xml.Linq.XElement> that is saved as an annotation is analogous to the sequence constructor in XSL, and the `ApplyTransforms` element is analogous in function to the `xsl:apply-templates` element in XSL.</span></span>  
  
-   <span data-ttu-id="90df6-127">采用此方法的优势之一是在用公式表述查询时，您始终是对未修改的源树编写查询。</span><span class="sxs-lookup"><span data-stu-id="90df6-127">One advantage to taking this approach - as you formulate queries, you are always writing queries on the unmodified source tree.</span></span> <span data-ttu-id="90df6-128">您不必担心对树所做的修改如何影响要编写的查询。</span><span class="sxs-lookup"><span data-stu-id="90df6-128">You need not worry about how modifications to the tree affect the queries that you are writing.</span></span>  
  
## <a name="transforming-a-tree"></a><span data-ttu-id="90df6-129">转换一个树</span><span class="sxs-lookup"><span data-stu-id="90df6-129">Transforming a Tree</span></span>  
 <span data-ttu-id="90df6-130">下面的第一个示例将所有 `Paragraph` 节点重命名为 `para`。</span><span class="sxs-lookup"><span data-stu-id="90df6-130">This first example renames all `Paragraph` nodes to `para`.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement root = XElement.Parse(@"  
<Root>  
    <Paragraph>This is a sentence with <b>bold</b> and <i>italic</i> text.</Paragraph>  
    <Paragraph>More text.</Paragraph>  
</Root>");  
  
// replace Paragraph with para  
foreach (var el in root.Descendants("Paragraph"))  
    el.AddAnnotation(  
        new XElement("para",  
            // same idea as xsl:apply-templates  
            new XElement(xf + "ApplyTransforms")  
        )  
    );  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newRoot = XForm(root);  
  
Console.WriteLine(newRoot);  
```  
  
 <span data-ttu-id="90df6-131">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="90df6-131">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <para>This is a sentence with <b>bold</b> and <i>italic</i> text.</para>  
  <para>More text.</para>  
</Root>  
```  
  
## <a name="a-more-complicated-transform"></a><span data-ttu-id="90df6-132">更复杂的转换</span><span class="sxs-lookup"><span data-stu-id="90df6-132">A More Complicated Transform</span></span>  
 <span data-ttu-id="90df6-133">下面的示例对树进行查询并计算 `Data` 元素的平均值和总和，并将它们作为新元素添加到树中。</span><span class="sxs-lookup"><span data-stu-id="90df6-133">The following example queries the tree and calculates the average and sum of the `Data` elements, and adds them as new elements to the tree.</span></span>  
  
```csharp  
XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
XName at = xf + "ApplyTransforms";  
  
XElement data = new XElement("Root",  
    new XElement("Data", 20),  
    new XElement("Data", 10),  
    new XElement("Data", 3)  
);  
  
// while adding annotations, you can query the source tree all you want,  
// as the tree is not mutated while annotating.  
data.AddAnnotation(  
    new XElement("Root",  
        new XElement(xf + "ApplyTransforms"),  
        new XElement("Average",  
            String.Format("{0:F4}",  
                data  
                .Elements("Data")  
                .Select(z => (Decimal)z)  
                .Average()  
            )  
        ),  
        new XElement("Sum",  
            data  
            .Elements("Data")  
            .Select(z => (int)z)  
            .Sum()  
        )  
    )  
);  
  
Console.WriteLine("Before Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(data);  
Console.WriteLine();  
Console.WriteLine();  
  
// The XForm method, shown later in this topic, accomplishes the transform  
XElement newData = XForm(data);  
  
Console.WriteLine("After Transform");  
Console.WriteLine("----------------");  
Console.WriteLine(newData);  
```  
  
 <span data-ttu-id="90df6-134">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="90df6-134">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
</Root>  
  
After Transform  
----------------  
<Root>  
  <Data>20</Data>  
  <Data>10</Data>  
  <Data>3</Data>  
  <Average>11.0000</Average>  
  <Sum>33</Sum>  
</Root>  
```  
  
## <a name="effecting-the-transform"></a><span data-ttu-id="90df6-135">实施转换</span><span class="sxs-lookup"><span data-stu-id="90df6-135">Effecting the Transform</span></span>  
 <span data-ttu-id="90df6-136">小函数 `XForm` 可以从原始的、已批注的树创建新的、转换后的树。</span><span class="sxs-lookup"><span data-stu-id="90df6-136">A small function, `XForm`, creates a new transformed tree from the original, annotated tree.</span></span>  
  
-   <span data-ttu-id="90df6-137">该函数的伪代码非常简单：</span><span class="sxs-lookup"><span data-stu-id="90df6-137">The pseudo code for the function is quite simple:</span></span>  
  
```  
The function takes an XElement as an argument and returns an XElement.   
If an element has an XElement annotation, then  
    Return a new XElement  
        The name of the new XElement is the annotation element's name.  
        All attributes are copied from the annotation to the new node.  
        All child nodes are copied from the annotation, with the  
            exception that the special node xf:ApplyTransforms is  
            recognized, and the source element's child nodes are  
            iterated. If the source child node is not an XElement, it  
            is copied to the new tree. If the source child is an  
            XElement, then it is transformed by calling this function  
            recursively.  
If an element is not annotated  
    Return a new XElement  
        The name of the new XElement is the source element's name  
        All attributes are copied from the source element to the  
            destination's element.  
        All child nodes are copied from the source element.  
        If the source child node is not an XElement, it is copied to  
            the new tree. If the source child is an XElement, then it  
            is transformed by calling this function recursively.  
```  
  
 <span data-ttu-id="90df6-138">下面是此函数的实现：</span><span class="sxs-lookup"><span data-stu-id="90df6-138">Following is the implementation of this function:</span></span>  
  
```csharp  
// Build a transformed XML tree per the annotations  
static XElement XForm(XElement source)  
{  
    XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    XName at = xf + "ApplyTransforms";  
  
    if (source.Annotation<XElement>() != null)  
    {  
        XElement anno = source.Annotation<XElement>();  
        return new XElement(anno.Name,  
            anno.Attributes(),  
            anno  
            .Nodes()  
            .Select(  
                (XNode n) =>  
                {  
                    XElement annoEl = n as XElement;  
                    if (annoEl != null)  
                    {  
                        if (annoEl.Name == at)  
                            return (object)(  
                                source.Nodes()  
                                .Select(  
                                    (XNode n2) =>  
                                    {  
                                        XElement e2 = n2 as XElement;  
                                        if (e2 == null)  
                                            return n2;  
                                        else  
                                            return XForm(e2);  
                                    }  
                                )  
                            );  
                        else  
                            return n;  
                    }  
                    else  
                        return n;  
                }  
            )  
        );  
    }  
    else  
    {  
        return new XElement(source.Name,  
            source.Attributes(),  
            source  
                .Nodes()  
                .Select(n =>  
                {  
                    XElement el = n as XElement;  
                    if (el == null)  
                        return n;  
                    else  
                        return XForm(el);  
                }  
                )  
        );  
    }  
}   
```  
  
## <a name="complete-example"></a><span data-ttu-id="90df6-139">完整的示例</span><span class="sxs-lookup"><span data-stu-id="90df6-139">Complete Example</span></span>  
 <span data-ttu-id="90df6-140">下面的代码是包括 `XForm` 函数的完整示例。</span><span class="sxs-lookup"><span data-stu-id="90df6-140">The following code is a complete example that includes the `XForm` function.</span></span> <span data-ttu-id="90df6-141">它包括此类型转换的几种典型用法：</span><span class="sxs-lookup"><span data-stu-id="90df6-141">It includes a few of the typical uses of this type of transform:</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Xml;  
using System.Xml.Linq;  
  
class Program  
{  
    static XNamespace xf = "http://www.microsoft.com/LinqToXmlTransform/2007";  
    static XName at = xf + "ApplyTransforms";  
  
    // Build a transformed XML tree per the annotations  
    static XElement XForm(XElement source)  
    {  
        if (source.Annotation<XElement>() != null)  
        {  
            XElement anno = source.Annotation<XElement>();  
            return new XElement(anno.Name,  
                anno.Attributes(),  
                anno  
                .Nodes()  
                .Select(  
                    (XNode n) =>  
                    {  
                        XElement annoEl = n as XElement;  
                        if (annoEl != null)  
                        {  
                            if (annoEl.Name == at)  
                                return (object)(  
                                    source.Nodes()  
                                    .Select(  
                                        (XNode n2) =>  
                                        {  
                                            XElement e2 = n2 as XElement;  
                                            if (e2 == null)  
                                                return n2;  
                                            else  
                                                return XForm(e2);  
                                        }  
                                    )  
                                );  
                            else  
                                return n;  
                        }  
                        else  
                            return n;  
                    }  
                )  
            );  
        }  
        else  
        {  
            return new XElement(source.Name,  
                source.Attributes(),  
                source  
                    .Nodes()  
                    .Select(n =>  
                    {  
                        XElement el = n as XElement;  
                        if (el == null)  
                            return n;  
                        else  
                            return XForm(el);  
                    }  
                    )  
            );  
        }  
    }  
  
    static void Main(string[] args)  
    {  
        XElement root = new XElement("Root",  
            new XComment("A comment"),  
            new XAttribute("Att1", 123),  
            new XElement("Child", 1),  
            new XElement("Child", 2),  
            new XElement("Other",  
                new XElement("GC", 3),  
                new XElement("GC", 4)  
            ),  
            XElement.Parse(  
              "<SomeMixedContent>This is <i>an</i> element that " +  
              "<b>has</b> some mixed content</SomeMixedContent>"),  
            new XElement("AnUnchangedElement", 42)  
        );  
  
        // each of the following serves the same semantic purpose as  
        // XSLT templates and sequence constructors  
  
        // replace Child with NewChild  
        foreach (var el in root.Elements("Child"))  
            el.AddAnnotation(new XElement("NewChild", (string)el));  
  
        // replace first GC with GrandChild, add an attribute  
        foreach (var el in root.Descendants("GC").Take(1))  
            el.AddAnnotation(  
                new XElement("GrandChild",  
                    new XAttribute("ANewAttribute", 999),  
                    (string)el  
                )  
            );  
  
        // replace Other with NewOther, add new child elements around original content  
        foreach (var el in root.Elements("Other"))  
            el.AddAnnotation(  
                new XElement("NewOther",  
                    new XElement("MyNewChild", 1),  
                    // same idea as xsl:apply-templates  
                    new XElement(xf + "ApplyTransforms"),  
                    new XElement("ChildThatComesAfter")  
                )  
            );  
  
        // change name of element that has mixed content  
        root.Descendants("SomeMixedContent").First().AddAnnotation(  
            new XElement("MixedContent",  
                new XElement(xf + "ApplyTransforms")  
            )  
        );  
  
        // replace <b> with <Bold>  
        foreach (var el in root.Descendants("b"))  
            el.AddAnnotation(  
                new XElement("Bold",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        // replace <i> with <Italic>  
        foreach (var el in root.Descendants("i"))  
            el.AddAnnotation(  
                new XElement("Italic",  
                    new XElement(xf + "ApplyTransforms")  
                )  
            );  
  
        Console.WriteLine("Before Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(root);  
        Console.WriteLine();  
        Console.WriteLine();  
        XElement newRoot = XForm(root);  
  
        Console.WriteLine("After Transform");  
        Console.WriteLine("----------------");  
        Console.WriteLine(newRoot);  
    }  
}  
```  
  
 <span data-ttu-id="90df6-142">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="90df6-142">This example produces the following output:</span></span>  
  
```  
Before Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <Child>1</Child>  
  <Child>2</Child>  
  <Other>  
    <GC>3</GC>  
    <GC>4</GC>  
  </Other>  
  <SomeMixedContent>This is <i>an</i> element that <b>has</b> some mixed content</SomeMixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
  
After Transform  
----------------  
<Root Att1="123">  
  <!--A comment-->  
  <NewChild>1</NewChild>  
  <NewChild>2</NewChild>  
  <NewOther>  
    <MyNewChild>1</MyNewChild>  
    <GrandChild ANewAttribute="999">3</GrandChild>  
    <GC>4</GC>  
    <ChildThatComesAfter />  
  </NewOther>  
  <MixedContent>This is <Italic>an</Italic> element that <Bold>has</Bold> some mixed content</MixedContent>  
  <AnUnchangedElement>42</AnUnchangedElement>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="90df6-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="90df6-143">See Also</span></span>

- [<span data-ttu-id="90df6-144">高级 LINQ to XML 编程 (C#)</span><span class="sxs-lookup"><span data-stu-id="90df6-144">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
