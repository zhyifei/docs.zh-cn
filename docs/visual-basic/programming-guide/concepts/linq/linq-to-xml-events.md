---
title: LINQ to XML 事件 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
ms.openlocfilehash: 216c2af87d2ae3a767548ccaa1efe118215cc6a0
ms.sourcegitcommit: 70c76a12449439bac0f7a359866be5a0311ce960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2018
ms.locfileid: "39245281"
---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="a2280-102">LINQ to XML 事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2280-102">LINQ to XML Events (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="a2280-103"> 事件使你可以在 XML 树发生改变时得到通知。</span><span class="sxs-lookup"><span data-stu-id="a2280-103"> events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="a2280-104">可以将事件添加到任何 <xref:System.Xml.Linq.XObject> 的实例。</span><span class="sxs-lookup"><span data-stu-id="a2280-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="a2280-105">事件处理程序然后将接收对该 <xref:System.Xml.Linq.XObject> 及其所有子代进行修改的事件。</span><span class="sxs-lookup"><span data-stu-id="a2280-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="a2280-106">例如，可以将事件处理程序添加到树根，然后从该事件处理程序中处理对树进行的所有修改。</span><span class="sxs-lookup"><span data-stu-id="a2280-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="a2280-107">有关 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 事件的示例，请参阅 <xref:System.Xml.Linq.XObject.Changing> 和 <xref:System.Xml.Linq.XObject.Changed>。</span><span class="sxs-lookup"><span data-stu-id="a2280-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="a2280-108">类型和事件</span><span class="sxs-lookup"><span data-stu-id="a2280-108">Types and Events</span></span>  
 <span data-ttu-id="a2280-109">在处理事件时使用下面的类型：</span><span class="sxs-lookup"><span data-stu-id="a2280-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="a2280-110">类型</span><span class="sxs-lookup"><span data-stu-id="a2280-110">Type</span></span>|<span data-ttu-id="a2280-111">描述</span><span class="sxs-lookup"><span data-stu-id="a2280-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="a2280-112">当 <xref:System.Xml.Linq.XObject> 发生事件时指定事件类型。</span><span class="sxs-lookup"><span data-stu-id="a2280-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="a2280-113">提供有关 <xref:System.Xml.Linq.XObject.Changing> 和 <xref:System.Xml.Linq.XObject.Changed> 事件的数据。</span><span class="sxs-lookup"><span data-stu-id="a2280-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="a2280-114">修改 XML 树时将引发以下事件：</span><span class="sxs-lookup"><span data-stu-id="a2280-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="a2280-115">Event</span><span class="sxs-lookup"><span data-stu-id="a2280-115">Event</span></span>|<span data-ttu-id="a2280-116">描述</span><span class="sxs-lookup"><span data-stu-id="a2280-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="a2280-117">在此 <xref:System.Xml.Linq.XObject> 或它的任何子代即将发生更改之前发生。</span><span class="sxs-lookup"><span data-stu-id="a2280-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="a2280-118">在 <xref:System.Xml.Linq.XObject> 或它的任何子代已经更改时发生。</span><span class="sxs-lookup"><span data-stu-id="a2280-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a2280-119">示例</span><span class="sxs-lookup"><span data-stu-id="a2280-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="a2280-120">描述</span><span class="sxs-lookup"><span data-stu-id="a2280-120">Description</span></span>  
 <span data-ttu-id="a2280-121">当您希望在 XML 树中保留一些聚合信息时事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="a2280-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="a2280-122">例如，您可能想保留一份发票合计，计算发票上各个项目的总和。</span><span class="sxs-lookup"><span data-stu-id="a2280-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="a2280-123">本示例使用事件来维护复杂元素 `Items` 之下所有子元素的总和。</span><span class="sxs-lookup"><span data-stu-id="a2280-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="a2280-124">代码</span><span class="sxs-lookup"><span data-stu-id="a2280-124">Code</span></span>  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="a2280-125">注释</span><span class="sxs-lookup"><span data-stu-id="a2280-125">Comments</span></span>  
 <span data-ttu-id="a2280-126">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="a2280-126">This code produces the following output:</span></span>  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a2280-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2280-127">See Also</span></span>  
 [<span data-ttu-id="a2280-128">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a2280-128">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
