---
title: 如何：创建未绑定的 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], unbound data
- DataGridView control [Windows Forms], displaying data without binding to a data source
- data [Windows Forms], unbound
ms.assetid: b5d4b47d-9a28-4d88-9dba-0a3c90fba71d
ms.openlocfilehash: da59f02c3f0465d330f73cfd5453d5bce58fca12
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57718371"
---
# <a name="how-to-create-an-unbound-windows-forms-datagridview-control"></a><span data-ttu-id="1c2e3-102">如何：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="1c2e3-102">How to: Create an Unbound Windows Forms DataGridView Control</span></span>
<span data-ttu-id="1c2e3-103">下面的代码示例演示如何以编程方式填充 <xref:System.Windows.Forms.DataGridView> 控件，而无需将其绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="1c2e3-103">The following code example demonstrates how to populate a <xref:System.Windows.Forms.DataGridView> control programmatically without binding it to a data source.</span></span> <span data-ttu-id="1c2e3-104">当有少量要以表格格式显示的数据时，这会非常有用。</span><span class="sxs-lookup"><span data-stu-id="1c2e3-104">This is useful when you have a small amount of data that you want to display in a table format.</span></span>  
  
 <span data-ttu-id="1c2e3-105">此代码示例的完整说明，请参阅[演练：创建未绑定的 Windows 窗体 DataGridView 控件](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2e3-105">For a complete explanation of this code example, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="1c2e3-106">示例</span><span class="sxs-lookup"><span data-stu-id="1c2e3-106">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/CS/simpleunbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewSimpleUnbound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewSimpleUnbound/VB/simpleunbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1c2e3-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="1c2e3-107">Compiling the Code</span></span>  
 <span data-ttu-id="1c2e3-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="1c2e3-108">This example requires:</span></span>  
  
-   <span data-ttu-id="1c2e3-109">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="1c2e3-109">References to the System, System.Drawing, and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="1c2e3-110">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="1c2e3-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="1c2e3-111">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="1c2e3-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  

## <a name="see-also"></a><span data-ttu-id="1c2e3-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c2e3-112">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="1c2e3-113">演练：创建未绑定的 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="1c2e3-113">Walkthrough: Creating an Unbound Windows Forms DataGridView Control</span></span>](walkthrough-creating-an-unbound-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1c2e3-114">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="1c2e3-114">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="1c2e3-115">Windows 窗体 DataGridView 控件中的数据显示模式</span><span class="sxs-lookup"><span data-stu-id="1c2e3-115">Data Display Modes in the Windows Forms DataGridView Control</span></span>](data-display-modes-in-the-windows-forms-datagridview-control.md)
