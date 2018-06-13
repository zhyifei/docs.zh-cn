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
ms.openlocfilehash: e3d0d2a8d422054e269ee92df1fdfcb5acb96eac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33590788"
---
# <a name="how-to-disable-adding-and-deleting-datarepeater-items-visual-studio"></a><span data-ttu-id="c0e87-102">如何：禁止添加和删除 DataRepeater 项 (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="c0e87-102">How to: Disable Adding and Deleting DataRepeater Items (Visual Studio)</span></span>
<span data-ttu-id="c0e87-103">默认情况下，用户可以添加和删除中的项<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="c0e87-103">By default, users can add and delete items in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="c0e87-104">用户可以通过按 CTRL + N 添加新项时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>具有焦点或通过单击**AddNewItem**按钮上<xref:System.Windows.Forms.BindingNavigator>控件。</span><span class="sxs-lookup"><span data-stu-id="c0e87-104">Users can add a new item by pressing CTRL+N when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **AddNewItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span> <span data-ttu-id="c0e87-105">用户可以删除某个项，通过按删除时<xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A>具有焦点或通过单击**DeleteItem**按钮上<xref:System.Windows.Forms.BindingNavigator>控件。</span><span class="sxs-lookup"><span data-stu-id="c0e87-105">Users can delete an item by pressing DELETE when a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeaterItemEventArgs.DataRepeaterItem%2A> has focus or by clicking the **DeleteItem** button on the <xref:System.Windows.Forms.BindingNavigator> control.</span></span>  
  
 <span data-ttu-id="c0e87-106">你可以禁用添加和/或删除在设计时或在运行时。</span><span class="sxs-lookup"><span data-stu-id="c0e87-106">You can disable adding and/or deleting at design time or at run time.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-design-time"></a><span data-ttu-id="c0e87-107">若要禁用在设计时添加和删除</span><span class="sxs-lookup"><span data-stu-id="c0e87-107">To disable adding and deleting at design time</span></span>  
  
1.  <span data-ttu-id="c0e87-108">在 Windows 窗体设计器中，选择<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>控件。</span><span class="sxs-lookup"><span data-stu-id="c0e87-108">In the Windows Forms Designer, select the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c0e87-109">您必须选择下方的控件。</span><span class="sxs-lookup"><span data-stu-id="c0e87-109">You must select the lower section of the control.</span></span> <span data-ttu-id="c0e87-110">如果您选择的项目模板部分，则将显示一组不同的属性。</span><span class="sxs-lookup"><span data-stu-id="c0e87-110">If you select the item template section, a different set of properties will be displayed.</span></span>  
  
2.  <span data-ttu-id="c0e87-111">在属性窗口中，设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A>属性**False**。</span><span class="sxs-lookup"><span data-stu-id="c0e87-111">In the Properties window, set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToAddItems%2A> property to **False**.</span></span>  
  
3.  <span data-ttu-id="c0e87-112">设置<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A>属性**False**。</span><span class="sxs-lookup"><span data-stu-id="c0e87-112">Set the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.AllowUserToDeleteItems%2A> property to **False**.</span></span>  
  
4.  <span data-ttu-id="c0e87-113">在 Windows 窗体设计器中，选择<xref:System.Windows.Forms.BindingNavigator>控件，，然后单击**AddNewItem**按钮 （使用在其上的加号按钮）。</span><span class="sxs-lookup"><span data-stu-id="c0e87-113">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **AddNewItem** button (the button with a plus sign on it).</span></span>  
  
5.  <span data-ttu-id="c0e87-114">在属性窗口中，设置<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>属性**False**。</span><span class="sxs-lookup"><span data-stu-id="c0e87-114">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
6.  <span data-ttu-id="c0e87-115">在 Windows 窗体设计器中，选择<xref:System.Windows.Forms.BindingNavigator>控件，，然后单击**DeleteItem**按钮 （带有红色 X 上的按钮）。</span><span class="sxs-lookup"><span data-stu-id="c0e87-115">In the Windows Forms Designer, select the <xref:System.Windows.Forms.BindingNavigator> control, and then click the **DeleteItem** button (the button with a red X on it).</span></span>  
  
7.  <span data-ttu-id="c0e87-116">在属性窗口中，设置<xref:System.Windows.Forms.ToolBarButton.Enabled%2A>属性**False**。</span><span class="sxs-lookup"><span data-stu-id="c0e87-116">In the Properties window, set the <xref:System.Windows.Forms.ToolBarButton.Enabled%2A> property to **False**.</span></span>  
  
8.  <span data-ttu-id="c0e87-117">在组件栏中，选择<xref:System.Windows.Forms.BindingSource>到<xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>绑定。</span><span class="sxs-lookup"><span data-stu-id="c0e87-117">In the Component Tray, select the <xref:System.Windows.Forms.BindingSource> to which the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> is bound.</span></span>  
  
9. <span data-ttu-id="c0e87-118">在属性窗口中，设置<xref:System.Windows.Forms.BindingSource.AllowNew%2A>属性**False**。</span><span class="sxs-lookup"><span data-stu-id="c0e87-118">In the Properties window, set the <xref:System.Windows.Forms.BindingSource.AllowNew%2A> property to **False**.</span></span>  
  
10. <span data-ttu-id="c0e87-119">在 Windows 窗体设计器中，双击**DeleteItem**按钮以打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="c0e87-119">In the Windows Forms Designer, double-click the **DeleteItem** button to open the Code Editor.</span></span>  
  
11. <span data-ttu-id="c0e87-120">在事件下拉列表中，选择`BindingNavigatorDeleteItem_EnabledChanged`事件。</span><span class="sxs-lookup"><span data-stu-id="c0e87-120">In the Events drop-down list, select the `BindingNavigatorDeleteItem_EnabledChanged` event.</span></span>  
  
12. <span data-ttu-id="c0e87-121">将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="c0e87-121">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="c0e87-122">此步骤是必需的因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮每次当前记录更改时。</span><span class="sxs-lookup"><span data-stu-id="c0e87-122">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
### <a name="to-disable-adding-and-deleting-at-run-time"></a><span data-ttu-id="c0e87-123">若要禁止添加和删除在运行时</span><span class="sxs-lookup"><span data-stu-id="c0e87-123">To disable adding and deleting at run time</span></span>  
  
1.  <span data-ttu-id="c0e87-124">在 Windows 窗体设计器中，双击窗体打开代码编辑器。</span><span class="sxs-lookup"><span data-stu-id="c0e87-124">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="c0e87-125">将以下代码添加到 `Form_Load` 事件中：</span><span class="sxs-lookup"><span data-stu-id="c0e87-125">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_2.vb)]  
  
3.  <span data-ttu-id="c0e87-126">将以下代码添加到 `BindingNavigatorDeleteItem_EnabledChanged` 事件处理程序中：</span><span class="sxs-lookup"><span data-stu-id="c0e87-126">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterDisableAddDelete#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio_1.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="c0e87-127">此步骤是必需的因为<xref:System.Windows.Forms.BindingSource>将启用**DeleteItem**按钮每次当前记录更改时。</span><span class="sxs-lookup"><span data-stu-id="c0e87-127">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0e87-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0e87-128">See Also</span></span>  
 <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>  
 [<span data-ttu-id="c0e87-129">DataRepeater 控件简介</span><span class="sxs-lookup"><span data-stu-id="c0e87-129">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="c0e87-130">DataRepeater 控件疑难解答</span><span class="sxs-lookup"><span data-stu-id="c0e87-130">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
