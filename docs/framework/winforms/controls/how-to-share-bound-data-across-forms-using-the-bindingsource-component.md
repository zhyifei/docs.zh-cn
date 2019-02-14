---
title: 如何：使用 BindingSource 组件跨窗体共享绑定数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- examples [Windows Forms], BindingSource component
- data binding [Windows Forms], sharing data across forms
- BindingSource component [Windows Forms], examples
- BindingSource [Windows Forms], using with multiple forms
ms.assetid: a1a49630-db9c-4485-b888-1f62a373a4f7
ms.openlocfilehash: 6631fb4c4483853b3c4ba6c2e3484654c4f83342
ms.sourcegitcommit: af0a22a4eb11bbcd33baec49150d551955b50a16
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "56260837"
---
# <a name="how-to-share-bound-data-across-forms-using-the-bindingsource-component"></a><span data-ttu-id="38093-102">如何：使用 BindingSource 组件跨窗体共享绑定数据</span><span class="sxs-lookup"><span data-stu-id="38093-102">How to: Share Bound Data Across Forms Using the BindingSource Component</span></span>
<span data-ttu-id="38093-103">使用 <xref:System.Windows.Forms.BindingSource> 组件可轻松跨窗体共享数据。</span><span class="sxs-lookup"><span data-stu-id="38093-103">You can easily share data across forms using the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="38093-104">例如，你可能想要展示一个对数据源数据进行汇总的只读窗体和另一个包含有关数据源中当前所选项的详细信息的可编辑窗体。</span><span class="sxs-lookup"><span data-stu-id="38093-104">For example, you may want to display one read-only form that summarizes the data-source data and another editable form that contains detailed information about the currently selected item in the data source.</span></span> <span data-ttu-id="38093-105">此示例演示这种情况。</span><span class="sxs-lookup"><span data-stu-id="38093-105">This example demonstrates this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="38093-106">示例</span><span class="sxs-lookup"><span data-stu-id="38093-106">Example</span></span>  
 <span data-ttu-id="38093-107">下面的代码示例演示如何跨窗体共享 <xref:System.Windows.Forms.BindingSource> 及其绑定数据。</span><span class="sxs-lookup"><span data-stu-id="38093-107">The following code example demonstrates how to share a <xref:System.Windows.Forms.BindingSource> and its bound data across forms.</span></span> <span data-ttu-id="38093-108">在此示例中，共享的 <xref:System.Windows.Forms.BindingSource> 传递给子窗体的构造函数。</span><span class="sxs-lookup"><span data-stu-id="38093-108">In this example, the shared <xref:System.Windows.Forms.BindingSource> is passed to the constructor of the child form.</span></span> <span data-ttu-id="38093-109">子窗体使用户可编辑主窗体中当前所选项的数据。</span><span class="sxs-lookup"><span data-stu-id="38093-109">The child form allows the user to edit the data for the currently selected item in the main form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38093-110">示例中处理了 <xref:System.Windows.Forms.BindingSource> 组件的 <xref:System.Windows.Forms.BindingSource.BindingComplete> 事件，以确保两个窗体保持同步。</span><span class="sxs-lookup"><span data-stu-id="38093-110">The <xref:System.Windows.Forms.BindingSource.BindingComplete> event for the <xref:System.Windows.Forms.BindingSource> component is handled in the example to ensure that the two forms remain synchronized.</span></span> <span data-ttu-id="38093-111">这操作的原因的详细信息，请参阅[如何：确保多个控件绑定到相同的数据源保持同步](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md)。</span><span class="sxs-lookup"><span data-stu-id="38093-111">For more information about why this is done, see [How to: Ensure Multiple Controls Bound to the Same Data Source Remain Synchronized](../../../../docs/framework/winforms/multiple-controls-bound-to-data-source-synchronized.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/CS/Form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingSourceMultipleForms#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingSourceMultipleForms/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="38093-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="38093-112">Compiling the Code</span></span>  
 <span data-ttu-id="38093-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="38093-113">This example requires:</span></span>  
  
-   <span data-ttu-id="38093-114">对 System、System.Windows.Forms、System.Drawing、System.Data 和 System.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="38093-114">References to the System, System.Windows.Forms, System.Drawing, System.Data, and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="38093-115">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="38093-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="38093-116">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="38093-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38093-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="38093-117">See also</span></span>
- [<span data-ttu-id="38093-118">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="38093-118">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
- [<span data-ttu-id="38093-119">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="38093-119">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="38093-120">如何：处理错误和因数据绑定而发生的异常</span><span class="sxs-lookup"><span data-stu-id="38093-120">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
