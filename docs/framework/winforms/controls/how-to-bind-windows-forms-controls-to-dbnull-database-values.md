---
title: "如何：将 Windows 窗体控件绑定到 DBNull 数据库值"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c96fd6d09b2ddefce4c682976fcff86c9b562a3f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="199e4-102">如何：将 Windows 窗体控件绑定到 DBNull 数据库值</span><span class="sxs-lookup"><span data-stu-id="199e4-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="199e4-103">将 Windows 窗体绑定到数据源且该数据源返回 <xref:System.DBNull> 值时，可以直接替换相应的值，而不用处理、格式化或解析事件。</span><span class="sxs-lookup"><span data-stu-id="199e4-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="199e4-104">在格式化或解析数据源的值时，<xref:System.Windows.Forms.Binding.NullValue%2A> 属性将 <xref:System.DBNull> 转换为指定的对象。</span><span class="sxs-lookup"><span data-stu-id="199e4-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="199e4-105">示例</span><span class="sxs-lookup"><span data-stu-id="199e4-105">Example</span></span>  
 <span data-ttu-id="199e4-106">以下示例演示在两种不同情况下如何绑定 <xref:System.DBNull> 值。</span><span class="sxs-lookup"><span data-stu-id="199e4-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="199e4-107">前者演示如何为字符串属性设置 <xref:System.Windows.Forms.Binding.NullValue%2A>，后者演示如何为图像属性设置 <xref:System.Windows.Forms.Binding.NullValue%2A>。</span><span class="sxs-lookup"><span data-stu-id="199e4-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="199e4-108">绑定属性和 <xref:System.Windows.Forms.Binding.NullValue%2A> 属性的类型必需相同，否则会引发错误，并且不会继续处理 <xref:System.Windows.Forms.Binding.NullValue%2A> 值。</span><span class="sxs-lookup"><span data-stu-id="199e4-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="199e4-109">在这种情况下，将不会引发异常。</span><span class="sxs-lookup"><span data-stu-id="199e4-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="199e4-110">编译代码</span><span class="sxs-lookup"><span data-stu-id="199e4-110">Compiling the Code</span></span>  
 <span data-ttu-id="199e4-111">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="199e4-111">This example requires:</span></span>  
  
-   <span data-ttu-id="199e4-112">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="199e4-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="199e4-113">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="199e4-113">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="199e4-114">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="199e4-114">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="199e4-115">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="199e4-115">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="199e4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="199e4-116">See Also</span></span>  
 [<span data-ttu-id="199e4-117">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="199e4-117">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="199e4-118">如何：处理因数据绑定而发生的错误和异常</span><span class="sxs-lookup"><span data-stu-id="199e4-118">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](../../../../docs/framework/winforms/controls/how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)  
 [<span data-ttu-id="199e4-119">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="199e4-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
