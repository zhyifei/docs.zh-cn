---
title: 如何：启用列重新排序中使用设计器在 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- columns [Windows Forms], reordering
- data [Windows Forms], displaying
ms.assetid: d82bd69c-6799-4439-a32c-91139c5901d1
ms.openlocfilehash: a08c15e4fea76d8f6e97db6d463c4141b7d13b4b
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718826"
---
# <a name="how-to-enable-column-reordering-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="9bbaa-102">如何：启用列重新排序中使用设计器在 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="9bbaa-102">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="9bbaa-103">查看显示在 Windows 窗体中的数据时<xref:System.Windows.Forms.DataGridView>控件，用户有时想要比较的特定列中的值。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-103">When viewing data displayed in a Windows Forms <xref:System.Windows.Forms.DataGridView> control, users sometimes want to compare the values in specific columns.</span></span> <span data-ttu-id="9bbaa-104">这可以是列广泛分散在控件中，如果不方便，尤其是当用户必须来回水平滚动才能看到他们感兴趣的所有列。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-104">This can be inconvenient if the columns are widely separated in the control, especially if users must scroll back and forth horizontally in order to see all the columns they are interested in.</span></span> <span data-ttu-id="9bbaa-105">可以通过使用户能够对列重新排序比较列的值更容易的任务。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-105">You can make the task of comparing column values easier by enabling your users to reorder the columns.</span></span> <span data-ttu-id="9bbaa-106">当启用列重新排序时，用户可以将列移到新位置通过拖放列标题中的使用鼠标。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-106">When you enable column reordering, users can move a column to a new position by dragging the column header with the mouse.</span></span>  
  
 <span data-ttu-id="9bbaa-107">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9bbaa-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9bbaa-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9bbaa-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9bbaa-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="9bbaa-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-enable-column-reordering"></a><span data-ttu-id="9bbaa-112">若要启用列重新排序</span><span class="sxs-lookup"><span data-stu-id="9bbaa-112">To enable column reordering</span></span>  
  
-   <span data-ttu-id="9bbaa-113">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，并选择**启用列重新排序**.</span><span class="sxs-lookup"><span data-stu-id="9bbaa-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Enable Column Reordering**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bbaa-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bbaa-114">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToOrderColumns%2A?displayProperty=nameWithType>
- [<span data-ttu-id="9bbaa-115">如何：冻结使用设计器在 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="9bbaa-115">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="9bbaa-116">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="9bbaa-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="9bbaa-117">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="9bbaa-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
