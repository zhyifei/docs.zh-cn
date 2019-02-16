---
title: 如何：添加和使用设计器在 Windows 窗体 DataGridView 控件中删除列
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 01ae8987f7a92abf79a758e82ed0ac863fad57ce
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332684"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="a22fd-102">如何：添加和使用设计器在 Windows 窗体 DataGridView 控件中删除列</span><span class="sxs-lookup"><span data-stu-id="a22fd-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="a22fd-103">Windows 窗体<xref:System.Windows.Forms.DataGridView>控件必须包含的列才能显示数据。</span><span class="sxs-lookup"><span data-stu-id="a22fd-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="a22fd-104">如果您计划手动填充该控件，您必须自行添加的列。</span><span class="sxs-lookup"><span data-stu-id="a22fd-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="a22fd-105">或者，可以将控件绑定到数据源，生成并自动填充列。</span><span class="sxs-lookup"><span data-stu-id="a22fd-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="a22fd-106">如果数据源包含多于你想要显示的列数，则可以删除不需要的列。</span><span class="sxs-lookup"><span data-stu-id="a22fd-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="a22fd-107">下面的过程要求**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="a22fd-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a22fd-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="a22fd-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a22fd-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="a22fd-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="a22fd-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="a22fd-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="a22fd-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="a22fd-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="a22fd-112">若要添加使用设计器的列</span><span class="sxs-lookup"><span data-stu-id="a22fd-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="a22fd-113">单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后选择**添加列**。</span><span class="sxs-lookup"><span data-stu-id="a22fd-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="a22fd-114">在中**添加列**对话框框中，选择**数据绑定列**选项和从数据源中，选择一列或选择**未绑定列**选项，并将列定义使用提供的字段。</span><span class="sxs-lookup"><span data-stu-id="a22fd-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="a22fd-115">单击**添加**按钮添加的列，使其出现在设计器中，如果现有的列已填入控件显示区域。</span><span class="sxs-lookup"><span data-stu-id="a22fd-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="a22fd-116">您可以修改列属性中的**编辑列**对话框中，使用户能够从控件的智能标记。</span><span class="sxs-lookup"><span data-stu-id="a22fd-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="a22fd-117">若要删除某一列使用设计器</span><span class="sxs-lookup"><span data-stu-id="a22fd-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="a22fd-118">选择**编辑列**从控件的智能标记。</span><span class="sxs-lookup"><span data-stu-id="a22fd-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="a22fd-119">选择一列从**选定列**列表。</span><span class="sxs-lookup"><span data-stu-id="a22fd-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="a22fd-120">单击**删除**按钮以删除列，使其从设计器中消失。</span><span class="sxs-lookup"><span data-stu-id="a22fd-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a22fd-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="a22fd-121">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a22fd-122">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="a22fd-122">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a22fd-123">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="a22fd-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
