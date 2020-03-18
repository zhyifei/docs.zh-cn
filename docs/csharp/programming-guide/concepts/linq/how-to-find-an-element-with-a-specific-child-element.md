---
title: 如何查找具有特定子元素的元素 (C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: 0536b1b92d4d7fc18b5d406bbcd24aefc6a840c6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "74141143"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="7c230-102">如何查找具有特定子元素的元素 (C#)</span><span class="sxs-lookup"><span data-stu-id="7c230-102">How to find an element with a specific child element (C#)</span></span>
<span data-ttu-id="7c230-103">本主题演示如何查找特定元素，该特定元素包含具有特定值的子元素。</span><span class="sxs-lookup"><span data-stu-id="7c230-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7c230-104">示例</span><span class="sxs-lookup"><span data-stu-id="7c230-104">Example</span></span>  
 <span data-ttu-id="7c230-105">示例查找 `Test` 元素，该元素包含具有值为“Examp2.EXE”的 `CommandLine` 子元素。</span><span class="sxs-lookup"><span data-stu-id="7c230-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="7c230-106">本示例使用以下 XML 文档：[示例 XML 文件：测试配置 (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="7c230-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](./sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="7c230-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="7c230-107">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="7c230-108">示例</span><span class="sxs-lookup"><span data-stu-id="7c230-108">Example</span></span>  
 <span data-ttu-id="7c230-109">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="7c230-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="7c230-110">有关详细信息，请参阅[命名空间概述(LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="7c230-110">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="7c230-111">本示例使用以下 XML 文档：[示例 XML 文件：命名空间中的测试配置](./sample-xml-file-test-configuration-in-a-namespace1.md)。</span><span class="sxs-lookup"><span data-stu-id="7c230-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](./sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfigInNamespace.xml");  
XNamespace ad = "http://www.adatum.com";  
IEnumerable<XElement> tests =  
    from el in root.Elements(ad + "Test")  
    where (string)el.Element(ad + "CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="7c230-112">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="7c230-112">This code produces the following output:</span></span>  
  
```output  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="7c230-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7c230-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="7c230-114">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="7c230-114">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="7c230-115">投影运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="7c230-115">Projection Operations (C#)</span></span>](./projection-operations.md)
