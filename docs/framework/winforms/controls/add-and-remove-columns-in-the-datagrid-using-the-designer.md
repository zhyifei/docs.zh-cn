---
title: 使用设计器在 DataGridView 控件中添加和删除列
ms.date: 03/30/2017
f1_keywords:
- vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
ms.openlocfilehash: 8843b1d30f3e5f31a060e27b41b0105e6584f155
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628600"
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="a0202-102">如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="a0202-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="a0202-103">Windows 窗体 <xref:System.Windows.Forms.DataGridView> 控件必须包含列才能显示数据。</span><span class="sxs-lookup"><span data-stu-id="a0202-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="a0202-104">如果你计划手动填充控件，则必须自行添加列。</span><span class="sxs-lookup"><span data-stu-id="a0202-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="a0202-105">或者，您可以将控件绑定到数据源，该数据源会自动生成并填充列。</span><span class="sxs-lookup"><span data-stu-id="a0202-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="a0202-106">如果数据源包含的列多于要显示的列数，则可以删除不需要的列。</span><span class="sxs-lookup"><span data-stu-id="a0202-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>

 <span data-ttu-id="a0202-107">以下过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="a0202-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="a0202-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="a0202-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="a0202-109">使用设计器添加列</span><span class="sxs-lookup"><span data-stu-id="a0202-109">To add a column using the designer</span></span>

1. <span data-ttu-id="a0202-110">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的设计器操作标志符号（![小号黑色箭头](./media/designer-actions-glyph.gif)），然后选择 "**添加列**"。</span><span class="sxs-lookup"><span data-stu-id="a0202-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>

2. <span data-ttu-id="a0202-111">在 "**添加列**" 对话框中，选择 "数据**绑定列**" 选项，然后从数据源中选择一个列，或选择 "**未绑定列**" 选项，然后使用提供的字段定义列。</span><span class="sxs-lookup"><span data-stu-id="a0202-111">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>

3. <span data-ttu-id="a0202-112">单击 "**添加**" 按钮添加列，如果现有列尚未填充控件显示区域，则会使其显示在设计器中。</span><span class="sxs-lookup"><span data-stu-id="a0202-112">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0202-113">您可以在 "**编辑列**" 对话框中修改列属性，该对话框可从控件的智能标记访问。</span><span class="sxs-lookup"><span data-stu-id="a0202-113">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>

## <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="a0202-114">使用设计器删除列</span><span class="sxs-lookup"><span data-stu-id="a0202-114">To remove a column using the designer</span></span>

1. <span data-ttu-id="a0202-115">从控件的智能标记中，选择 "**编辑列**"。</span><span class="sxs-lookup"><span data-stu-id="a0202-115">Choose **Edit Columns** from the control's smart tag.</span></span>

2. <span data-ttu-id="a0202-116">从 "**选定的列**" 列表中选择一列。</span><span class="sxs-lookup"><span data-stu-id="a0202-116">Select a column from the **Selected Columns** list.</span></span>

3. <span data-ttu-id="a0202-117">单击 "**删除**" 按钮可删除该列，使其从设计器中消失。</span><span class="sxs-lookup"><span data-stu-id="a0202-117">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>

## <a name="see-also"></a><span data-ttu-id="a0202-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0202-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="a0202-119">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="a0202-119">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="a0202-120">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="a0202-120">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
