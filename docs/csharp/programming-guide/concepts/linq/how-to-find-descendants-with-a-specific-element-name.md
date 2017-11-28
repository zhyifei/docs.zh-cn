---
title: "如何：查找具有特定元素名称的后代 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: f684da20-bee9-47f5-9607-7e3fd7e67470
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b1cc45f07accd7ae6dcc530f0fd5a9078bce949d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-descendants-with-a-specific-element-name-c"></a><span data-ttu-id="46d86-102">如何：查找具有特定元素名称的后代 (C#)</span><span class="sxs-lookup"><span data-stu-id="46d86-102">How to: Find Descendants with a Specific Element Name (C#)</span></span>
<span data-ttu-id="46d86-103">有时，您想要查找所有具有特定名称的子代。</span><span class="sxs-lookup"><span data-stu-id="46d86-103">Sometimes you want to find all descendants with a particular name.</span></span> <span data-ttu-id="46d86-104">可以编写代码用于循环访问所有子代，但使用 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴更简单。</span><span class="sxs-lookup"><span data-stu-id="46d86-104">You could write code to iterate through all of the descendants, but it is easier to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46d86-105">示例</span><span class="sxs-lookup"><span data-stu-id="46d86-105">Example</span></span>  
 <span data-ttu-id="46d86-106">下面的示例演示如何根据元素名称查找子代。</span><span class="sxs-lookup"><span data-stu-id="46d86-106">The following example shows how to find descendants based on the element name.</span></span>  
  
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
  
 <span data-ttu-id="46d86-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="46d86-107">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="example"></a><span data-ttu-id="46d86-108">示例</span><span class="sxs-lookup"><span data-stu-id="46d86-108">Example</span></span>  
 <span data-ttu-id="46d86-109">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="46d86-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="46d86-110">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="46d86-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
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
  
 <span data-ttu-id="46d86-111">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="46d86-111">This code produces the following output:</span></span>  
  
```  
Some text that is broken up into multiple segments.  
```  
  
## <a name="see-also"></a><span data-ttu-id="46d86-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46d86-112">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.Descendants%2A>  
 [<span data-ttu-id="46d86-113">基本查询 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="46d86-113">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
