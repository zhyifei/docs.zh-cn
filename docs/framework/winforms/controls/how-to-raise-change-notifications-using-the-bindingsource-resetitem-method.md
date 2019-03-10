---
title: 如何：使用 BindingSource ResetItem 方法引发更改通知
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- change notifications [Windows Forms], raising
- data binding [Windows Forms], change notifications
- BindingSource component [Windows Forms], raising change notifications with
- data sources [Windows Forms], detecting changes
- change notifications
ms.assetid: ab8b4096-37ff-4e30-aabc-de79a2f2e972
ms.openlocfilehash: a24adf06999784476cd40b91ed53c068b94819e0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57721887"
---
# <a name="how-to-raise-change-notifications-using-the-bindingsource-resetitem-method"></a><span data-ttu-id="50577-102">如何：使用 BindingSource ResetItem 方法引发更改通知</span><span class="sxs-lookup"><span data-stu-id="50577-102">How to: Raise Change Notifications Using the BindingSource ResetItem Method</span></span>
<span data-ttu-id="50577-103">当对项进行更改、添加或删除时，控件的一些数据源不会引发更改通知。</span><span class="sxs-lookup"><span data-stu-id="50577-103">Some data sources for your controls do not raise change notifications when items are changed, added, or deleted.</span></span> <span data-ttu-id="50577-104">使用 <xref:System.Windows.Forms.BindingSource> 组件，可以绑定到此类数据源并从代码引发更改通知。</span><span class="sxs-lookup"><span data-stu-id="50577-104">With the <xref:System.Windows.Forms.BindingSource> component, you can bind to such data sources and raise a change notification from your code.</span></span>  
  
## <a name="example"></a><span data-ttu-id="50577-105">示例</span><span class="sxs-lookup"><span data-stu-id="50577-105">Example</span></span>  
 <span data-ttu-id="50577-106">此窗体演示了使用 <xref:System.Windows.Forms.BindingSource> 组件将列表绑定到 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="50577-106">This form demonstrates using a <xref:System.Windows.Forms.BindingSource> component to bind a list to a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="50577-107">该列表不会引发更改通知，因此当更改列表中的项时，会调用 <xref:System.Windows.Forms.BindingSource> 上的 <xref:System.Windows.Forms.BindingSource.ResetItem%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="50577-107">The list does not raise change notifications, so the <xref:System.Windows.Forms.BindingSource.ResetItem%2A> method on the <xref:System.Windows.Forms.BindingSource> is called when an item in the list is changed.</span></span> <span data-ttu-id="50577-108">.</span><span class="sxs-lookup"><span data-stu-id="50577-108">.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.ResetItem#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.ResetItem/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="50577-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="50577-109">Compiling the Code</span></span>  
 <span data-ttu-id="50577-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="50577-110">This example requires:</span></span>  
  
-   <span data-ttu-id="50577-111">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="50577-111">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="50577-112">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="50577-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="50577-113">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="50577-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50577-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="50577-114">See also</span></span>
- <xref:System.Windows.Forms.BindingNavigator>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="50577-115">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="50577-115">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="50577-116">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="50577-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
