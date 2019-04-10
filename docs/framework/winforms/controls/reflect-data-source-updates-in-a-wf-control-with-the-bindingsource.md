---
title: 如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], updating
- BindingSource component [Windows Forms], updating data binding
- examples [Windows Forms], BindingSource component
- data sources [Windows Forms], updating
- BindingSource component [Windows Forms], examples
ms.assetid: bd8bd9b2-af8a-4f11-a3d5-54eecbe2400b
ms.openlocfilehash: 16dbe4da1efecd120d4da4d66c3d79ec907b92a6
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218638"
---
# <a name="how-to-reflect-data-source-updates-in-a-windows-forms-control-with-the-bindingsource"></a><span data-ttu-id="e529b-102">如何：使用 BindingSource 在 Windows 窗体控件中反映数据源更新</span><span class="sxs-lookup"><span data-stu-id="e529b-102">How to: Reflect Data Source Updates in a Windows Forms Control with the BindingSource</span></span>
<span data-ttu-id="e529b-103">使用绑定数据的控件时，如果数据源不引发更改列表的事件，有时需要对数据源中的更改作出响应。</span><span class="sxs-lookup"><span data-stu-id="e529b-103">When you use data-bound controls, you sometimes have to respond to changes in the data source when the data source does not raise list-changed events.</span></span> <span data-ttu-id="e529b-104">当使用 <xref:System.Windows.Forms.BindingSource> 组件将数据源绑定到 Windows 窗体控件时，可以通过调用 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 方法通知控件数据源已更改。</span><span class="sxs-lookup"><span data-stu-id="e529b-104">When you use the <xref:System.Windows.Forms.BindingSource> component to bind your data source to a Windows Forms control, you can notify the control that your data source has changed by calling the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e529b-105">示例</span><span class="sxs-lookup"><span data-stu-id="e529b-105">Example</span></span>  
 <span data-ttu-id="e529b-106">下面的代码示例演示如何使用 <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> 方法通知绑定的控件有关数据源中的更新。</span><span class="sxs-lookup"><span data-stu-id="e529b-106">The following code example demonstrates using the <xref:System.Windows.Forms.BindingSource.ResetBindings%2A> method to notify a bound control about an update in the data source.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetBindings#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetBindings/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e529b-107">编译代码</span><span class="sxs-lookup"><span data-stu-id="e529b-107">Compiling the Code</span></span>  
 <span data-ttu-id="e529b-108">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="e529b-108">This example requires:</span></span>  
  
-   <span data-ttu-id="e529b-109">对 System、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="e529b-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="e529b-110">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="e529b-110">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="e529b-111">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="e529b-111">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e529b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="e529b-112">See also</span></span>

- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="e529b-113">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="e529b-113">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="e529b-114">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="e529b-114">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
