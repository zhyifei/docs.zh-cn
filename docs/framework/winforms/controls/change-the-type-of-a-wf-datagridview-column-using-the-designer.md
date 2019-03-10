---
title: 如何：更改 Windows 窗体 DataGridView 列使用设计器的类型
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
ms.openlocfilehash: 99728e473223f3393cc9d09f38728cf873a95c99
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718813"
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="9a11a-102">如何：更改 Windows 窗体 DataGridView 列使用设计器的类型</span><span class="sxs-lookup"><span data-stu-id="9a11a-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="9a11a-103">有时会想要更改的列的已添加到 Windows 窗体类型<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="9a11a-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9a11a-104">例如，你可能想要修改某些时将控件绑定到数据源自动生成的列的类型。</span><span class="sxs-lookup"><span data-stu-id="9a11a-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="9a11a-105">所显示的表具有包含相关表中的行的外键的列时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="9a11a-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="9a11a-106">在这种情况下，你可能想要替换文本中显示的列的组合框中显示列的相关表中更有意义的值与这些外键。</span><span class="sxs-lookup"><span data-stu-id="9a11a-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="9a11a-107">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="9a11a-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="9a11a-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9a11a-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9a11a-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="9a11a-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9a11a-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="9a11a-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9a11a-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="9a11a-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="9a11a-112">若要更改使用设计器的列的类型</span><span class="sxs-lookup"><span data-stu-id="9a11a-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="9a11a-113">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="9a11a-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="9a11a-114">选择一列从**选定列**列表。</span><span class="sxs-lookup"><span data-stu-id="9a11a-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="9a11a-115">在中**列属性**网格中，设置`ColumnType`属性设置为新的列类型。</span><span class="sxs-lookup"><span data-stu-id="9a11a-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9a11a-116">`ColumnType`属性是一个仅限设计时间属性，指示表示列类型的类。</span><span class="sxs-lookup"><span data-stu-id="9a11a-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="9a11a-117">它不是实际的属性列类中定义。</span><span class="sxs-lookup"><span data-stu-id="9a11a-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a11a-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a11a-118">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn>
- [<span data-ttu-id="9a11a-119">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="9a11a-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="9a11a-120">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="9a11a-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
