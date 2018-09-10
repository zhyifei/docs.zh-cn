---
title: 如何：使用命名空间创建文档 (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 0fa19af47847b0d6b804528af3f766c9775e74f3
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863682"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="04acd-102">如何：使用命名空间创建文档 (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="04acd-102">How to: Create a Document with Namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="04acd-103">本主题演示如何创建包含命名空间的文档。</span><span class="sxs-lookup"><span data-stu-id="04acd-103">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04acd-104">示例</span><span class="sxs-lookup"><span data-stu-id="04acd-104">Example</span></span>  
 <span data-ttu-id="04acd-105">若要创建一个属于命名空间的元素或属性，请首先声明和初始化一个 <xref:System.Xml.Linq.XNamespace> 对象。</span><span class="sxs-lookup"><span data-stu-id="04acd-105">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="04acd-106">然后使用加法运算符重载来组合命名空间和本地名称（以字符串表示）。</span><span class="sxs-lookup"><span data-stu-id="04acd-106">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="04acd-107">下面的示例创建一个包含一个命名空间的文档。</span><span class="sxs-lookup"><span data-stu-id="04acd-107">The following example creates a document with one namespace.</span></span> <span data-ttu-id="04acd-108">默认情况下，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 使用默认命名空间序列化此文档。</span><span class="sxs-lookup"><span data-stu-id="04acd-108">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="04acd-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="04acd-109">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="04acd-110">示例</span><span class="sxs-lookup"><span data-stu-id="04acd-110">Example</span></span>  
 <span data-ttu-id="04acd-111">下面的示例创建一个包含一个命名空间的文档。</span><span class="sxs-lookup"><span data-stu-id="04acd-111">The following example creates a document with one namespace.</span></span> <span data-ttu-id="04acd-112">另外，还创建一个属性，该属性声明具有命名空间前缀的命名空间。</span><span class="sxs-lookup"><span data-stu-id="04acd-112">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="04acd-113">若要创建一个声明具有前缀的命名空间的属性，请创建一个属性，其中该属性的名称为命名空间前缀，并且此名称位于 <xref:System.Xml.Linq.XNamespace.Xmlns%2A> 命名空间中。</span><span class="sxs-lookup"><span data-stu-id="04acd-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="04acd-114">此属性的值即是命名空间的 URI。</span><span class="sxs-lookup"><span data-stu-id="04acd-114">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="04acd-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="04acd-115">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="04acd-116">示例</span><span class="sxs-lookup"><span data-stu-id="04acd-116">Example</span></span>  
 <span data-ttu-id="04acd-117">下面的示例演示如何创建一个包含两个命名空间的文档。</span><span class="sxs-lookup"><span data-stu-id="04acd-117">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="04acd-118">一个是默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="04acd-118">One is the default namespace.</span></span> <span data-ttu-id="04acd-119">另一个是具有前缀的命名空间。</span><span class="sxs-lookup"><span data-stu-id="04acd-119">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="04acd-120">通过在根元素中包括命名空间属性，命名空间进行了序列化，从而 `http://www.adventure-works.com` 是默认命名空间，而 `www.fourthcoffee.com` 用“fc”前缀进行了序列化。</span><span class="sxs-lookup"><span data-stu-id="04acd-120">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="04acd-121">若要创建一个声明默认命名空间的属性，请创建一个名称为“xmlns”的属性，而无需命名空间。</span><span class="sxs-lookup"><span data-stu-id="04acd-121">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="04acd-122">该属性的值即是默认命名空间 URI。</span><span class="sxs-lookup"><span data-stu-id="04acd-122">The value of the attribute is the default namespace URI.</span></span>  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="04acd-123">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="04acd-123">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="04acd-124">示例</span><span class="sxs-lookup"><span data-stu-id="04acd-124">Example</span></span>  
 <span data-ttu-id="04acd-125">下面的示例创建一个包含两个命名空间的文档，这两个命名空间都具有命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="04acd-125">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="04acd-126">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="04acd-126">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="04acd-127">示例</span><span class="sxs-lookup"><span data-stu-id="04acd-127">Example</span></span>  
 <span data-ttu-id="04acd-128">另一种可获得相同结果的方法是使用扩展名，而不是声明和创建一个 <xref:System.Xml.Linq.XNamespace> 对象。</span><span class="sxs-lookup"><span data-stu-id="04acd-128">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="04acd-129">这种方法的性能较低。</span><span class="sxs-lookup"><span data-stu-id="04acd-129">This approach has performance implications.</span></span> <span data-ttu-id="04acd-130">每次将包含扩展名的字符串传递给 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 时，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 都必须分析名称，查找原子化命名空间，再查找原子化名称。</span><span class="sxs-lookup"><span data-stu-id="04acd-130">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="04acd-131">这个过程会占用 CPU 时间。</span><span class="sxs-lookup"><span data-stu-id="04acd-131">This process takes CPU time.</span></span> <span data-ttu-id="04acd-132">如果性能很重要，则您可能希望显式声明和使用 <xref:System.Xml.Linq.XNamespace> 对象。</span><span class="sxs-lookup"><span data-stu-id="04acd-132">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="04acd-133">如果性能是重要问题，请参阅 [XName 对象的预先原子化 (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/pre-atomization-of-xname-objects-linq-to-xml.md) 了解详细信息</span><span class="sxs-lookup"><span data-stu-id="04acd-133">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="04acd-134">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="04acd-134">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="04acd-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="04acd-135">See Also</span></span>

- [<span data-ttu-id="04acd-136">使用 XML 命名空间 (C#)</span><span class="sxs-lookup"><span data-stu-id="04acd-136">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
