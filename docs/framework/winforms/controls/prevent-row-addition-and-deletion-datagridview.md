---
title: 如何：防止在 Windows 窗体 DataGridView 控件中添加和删除行
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], disabling data entry
- data entry [Windows Forms], disabling in grids
- data grids [Windows Forms], disabling data entry
ms.assetid: ef9539ce-539b-404e-84b6-ac282b64b88c
ms.openlocfilehash: 6263c92e6a981983c19e9d7f2357c581bee5ec07
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43875370"
---
# <a name="how-to-prevent-row-addition-and-deletion-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d7d09-102">如何：防止在 Windows 窗体 DataGridView 控件中添加和删除行</span><span class="sxs-lookup"><span data-stu-id="d7d09-102">How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d7d09-103">有时想要阻止用户在 <xref:System.Windows.Forms.DataGridView> 控件中输入新的数据行或删除现有行。</span><span class="sxs-lookup"><span data-stu-id="d7d09-103">Sometimes you will want to prevent users from entering new rows of data or deleting existing rows in your <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="d7d09-104"><xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> 属性指示新记录的行是否显示在控件底部，而 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> 属性指示行是否可删除。</span><span class="sxs-lookup"><span data-stu-id="d7d09-104">The <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A> property indicates whether the row for new records is present at the bottom of the control, while the <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A> property indicates whether rows can be removed.</span></span> <span data-ttu-id="d7d09-105">以下代码示例使用这些属性，并设置 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> 属性以使控件完全只读。</span><span class="sxs-lookup"><span data-stu-id="d7d09-105">The following code example uses these properties and also sets the <xref:System.Windows.Forms.DataGridView.ReadOnly%2A> property to make the control entirely read-only.</span></span>  
  
 <span data-ttu-id="d7d09-106">Visual Studio 中对此任务提供支持。</span><span class="sxs-lookup"><span data-stu-id="d7d09-106">There is support for this task in Visual Studio.</span></span>  <span data-ttu-id="d7d09-107">另请参阅[如何： 防止添加和删除行在 Windows 窗体 DataGridView 控件中使用设计器](https://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="d7d09-107">Also see [How to: Prevent Row Addition and Deletion in the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/k5c88sw3\(v=vs.110\)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7d09-108">示例</span><span class="sxs-lookup"><span data-stu-id="d7d09-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#090)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#090](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#090)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7d09-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="d7d09-109">Compiling the Code</span></span>  
 <span data-ttu-id="d7d09-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d7d09-110">This example requires:</span></span>  
  
-   <span data-ttu-id="d7d09-111">名为 `dataGridView1` 的 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="d7d09-111">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1`.</span></span>  
  
-   <span data-ttu-id="d7d09-112">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="d7d09-112">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7d09-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7d09-113">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.ReadOnly%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToAddRows%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.AllowUserToDeleteRows%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="d7d09-114">Windows 窗体 DataGridView 控件中的列、行和单元格基本功能</span><span class="sxs-lookup"><span data-stu-id="d7d09-114">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)
