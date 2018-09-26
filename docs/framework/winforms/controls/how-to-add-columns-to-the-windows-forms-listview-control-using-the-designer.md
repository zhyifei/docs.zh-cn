---
title: 如何：使用设计器向 Windows 窗体 ListView 控件添加列
ms.date: 03/30/2017
helpviewer_keywords:
- ListView control [Windows Forms], adding column headers
- columns [Windows Forms], adding to ListView controls
ms.assetid: 5b1a8b4d-587e-479a-95c1-f9b90884f13a
ms.openlocfilehash: 4c696644e61004bcac48399ffc752e40675642fc
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47199867"
---
# <a name="how-to-add-columns-to-the-windows-forms-listview-control-using-the-designer"></a><span data-ttu-id="4d54c-102">如何：使用设计器向 Windows 窗体 ListView 控件添加列</span><span class="sxs-lookup"><span data-stu-id="4d54c-102">How to: Add Columns to the Windows Forms ListView Control Using the Designer</span></span>
<span data-ttu-id="4d54c-103">Windows 窗体<xref:System.Windows.Forms.ListView>控件可以显示多个列的每个列表项中**详细信息**视图。</span><span class="sxs-lookup"><span data-stu-id="4d54c-103">The Windows Forms <xref:System.Windows.Forms.ListView> control can display multiple columns for each list item when in the **Details** view.</span></span> <span data-ttu-id="4d54c-104">可以使用列来显示多种类型的每个列表项的相关信息。</span><span class="sxs-lookup"><span data-stu-id="4d54c-104">You can use the columns to display several types of information about each list item.</span></span> <span data-ttu-id="4d54c-105">例如，文件的列表可以显示文件名、 文件类型、 大小和文件的上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="4d54c-105">For example, a list of files could display the file name, file type, size, and date the file was last modified.</span></span> <span data-ttu-id="4d54c-106">创建后填充列的信息，请参阅[如何： 在使用 Windows 窗体 ListView 控件的列中显示子项](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="4d54c-106">For information on populating the columns once they are created, see [How to: Display Subitems in Columns with the Windows Forms ListView Control](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md).</span></span>  
  
 <span data-ttu-id="4d54c-107">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.ListView>控件。</span><span class="sxs-lookup"><span data-stu-id="4d54c-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="4d54c-108">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="4d54c-108">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d54c-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="4d54c-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4d54c-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="4d54c-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4d54c-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="4d54c-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-columns-in-the-designer"></a><span data-ttu-id="4d54c-112">若要在设计器中添加列</span><span class="sxs-lookup"><span data-stu-id="4d54c-112">To add columns in the designer</span></span>  
  
1.  <span data-ttu-id="4d54c-113">在中**属性**窗口中，设置控件的<xref:System.Windows.Forms.ListView.View%2A>属性设置为<xref:System.Windows.Forms.View.Details>。</span><span class="sxs-lookup"><span data-stu-id="4d54c-113">In the **Properties** window, set the control's <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
2.  <span data-ttu-id="4d54c-114">在中**属性**窗口中，单击**省略号**按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 旁边<xref:System.Windows.Forms.ListView.Columns%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="4d54c-114">In the **Properties** window, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) next to the <xref:System.Windows.Forms.ListView.Columns%2A> property.</span></span>  
  
     <span data-ttu-id="4d54c-115">**ColumnHeader 集合编辑器**出现。</span><span class="sxs-lookup"><span data-stu-id="4d54c-115">The **ColumnHeader Collection Editor** appears.</span></span>  
  
3.  <span data-ttu-id="4d54c-116">使用**添加**按钮以添加新列。</span><span class="sxs-lookup"><span data-stu-id="4d54c-116">Use the **Add** button to add new columns.</span></span> <span data-ttu-id="4d54c-117">然后，您可以选择列标题并设置其文本 （列的标题）、 文本对齐方式和宽度。</span><span class="sxs-lookup"><span data-stu-id="4d54c-117">You can then select the column header and set its text (the caption of the column), text alignment, and width.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d54c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d54c-118">See Also</span></span>  
 [<span data-ttu-id="4d54c-119">ListView 控件概述</span><span class="sxs-lookup"><span data-stu-id="4d54c-119">ListView Control Overview</span></span>](../../../../docs/framework/winforms/controls/listview-control-overview-windows-forms.md)  
 [<span data-ttu-id="4d54c-120">如何：使用 Windows 窗体 ListView 控件添加和删除项</span><span class="sxs-lookup"><span data-stu-id="4d54c-120">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="4d54c-121">如何：使用 Windows 窗体 ListView 控件在列中显示子项</span><span class="sxs-lookup"><span data-stu-id="4d54c-121">How to: Display Subitems in Columns with the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-subitems-in-columns-with-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="4d54c-122">如何：显示 Windows 窗体 ListView 控件的图标</span><span class="sxs-lookup"><span data-stu-id="4d54c-122">How to: Display Icons for the Windows Forms ListView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-display-icons-for-the-windows-forms-listview-control.md)  
 [<span data-ttu-id="4d54c-123">如何：向 TreeView 或 ListView 控件（Windows 窗体）添加自定义信息</span><span class="sxs-lookup"><span data-stu-id="4d54c-123">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](../../../../docs/framework/winforms/controls/add-custom-information-to-a-treeview-or-listview-control-wf.md)
