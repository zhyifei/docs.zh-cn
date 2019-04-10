---
title: 如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序
ms.date: 03/30/2017
helpviewer_keywords:
- columns [Windows Forms], order of
- DataGridView control [Windows Forms], column order
- Windows Forms, columns
- data [Windows Forms], displaying
ms.assetid: 7fe52a98-75d6-448c-97a5-65ca2c568c1a
ms.openlocfilehash: 131ef2a04caa17aa268c0e8d229a1070061c4373
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175300"
---
# <a name="how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="ea269-102">如何：使用设计器更改 Windows 窗体 DataGridView 控件中列的顺序</span><span class="sxs-lookup"><span data-stu-id="ea269-102">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="ea269-103">当绑定 Windows 窗体<xref:System.Windows.Forms.DataGridView>由数据源指定控件与数据源，自动生成的列的显示顺序。</span><span class="sxs-lookup"><span data-stu-id="ea269-103">When you bind a Windows Forms <xref:System.Windows.Forms.DataGridView> control to a data source, the display order of the automatically generated columns is dictated by the data source.</span></span> <span data-ttu-id="ea269-104">如果此顺序是不愿意，你可以使用设计器的列的顺序。</span><span class="sxs-lookup"><span data-stu-id="ea269-104">If this order is not what you prefer, you can change the order of the columns using the designer.</span></span> <span data-ttu-id="ea269-105">您可能想要将未绑定的列添加到控件并更改其显示顺序。</span><span class="sxs-lookup"><span data-stu-id="ea269-105">You may also want to add unbound columns to the control and change their display order.</span></span> <span data-ttu-id="ea269-106">有关如何以编程方式更改列顺序的信息，请参阅[如何：更改 Windows 窗体 DataGridView 控件中的列顺序](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ea269-106">For information about how to change the column order programmatically, see [How to: Change the Order of Columns in the Windows Forms DataGridView Control](how-to-change-the-order-of-columns-in-the-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="ea269-107">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="ea269-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="ea269-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ea269-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ea269-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="ea269-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ea269-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="ea269-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ea269-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)</span><span class="sxs-lookup"><span data-stu-id="ea269-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)</span></span>  
  
### <a name="to-change-the-column-order-using-the-designer"></a><span data-ttu-id="ea269-112">若要更改列的顺序使用设计器</span><span class="sxs-lookup"><span data-stu-id="ea269-112">To change the column order using the designer</span></span>  
  
1.  <span data-ttu-id="ea269-113">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="ea269-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="ea269-114">选择一列从**选定列**列表。</span><span class="sxs-lookup"><span data-stu-id="ea269-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="ea269-115">单击向上或向下键的右侧**所选列**列表之前所选的列中所需的位置。</span><span class="sxs-lookup"><span data-stu-id="ea269-115">Click the up or down arrow to the right of the **Selected Columns** list until the selected column is in the position you want.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea269-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea269-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="ea269-117">如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="ea269-117">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)
- [<span data-ttu-id="ea269-118">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="ea269-118">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="ea269-119">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="ea269-119">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
