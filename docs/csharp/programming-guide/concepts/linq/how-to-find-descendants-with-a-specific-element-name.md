---
title: 如何：查找具有特定元素名称的子代 (C#)
ms.date: 07/20/2015
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
ms.openlocfilehash: c54b3c6a01459781b8ed9d5495bf9eb8937363fa
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486752"
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="5d669-102">如何：查找具有特定元素名称的子代 (C#)</span><span class="sxs-lookup"><span data-stu-id="5d669-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="5d669-103">有时，您想要查找所有具有特定名称的子代。</span><span class="sxs-lookup"><span data-stu-id="5d669-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="5d669-104">可以编写代码用于循环访问所有子代，但使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴更简单。</span><span class="sxs-lookup"><span data-stu-id="5d669-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d669-105">示例</span><span class="sxs-lookup"><span data-stu-id="5d669-105">Example</span></span>  
 <span data-ttu-id="5d669-106">下面的示例演示如何根据元素名称查找子代。</span><span class="sxs-lookup"><span data-stu-id="5d669-106">The following example shows how to find descendants based on the element name.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
IEnumerable<string> textSegs =  
    from seg in root.Descendants("t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5d669-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="5d669-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="5d669-108">示例</span><span class="sxs-lookup"><span data-stu-id="5d669-108">Example</span></span>  
 <span data-ttu-id="5d669-109">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="5d669-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="5d669-110">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="5d669-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<root xmlns='http://www.adatum.com'>  
  <para>  
    <r>  
      <t>Some text </t>  
    </r>  
    <n>  
      <r>  
        <t>that is broken up into </t>  
      </r>  
    </n>  
    <n>  
      <r>  
        <t>multiple segments.</t>  
      </r>  
    </n>  
  </para>  
</root>");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<string> textSegs =  
    from seg in root.Descendants(ad + "t")  
    select (string)seg;  
  
string str = textSegs.Aggregate(new StringBuilder(),  
    (sb, i) => sb.Append(i),  
    sp => sp.ToString()  
);  
  
Console.WriteLine(str);  
```  
  
 <span data-ttu-id="5d669-111">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="5d669-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="5d669-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d669-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A>
