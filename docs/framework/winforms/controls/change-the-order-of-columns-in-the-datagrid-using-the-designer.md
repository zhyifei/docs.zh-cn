---
title: 如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 78e6b62c626b5981ebfa85972b3eaae638468757
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33525760"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="5c150-102">如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序</span><span class="sxs-lookup"><span data-stu-id="5c150-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="5c150-103">当你将绑定 Windows 窗体<xref:System.Windows.Forms.DataGridView>控件添加到数据源，自动生成的列的显示顺序由数据源。</span><span class="sxs-lookup"><span data-stu-id="5c150-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="5c150-104">如果此顺序是不需要，你可以更改使用设计器的列的顺序。</span><span class="sxs-lookup"><span data-stu-id="5c150-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="5c150-105">你可能还想要将未绑定的列添加到控件和更改其显示顺序。</span><span class="sxs-lookup"><span data-stu-id="5c150-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="5c150-106">有关如何以编程方式更改列顺序的信息，请参阅[如何： 更改 Windows 窗体 DataGridView 控件中的列顺序](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="5c150-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="5c150-107">下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="5c150-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="5c150-108">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="5c150-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c150-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="5c150-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="5c150-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="5c150-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="5c150-111">有关详细信息，请参阅[Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)</span><span class="sxs-lookup"><span data-stu-id="5c150-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)</span></span>  
  
### <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="5c150-112">若要更改列顺序使用设计器</span><span class="sxs-lookup"><span data-stu-id="5c150-112">To change the column order using the designer</span></span>  
  
1.  <span data-ttu-id="5c150-113">单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 右上角<xref:System.Windows.Forms.DataGridView>控制，，然后选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="5c150-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="5c150-114">选择从列**选定的列**列表。</span><span class="sxs-lookup"><span data-stu-id="5c150-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="5c150-115">单击向上或向下箭头右侧**所选列**列表之前所选的列中所需的位置。</span><span class="sxs-lookup"><span data-stu-id="5c150-115">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c150-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c150-116">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="5c150-117">如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列</span><span class="sxs-lookup"><span data-stu-id="5c150-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="5c150-118">如何： 创建 Windows 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="5c150-118">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="5c150-119">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="5c150-119">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
