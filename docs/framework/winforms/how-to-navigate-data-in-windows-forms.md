---
title: "如何：在 Windows 窗体中导航数据"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7c754bba18e93f63306701381f66af04b593c473
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-data-in-windows-forms"></a><span data-ttu-id="532f8-102">如何：在 Windows 窗体中导航数据</span><span class="sxs-lookup"><span data-stu-id="532f8-102">How to: Navigate Data in Windows Forms</span></span>
<span data-ttu-id="532f8-103">在 Windows 应用程序，以浏览数据源中的记录的最简单方法是将绑定<xref:System.Windows.Forms.BindingSource>组件到数据源，然后将控件绑定到<xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="532f8-103">In a Windows application, the easiest way to navigate through records in a data source is to bind a <xref:System.Windows.Forms.BindingSource> component to the data source and then bind controls to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="532f8-104">你可以然后使用内置的导航方法上,<xref:System.Windows.Forms.BindingSource>此类<xref:System.Windows.Forms.BindingSource.MoveNext%2A>， <xref:System.Windows.Forms.BindingSource.MoveLast%2A>，<xref:System.Windows.Forms.BindingSource.MovePrevious%2A>和<xref:System.Windows.Forms.BindingSource.MoveFirst%2A>。</span><span class="sxs-lookup"><span data-stu-id="532f8-104">You can then use the built-in navigation method on the <xref:System.Windows.Forms.BindingSource> such a <xref:System.Windows.Forms.BindingSource.MoveNext%2A>, <xref:System.Windows.Forms.BindingSource.MoveLast%2A>, <xref:System.Windows.Forms.BindingSource.MovePrevious%2A> and <xref:System.Windows.Forms.BindingSource.MoveFirst%2A>.</span></span> <span data-ttu-id="532f8-105">使用这些方法将调整<xref:System.Windows.Forms.BindingSource.Position%2A>和<xref:System.Windows.Forms.BindingSource.Current%2A>属性<xref:System.Windows.Forms.BindingSource>正确。</span><span class="sxs-lookup"><span data-stu-id="532f8-105">Using these methods will adjust the <xref:System.Windows.Forms.BindingSource.Position%2A> and <xref:System.Windows.Forms.BindingSource.Current%2A> properties of the <xref:System.Windows.Forms.BindingSource> appropriately.</span></span> <span data-ttu-id="532f8-106">此外可以查找某个项，并将其设置为当前项，通过设置<xref:System.Windows.Forms.BindingSource.Position%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="532f8-106">You can also find an item and set it as the current item by setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property.</span></span>  
  
### <a name="to-increment-the-position-in-a-data-source"></a><span data-ttu-id="532f8-107">若要递增的数据源中的位置</span><span class="sxs-lookup"><span data-stu-id="532f8-107">To increment the position in a data source</span></span>  
  
1.  <span data-ttu-id="532f8-108">设置<xref:System.Windows.Forms.BindingSource.Position%2A>属性<xref:System.Windows.Forms.BindingSource>绑定到记录的位置以转到数据。</span><span class="sxs-lookup"><span data-stu-id="532f8-108">Set the <xref:System.Windows.Forms.BindingSource.Position%2A> property of the <xref:System.Windows.Forms.BindingSource> for your bound data to the record position to go to.</span></span> <span data-ttu-id="532f8-109">下面的示例演示如何使用<xref:System.Windows.Forms.BindingSource.MoveNext%2A>方法<xref:System.Windows.Forms.BindingSource>递增<xref:System.Windows.Forms.BindingSource.Position%2A>属性时`nextButton`单击。</span><span class="sxs-lookup"><span data-stu-id="532f8-109">The following example illustrates using the <xref:System.Windows.Forms.BindingSource.MoveNext%2A> method of the <xref:System.Windows.Forms.BindingSource> to increment the <xref:System.Windows.Forms.BindingSource.Position%2A> property when the `nextButton` is clicked.</span></span> <span data-ttu-id="532f8-110"><xref:System.Windows.Forms.BindingSource>与关联`Customers`数据集的表`Northwind`。</span><span class="sxs-lookup"><span data-stu-id="532f8-110">The <xref:System.Windows.Forms.BindingSource> is associated with the `Customers` table of a dataset `Northwind`.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="532f8-111">设置<xref:System.Windows.Forms.BindingSource.Position%2A>属性的第一个或最后一个记录之外的值不会导致错误，作为[!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]不允许你将位置设置为的值超出了列表的界限。</span><span class="sxs-lookup"><span data-stu-id="532f8-111">Setting the <xref:System.Windows.Forms.BindingSource.Position%2A> property to a value beyond the first or last record does not result in an error, as the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] will not allow you to set the position to a value outside the bounds of the list.</span></span> <span data-ttu-id="532f8-112">如果这很重要应用程序，以了解是否已越过的第一个或最后一个记录中，包括逻辑来测试是否将超过数据元素计数。</span><span class="sxs-lookup"><span data-stu-id="532f8-112">If it is important in your application to know whether you have gone past the first or last record, include logic to test whether you will exceed the data element count.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.NavigatingData#4](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#4)]  
  
