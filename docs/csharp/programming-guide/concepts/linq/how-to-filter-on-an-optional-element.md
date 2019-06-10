---
title: 如何：筛选可选元素 (C#)
ms.date: 07/20/2015
ms.assetid: f99e2f93-fca5-403f-8a0c-770761d4905a
ms.openlocfilehash: 6dba732268ff9ff1a206cd13e31f94c394a17b39
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485714"
---
# <a name="how-to-filter-on-an-optional-element-c"></a><span data-ttu-id="8c86a-102">如何：筛选可选元素 (C#)</span><span class="sxs-lookup"><span data-stu-id="8c86a-102">How to: Filter on an Optional Element (C#)</span></span>
<span data-ttu-id="8c86a-103">有时，尽管不能确定某个元素是否存在于 XML 文档中，您还是会尝试筛选该元素。</span><span class="sxs-lookup"><span data-stu-id="8c86a-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="8c86a-104">应当执行搜索，这样如果特定元素没有子元素，就不会因为筛选它而触发空引用异常。</span><span class="sxs-lookup"><span data-stu-id="8c86a-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="8c86a-105">在下面的示例中，`Child5` 元素没有 `Type` 子元素，但是查询仍可以正确执行。</span><span class="sxs-lookup"><span data-stu-id="8c86a-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8c86a-106">示例</span><span class="sxs-lookup"><span data-stu-id="8c86a-106">Example</span></span>  
 <span data-ttu-id="8c86a-107">本示例使用 <xref:System.Xml.Linq.Extensions.Elements%2A> 扩展方法。</span><span class="sxs-lookup"><span data-stu-id="8c86a-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
var cList =  
    from typeElement in root.Elements().Elements("Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element("Text");  
foreach(string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="8c86a-108">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="8c86a-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="8c86a-109">示例</span><span class="sxs-lookup"><span data-stu-id="8c86a-109">Example</span></span>  
 <span data-ttu-id="8c86a-110">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="8c86a-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="8c86a-111">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="8c86a-111">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Parse(@"<Root xmlns='http://www.adatum.com'>  
  <Child1>  
    <Text>Child One Text</Text>  
    <Type Value=""Yes""/>  
  </Child1>  
  <Child2>  
    <Text>Child Two Text</Text>  
    <Type Value=""Yes""/>  
  </Child2>  
  <Child3>  
    <Text>Child Three Text</Text>  
    <Type Value=""No""/>  
  </Child3>  
  <Child4>  
    <Text>Child Four Text</Text>  
    <Type Value=""Yes""/>  
  </Child4>  
  <Child5>  
    <Text>Child Five Text</Text>  
  </Child5>  
</Root>");  
XNamespace ad = "http://www.adatum.com";  
var cList =  
    from typeElement in root.Elements().Elements(ad + "Type")  
    where (string)typeElement.Attribute("Value") == "Yes"  
    select (string)typeElement.Parent.Element(ad + "Text");  
foreach (string str in cList)  
    Console.WriteLine(str);  
```  
  
 <span data-ttu-id="8c86a-112">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="8c86a-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c86a-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c86a-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="8c86a-114">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="8c86a-114">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="8c86a-115">投影运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="8c86a-115">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
