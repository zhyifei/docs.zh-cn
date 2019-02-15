---
title: 如何：使用设计器的 Windows 窗体 ListView 控件中的项进行分组
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], grouping items
- grouping
- groups [Windows Forms], in Windows Forms controls
ms.assetid: 8b615000-69d9-4c64-acaf-b54fa09b69e3
ms.openlocfilehash: 964f2130c650d486bf8a20af96b74122b1450e05
ms.sourcegitcommit: bef803e2025642df39f2f1e046767d89031e0304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2019
ms.locfileid: "56304422"
---
# <a name="how-to-group-items-in-a-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="7e9d9-102">如何：使用设计器的 Windows 窗体 ListView 控件中的项进行分组</span><span class="sxs-lookup"><span data-stu-id="7e9d9-102">How to: Group Items in a Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="7e9d9-103">分组功能<xref:System.Windows.Forms.ListView>控件使您能够以分组方式显示项的相关的集。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-103">The grouping feature of the <xref:System.Windows.Forms.ListView> control enables you to display related sets of items in groups.</span></span> <span data-ttu-id="7e9d9-104">由包含组标题的水平组标头在屏幕上分隔这些组。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-104">These groups are separated on the screen by horizontal group headers that contain the group titles.</span></span> <span data-ttu-id="7e9d9-105">可以使用<xref:System.Windows.Forms.ListView>组以使大型列表对项目分组按字母顺序，按日期，或任何其他逻辑分组的导航。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-105">You can use <xref:System.Windows.Forms.ListView> groups to make navigating large lists easier by grouping items alphabetically, by date, or by any other logical grouping.</span></span> <span data-ttu-id="7e9d9-106">下图显示了一些分组的项。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-106">The following image shows some grouped items.</span></span>  
  
 <span data-ttu-id="7e9d9-107">![ListView 组](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span><span class="sxs-lookup"><span data-stu-id="7e9d9-107">![ListView Groups](../../../../docs/framework/winforms/controls/media/listviewgroups.gif "ListViewGroups")</span></span>  
  
 <span data-ttu-id="7e9d9-108">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-108">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="7e9d9-109">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-109">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
 <span data-ttu-id="7e9d9-110">若要启用分组，您必须首先创建一个或多个<xref:System.Windows.Forms.ListViewGroup>对象在设计器中或以编程方式。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-110">To enable grouping, you must first create one or more <xref:System.Windows.Forms.ListViewGroup> objects either in the designer or programmatically.</span></span> <span data-ttu-id="7e9d9-111">一旦已定义的组，可以将项分配给它。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-111">Once a group has been defined, you can assign items to it.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7e9d9-112"><xref:System.Windows.Forms.ListView> 组是仅适用于[!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)]当应用程序调用<xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-112"><xref:System.Windows.Forms.ListView> groups are available only on [!INCLUDE[WinXpFamily](../../../../includes/winxpfamily-md.md)] when your application calls the <xref:System.Windows.Forms.Application.EnableVisualStyles%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7e9d9-113">在早期操作系统上与组相关的任何代码不起作用和组将不会出现。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-113">On earlier operating systems, any code relating to groups has no effect and the groups will not appear.</span></span> <span data-ttu-id="7e9d9-114">有关详细信息，请参阅 <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-114">For more information, see <xref:System.Windows.Forms.ListView.Groups%2A?displayProperty=nameWithType>.</span></span>  
>   
>  <span data-ttu-id="7e9d9-115">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-115">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7e9d9-116">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-116">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7e9d9-117">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-117">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-groups-in-the-designer"></a><span data-ttu-id="7e9d9-118">若要添加或删除在设计器中的组</span><span class="sxs-lookup"><span data-stu-id="7e9d9-118">To add or remove groups in the designer</span></span>  
  
1.  <span data-ttu-id="7e9d9-119">在中**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮旁边<xref:System.Windows.Forms.ListView.Groups%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-119">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Groups%2A> property.</span></span>  
  
     <span data-ttu-id="7e9d9-120">**ListViewGroup 集合编辑器**出现。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-120">The **ListViewGroup Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="7e9d9-121">若要添加组，请单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-121">To add a group, click the **Add** button.</span></span> <span data-ttu-id="7e9d9-122">然后可以设置属性的新组，如<xref:System.Windows.Forms.ListViewGroup.Header%2A>和<xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-122">You can then set properties of the new group, such as the <xref:System.Windows.Forms.ListViewGroup.Header%2A> and <xref:System.Windows.Forms.ListViewGroup.HeaderAlignment%2A> properties.</span></span> <span data-ttu-id="7e9d9-123">若要删除某个组，选择它，然后单击**删除**按钮。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-123">To remove a group, select it and click the **Remove** button.</span></span>  
  
### <a name="to-assign-items-to-groups-in-the-designer"></a><span data-ttu-id="7e9d9-124">若要将项分配给在设计器中的组</span><span class="sxs-lookup"><span data-stu-id="7e9d9-124">To assign items to groups in the designer</span></span>  
  
1.  <span data-ttu-id="7e9d9-125">在中**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮旁边<xref:System.Windows.Forms.ListView.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-125">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="7e9d9-126">**列表视图项集合编辑器**出现。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-126">The **ListViewItem Collection Editor** appears.</span></span>  
  
2.  <span data-ttu-id="7e9d9-127">若要添加新项，请单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-127">To add a new item, click the **Add** button.</span></span> <span data-ttu-id="7e9d9-128">然后可以设置属性的新项，如<xref:System.Windows.Forms.ListViewItem.Text%2A>和<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-128">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListViewItem.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
3.  <span data-ttu-id="7e9d9-129">选择<xref:System.Windows.Forms.ListViewItem.Group%2A>属性并从下拉列表中选择一个组。</span><span class="sxs-lookup"><span data-stu-id="7e9d9-129">Select the <xref:System.Windows.Forms.ListViewItem.Group%2A> property and choose a group from the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e9d9-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e9d9-130">See also</span></span>
- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.ListView.Groups%2A>
- <xref:System.Windows.Forms.ListViewGroup>
- [<span data-ttu-id="7e9d9-131">ListView 控件</span><span class="sxs-lookup"><span data-stu-id="7e9d9-131">ListView Control</span></span>](../../../../docs/framework/winforms/controls/listview-control-windows-forms.md)
- [<span data-ttu-id="7e9d9-132">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="7e9d9-132">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)
- [<span data-ttu-id="7e9d9-133">如何：添加和删除使用 Windows 窗体 ListView 控件的项</span><span class="sxs-lookup"><span data-stu-id="7e9d9-133">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
