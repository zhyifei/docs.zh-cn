---
title: 使用设计器防止 DataGridView 控件中添加和删除行
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: cca497aeaedd0c9f988241092eed707ecc259859
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628886"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="2c771-102">如何：使用设计器防止在 Windows 窗体 DataGridView 控件中添加和删除行</span><span class="sxs-lookup"><span data-stu-id="2c771-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="2c771-103">有时想要阻止用户在 <xref:System.Windows.Forms.DataGridView> 控件中输入新的数据行或删除现有行。</span><span class="sxs-lookup"><span data-stu-id="2c771-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2c771-104">新行在控件底部的新记录的特殊行中输入。</span><span class="sxs-lookup"><span data-stu-id="2c771-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="2c771-105">禁用行添加后，不会显示新记录的行。</span><span class="sxs-lookup"><span data-stu-id="2c771-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="2c771-106">然后，您可以通过禁用行删除和单元格编辑来使控件完全只读。</span><span class="sxs-lookup"><span data-stu-id="2c771-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>

 <span data-ttu-id="2c771-107">下面的过程需要一个**Windows 应用程序**项目，其中包含一个包含 <xref:System.Windows.Forms.DataGridView> 控件的窗体。</span><span class="sxs-lookup"><span data-stu-id="2c771-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="2c771-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="2c771-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>

## <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="2c771-109">禁止添加和删除行</span><span class="sxs-lookup"><span data-stu-id="2c771-109">To prevent row addition and deletion</span></span>

- <span data-ttu-id="2c771-110">单击 <xref:System.Windows.Forms.DataGridView> 控件右上角的设计器操作标志符号（![小黑色箭头](./media/designer-actions-glyph.gif)），然后清除 "**启用添加**" 和 "**启用删除**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2c771-110">Click the designer actions glyph (![Small black arrow](./media/designer-actions-glyph.gif)) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2c771-111">若要使控件完全只读，请清除 "**启用编辑**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="2c771-111">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>

## <a name="see-also"></a><span data-ttu-id="2c771-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c771-112">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2c771-113">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="2c771-113">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="2c771-114">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="2c771-114">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
