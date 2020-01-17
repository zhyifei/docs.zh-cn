---
title: 如何检索单个特性 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 1b6b07b9-933f-47e9-874e-e790cab49dc5
ms.openlocfilehash: 31b34bddc9e748b473641235402847991d444c39
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347492"
---
# <a name="how-to-retrieve-a-single-attribute-linq-to-xml-c"></a><span data-ttu-id="ab176-102">如何检索单个特性 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ab176-102">How to retrieve a single attribute (LINQ to XML) (C#)</span></span>
<span data-ttu-id="ab176-103">本主题说明在给定属性名称的情况下，如何检索元素的单个属性。</span><span class="sxs-lookup"><span data-stu-id="ab176-103">This topic explains how to retrieve a single attribute of an element, given the attribute name.</span></span> <span data-ttu-id="ab176-104">这对于编写查询表达式查找具有特定属性的元素十分有用。</span><span class="sxs-lookup"><span data-stu-id="ab176-104">This is useful for writing query expressions where you want to find an element that has a particular attribute.</span></span>  
  
 <span data-ttu-id="ab176-105"><xref:System.Xml.Linq.XElement.Attribute%2A> 类的 <xref:System.Xml.Linq.XElement> 方法返回具有指定名称的 <xref:System.Xml.Linq.XAttribute>。</span><span class="sxs-lookup"><span data-stu-id="ab176-105">The <xref:System.Xml.Linq.XElement.Attribute%2A> method of the <xref:System.Xml.Linq.XElement> class returns the <xref:System.Xml.Linq.XAttribute> with the specified name.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab176-106">示例</span><span class="sxs-lookup"><span data-stu-id="ab176-106">Example</span></span>  
 <span data-ttu-id="ab176-107">下面的示例使用 <xref:System.Xml.Linq.XElement.Attribute%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="ab176-107">The following example uses the <xref:System.Xml.Linq.XElement.Attribute%2A> method.</span></span>  
  
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
  
 <span data-ttu-id="ab176-108">本示例首先在名为 `Phone` 的树中查找所有后代，然后查找名为 `type` 的属性。</span><span class="sxs-lookup"><span data-stu-id="ab176-108">This example finds all the descendants in the tree named `Phone`, and then finds the attribute named `type`.</span></span>  
  
 <span data-ttu-id="ab176-109">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="ab176-109">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="example"></a><span data-ttu-id="ab176-110">示例</span><span class="sxs-lookup"><span data-stu-id="ab176-110">Example</span></span>  
 <span data-ttu-id="ab176-111">如果希望检索属性的值，可以强制转换该值，就像使用 <xref:System.Xml.Linq.XElement> 对象时一样。</span><span class="sxs-lookup"><span data-stu-id="ab176-111">If you want to retrieve the value of the attribute, you can cast it, just as you do for with <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="ab176-112">下面的示例演示这一操作。</span><span class="sxs-lookup"><span data-stu-id="ab176-112">The following example demonstrates this.</span></span>  
  
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
  
 <span data-ttu-id="ab176-113">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="ab176-113">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="ab176-114">为 <xref:System.Xml.Linq.XAttribute> 类提供了以下类型的显式强制转换运算符：`string`、`bool`、`bool?`、`int`、`int?`、`uint`、`uint?`、`long`、`long?`、`ulong`、`ulong?`、`float`、`float?`、`double`、`double?`、`decimal`、`decimal?`、`DateTime`、`DateTime?`、`TimeSpan`、`TimeSpan?`、`GUID` 和 `GUID?`。</span><span class="sxs-lookup"><span data-stu-id="ab176-114">provides explicit cast operators for the <xref:System.Xml.Linq.XAttribute> class to `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ab176-115">示例</span><span class="sxs-lookup"><span data-stu-id="ab176-115">Example</span></span>  
 <span data-ttu-id="ab176-116">下面的示例显式命名空间中的属性的相同代码。</span><span class="sxs-lookup"><span data-stu-id="ab176-116">The following example shows the same code for an attribute that is in a namespace.</span></span> <span data-ttu-id="ab176-117">有关详细信息，请参阅[命名空间概述(LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="ab176-117">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="ab176-118">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="ab176-118">This code produces the following output:</span></span>  
  
```output  
home  
work  
```  
  
## <a name="see-also"></a><span data-ttu-id="ab176-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab176-119">See also</span></span>

- [<span data-ttu-id="ab176-120">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="ab176-120">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
