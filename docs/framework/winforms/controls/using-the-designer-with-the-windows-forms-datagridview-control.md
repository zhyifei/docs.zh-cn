---
title: 将设计器与 Windows 窗体 DataGridView 控件结合使用
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- DataGridView control [Windows Forms], designer support
- formatting [Windows Forms]
ms.assetid: b66057a6-5983-4864-b4e7-8cbc88a7010c
ms.openlocfilehash: daac7dca27ac5dca8df4db24c9a3e22dae831377
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948000"
---
# <a name="using-the-designer-with-the-windows-forms-datagridview-control"></a><span data-ttu-id="2582e-102">将设计器与 Windows 窗体 DataGridView 控件结合使用</span><span class="sxs-lookup"><span data-stu-id="2582e-102">Using the Designer with the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2582e-103">Visual Studio 提供了设计器支持`DataGridView`使您可以执行许多安装程序任务而无需编写代码的控制。</span><span class="sxs-lookup"><span data-stu-id="2582e-103">Visual Studio provides designer support for the `DataGridView` control that enables you to perform many setup tasks without writing code.</span></span> <span data-ttu-id="2582e-104">这些任务包括的绑定到修改的列的数据源控件用于显示数据，并调整的外观和控件的基本行为。</span><span class="sxs-lookup"><span data-stu-id="2582e-104">These tasks include binding the control to a data source, modifying the columns used to display data, and adjusting the appearance and basic behavior of the control.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2582e-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2582e-105">In This Section</span></span>  
 [<span data-ttu-id="2582e-106">如何：添加和使用设计器在 Windows 窗体 DataGridView 控件中删除列</span><span class="sxs-lookup"><span data-stu-id="2582e-106">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-107">介绍如何使用**中添加列**并**编辑列**对话框来填充和修改列集合。</span><span class="sxs-lookup"><span data-stu-id="2582e-107">Describes how to use the **Add Columns** and **Edit Columns** dialog boxes to populate and modify the columns collection.</span></span>  
  
 [<span data-ttu-id="2582e-108">如何：将数据绑定到使用设计器在 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2582e-108">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>](bind-data-to-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-109">介绍如何使用**选择数据源**控件的智能标记上的选项，以连接到数据。</span><span class="sxs-lookup"><span data-stu-id="2582e-109">Describes how to use the **Choose Data Source** option on the control's smart tag to connect to data.</span></span>  
  
 [<span data-ttu-id="2582e-110">如何：更改使用设计器在 Windows 窗体 DataGridView 控件中的列顺序</span><span class="sxs-lookup"><span data-stu-id="2582e-110">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-111">介绍如何使用**编辑列**对话框可以重新排列列。</span><span class="sxs-lookup"><span data-stu-id="2582e-111">Describes how to use the **Edit Columns** dialog box to rearrange columns.</span></span>  
  
 [<span data-ttu-id="2582e-112">如何：更改 Windows 窗体 DataGridView 列使用设计器的类型</span><span class="sxs-lookup"><span data-stu-id="2582e-112">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 <span data-ttu-id="2582e-113">介绍如何使用**编辑列**对话框可以更改列类型。</span><span class="sxs-lookup"><span data-stu-id="2582e-113">Describes how to use the **Edit Columns** dialog box to change column types.</span></span>  
  
 [<span data-ttu-id="2582e-114">如何：启用列重新排序中使用设计器在 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2582e-114">How to: Enable Column Reordering in the Windows Forms DataGridView Control Using the Designer</span></span>](enable-column-reordering-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-115">介绍如何使用控件的智能标记，以便用户可以重新排列列。</span><span class="sxs-lookup"><span data-stu-id="2582e-115">Describes how to use the control's smart tag to enable users to rearrange columns.</span></span>  
  
 [<span data-ttu-id="2582e-116">如何：冻结使用设计器在 Windows 窗体 DataGridView 控件中的列</span><span class="sxs-lookup"><span data-stu-id="2582e-116">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](freeze-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-117">介绍如何使用**编辑列**对话框来防止特定列的滚动。</span><span class="sxs-lookup"><span data-stu-id="2582e-117">Describes how to use the **Edit Columns** dialog box to prevent specific columns from scrolling.</span></span>  
  
 [<span data-ttu-id="2582e-118">如何：在使用设计器在 Windows 窗体 DataGridView 控件中隐藏列</span><span class="sxs-lookup"><span data-stu-id="2582e-118">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](hide-columns-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-119">介绍如何使用**编辑列**对话框可以隐藏特定的列。</span><span class="sxs-lookup"><span data-stu-id="2582e-119">Describes how to use the **Edit Columns** dialog box to hide specific columns.</span></span>  
  
 [<span data-ttu-id="2582e-120">如何：使列成为只读使用设计器在 Windows 窗体 DataGridView 控件中</span><span class="sxs-lookup"><span data-stu-id="2582e-120">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-121">介绍如何使用**编辑列**对话框中，若要阻止用户编辑中的特定列的值。</span><span class="sxs-lookup"><span data-stu-id="2582e-121">Describes how to use the **Edit Columns** dialog box to prevent users from editing values in specific columns.</span></span>  
  
 [<span data-ttu-id="2582e-122">如何：防止添加和使用设计器在 Windows 窗体 DataGridView 控件中的删除行</span><span class="sxs-lookup"><span data-stu-id="2582e-122">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer</span></span>](prevent-row-addition-and-deletion-in-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-123">介绍如何使用控件的智能标记以防止用户添加或删除行。</span><span class="sxs-lookup"><span data-stu-id="2582e-123">Describes how to use the control's smart tag to prevent users from adding or deleting rows.</span></span>  
  
 [<span data-ttu-id="2582e-124">如何：设置为使用设计器在 Windows 窗体 DataGridView 控件中交替行样式</span><span class="sxs-lookup"><span data-stu-id="2582e-124">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control Using the Designer</span></span>](set-alternating-row-styles-for-the-datagrid-using-the-designer.md)  
 <span data-ttu-id="2582e-125">介绍如何使用**CellStyle 生成器**对话框控件中创建类似分类帐的外观。</span><span class="sxs-lookup"><span data-stu-id="2582e-125">Describes how to use the **CellStyle Builder** dialog box to create a ledger-like appearance in the control.</span></span>  
  
 [<span data-ttu-id="2582e-126">如何：有关使用设计器在 Windows 窗体 DataGridView 控件中设置默认单元格样式和数据格式</span><span class="sxs-lookup"><span data-stu-id="2582e-126">How to: Set Default Cell Styles and Data Formats for the Windows Forms DataGridView Control Using the Designer</span></span>](default-cell-styles-datagridview.md)  
 <span data-ttu-id="2582e-127">介绍如何使用**CellStyle 生成器**对话框中，若要设置的基本外观和数据显示格式以获得该控件。</span><span class="sxs-lookup"><span data-stu-id="2582e-127">Describes how to use the **CellStyle Builder** dialog box to set up the basic appearance and data-display formats for the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2582e-128">参考</span><span class="sxs-lookup"><span data-stu-id="2582e-128">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="2582e-129">提供关于 <xref:System.Windows.Forms.DataGridView> 控件的参考文档。</span><span class="sxs-lookup"><span data-stu-id="2582e-129">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2582e-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="2582e-130">See also</span></span>

- [<span data-ttu-id="2582e-131">DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="2582e-131">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
