---
title: 如何：控制命名空间前缀 (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 91117307caf7e55bd8b512fbd841760616f0b2c5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54623737"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="b9261-102">如何：控制命名空间前缀 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="b9261-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="b9261-103">本主题说明如何控制命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="b9261-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b9261-104">示例</span><span class="sxs-lookup"><span data-stu-id="b9261-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b9261-105">描述</span><span class="sxs-lookup"><span data-stu-id="b9261-105">Description</span></span>  
 <span data-ttu-id="b9261-106">本示例声明两个命名空间。</span><span class="sxs-lookup"><span data-stu-id="b9261-106">This example declares two namespaces.</span></span> <span data-ttu-id="b9261-107">它指定`http://www.adventure-works.com`命名空间具有前缀`aw`，并且`www.fourthcoffee.com`命名空间具有前缀的`fc`。</span><span class="sxs-lookup"><span data-stu-id="b9261-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b9261-108">代码</span><span class="sxs-lookup"><span data-stu-id="b9261-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="b9261-109">注释</span><span class="sxs-lookup"><span data-stu-id="b9261-109">Comments</span></span>  
 <span data-ttu-id="b9261-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="b9261-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b9261-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9261-111">See also</span></span>
- [<span data-ttu-id="b9261-112">使用 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b9261-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
