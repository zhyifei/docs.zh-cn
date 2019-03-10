---
title: 如何：将对象绑定到 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], object binding
- data grids [Windows Forms], object binding
- object binding [Windows Forms], DataGridView control
ms.assetid: cb8f29fa-577e-4e2b-883f-3a01c6189b9c
ms.openlocfilehash: 9f3ce61b3692f0b83298bdf9a19cb98fb5d5ab7f
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723798"
---
# <a name="how-to-bind-objects-to-windows-forms-datagridview-controls"></a><span data-ttu-id="f72fd-102">如何：将对象绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="f72fd-102">How to: Bind Objects to Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="f72fd-103">下面的代码示例演示如何将对象集合绑定到 <xref:System.Windows.Forms.DataGridView> 控件，以便每个对象可显示为单独的一行。</span><span class="sxs-lookup"><span data-stu-id="f72fd-103">The following code example demonstrates how to bind a collection of objects to a <xref:System.Windows.Forms.DataGridView> control so that each object displays as a separate row.</span></span> <span data-ttu-id="f72fd-104">此示例还演示了如何显示 <xref:System.Windows.Forms.DataGridViewComboBoxColumn> 中具有枚举类型的属性，从而使组合框下拉列表包含枚举值。</span><span class="sxs-lookup"><span data-stu-id="f72fd-104">This example also illustrates how to display a property with an enumeration type in a <xref:System.Windows.Forms.DataGridViewComboBoxColumn> so that the combo box drop-down list contains the enumeration values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f72fd-105">示例</span><span class="sxs-lookup"><span data-stu-id="f72fd-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/CS/collectionbound.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView._CollectionBound#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView._CollectionBound/VB/collectionbound.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f72fd-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="f72fd-106">Compiling the Code</span></span>  
 <span data-ttu-id="f72fd-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f72fd-107">This example requires:</span></span>  
  
-   <span data-ttu-id="f72fd-108">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="f72fd-108">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="f72fd-109">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="f72fd-109">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="f72fd-110">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="f72fd-110">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f72fd-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f72fd-111">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- [<span data-ttu-id="f72fd-112">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="f72fd-112">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f72fd-113">如何：访问对象绑定到 Windows 窗体 DataGridView 行</span><span class="sxs-lookup"><span data-stu-id="f72fd-113">How to: Access Objects Bound to Windows Forms DataGridView Rows</span></span>](how-to-access-objects-bound-to-windows-forms-datagridview-rows.md)
