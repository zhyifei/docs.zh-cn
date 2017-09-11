---
title: "LINQ to XML 事件 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e2358808dfeafab1576a686563e6025f90e78954
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="d5a48-102">LINQ to XML 事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5a48-102">LINQ to XML Events (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="d5a48-103">事件让您可以在 XML 树发生改变时得到通知。</span><span class="sxs-lookup"><span data-stu-id="d5a48-103"> events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="d5a48-104">可以将事件添加到任何<xref:System.Xml.Linq.XObject>。</xref:System.Xml.Linq.XObject>实例</span><span class="sxs-lookup"><span data-stu-id="d5a48-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="d5a48-105">事件处理程序随后会收到进行修改时，事件<xref:System.Xml.Linq.XObject>及其所有子代。</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="d5a48-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="d5a48-106">例如，可以将事件处理程序添加到树根，然后从该事件处理程序中处理对树进行的所有修改。</span><span class="sxs-lookup"><span data-stu-id="d5a48-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="d5a48-107">有关的示例[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]事件，请参见<xref:System.Xml.Linq.XObject.Changing>和<xref:System.Xml.Linq.XObject.Changed>。</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="d5a48-107">For examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="d5a48-108">类型和事件</span><span class="sxs-lookup"><span data-stu-id="d5a48-108">Types and Events</span></span>  
 <span data-ttu-id="d5a48-109">在处理事件时使用下面的类型：</span><span class="sxs-lookup"><span data-stu-id="d5a48-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="d5a48-110">类型</span><span class="sxs-lookup"><span data-stu-id="d5a48-110">Type</span></span>|<span data-ttu-id="d5a48-111">说明</span><span class="sxs-lookup"><span data-stu-id="d5a48-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="d5a48-112"><xref:System.Xml.Linq.XObjectChange></xref:System.Xml.Linq.XObjectChange></span><span class="sxs-lookup"><span data-stu-id="d5a48-112"><xref:System.Xml.Linq.XObjectChange></span></span>|<span data-ttu-id="d5a48-113">以团队<xref:System.Xml.Linq.XObject>。</xref:System.Xml.Linq.XObject>引发事件时指定的事件类型</span><span class="sxs-lookup"><span data-stu-id="d5a48-113">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="d5a48-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></xref:System.Xml.Linq.XObjectChangeEventArgs></span><span class="sxs-lookup"><span data-stu-id="d5a48-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></span></span>|<span data-ttu-id="d5a48-115">将提供数据供<xref:System.Xml.Linq.XObject.Changing>和<xref:System.Xml.Linq.XObject.Changed>事件。</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="d5a48-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="d5a48-116">修改 XML 树时将引发以下事件：</span><span class="sxs-lookup"><span data-stu-id="d5a48-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="d5a48-117">Event</span><span class="sxs-lookup"><span data-stu-id="d5a48-117">Event</span></span>|<span data-ttu-id="d5a48-118">描述</span><span class="sxs-lookup"><span data-stu-id="d5a48-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d5a48-119"><xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="d5a48-119"><xref:System.Xml.Linq.XObject.Changing></span></span>|<span data-ttu-id="d5a48-120">这前发生<xref:System.Xml.Linq.XObject>或其任何子代即将更改。</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="d5a48-120">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<span data-ttu-id="d5a48-121"><xref:System.Xml.Linq.XObject.Changed></xref:System.Xml.Linq.XObject.Changed></span><span class="sxs-lookup"><span data-stu-id="d5a48-121"><xref:System.Xml.Linq.XObject.Changed></span></span>|<span data-ttu-id="d5a48-122">发生时<xref:System.Xml.Linq.XObject>已更改或已改变的任何子代。</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="d5a48-122">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d5a48-123">示例</span><span class="sxs-lookup"><span data-stu-id="d5a48-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="d5a48-124">描述</span><span class="sxs-lookup"><span data-stu-id="d5a48-124">Description</span></span>  
 <span data-ttu-id="d5a48-125">当您希望在 XML 树中保留一些聚合信息时事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="d5a48-125">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="d5a48-126">例如，您可能想保留一份发票合计，计算发票上各个项目的总和。</span><span class="sxs-lookup"><span data-stu-id="d5a48-126">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="d5a48-127">本示例使用事件来维护复杂元素 `Items` 之下所有子元素的总和。</span><span class="sxs-lookup"><span data-stu-id="d5a48-127">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="d5a48-128">代码</span><span class="sxs-lookup"><span data-stu-id="d5a48-128">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="d5a48-129">注释</span><span class="sxs-lookup"><span data-stu-id="d5a48-129">Comments</span></span>  
 <span data-ttu-id="d5a48-130">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="d5a48-130">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="d5a48-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5a48-131">See Also</span></span>  
 [<span data-ttu-id="d5a48-132">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d5a48-132">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
