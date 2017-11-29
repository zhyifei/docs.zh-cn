---
title: "如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.DataGridViewAddColumnDialog
helpviewer_keywords:
- DataGridView control [Windows Forms], adding columns
- DataGridView control [Windows Forms], removing columns
ms.assetid: 9e709f35-0a8c-4e7e-b4c4-bacb7a834077
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71b02124dd68299552737df35163e3b766d4df73
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-and-remove-columns-in-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="3d800-102">如何：使用设计器添加和移除 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="3d800-102">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="3d800-103">Windows 窗体<xref:System.Windows.Forms.DataGridView>控件必须包含才能显示数据的列。</span><span class="sxs-lookup"><span data-stu-id="3d800-103">The Windows Forms <xref:System.Windows.Forms.DataGridView> control must contain columns in order to display data.</span></span> <span data-ttu-id="3d800-104">如果你计划手动填充该控件，你必须自己添加列。</span><span class="sxs-lookup"><span data-stu-id="3d800-104">If you plan to populate the control manually, you must add the columns yourself.</span></span> <span data-ttu-id="3d800-105">或者，你可以将控件绑定到数据源，也不能生成自动填充列。</span><span class="sxs-lookup"><span data-stu-id="3d800-105">Alternately, you can bind the control to a data source, which generates and populates the columns automatically.</span></span> <span data-ttu-id="3d800-106">如果数据源包含多于你想要显示的列数，则可以删除不需要的列。</span><span class="sxs-lookup"><span data-stu-id="3d800-106">If the data source contains more columns than you want to display, you can remove the unwanted columns.</span></span>  
  
 <span data-ttu-id="3d800-107">下面的过程要求**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="3d800-107">The following procedures require a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="3d800-108">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="3d800-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d800-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="3d800-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="3d800-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="3d800-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="3d800-111">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="3d800-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-column-using-the-designer"></a><span data-ttu-id="3d800-112">若要添加使用设计器的列</span><span class="sxs-lookup"><span data-stu-id="3d800-112">To add a column using the designer</span></span>  
  
1.  <span data-ttu-id="3d800-113">单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 右上角<xref:System.Windows.Forms.DataGridView>控制，，然后选择**添加列**。</span><span class="sxs-lookup"><span data-stu-id="3d800-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Add Column**.</span></span>  
  
2.  <span data-ttu-id="3d800-114">在**添加列**对话框框中，选择**数据绑定列**选项和从数据源中，选择一列或选择**未绑定列**选项和定义列使用提供的字段。</span><span class="sxs-lookup"><span data-stu-id="3d800-114">In the **Add Column** dialog box, choose the **Databound Column** option and select a column from the data source, or choose the **Unbound Column** option and define the column using the fields provided.</span></span>  
  
3.  <span data-ttu-id="3d800-115">单击**添加**按钮以添加列，使其出现在设计器中的现有列不能已填充控件显示区域时。</span><span class="sxs-lookup"><span data-stu-id="3d800-115">Click the **Add** button to add the column, causing it to appear in the designer if the existing columns do not already fill the control display area.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d800-116">你可以修改中的列属性**编辑列**对话框中，你可以访问从控件的智能标记。</span><span class="sxs-lookup"><span data-stu-id="3d800-116">You can modify column properties in the **Edit Columns** dialog box, which you can access from the control's smart tag.</span></span>  
  
### <a name="to-remove-a-column-using-the-designer"></a><span data-ttu-id="3d800-117">若要删除某一列使用设计器</span><span class="sxs-lookup"><span data-stu-id="3d800-117">To remove a column using the designer</span></span>  
  
1.  <span data-ttu-id="3d800-118">选择**编辑列**从控件的智能标记。</span><span class="sxs-lookup"><span data-stu-id="3d800-118">Choose **Edit Columns** from the control's smart tag.</span></span>  
  
2.  <span data-ttu-id="3d800-119">选择从列**选定的列**列表。</span><span class="sxs-lookup"><span data-stu-id="3d800-119">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="3d800-120">单击**删除**按钮以删除列，使其从设计器中消失。</span><span class="sxs-lookup"><span data-stu-id="3d800-120">Click the **Remove** button to delete the column, causing it to disappear from the designer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d800-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d800-121">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 [<span data-ttu-id="3d800-122">如何： 创建 Windows 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="3d800-122">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="3d800-123">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="3d800-123">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
