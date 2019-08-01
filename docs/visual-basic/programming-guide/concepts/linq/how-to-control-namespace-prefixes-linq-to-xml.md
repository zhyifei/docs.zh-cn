---
title: 如何：控制命名空间前缀 (Visual Basic) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 2b89b49aa76df526c08143cad49685386ffd5e7c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709824"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="c4e66-102">如何：控制命名空间前缀 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="c4e66-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="c4e66-103">本主题说明如何控制命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="c4e66-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4e66-104">示例</span><span class="sxs-lookup"><span data-stu-id="c4e66-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="c4e66-105">描述</span><span class="sxs-lookup"><span data-stu-id="c4e66-105">Description</span></span>  
 <span data-ttu-id="c4e66-106">本示例声明两个命名空间。</span><span class="sxs-lookup"><span data-stu-id="c4e66-106">This example declares two namespaces.</span></span> <span data-ttu-id="c4e66-107">它指定`http://www.adventure-works.com`命名空间具有前缀`aw`, `www.fourthcoffee.com`命名空间具有前缀`fc`。</span><span class="sxs-lookup"><span data-stu-id="c4e66-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="c4e66-108">代码</span><span class="sxs-lookup"><span data-stu-id="c4e66-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="c4e66-109">注释</span><span class="sxs-lookup"><span data-stu-id="c4e66-109">Comments</span></span>  
 <span data-ttu-id="c4e66-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c4e66-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c4e66-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4e66-111">See also</span></span>

- [<span data-ttu-id="c4e66-112">命名空间概述 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c4e66-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
