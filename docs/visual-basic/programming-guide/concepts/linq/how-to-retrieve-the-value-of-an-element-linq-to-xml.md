---
title: "如何︰ 检索元素 (LINQ to XML) 的值 (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 76b9b2a5-b3ba-49da-ba74-82100e1bd21c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: be5eebc382f83819fd978554f830b6ba12227902
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-visual-basic"></a><span data-ttu-id="57dd6-102">如何︰ 检索元素 (LINQ to XML) 的值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57dd6-102">How to: Retrieve the Value of an Element (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="57dd6-103">本主题演示如何获取元素的值。</span><span class="sxs-lookup"><span data-stu-id="57dd6-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="57dd6-104">有两种主要方法可以完成此操作。</span><span class="sxs-lookup"><span data-stu-id="57dd6-104">There are two main ways to do this.</span></span> <span data-ttu-id="57dd6-105">一种方法是将强制转换<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>到所需的类型。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="57dd6-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="57dd6-106">然后，显式转换运算符将元素或属性的内容转换为指定的类型，并将其分配给变量。</span><span class="sxs-lookup"><span data-stu-id="57dd6-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="57dd6-107">或者，可以使用<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>属性或<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>属性。</xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="57dd6-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName> property.</span></span>  
  
 <span data-ttu-id="57dd6-108">对于 Visual Basic，最好的方法是使用<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>属性。</xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="57dd6-108">With Visual Basic, the best approach is to use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57dd6-109">示例</span><span class="sxs-lookup"><span data-stu-id="57dd6-109">Example</span></span>  
 <span data-ttu-id="57dd6-110">若要检索的元素的值，只需转换<xref:System.Xml.Linq.XElement>对象传递给所需的类型。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="57dd6-110">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="57dd6-111">任何时候都可以将元素强制转换为字符串，如下所示：</span><span class="sxs-lookup"><span data-stu-id="57dd6-111">You can always cast an element to a string, as follows:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="57dd6-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="57dd6-112">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="57dd6-113">示例</span><span class="sxs-lookup"><span data-stu-id="57dd6-113">Example</span></span>  
 <span data-ttu-id="57dd6-114">此外，还可以将元素强制转换为字符串以外的其他类型。</span><span class="sxs-lookup"><span data-stu-id="57dd6-114">You can also cast elements to types other than string.</span></span> <span data-ttu-id="57dd6-115">例如，如果有一个包含一个整数的元素，可以将它强制转换为 `int`，如下面的代码所示：</span><span class="sxs-lookup"><span data-stu-id="57dd6-115">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```vb  
Dim e As XElement = <Age>44</Age>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & CInt(e))  
```  
  
 <span data-ttu-id="57dd6-116">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="57dd6-116">This example produces the following output:</span></span>  
  
```  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="57dd6-117"> 提供了以下数据类型的显式强制转换运算符：`string`、`bool`、`bool?`、`int`、`int?`、`uint`、`uint?`、`long`、`long?`、`ulong`、`ulong?`、`float`、`float?`、`double`、`double?`、`decimal`、`decimal?`、`DateTime`、`DateTime?`、`TimeSpan`、`TimeSpan?`、`GUID` 和 `GUID?`。</span><span class="sxs-lookup"><span data-stu-id="57dd6-117"> provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="57dd6-118">提供的相同的强制转换运算符<xref:System.Xml.Linq.XAttribute>对象。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="57dd6-118"> provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="57dd6-119">示例</span><span class="sxs-lookup"><span data-stu-id="57dd6-119">Example</span></span>  
 <span data-ttu-id="57dd6-120">您可以使用<xref:System.Xml.Linq.XElement.Value%2A>属性来检索元素的内容︰</xref:System.Xml.Linq.XElement.Value%2A></span><span class="sxs-lookup"><span data-stu-id="57dd6-120">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```vb  
Dim e As XElement = <StringElement>abcde</StringElement>  
Console.WriteLine(e)  
Console.WriteLine("Value of e:" & e.Value)  
```  
  
 <span data-ttu-id="57dd6-121">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="57dd6-121">This example produces the following output:</span></span>  
  
```  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="57dd6-122">示例</span><span class="sxs-lookup"><span data-stu-id="57dd6-122">Example</span></span>  
 <span data-ttu-id="57dd6-123">有时，尽管不能确定某个元素是否存在，还是会尝试检索该元素的值。</span><span class="sxs-lookup"><span data-stu-id="57dd6-123">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="57dd6-124">在这种情况下，当您将分配的强制转换后的元素为 null 的类型 (或者`string`或中可以为 null 的类型之一[!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)])，如果该元素不存在则将分配变量设置为`Nothing`。</span><span class="sxs-lookup"><span data-stu-id="57dd6-124">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)]), if the element does not exist the assigned variable is just set to `Nothing`.</span></span> <span data-ttu-id="57dd6-125">下面的代码演示当元素可能存在也可能不存在，它更加轻松地使用强制转换比使用<xref:System.Xml.Linq.XElement.Value%2A>属性。</xref:System.Xml.Linq.XElement.Value%2A></span><span class="sxs-lookup"><span data-stu-id="57dd6-125">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```vb  
Dim root As XElement = <Root>  
                           <Child1>child 1 content</Child1>  
                           <Child2>2</Child2>  
                       </Root>  
  
' The following assignments show why it is easier to use  
' casting when the element might or might not exist.  
  
Dim c1 As String = CStr(root.Element("Child1"))  
Console.WriteLine("c1:{0}", IIf(c1 Is Nothing, "element does not exist", c1))  
  
Dim c2 As Nullable(Of Integer) = CType(root.Element("Child2"), Nullable(Of Integer))  
Console.WriteLine("c2:{0}", IIf(Not (c2.HasValue), "element does not exist", c2.ToString()))  
  
Dim c3 As String = CStr(root.Element("Child3"))  
Console.WriteLine("c3:{0}", IIf(c3 Is Nothing, "element does not exist", c3))  
  
Dim c4 As Nullable(Of Integer) = CType(root.Element("Child4"), Nullable(Of Integer))  
Console.WriteLine("c4:{0}", IIf(Not (c4.HasValue), "element does not exist", c4.ToString()))  
  
Console.WriteLine()  
  
' The following assignments show the required code when using  
' the Value property when the attribute might or might not exist.  
' Notice that this is more difficult than the casting approach.  
  
Dim e1 As XElement = root.Element("Child1")  
Dim v1 As String  
If (e1 Is Nothing) Then  
    v1 = Nothing  
Else  
    v1 = e1.Value  
End If  
Console.WriteLine("v1:{0}", IIf(v1 Is Nothing, "element does not exist", v1))  
  
Dim e2 As XElement = root.Element("Child2")  
Dim v2 As Nullable(Of Integer)  
If (e2 Is Nothing) Then  
    v2 = Nothing  
Else  
    v2 = e2.Value  
End If  
Console.WriteLine("v2:{0}", IIf(Not (v2.HasValue), "element does not exist", v2))  
  
Dim e3 As XElement = root.Element("Child3")  
Dim v3 As String  
If (e3 Is Nothing) Then  
    v3 = Nothing  
Else  
    v3 = e3.Value  
End If  
Console.WriteLine("v3:{0}", IIf(v3 Is Nothing, "element does not exist", v3))  
  
Dim e4 As XElement = root.Element("Child4")  
Dim v4 As Nullable(Of Integer)  
If (e4 Is Nothing) Then  
    v4 = Nothing  
Else  
    v4 = e4.Value  
End If  
Console.WriteLine("v4:{0}", IIf(Not (v4.HasValue), "element does not exist", v4))  
```  
  
 <span data-ttu-id="57dd6-126">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="57dd6-126">This code produces the following output:</span></span>  
  
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
  
 <span data-ttu-id="57dd6-127">通常情况下，当使用强制转换来检索元素和属性的内容时，可以编写更简易的代码。</span><span class="sxs-lookup"><span data-stu-id="57dd6-127">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57dd6-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57dd6-128">See Also</span></span>  
 [<span data-ttu-id="57dd6-129">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="57dd6-129">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
