---
title: "如何：控制命名空间前缀 (Visual Basic) (LINQ to XML)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a48feeb25cc8d28d57edc7421f73b2829f8c19ef
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="60f80-102">如何：控制命名空间前缀 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="60f80-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="60f80-103">本主题说明如何控制命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="60f80-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60f80-104">示例</span><span class="sxs-lookup"><span data-stu-id="60f80-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="60f80-105">描述</span><span class="sxs-lookup"><span data-stu-id="60f80-105">Description</span></span>  
 <span data-ttu-id="60f80-106">本示例声明两个命名空间。</span><span class="sxs-lookup"><span data-stu-id="60f80-106">This example declares two namespaces.</span></span> <span data-ttu-id="60f80-107">它指定`http://www.adventure-works.com`命名空间具有前缀`aw`，且`www.fourthcoffee.com`命名空间具有的前缀`fc`。</span><span class="sxs-lookup"><span data-stu-id="60f80-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="60f80-108">代码</span><span class="sxs-lookup"><span data-stu-id="60f80-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="60f80-109">注释</span><span class="sxs-lookup"><span data-stu-id="60f80-109">Comments</span></span>  
 <span data-ttu-id="60f80-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="60f80-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="60f80-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60f80-111">See Also</span></span>  
 [<span data-ttu-id="60f80-112">处理 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60f80-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
