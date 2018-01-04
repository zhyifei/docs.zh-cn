---
title: "如何：使用设计器更改 Windows 窗体 DataGridView 列的类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms, columns
- columns [Windows Forms], types
- DataGridView control [Windows Forms], changing column type
- data [Windows Forms], displaying
ms.assetid: 7f994d45-600d-4190-a187-35803214b40c
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f2c0cc5136aaed3f7465102e7e7b6d2d9c2fc920
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-change-the-type-of-a-windows-forms-datagridview-column-using-the-designer"></a><span data-ttu-id="195a8-102">如何：使用设计器更改 Windows 窗体 DataGridView 列的类型</span><span class="sxs-lookup"><span data-stu-id="195a8-102">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>
<span data-ttu-id="195a8-103">有时你将想要更改已添加到 Windows 窗体的列类型<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="195a8-103">Sometimes you will want to change the type of a column that has already been added to a Windows Forms <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="195a8-104">例如，你可能想要修改的某些列时将控件绑定到数据源自动生成的类型。</span><span class="sxs-lookup"><span data-stu-id="195a8-104">For example, you may want to modify the types of some of the columns that are generated automatically when you bind the control to a data source.</span></span> <span data-ttu-id="195a8-105">当所显示的表包含相关表中的行的外键的列时，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="195a8-105">This is useful when the table you display has columns containing foreign keys to rows in a related table.</span></span> <span data-ttu-id="195a8-106">在这种情况下，你可能想要替换文本中显示的列的组合框中显示列的相关表中更有意义的值与这些外键。</span><span class="sxs-lookup"><span data-stu-id="195a8-106">In this case, you may want to replace the text box columns that display these foreign keys with combo box columns that display more meaningful values from the related table.</span></span>  
  
 <span data-ttu-id="195a8-107">下面的过程需要**Windows 应用程序**具有一个窗体包含项目<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="195a8-107">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="195a8-108">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="195a8-108">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="195a8-109">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="195a8-109">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="195a8-110">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="195a8-110">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="195a8-111">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="195a8-111">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-change-the-type-of-a-column-using-the-designer"></a><span data-ttu-id="195a8-112">若要更改使用设计器的列的类型</span><span class="sxs-lookup"><span data-stu-id="195a8-112">To change the type of a column using the designer</span></span>  
  
1.  <span data-ttu-id="195a8-113">单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 右上角<xref:System.Windows.Forms.DataGridView>控制，，然后选择**编辑列**。</span><span class="sxs-lookup"><span data-stu-id="195a8-113">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control, and then select **Edit Columns**.</span></span>  
  
2.  <span data-ttu-id="195a8-114">选择从列**选定的列**列表。</span><span class="sxs-lookup"><span data-stu-id="195a8-114">Select a column from the **Selected Columns** list.</span></span>  
  
3.  <span data-ttu-id="195a8-115">在**列属性**网格中，设置`ColumnType`为新的列类型的属性。</span><span class="sxs-lookup"><span data-stu-id="195a8-115">In the **Column Properties** grid, set the `ColumnType` property to the new column type.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="195a8-116">`ColumnType`属性是仅限设计时间属性，该值指示类表示的列类型。</span><span class="sxs-lookup"><span data-stu-id="195a8-116">The `ColumnType` property is a design-time-only property that indicates the class representing the column type.</span></span> <span data-ttu-id="195a8-117">它不是实际属性列类中定义。</span><span class="sxs-lookup"><span data-stu-id="195a8-117">It is not an actual property defined in a column class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="195a8-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="195a8-118">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 [<span data-ttu-id="195a8-119">如何： 创建 Windows 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="195a8-119">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="195a8-120">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="195a8-120">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)
