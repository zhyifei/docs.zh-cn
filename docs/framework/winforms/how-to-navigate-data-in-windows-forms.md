---
title: 如何：在 Windows 窗体中导航数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- cursors [Windows Forms], data sources
- data sources [Windows Forms], Windows Forms
- Windows Forms, navigating
- CurrencyManager class [Windows Forms], navigating Windows Forms data
- data [Windows Forms], navigating
ms.assetid: 97360f7b-b181-4084-966a-4c62518f735b
ms.openlocfilehash: eb973497f51592b5d34c22e62da77612aec23c35
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964275"
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="23cc3-102">如何：在 Windows 窗体中导航数据</span><span class="sxs-lookup"><span data-stu-id="23cc3-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="23cc3-103">在 Windows 应用程序中, 在数据源中导航记录的最简单方法是将<xref:System.Windows.Forms.BindingSource>组件绑定到数据源, 然后将控件绑定<xref:System.Windows.Forms.BindingSource>到。</span><span class="sxs-lookup"><span data-stu-id="23cc3-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="23cc3-104">然后<xref:System.Windows.Forms.BindingSource> <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, 你可以在、 <xref:System.Windows.Forms.BindingSource.MoveLast%2A> <xref:System.Windows.Forms.BindingSource.MovePrevious%2A>和上使用内置的导航方法。<xref:System.Windows.Forms.BindingSource.MoveFirst%2A></span><span class="sxs-lookup"><span data-stu-id="23cc3-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="23cc3-105">使用这些方法会<xref:System.Windows.Forms.BindingSource.Position%2A> <xref:System.Windows.Forms.BindingSource>正确地调整<xref:System.Windows.Forms.BindingSource.Current%2A>和属性。</span><span class="sxs-lookup"><span data-stu-id="23cc3-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="23cc3-106">还可以通过设置<xref:System.Windows.Forms.BindingSource.Position%2A>属性来查找项并将其设置为当前项。</span><span class="sxs-lookup"><span data-stu-id="23cc3-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="23cc3-107">递增数据源中的位置</span><span class="sxs-lookup"><span data-stu-id="23cc3-107">To increment the position in a data source</span></span>  
  
1. <span data-ttu-id="23cc3-108">将绑定数据的的<xref:System.Windows.Forms.BindingSource> 属性设置为要定位到的记录位置。<xref:System.Windows.Forms.BindingSource.Position%2A></span><span class="sxs-lookup"><span data-stu-id="23cc3-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="23cc3-109"><xref:System.Windows.Forms.BindingSource.MoveNext%2A>下面的示例演示<xref:System.Windows.Forms.BindingSource>如何使用的方法在单击时`nextButton`递增<xref:System.Windows.Forms.BindingSource.Position%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="23cc3-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="23cc3-110"><xref:System.Windows.Forms.BindingSource>与dataset 的`Northwind`表相关联。 `Customers`</span><span class="sxs-lookup"><span data-stu-id="23cc3-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="23cc3-111"><xref:System.Windows.Forms.BindingSource.Position%2A>将属性设置为超出第一条或最后一条记录的值不会导致错误, 因为 .NET Framework 不允许将位置设置为列表边界以外的值。</span><span class="sxs-lookup"><span data-stu-id="23cc3-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the .NET Framework will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="23cc3-112">如果你的应用程序中有必要了解你是否已超出第一条或最后一条记录, 请包括用于测试是否会超出数据元素计数的逻辑。</span><span class="sxs-lookup"><span data-stu-id="23cc3-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="23cc3-113">检查是否已通过结尾或开头</span><span class="sxs-lookup"><span data-stu-id="23cc3-113">To check whether you have passed the end or beginning</span></span>  
  
1. <span data-ttu-id="23cc3-114">为 <xref:System.Windows.Forms.BindingSource.PositionChanged> 事件创建一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="23cc3-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="23cc3-115">在处理程序中, 你可以测试建议的位置值是否超过了实际的数据元素计数。</span><span class="sxs-lookup"><span data-stu-id="23cc3-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="23cc3-116">下面的示例演示如何测试是否已到达最后一个数据元素。</span><span class="sxs-lookup"><span data-stu-id="23cc3-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="23cc3-117">在此示例中, 如果您位于最后一个元素, 则窗体上的 "**下一步**" 按钮处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="23cc3-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="23cc3-118">请注意, 如果您在代码中导航列表, 应重新启用 "**下一步**" 按钮, 以便用户可以浏览新列表的整个长度。</span><span class="sxs-lookup"><span data-stu-id="23cc3-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="23cc3-119">此外, 请注意<xref:System.Windows.Forms.BindingSource.PositionChanged> , 所使用的特定<xref:System.Windows.Forms.BindingSource>的事件需要与其事件处理方法关联。</span><span class="sxs-lookup"><span data-stu-id="23cc3-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="23cc3-120">下面是用于处理<xref:System.Windows.Forms.BindingSource.PositionChanged>事件的方法的示例:</span><span class="sxs-lookup"><span data-stu-id="23cc3-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="23cc3-121">查找项并将其设置为当前项</span><span class="sxs-lookup"><span data-stu-id="23cc3-121">To find an item and set it as the current item</span></span>  
  
1. <span data-ttu-id="23cc3-122">查找要设置为当前项的记录。</span><span class="sxs-lookup"><span data-stu-id="23cc3-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="23cc3-123">如果数据源实现<xref:System.Windows.Forms.BindingSource.Find%2A> <xref:System.Windows.Forms.BindingSource> <xref:System.ComponentModel.IBindingList>, 则可以使用的方法执行此操作。</span><span class="sxs-lookup"><span data-stu-id="23cc3-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="23cc3-124">实现<xref:System.ComponentModel.IBindingList>的数据源的一些示例包括<xref:System.ComponentModel.BindingList%601>和<xref:System.Data.DataView>。</span><span class="sxs-lookup"><span data-stu-id="23cc3-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="23cc3-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="23cc3-125">See also</span></span>

- [<span data-ttu-id="23cc3-126">Windows 窗体支持的数据源</span><span class="sxs-lookup"><span data-stu-id="23cc3-126">Data Sources Supported by Windows Forms</span></span>](data-sources-supported-by-windows-forms.md)
- [<span data-ttu-id="23cc3-127">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="23cc3-127">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="23cc3-128">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="23cc3-128">Data Binding and Windows Forms</span></span>](data-binding-and-windows-forms.md)
- [<span data-ttu-id="23cc3-129">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="23cc3-129">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
