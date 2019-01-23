---
title: 如何：禁止添加和删除 DataRepeater 项 (Visual Studio)
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, disabling delete
- DataRepeater, disabling add
ms.assetid: 298d8f60-ddfe-4361-ab66-cf76d0df5220
ms.openlocfilehash: 3a304132d0514da4c19811be2536c9516e2838f0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54618537"
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a><span data-ttu-id="07479-102">如何：禁止添加和删除 DataRepeater 项 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="07479-102">How to: Disable Adding and Deleting DataRepeater Items (Visual Studio)</span></span>
<span data-ttu-id="07479-103">默认情况下，用户可以添加和删除项<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="07479-103">By default, users can add and delete items in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="07479-104">用户可以通过按 CTRL + N 添加新项时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>具有焦点或通过单击**AddNewItem**按钮<xref:System.Windows.Forms.BindingNavigator>控件。</span><span class="sxs-lookup"><span data-stu-id="07479-104">Users can add a new item by pressing CTRL+N when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **AddNewItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span> <span data-ttu-id="07479-105">用户可以通过按删除项时删除<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>具有焦点或通过单击**DeleteItem**按钮<xref:System.Windows.Forms.BindingNavigator>控件。</span><span class="sxs-lookup"><span data-stu-id="07479-105">Users can delete an item by pressing DELETE when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **DeleteItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
 <span data-ttu-id="07479-106">您可以禁用添加和/或删除在设计时或在运行时。</span><span class="sxs-lookup"><span data-stu-id="07479-106">You can disable adding and/or deleting at design time or at run time.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a><span data-ttu-id="07479-107">若要禁用在设计时添加和删除</span><span class="sxs-lookup"><span data-stu-id="07479-107">To disable adding and deleting at design time</span></span>  
  
1.  <span data-ttu-id="07479-108">在 Windows 窗体设计器中，选择<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="07479-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="07479-109">必须选择该控件的下半部分。</span><span class="sxs-lookup"><span data-stu-id="07479-109">You must select the lower section of the control.</span></span> <span data-ttu-id="07479-110">如果选择项模板部分，将显示一组不同的属性。</span><span class="sxs-lookup"><span data-stu-id="07479-110">If you select the item template section, a different set of properties will be displayed.</span></span>  
  
2.  <span data-ttu-id="07479-111">在属性窗口中设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A>属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="07479-111">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> property to **False**.</span></span>  
  
3.  <span data-ttu-id="07479-112">设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A>属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="07479-112">Set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> property to **False**.</span></span>  
  
4.  <span data-ttu-id="07479-113">在 Windows 窗体设计器中，选择<xref:System.Windows.Forms.BindingNavigator>控件，，然后单击**AddNewItem**按钮 （带有其上的加号按钮）。</span><span class="sxs-lookup"><span data-stu-id="07479-113">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **AddNewItem** button (the button with a plus sign on it).</span></span>  
  
5.  <span data-ttu-id="07479-114">在属性窗口中设置<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="07479-114">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
6.  <span data-ttu-id="07479-115">在 Windows 窗体设计器中，选择<xref:System.Windows.Forms.BindingNavigator>控件，，然后单击**DeleteItem**按钮 （带有红色 X 上的按钮）。</span><span class="sxs-lookup"><span data-stu-id="07479-115">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **DeleteItem** button (the button with a red X on it).</span></span>  
  
7.  <span data-ttu-id="07479-116">在属性窗口中设置<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="07479-116">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
8.  <span data-ttu-id="07479-117">在组件栏中，选择<xref:System.Windows.Forms.BindingSource>到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>绑定。</span><span class="sxs-lookup"><span data-stu-id="07479-117">In the Component Tray, select the <xref:System.Windows.Forms.BindingSource> to which the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> is bound.</span></span>  
  
9. <span data-ttu-id="07479-118">在属性窗口中设置<xref:System.Windows.Forms.BindingSource.AllowNew%2A>属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="07479-118">In the Properties window, set the <xref:System.Windows.Forms.BindingSource.AllowNew%2A> property to **False**.</span></span>  
  
10. <span data-ttu-id="07479-119">在 Windows 窗体设计器中，双击**DeleteItem**按钮以打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="07479-119">In the Windows Forms Designer, double-click the **DeleteItem** button to open the Code Editor.</span></span>  
  
11. <span data-ttu-id="07479-120">在事件下拉列表中选择`BindingNavigatorDeleteItem_EnabledChanged`事件。</span><span class="sxs-lookup"><span data-stu-id="07479-120">In the Events drop-down list, select the `BindingNavigatorDeleteItem_EnabledChanged` event.</span></span>  
  
12. <span data-ttu-id="07479-121">将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="07479-121">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="07479-122">此步骤是必需的因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮每次当前记录更改时。</span><span class="sxs-lookup"><span data-stu-id="07479-122">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a><span data-ttu-id="07479-123">若要禁止添加和删除在运行时</span><span class="sxs-lookup"><span data-stu-id="07479-123">To disable adding and deleting at run time</span></span>  
  
1.  <span data-ttu-id="07479-124">在 Windows 窗体设计器中，双击窗体打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="07479-124">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="07479-125">将以下代码添加到 `Form_Load` 事件中：</span><span class="sxs-lookup"><span data-stu-id="07479-125">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  <span data-ttu-id="07479-126">将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="07479-126">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="07479-127">此步骤是必需的因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮每次当前记录更改时。</span><span class="sxs-lookup"><span data-stu-id="07479-127">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07479-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="07479-128">See also</span></span>
- <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>
- [<span data-ttu-id="07479-129">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="07479-129">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)
- [<span data-ttu-id="07479-130">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="07479-130">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
