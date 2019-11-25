---
title: 如何查找子元素的后代 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 505b7512-bb8b-4f85-abbf-491f039c961e
ms.openlocfilehash: fb3e20ce21c1f6d2a71f2f71b8acec7cecf0f3ed
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141092"
---
# <a name="how-to-find-descendants-of-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="14396-102">如何查找子元素的后代 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="14396-102">How to find descendants of a child element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="14396-103">本主题演示如何获取具有特定名称的子元素的后代元素。</span><span class="sxs-lookup"><span data-stu-id="14396-103">This topic shows how to get the descendant elements of a child element with a particular name.</span></span>  
  
 <span data-ttu-id="14396-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="14396-104">The XPath expression is:</span></span>  
  
 `./Paragraph//Text/text()`  
  
## <a name="example"></a><span data-ttu-id="14396-105">示例</span><span class="sxs-lookup"><span data-stu-id="14396-105">Example</span></span>  
 <span data-ttu-id="14396-106">本示例模拟从文字处理文档的 XML 表示形式中提取文本的问题。</span><span class="sxs-lookup"><span data-stu-id="14396-106">This example simulates the problems of extracting text from an XML representation of a word processing document.</span></span> <span data-ttu-id="14396-107">示例首先选择所有 `Paragraph` 元素，然后选择每个 `Text` 元素的所有 `Paragraph` 后代元素。</span><span class="sxs-lookup"><span data-stu-id="14396-107">It first selects all `Paragraph` elements, and then it selects all `Text` descendant elements of each `Paragraph` element.</span></span> <span data-ttu-id="14396-108">它不选择 `Text` 元素的后代 `Comment` 元素。</span><span class="sxs-lookup"><span data-stu-id="14396-108">This doesn't select the descendant `Text` elements of the `Comment` element.</span></span>  
  
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
  
 <span data-ttu-id="14396-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="14396-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
This is the start of a sentence.  This is a second sentence.  
```  
  