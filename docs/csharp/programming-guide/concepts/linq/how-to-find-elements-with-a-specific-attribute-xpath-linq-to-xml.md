---
title: 如何：查找具有特定属性的元素 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: daed00dd-923a-43be-8a90-eee406f6f574
ms.openlocfilehash: 18dbd3170b5e3f8f8b3e11c66430d71ba6acd0da
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33318082"
---
# <a name="how-to-find-elements-with-a-specific-attribute-xpath-linq-to-xml-c"></a><span data-ttu-id="91d4f-102">如何：查找具有特定属性的元素 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="91d4f-102">How to: Find Elements with a Specific Attribute (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="91d4f-103">有时需要查找具有特定属性的所有元素。</span><span class="sxs-lookup"><span data-stu-id="91d4f-103">Sometimes you want to find all elements that have a specific attribute.</span></span> <span data-ttu-id="91d4f-104">您并不关心属性的内容，</span><span class="sxs-lookup"><span data-stu-id="91d4f-104">You are not concerned about the contents of the attribute.</span></span> <span data-ttu-id="91d4f-105">而是根据属性是否存在进行选择。</span><span class="sxs-lookup"><span data-stu-id="91d4f-105">Instead, you want to select based on the existence of the attribute.</span></span>  
  
 <span data-ttu-id="91d4f-106">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="91d4f-106">The XPath expression is:</span></span>  
  
 `./*[@Select]`  
  
## <a name="example"></a><span data-ttu-id="91d4f-107">示例</span><span class="sxs-lookup"><span data-stu-id="91d4f-107">Example</span></span>  
 <span data-ttu-id="91d4f-108">下面的代码选择具有 `Select` 属性的所有元素。</span><span class="sxs-lookup"><span data-stu-id="91d4f-108">The following code selects just the elements that have the `Select` attribute.</span></span>  
  
```csharp  
XElement doc = XElement.Parse(  
@"<Root>  
    <Child1>1</Child1>  
    <Child2 Select='true'>2</Child2>  
    <Child3>3</Child3>  
    <Child4 Select='true'>4</Child4>  
    <Child5>5</Child5>  
</Root>");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    from el in doc.Elements()  
    where el.Attribute("Select") != null  
    select el;  
  
// XPath expression  
IEnumerable<XElement> list2 =  
    ((IEnumerable)doc.XPathEvaluate("./*[@Select]")).Cast<XElement>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="91d4f-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="91d4f-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child2 Select="true">2</Child2>  
<Child4 Select="true">4</Child4>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91d4f-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="91d4f-110">See Also</span></span>  
 [<span data-ttu-id="91d4f-111">针对 XPath 用户的 LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="91d4f-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
