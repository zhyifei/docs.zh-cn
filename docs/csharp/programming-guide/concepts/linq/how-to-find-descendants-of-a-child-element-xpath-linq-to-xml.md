---
title: 如何：查找子元素的后代 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: 548ec3f76a17ef8575e7e5e90ef4cbf8d2666a64
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33324988"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="44e2e-102">如何：查找子元素的后代 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="44e2e-102">How to: Find Descendants of a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="44e2e-103">本主题演示如何获取具有特定名称的子元素的后代元素。</span><span class="sxs-lookup"><span data-stu-id="44e2e-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="44e2e-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="44e2e-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="44e2e-105">示例</span><span class="sxs-lookup"><span data-stu-id="44e2e-105">Example</span></span>  
 <span data-ttu-id="44e2e-106">本示例模拟从文字处理文档的 XML 表示形式中提取文本的问题。</span><span class="sxs-lookup"><span data-stu-id="44e2e-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="44e2e-107">示例首先选择所有 `Paragraph` 元素，然后选择每个 `Text` 元素的所有 `Paragraph` 后代元素。</span><span class="sxs-lookup"><span data-stu-id="44e2e-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="44e2e-108">它不选择 `Text` 元素的后代 `Comment` 元素。</span><span class="sxs-lookup"><span data-stu-id="44e2e-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root>  
  <Paragraph>  
    <Text>This is the start of</Text>  
  </Paragraph>  
  <Comment>  
    <Text>This comment is not part of the paragraph text.</Text>  
  </Comment>  
  <Paragraph>  
    <Annotation Emphasis='true'>  
      <Text> a sentence.</Text>  
    </Annotation>  
  </Paragraph>  
  <Paragraph>  
    <Text>  This is a second sentence.</Text>  
  </Paragraph>  
</Root>");  
  
// LINQ to XML query  
string str1 =  
    root  
    .Elements("Paragraph")  
    .Descendants("Text")  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
// XPath expression  
string str2 =  
    ((IEnumerable)root.XPathEvaluate("./Paragraph//Text/text()"))  
    .Cast<XText>()  
    .Select(s => s.Value)  
    .Aggregate(  
        new StringBuilder(),  
        (s, i) => s.Append(i),  
        s => s.ToString()  
    );  
  
if (str1 == str2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(str2);  
```  
  
 <span data-ttu-id="44e2e-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="44e2e-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  
## <a name="see-also"></a><span data-ttu-id="44e2e-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="44e2e-110">See Also</span></span>  
 [<span data-ttu-id="44e2e-111">针对 XPath 用户的 LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="44e2e-111">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
