---
title: 如何：通过 LINQ to XML 使用字典 (C#)
ms.date: 07/20/2015
ms.assetid: 57bcefe3-8433-4d3b-935a-511c9bcbdfa8
ms.openlocfilehash: 3f3b2a19f2527ef5d2fececf916c09256e90af7b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319866"
---
# <a name="how-to-work-with-dictionaries-using-linq-to-xml-c"></a><span data-ttu-id="04d15-102">如何：通过 LINQ to XML 使用字典 (C#)</span><span class="sxs-lookup"><span data-stu-id="04d15-102">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>
<span data-ttu-id="04d15-103">通常需要将各种数据结构转换为 XML 和将 XML 转换回其他数据结构。</span><span class="sxs-lookup"><span data-stu-id="04d15-103">It is often convenient to convert varieties of data structures to XML, and XML back to other data structures.</span></span> <span data-ttu-id="04d15-104">本主题通过 <xref:System.Collections.Generic.Dictionary%602> 和 XML 的相互转换演示这一常规方法的具体实现。</span><span class="sxs-lookup"><span data-stu-id="04d15-104">This topic shows a specific implementation of this general approach by converting a <xref:System.Collections.Generic.Dictionary%602> to XML and back.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04d15-105">示例</span><span class="sxs-lookup"><span data-stu-id="04d15-105">Example</span></span>  
 <span data-ttu-id="04d15-106">本示例使用函数构造形式：查询投影新 <xref:System.Xml.Linq.XElement> 对象，生成的集合作为自变量传递给根 <xref:System.Xml.Linq.XElement> 对象的构造函数。</span><span class="sxs-lookup"><span data-stu-id="04d15-106">This example uses a form of functional construction in which a query projects new <xref:System.Xml.Linq.XElement> objects, and the resulting collection is passed as an argument to the constructor of the Root <xref:System.Xml.Linq.XElement> object.</span></span>  
  
```csharp  
Dictionary<string, string> dict = new Dictionary<string, string>();  
dict.Add("Child1", "Value1");  
dict.Add("Child2", "Value2");  
dict.Add("Child3", "Value3");  
dict.Add("Child4", "Value4");  
XElement root = new XElement("Root",  
    from keyValue in dict  
    select new XElement(keyValue.Key, keyValue.Value)  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="04d15-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="04d15-107">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>Value1</Child1>  
  <Child2>Value2</Child2>  
  <Child3>Value3</Child3>  
  <Child4>Value4</Child4>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="04d15-108">示例</span><span class="sxs-lookup"><span data-stu-id="04d15-108">Example</span></span>  
 <span data-ttu-id="04d15-109">下面的代码从 XML 创建一个字典。</span><span class="sxs-lookup"><span data-stu-id="04d15-109">The following code creates a dictionary from XML.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "Value1"),  
    new XElement("Child2", "Value2"),  
    new XElement("Child3", "Value3"),  
    new XElement("Child4", "Value4")  
);  
  
Dictionary<string, string> dict = new Dictionary<string, string>();  
foreach (XElement el in root.Elements())  
    dict.Add(el.Name.LocalName, el.Value);  
foreach (string str in dict.Keys)  
    Console.WriteLine("{0}:{1}", str, dict[str]);  
```  
  
 <span data-ttu-id="04d15-110">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="04d15-110">This code produces the following output:</span></span>  
  
```  
Child1:Value1  
Child2:Value2  
Child3:Value3  
Child4:Value4  
```  
  
## <a name="see-also"></a><span data-ttu-id="04d15-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="04d15-111">See Also</span></span>  
 [<span data-ttu-id="04d15-112">投影和转换 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="04d15-112">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