### <a name="to-check-whether-you-have-passed-the-end-or-beginning"></a><span data-ttu-id="532f8-113">若要检查是否已通过末尾或开头</span><span class="sxs-lookup"><span data-stu-id="532f8-113">To check whether you have passed the end or beginning</span></span>  
  
1.  <span data-ttu-id="532f8-114">为 <xref:System.Windows.Forms.BindingSource.PositionChanged> 事件创建一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="532f8-114">Create an event handler for the <xref:System.Windows.Forms.BindingSource.PositionChanged> event.</span></span> <span data-ttu-id="532f8-115">在处理程序中，你可以测试是否建议的位置值超出实际数据元素计数。</span><span class="sxs-lookup"><span data-stu-id="532f8-115">In the handler, you can test whether the proposed position value has exceeded the actual data element count.</span></span>  
  
     <span data-ttu-id="532f8-116">下面的示例演示如何测试是否已到达最后一个的数据元素。</span><span class="sxs-lookup"><span data-stu-id="532f8-116">The following example illustrates how you can test whether you have reached the last data element.</span></span> <span data-ttu-id="532f8-117">在示例中，如果你在最后一个元素，**下一步**窗体上的按钮处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="532f8-117">In the example, if you are at the last element, the **Next** button on the form is disabled.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="532f8-118">请注意，你应更改在代码中导航的列表，则应该重新启用**下一步**按钮，以便用户可以浏览新列表的整个长度。</span><span class="sxs-lookup"><span data-stu-id="532f8-118">Be aware that, should you change the list you are navigating in code, you should re-enable the **Next** button, so that users may browse the entire length of the new list.</span></span> <span data-ttu-id="532f8-119">此外，请注意，上述<xref:System.Windows.Forms.BindingSource.PositionChanged>针对特定的事件<xref:System.Windows.Forms.BindingSource>你正在使用必须与其事件处理方法关联。</span><span class="sxs-lookup"><span data-stu-id="532f8-119">Additionally, be aware that the above <xref:System.Windows.Forms.BindingSource.PositionChanged> event for the specific <xref:System.Windows.Forms.BindingSource> you are working with needs to be associated with its event-handling method.</span></span> <span data-ttu-id="532f8-120">以下是用于处理的方法的示例<xref:System.Windows.Forms.BindingSource.PositionChanged>事件：</span><span class="sxs-lookup"><span data-stu-id="532f8-120">The following is an example of a method for handling the <xref:System.Windows.Forms.BindingSource.PositionChanged> event:</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.NavigatingData#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#3)]  
  
### <a name="to-find-an-item-and-set-it-as-the-current-item"></a><span data-ttu-id="532f8-121">若要查找某个项并将其设置为当前项</span><span class="sxs-lookup"><span data-stu-id="532f8-121">To find an item and set it as the current item</span></span>  
  
1.  <span data-ttu-id="532f8-122">查找你想要将设置为当前项的记录。</span><span class="sxs-lookup"><span data-stu-id="532f8-122">Find the record you wish to set as the current item.</span></span> <span data-ttu-id="532f8-123">你可以执行此使用<xref:System.Windows.Forms.BindingSource.Find%2A>方法<xref:System.Windows.Forms.BindingSource>，如果你的数据源实现<xref:System.ComponentModel.IBindingList>。</span><span class="sxs-lookup"><span data-stu-id="532f8-123">You can do this using the <xref:System.Windows.Forms.BindingSource.Find%2A> method of the <xref:System.Windows.Forms.BindingSource>, if your data source implements <xref:System.ComponentModel.IBindingList>.</span></span> <span data-ttu-id="532f8-124">一些示例数据源实现<xref:System.ComponentModel.IBindingList>是<xref:System.ComponentModel.BindingList%601>和<xref:System.Data.DataView>。</span><span class="sxs-lookup"><span data-stu-id="532f8-124">Some examples of data sources that implement <xref:System.ComponentModel.IBindingList> are <xref:System.ComponentModel.BindingList%601> and <xref:System.Data.DataView>.</span></span>  
  
     [!code-csharp[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.NavigatingData#2](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.NavigatingData/VB/Form1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="532f8-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="532f8-125">See Also</span></span>  
 [<span data-ttu-id="532f8-126">Windows 窗体支持的数据源</span><span class="sxs-lookup"><span data-stu-id="532f8-126">Data Sources Supported by Windows Forms</span></span>](../../../docs/framework/winforms/data-sources-supported-by-windows-forms.md)  
 [<span data-ttu-id="532f8-127">Windows 窗体数据绑定中的更改通知</span><span class="sxs-lookup"><span data-stu-id="532f8-127">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="532f8-128">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="532f8-128">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)  
 [<span data-ttu-id="532f8-129">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="532f8-129">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
