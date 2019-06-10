---
title: 如何：检索单个特性 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: cfab2cbb80eb330a5fd745871eb272cca0b37798
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486440"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="e2d95-102">如何：检索单个特性 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e2d95-102">How to: Retrieve a Single Attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e2d95-103">本主题说明在给定属性名称的情况下，如何检索元素的单个属性。</span><span class="sxs-lookup"><span data-stu-id="e2d95-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="e2d95-104">这对于编写查询表达式查找具有特定属性的元素十分有用。</span><span class="sxs-lookup"><span data-stu-id="e2d95-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="e2d95-105"><xref:System.Xml.Linq.XElement.Attribute%2A> 类的 <xref:System.Xml.Linq.XElement> 方法返回具有指定名称的 <xref:System.Xml.Linq.XAttribute>。</span><span class="sxs-lookup"><span data-stu-id="e2d95-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2d95-106">示例</span><span class="sxs-lookup"><span data-stu-id="e2d95-106">Example</span></span>  
 <span data-ttu-id="e2d95-107">下面的示例使用 <xref:System.Xml.Linq.XElement.Attribute%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="e2d95-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="e2d95-108">本示例首先在名为 `Phone` 的树中查找所有后代，然后查找名为 `type` 的属性。</span><span class="sxs-lookup"><span data-stu-id="e2d95-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="e2d95-109">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="e2d95-109">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="e2d95-110">示例</span><span class="sxs-lookup"><span data-stu-id="e2d95-110">Example</span></span>  
 <span data-ttu-id="e2d95-111">如果希望检索属性的值，可以强制转换该值，就像使用 <xref:System.Xml.Linq.XElement> 对象时一样。</span><span class="sxs-lookup"><span data-stu-id="e2d95-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="e2d95-112">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="e2d95-112">The following example demonstrates this.</span></span>  
  
```csharp  
XElement cust = new XElement("PhoneNumbers",  
    new XElement("Phone",  
        new XAttribute("type", "home"),  
        "555-555-5555"),  
    new XElement("Phone",  
        new XAttribute("type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =   
    from el in cust.Descendants("Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute("type"));  
```  
  
 <span data-ttu-id="e2d95-113">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="e2d95-113">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="e2d95-114">为 <xref:System.Xml.Linq.XAttribute> 类提供了以下类型的显式强制转换运算符：`string`、`bool`、`bool?`、`int`、`int?`、`uint`、`uint?`、`long`、`long?`、`ulong`、`ulong?`、`float`、`float?`、`double`、`double?`、`decimal`、`decimal?`、`DateTime`、`DateTime?`、`TimeSpan`、`TimeSpan?`、`GUID` 和 `GUID?`。</span><span class="sxs-lookup"><span data-stu-id="e2d95-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e2d95-115">示例</span><span class="sxs-lookup"><span data-stu-id="e2d95-115">Example</span></span>  
 <span data-ttu-id="e2d95-116">下面的示例显式命名空间中的属性的相同代码。</span><span class="sxs-lookup"><span data-stu-id="e2d95-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="e2d95-117">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="e2d95-117">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/namespaces-overview-linq-to-xml.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement cust = new XElement(aw + "PhoneNumbers",  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "home"),  
        "555-555-5555"),  
    new XElement(aw + "Phone",  
        new XAttribute(aw + "type", "work"),  
        "555-555-6666")  
);  
IEnumerable<XElement> elList =  
    from el in cust.Descendants(aw + "Phone")  
    select el;  
foreach (XElement el in elList)  
    Console.WriteLine((string)el.Attribute(aw + "type"));  
```  
  
 <span data-ttu-id="e2d95-118">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="e2d95-118">This code produces the following output:</span></span>  
  
```  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2d95-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2d95-119">See also</span></span>

- [<span data-ttu-id="e2d95-120">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="e2d95-120">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes-overview.md)
