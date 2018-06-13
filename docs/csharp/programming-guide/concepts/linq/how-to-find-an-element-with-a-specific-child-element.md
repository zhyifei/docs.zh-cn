---
title: 如何：查找具有特定子元素的元素 (C#)
ms.date: 07/20/2015
ms.assetid: 00cf5555-374e-4369-bf93-7bd2e7f21db3
ms.openlocfilehash: e7528784f898f0f9ba84095b080eb82f8458424e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323883"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-c"></a><span data-ttu-id="cfd19-102">如何：查找具有特定子元素的元素 (C#)</span><span class="sxs-lookup"><span data-stu-id="cfd19-102">How to: Find an Element with a Specific Child Element (C#)</span></span>
<span data-ttu-id="cfd19-103">本主题演示如何查找特定元素，该特定元素包含具有特定值的子元素。</span><span class="sxs-lookup"><span data-stu-id="cfd19-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cfd19-104">示例</span><span class="sxs-lookup"><span data-stu-id="cfd19-104">Example</span></span>  
 <span data-ttu-id="cfd19-105">示例查找 `Test` 元素，该元素包含具有值为“Examp2.EXE”的 `CommandLine` 子元素。</span><span class="sxs-lookup"><span data-stu-id="cfd19-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="cfd19-106">本示例使用以下 XML 文档：[示例 XML 文件：测试配置 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd19-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("TestConfig.xml");  
IEnumerable<XElement> tests =  
    from el in root.Elements("Test")  
    where (string)el.Element("CommandLine") == "Examp2.EXE"  
    select el;  
foreach (XElement el in tests)  
    Console.WriteLine((string)el.Attribute("TestId"));  
```  
  
 <span data-ttu-id="cfd19-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="cfd19-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="example"></a><span data-ttu-id="cfd19-108">示例</span><span class="sxs-lookup"><span data-stu-id="cfd19-108">Example</span></span>  
 <span data-ttu-id="cfd19-109">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="cfd19-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="cfd19-110">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd19-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="cfd19-111">本示例使用以下 XML 文档：[示例 XML 文件：命名空间中的测试配置](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md)。</span><span class="sxs-lookup"><span data-stu-id="cfd19-111">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace1.md).</span></span>  
  
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
  
 <span data-ttu-id="cfd19-112">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="cfd19-112">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="cfd19-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfd19-113">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="cfd19-114">基本查询 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cfd19-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="cfd19-115">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="cfd19-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="cfd19-116">投影运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="cfd19-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
