---
title: 如何：使用设计器用 Windows 窗体 ListView 控件添加和移除项
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], populating
- ListView control [Windows Forms], adding list items
ms.assetid: 217611ee-fd11-4d39-9a54-a37c3e781be1
ms.openlocfilehash: 0480c8980f0eba17229fff0c1e947cac5216fb9e
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47203433"
---
# <a name="how-to-add-and-remove-items-with-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="dd3aa-102">如何：使用设计器用 Windows 窗体 ListView 控件添加和移除项</span><span class="sxs-lookup"><span data-stu-id="dd3aa-102">How to: Add and Remove Items with the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="dd3aa-103">将项添加到 Windows 窗体的过程<xref:System.Windows.Forms.ListView>控件主要包括指定项并为其分配属性。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-103">The process of adding an item to a Windows Forms <xref:System.Windows.Forms.ListView> control consists primarily of specifying the item and assigning properties to it.</span></span> <span data-ttu-id="dd3aa-104">可在任何时间完成添加或删除列表项。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-104">Adding or removing list items can be done at any time.</span></span>  
  
 <span data-ttu-id="dd3aa-105">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-105">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="dd3aa-106">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-106">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd3aa-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dd3aa-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dd3aa-109">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-or-remove-items-using-the-designer"></a><span data-ttu-id="dd3aa-110">若要添加或删除项目使用设计器</span><span class="sxs-lookup"><span data-stu-id="dd3aa-110">To add or remove items using the designer</span></span>  
  
1.  <span data-ttu-id="dd3aa-111">选择 <xref:System.Windows.Forms.ListView> 控件。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-111">Select the <xref:System.Windows.Forms.ListView> control.</span></span>  
  
2.  <span data-ttu-id="dd3aa-112">在中**属性**窗口中，单击**省略号**(![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 按钮旁边<xref:System.Windows.Forms.ListView.Items%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-112">In the **Properties** window, click the **Ellipsis** (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) button next to the <xref:System.Windows.Forms.ListView.Items%2A> property.</span></span>  
  
     <span data-ttu-id="dd3aa-113">**列表视图项集合编辑器**出现。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-113">The **ListViewItem Collection Editor** appears.</span></span>  
  
3.  <span data-ttu-id="dd3aa-114">若要添加某个项，请单击**添加**按钮。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-114">To add an item, click the **Add** button.</span></span> <span data-ttu-id="dd3aa-115">然后可以设置属性的新项，如<xref:System.Windows.Forms.ListView.Text%2A>和<xref:System.Windows.Forms.ListViewItem.ImageIndex%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-115">You can then set properties of the new item, such as the <xref:System.Windows.Forms.ListView.Text%2A> and <xref:System.Windows.Forms.ListViewItem.ImageIndex%2A> properties.</span></span>  
  
4.  <span data-ttu-id="dd3aa-116">若要删除某个项，请选择它，然后单击**删除**按钮。</span><span class="sxs-lookup"><span data-stu-id="dd3aa-116">To remove an item, select it and click the **Remove** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd3aa-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="dd3aa-117">See Also</span></span>  
 [<span data-ttu-id="dd3aa-118">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="dd3aa-118">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="dd3aa-119">如何：向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="dd3aa-119">How to: Add Columns to the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-columns-to-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="dd3aa-120">如何：使用 Windows 窗体 ListView 控件在列中显示子项</span><span class="sxs-lookup"><span data-stu-id="dd3aa-120">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="dd3aa-121">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="dd3aa-121">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="dd3aa-122">如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息</span><span class="sxs-lookup"><span data-stu-id="dd3aa-122">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)  
 [<span data-ttu-id="dd3aa-123">如何：在 Windows 窗体 ListView 控件中对项进行分组</span><span class="sxs-lookup"><span data-stu-id="dd3aa-123">How to: Group Items in a Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-group-items-in-a-windows-forms-listview-control.md)
