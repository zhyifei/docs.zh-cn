---
title: 如何：使用设计器防止在 Windows 窗体 DataGridView 控件中添加和删除行
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], preventing row addition or deletion
ms.assetid: a17722bd-9400-41e6-8dcc-c9c151f0a749
ms.openlocfilehash: b365c54da59ce8b1b3872f9084e3954eebb4918d
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64654244"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="02c8a-102">如何：使用设计器防止在 Windows 窗体 DataGridView 控件中添加和删除行</span><span class="sxs-lookup"><span data-stu-id="02c8a-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="02c8a-103">有时想要阻止用户在 <xref:System.Windows.Forms.DataGridView> 控件中输入新的数据行或删除现有行。</span><span class="sxs-lookup"><span data-stu-id="02c8a-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="02c8a-104">在控件底部的新记录的特殊行中输入新行。</span><span class="sxs-lookup"><span data-stu-id="02c8a-104">New rows are entered in the special row for new records at the bottom of the control.</span></span> <span data-ttu-id="02c8a-105">禁用添加行时不会显示新记录所对应的行。</span><span class="sxs-lookup"><span data-stu-id="02c8a-105">When you disable row addition, the row for new records is not displayed.</span></span> <span data-ttu-id="02c8a-106">您然后可以通过禁用删除行和单元格内编辑使控件完全只读的。</span><span class="sxs-lookup"><span data-stu-id="02c8a-106">You can then make the control entirely read-only by disabling row deletion and cell editing.</span></span>  
  
 <span data-ttu-id="02c8a-107">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="02c8a-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="02c8a-108">有关设置此类项目的信息，请参阅[如何：创建 Windows 窗体应用程序项目](/visualstudio/ide/step-1-create-a-windows-forms-application-project)和[如何：将控件添加到 Windows 窗体](how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="02c8a-108">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="02c8a-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="02c8a-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="02c8a-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="02c8a-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="02c8a-111">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="02c8a-111">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-prevent-row-addition-and-deletion"></a><span data-ttu-id="02c8a-112">若要防止添加和删除行</span><span class="sxs-lookup"><span data-stu-id="02c8a-112">To prevent row addition and deletion</span></span>  
  
- <span data-ttu-id="02c8a-113">单击智能标记标志符号 (![智能标记标志符号](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 上的右上角<xref:System.Windows.Forms.DataGridView>控件，然后再清除**启用添加**并**启用删除**复选框。</span><span class="sxs-lookup"><span data-stu-id="02c8a-113">Click the smart tag glyph (![Smart Tag Glyph](./media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then clear the **Enable Adding** and **Enable Deleting** check boxes.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="02c8a-114">若要使控件完全只读的请清除**启用编辑**也复选框。</span><span class="sxs-lookup"><span data-stu-id="02c8a-114">To make the control entirely read-only, clear the **Enable Editing** check box as well.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c8a-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="02c8a-115">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>
- [<span data-ttu-id="02c8a-116">如何：创建 Windows 窗体应用程序项目</span><span class="sxs-lookup"><span data-stu-id="02c8a-116">How to: Create a Windows Forms application project</span></span>](/visualstudio/ide/step-1-create-a-windows-forms-application-project)
- [<span data-ttu-id="02c8a-117">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="02c8a-117">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
