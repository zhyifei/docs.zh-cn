---
title: 创建未绑定的 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: 0b477eba6d8455554d72dc7ec8cfce68a91add38
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731004"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="fdb91-102">如何：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="fdb91-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="fdb91-103">下面的代码示例演示如何以编程方式填充 <xref:System.Windows.Forms.DataGridView> 控件，而无需将其绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="fdb91-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="fdb91-104">当有少量要以表格格式显示的数据时，这会非常有用。</span><span class="sxs-lookup"><span data-stu-id="fdb91-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="fdb91-105">有关此代码示例的完整说明，请参阅[演练：创建未绑定的 Windows 窗体 DataGridView 控件](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="fdb91-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdb91-106">示例</span><span class="sxs-lookup"><span data-stu-id="fdb91-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fdb91-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="fdb91-107">Compiling the Code</span></span>  
 <span data-ttu-id="fdb91-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="fdb91-108">This example requires:</span></span>  
  
- <span data-ttu-id="fdb91-109">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="fdb91-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fdb91-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fdb91-110">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="fdb91-111">演练：创建未绑定 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="fdb91-111">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fdb91-112">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="fdb91-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="fdb91-113">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="fdb91-113">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
