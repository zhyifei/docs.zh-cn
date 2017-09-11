---
title: "如何︰ 创建包含命名空间 (LINQ to XML) 的文档 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: cc5b0d4d-360c-4ada-94fa-2d2916e989be
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 60206722fff1d10c8368cbdd24ec6ca15dd207be
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-create-a-document-with-namespaces-linq-to-xml-visual-basic"></a><span data-ttu-id="e274e-102">如何：使用命名空间创建文档 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e274e-102">How to: Create a Document with Namespaces (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="e274e-103">本主题演示如何在 Visual Basic 中创建包含命名空间的文档。</span><span class="sxs-lookup"><span data-stu-id="e274e-103">This topic shows how to create a document with namespaces in Visual Basic.</span></span>  
  
 <span data-ttu-id="e274e-104">在 Visual Basic 中使用 XML 文本时，用户可以定义一个全局默认 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e274e-104">When using XML literals in Visual Basic, users can define one global default XML namespace.</span></span> <span data-ttu-id="e274e-105">该命名空间对 XML 文本和 XML 属性都是默认的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e274e-105">This namespace is the default namespace for both XML literals and XML properties.</span></span> <span data-ttu-id="e274e-106">可以在项目级别或文件级别上定义默认的 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="e274e-106">The default XML namespace can be defined at either the project level or the file level.</span></span> <span data-ttu-id="e274e-107">如果在文件级别上定义，则会重写项目级别上的默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="e274e-107">If it is defined at the file level, it overrides the default namespace at the project level.</span></span>  
  
 <span data-ttu-id="e274e-108">还可以定义其他命名空间，并为这些命名空间指定命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e274e-108">You can also define other namespaces, and specify the namespace prefixes for those namespaces.</span></span>  
  
 <span data-ttu-id="e274e-109">通过使用 `Imports` 关键字来定义默认命名空间和带前缀的命名空间。</span><span class="sxs-lookup"><span data-stu-id="e274e-109">You define both default namespaces and namespaces with a prefix by using the `Imports` keyword.</span></span>  
  
 <span data-ttu-id="e274e-110">有关详细信息，请参阅[在 Visual Basic 中的 XML 文本简介](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md)。</span><span class="sxs-lookup"><span data-stu-id="e274e-110">For more information, see [Introduction to XML Literals in Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md).</span></span>  
  
 <span data-ttu-id="e274e-111">请注意，默认 XML 命名空间仅适用于元素，而不适用于属性。</span><span class="sxs-lookup"><span data-stu-id="e274e-111">Note that the default XML namespace only applies to elements and not to attributes.</span></span> <span data-ttu-id="e274e-112">默认情况下属性从不在命名空间中。</span><span class="sxs-lookup"><span data-stu-id="e274e-112">Attributes are by default always in no namespace.</span></span> <span data-ttu-id="e274e-113">但是可以使用命名空间前缀将属性置于一个命名空间中。</span><span class="sxs-lookup"><span data-stu-id="e274e-113">However, you can use a namespace prefix to put an attribute in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e274e-114">示例</span><span class="sxs-lookup"><span data-stu-id="e274e-114">Example</span></span>  
 <span data-ttu-id="e274e-115">此示例创建一个包含命名空间的文档。</span><span class="sxs-lookup"><span data-stu-id="e274e-115">This example creates a document that contains a namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child aw:Att="attvalue"/>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="e274e-116">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="e274e-116">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child aw:Att="attvalue" />  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="e274e-117">示例</span><span class="sxs-lookup"><span data-stu-id="e274e-117">Example</span></span>  
 <span data-ttu-id="e274e-118">此示例创建一个包含两个命名空间的文档，其中一个为默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="e274e-118">This example creates a document that contains two namespaces, one of which is the default namespace.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child Att="attvalue"/>  
                <fc:Child2>child2 content</fc:Child2>  
            </Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="e274e-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="e274e-119">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns:fc="www.fourthcoffee.com" xmlns="http://www.adventure-works.com">  
  <Child Att="attvalue" />  
  <fc:Child2>child2 content</fc:Child2>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="e274e-120">示例</span><span class="sxs-lookup"><span data-stu-id="e274e-120">Example</span></span>  
 <span data-ttu-id="e274e-121">下面的示例创建一个包含多个命名空间的文档，每个命名空间都具有命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="e274e-121">The following example creates a document that contains multiple namespaces, both with namespace prefixes.</span></span>  
  
 <span data-ttu-id="e274e-122">序列化 XML 树时，[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 发出所需的命名空间声明，这样每个元素都位于所指定的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="e274e-122">When serializing an XML tree, [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] emits namespace declarations as required so that each element is in its designated namespace.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
 <span data-ttu-id="e274e-123">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="e274e-123">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="e274e-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e274e-124">See Also</span></span>  
 [<span data-ttu-id="e274e-125">使用 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e274e-125">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
