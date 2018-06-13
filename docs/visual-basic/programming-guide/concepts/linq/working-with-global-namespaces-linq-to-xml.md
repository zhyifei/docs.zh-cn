---
title: 使用全局命名空间 (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 0a8064d5-e02f-4315-ad48-6deaa443a2f0
ms.openlocfilehash: c1f34b374f956ec0a8b9658742e529d7ccb1b2ce
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33648900"
---
# <a name="working-with-global-namespaces-visual-basic-linq-to-xml"></a><span data-ttu-id="d83cf-102">使用全局命名空间 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="d83cf-102">Working with Global Namespaces (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="d83cf-103">在 Visual Basic 中的 XML 文本的主要功能之一是能够使用声明 XML 命名空间`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="d83cf-103">One of the key features of XML literals in Visual Basic is the capability to declare XML namespaces by using the `Imports` statement.</span></span> <span data-ttu-id="d83cf-104">使用此功能时，您可以声明使用前缀的 XML 命名空间，也可以声明默认的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-104">Using this feature, you can declare an XML namespace that uses a prefix, or you can declare a default XML namespace.</span></span>  
  
 <span data-ttu-id="d83cf-105">此功能在两种情况下有用。</span><span class="sxs-lookup"><span data-stu-id="d83cf-105">This capability is useful in two situations.</span></span> <span data-ttu-id="d83cf-106">首先，使用 XML 文本声明的命名空间不会延续到嵌入的表达式。</span><span class="sxs-lookup"><span data-stu-id="d83cf-106">First, namespaces declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="d83cf-107">声明全局命名空间可减少与命名空间一起使用嵌入表达式所必须执行的工作量。</span><span class="sxs-lookup"><span data-stu-id="d83cf-107">Declaring global namespaces reduces the amount of work that you have to do to use embedded expressions with namespaces.</span></span> <span data-ttu-id="d83cf-108">其次，您必须声明全局命名空间才能与 XML 属性一起使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-108">Second, you must declare global namespaces in order to use namespaces with XML properties.</span></span>  
  
 <span data-ttu-id="d83cf-109">您可以在项目级别声明全局命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-109">You can declare global namespaces at the project level.</span></span> <span data-ttu-id="d83cf-110">您也可以在模块级别声明全局命名空间，这会重写项目级全局命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-110">You can also declare global namespaces at the module level, which overrides the project-level global namespaces.</span></span> <span data-ttu-id="d83cf-111">最后，您可以使用 XML 文本重写全局命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-111">Finally, you can override global namespaces in an XML literal.</span></span>  
  
 <span data-ttu-id="d83cf-112">在使用全局声明的命名空间中的 XML 文本或 XML 属性时，您可以在 Visual Studio 中通过将鼠标悬停在 XML 文本或属性上来查看扩展的 XML 文本或属性的名称。</span><span class="sxs-lookup"><span data-stu-id="d83cf-112">When using XML literals or XML properties that are in globally-declared namespaces, you can see the expanded name of XML literals or properties by hovering over them in Visual Studio.</span></span> <span data-ttu-id="d83cf-113">您会在工具提示中看到扩展的名称。</span><span class="sxs-lookup"><span data-stu-id="d83cf-113">You will see the expanded name in a tooltip.</span></span>  
  
 <span data-ttu-id="d83cf-114">使用 <xref:System.Xml.Linq.XNamespace> 方法可以获取对应于全局命名空间的 `GetXmlNamespace` 对象。</span><span class="sxs-lookup"><span data-stu-id="d83cf-114">You can get an <xref:System.Xml.Linq.XNamespace> object that corresponds to a global namespace using the `GetXmlNamespace` method.</span></span>  
  
## <a name="examples-of-global-namespaces"></a><span data-ttu-id="d83cf-115">全局命名空间的示例</span><span class="sxs-lookup"><span data-stu-id="d83cf-115">Examples of Global Namespaces</span></span>  
 <span data-ttu-id="d83cf-116">下面的示例通过使用 `Imports` 语句声明一个默认的全局命名空间，然后使用 XML 文本在该命名空间中初始化一个 <xref:System.Xml.Linq.XElement> 对象：</span><span class="sxs-lookup"><span data-stu-id="d83cf-116">The following example declares a default global namespace by using the `Imports` statement, and then uses an XML literal to initialize an <xref:System.Xml.Linq.XElement> object in that namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d83cf-117">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-117">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" />  
```  
  
 <span data-ttu-id="d83cf-118">下面的示例声明一个具有前缀的全局命名空间，然后使用 XML 文本初始化一个元素：</span><span class="sxs-lookup"><span data-stu-id="d83cf-118">The following example declares a global namespace with a prefix, and then uses an XML literal to initialize an element:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d83cf-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-119">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" />  
```  
  
## <a name="global-namespaces-and-embedded-expressions"></a><span data-ttu-id="d83cf-120">全局命名空间和嵌入式表达式</span><span class="sxs-lookup"><span data-stu-id="d83cf-120">Global Namespaces and Embedded Expressions</span></span>  
 <span data-ttu-id="d83cf-121">使用 XML 文本声明的命名空间不会延续到嵌入的表达式。</span><span class="sxs-lookup"><span data-stu-id="d83cf-121">Namespaces that are declared in XML literals do not carry over into embedded expressions.</span></span> <span data-ttu-id="d83cf-122">下面的示例声明一个默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-122">The following example declares a default namespace.</span></span> <span data-ttu-id="d83cf-123">然后对 `Child` 元素使用一个嵌入式表达式。</span><span class="sxs-lookup"><span data-stu-id="d83cf-123">It then uses an embedded expression for the `Child` element.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="d83cf-124">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-124">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="" />  
</Root>  
```  
  
 <span data-ttu-id="d83cf-125">您可以看到，生成的 XML 包括一个默认命名空间声明，从而使 `Child` 元素不在任何命名空间中。</span><span class="sxs-lookup"><span data-stu-id="d83cf-125">As you can see, the resulting XML includes a declaration of a default namespace so that the `Child` element is in no namespace.</span></span>  
  
 <span data-ttu-id="d83cf-126">您可以在嵌入式表达式中重新声明该命名空间，如下所示：</span><span class="sxs-lookup"><span data-stu-id="d83cf-126">You could re-declare the namespace in the embedded expression, as follows:</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <%= <Child xmlns="http://www.adventure-works.com"/> %>  
    </Root>  
Console.WriteLine(root)  
```  
  
 <span data-ttu-id="d83cf-127">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-127">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child xmlns="http://www.adventure-works.com" />  
</Root>  
```  
  
 <span data-ttu-id="d83cf-128">但是，这种方法更不便于使用，更好的方法是使用全局默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-128">However, this is more cumbersome to use than the global default namespace, which is a better approach.</span></span> <span data-ttu-id="d83cf-129">通过使用全局默认命名空间，您可以使用 XML 文本而无需声明命名空间。</span><span class="sxs-lookup"><span data-stu-id="d83cf-129">With the global default namespace, you can use XML literals without declaring namespaces.</span></span> <span data-ttu-id="d83cf-130">生成的 XML 将处于全局声明的默认命名空间中。</span><span class="sxs-lookup"><span data-stu-id="d83cf-130">The resulting XML will be in the globally-declared default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <Root>  
                                   <%= <Child/> %>  
                               </Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d83cf-131">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-131">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child />  
</Root>  
```  
  
## <a name="using-namespaces-with-xml-properties"></a><span data-ttu-id="d83cf-132">与 XML 属性一起使用命名空间</span><span class="sxs-lookup"><span data-stu-id="d83cf-132">Using Namespaces with XML Properties</span></span>  
 <span data-ttu-id="d83cf-133">如果您使用位于某一命名空间中的 XML 树并使用 XML 属性，则必须使用全局命名空间，以使 XML 属性也位于正确的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="d83cf-133">If you are working with an XML tree that is in a namespace, and you use XML properties, then you must use a global namespace so that the XML properties will also be in the correct namespace.</span></span> <span data-ttu-id="d83cf-134">下面的示例在一个命名空间中一个声明 XML 树。</span><span class="sxs-lookup"><span data-stu-id="d83cf-134">The following example declares an XML tree in a namespace.</span></span> <span data-ttu-id="d83cf-135">然后打印 `Child` 元素的计数。</span><span class="sxs-lookup"><span data-stu-id="d83cf-135">It then prints the count of `Child` elements.</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root xmlns="http://www.adventure-works.com">  
        <Child>content</Child>  
    </Root>  
Console.WriteLine(root.<Child>.Count())  
```  
  
 <span data-ttu-id="d83cf-136">本示例指示没有 `Child` 元素。</span><span class="sxs-lookup"><span data-stu-id="d83cf-136">This example indicates that there are no `Child` elements.</span></span> <span data-ttu-id="d83cf-137">它将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-137">It produces the following output:</span></span>  
  
```  
0  
```  
  
 <span data-ttu-id="d83cf-138">但如果您声明一个默认的全局命名空间，则 XML 文本和 XML 属性都将位于该默认的全局命名空间中：</span><span class="sxs-lookup"><span data-stu-id="d83cf-138">If, however, you declare a default global namespace, then both the XML literal and the XML property are in the default global namespace:</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>content</Child>  
            </Root>  
        Console.WriteLine(root.<Child>.Count())  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d83cf-139">本示例指示有一个 `Child` 元素。</span><span class="sxs-lookup"><span data-stu-id="d83cf-139">This example indicates that there is one `Child` element.</span></span> <span data-ttu-id="d83cf-140">它将生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-140">It produces the following output:</span></span>  
  
```  
1  
```  
  
 <span data-ttu-id="d83cf-141">如果您声明一个具有前缀的全局命名空间，则可以对 XML 文本和 XML 属性使用该前缀：</span><span class="sxs-lookup"><span data-stu-id="d83cf-141">If you declare a global namespace that has a prefix, you can use the prefix for both XML literals and XML properties:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>content</aw:Child>  
            </aw:Root>  
        Console.WriteLine(root.<aw:Child>.Count())  
    End Sub  
End Module  
```  
  
## <a name="xnamespace-and-global-namespaces"></a><span data-ttu-id="d83cf-142">XNamespace 和全局命名空间</span><span class="sxs-lookup"><span data-stu-id="d83cf-142">XNamespace and Global Namespaces</span></span>  
 <span data-ttu-id="d83cf-143">通过使用 <xref:System.Xml.Linq.XNamespace> 方法，可以获取一个 `GetXmlNamespace` 对象：</span><span class="sxs-lookup"><span data-stu-id="d83cf-143">You can get an <xref:System.Xml.Linq.XNamespace> object by using the `GetXmlNamespace` method:</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = <aw:Root/>  
        Dim xn As XNamespace = GetXmlNamespace(aw)  
        Console.WriteLine(xn)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d83cf-144">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d83cf-144">This example produces the following output:</span></span>  
  
```  
http://www.adventure-works.com  
```  
  
## <a name="see-also"></a><span data-ttu-id="d83cf-145">请参阅</span><span class="sxs-lookup"><span data-stu-id="d83cf-145">See Also</span></span>  
 [<span data-ttu-id="d83cf-146">处理 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d83cf-146">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
