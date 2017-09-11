---
title: "如何：检索元素的值 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 70e60c799157c7aa577bb8abd1fa6aaad746d3d1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="e48f6-102">如何：检索元素的值 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e48f6-102">How to: Retrieve the Value of an Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="e48f6-103">本主题演示如何获取元素的值。</span><span class="sxs-lookup"><span data-stu-id="e48f6-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="e48f6-104">有两种主要方法可以完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e48f6-104">There are two main ways to do this.</span></span> <span data-ttu-id="e48f6-105">一种方法是将 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XAttribute> 强制转换为所需的类型。</span><span class="sxs-lookup"><span data-stu-id="e48f6-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="e48f6-106">然后，显式转换运算符将元素或属性的内容转换为指定的类型，并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="e48f6-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="e48f6-107">此外，还可以使用 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> 属性或 <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> 属性。</span><span class="sxs-lookup"><span data-stu-id="e48f6-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> property.</span></span>  
  
 <span data-ttu-id="e48f6-108">但是，对于 C#，强制转换通常是更好的方法。</span><span class="sxs-lookup"><span data-stu-id="e48f6-108">With C#, however, casting is generally the better approach.</span></span> <span data-ttu-id="e48f6-109">在检索可能存在也可能不存在的元素（或属性）的值时，如果将元素或属性强制转换为可以为 null 的类型，则代码会更易于编写。</span><span class="sxs-lookup"><span data-stu-id="e48f6-109">If you cast the element or attribute to a nullable type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="e48f6-110">本主题最后一个示例对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="e48f6-110">The last example in this topic demonstrates this.</span></span> <span data-ttu-id="e48f6-111">但是，无法通过强制转换设置元素的内容，而通过 <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> 属性可以做到这一点。</span><span class="sxs-lookup"><span data-stu-id="e48f6-111">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e48f6-112">示例</span><span class="sxs-lookup"><span data-stu-id="e48f6-112">Example</span></span>  
 <span data-ttu-id="e48f6-113">若要检索元素的值，只需将 <xref:System.Xml.Linq.XElement> 对象强制转换为所需的类型即可。</span><span class="sxs-lookup"><span data-stu-id="e48f6-113">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="e48f6-114">任何时候都可以将元素强制转换为字符串，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e48f6-114">You can always cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="e48f6-115">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="e48f6-115">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="e48f6-116">示例</span><span class="sxs-lookup"><span data-stu-id="e48f6-116">Example</span></span>  
 <span data-ttu-id="e48f6-117">此外，还可以将元素强制转换为字符串以外的其他类型。</span><span class="sxs-lookup"><span data-stu-id="e48f6-117">You can also cast elements to types other than string.</span></span> <span data-ttu-id="e48f6-118">例如，如果有一个包含一个整数的元素，可以将它强制转换为 `int`，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="e48f6-118">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="e48f6-119">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="e48f6-119">This example produces the following output:</span></span>  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="e48f6-120"> 提供了以下数据类型的显式强制转换运算符：`string`、`bool`、`bool?`、`int`、`int?`、`uint`、`uint?`、`long`、`long?`、`ulong`、`ulong?`、`float`、`float?`、`double`、`double?`、`decimal`、`decimal?`、`DateTime`、`DateTime?`、`TimeSpan`、`TimeSpan?`、`GUID` 和 `GUID?`。</span><span class="sxs-lookup"><span data-stu-id="e48f6-120"> provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="e48f6-121"> 为 <xref:System.Xml.Linq.XAttribute> 对象提供了相同的强制转换运算符。</span><span class="sxs-lookup"><span data-stu-id="e48f6-121"> provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e48f6-122">示例</span><span class="sxs-lookup"><span data-stu-id="e48f6-122">Example</span></span>  
 <span data-ttu-id="e48f6-123">可以使用 <xref:System.Xml.Linq.XElement.Value%2A> 属性来检索元素的内容：</span><span class="sxs-lookup"><span data-stu-id="e48f6-123">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");   
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="e48f6-124">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="e48f6-124">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="e48f6-125">示例</span><span class="sxs-lookup"><span data-stu-id="e48f6-125">Example</span></span>  
 <span data-ttu-id="e48f6-126">有时，尽管不能确定某个元素是否存在，还是会尝试检索该元素的值。</span><span class="sxs-lookup"><span data-stu-id="e48f6-126">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="e48f6-127">在这种情况下，将强制转换后的元素分配给可以为 null 的类型（`string` 或 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] 中可以为 null 的类型之一）时，如果该元素不存在，则将分配的变量设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e48f6-127">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]), if the element does not exist the assigned variable is just set to `null`.</span></span> <span data-ttu-id="e48f6-128">下面的代码演示当元素可能存在也可能不存在时，使用强制转换比使用 <xref:System.Xml.Linq.XElement.Value%2A> 属性更加简单。</span><span class="sxs-lookup"><span data-stu-id="e48f6-128">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="e48f6-129">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="e48f6-129">This code produces the following output:</span></span>  
  
```  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="e48f6-130">通常情况下，当使用强制转换来检索元素和属性的内容时，可以编写更简易的代码。</span><span class="sxs-lookup"><span data-stu-id="e48f6-130">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e48f6-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="e48f6-131">See Also</span></span>  
 [<span data-ttu-id="e48f6-132">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="e48f6-132">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

