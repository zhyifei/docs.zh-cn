---
title: "如何：将 Windows 窗体控件绑定到类型"
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
- controls [Windows Forms], binding to a type
- BindingSource component [Windows Forms], binding to a type
- types [Windows Forms], binding controls to
ms.assetid: 94faeebb-d2bc-45d6-86d7-96a42661b43d
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d346e1f853d735e8aae0dd5647c14ac6eb8c237b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-a-windows-forms-control-to-a-type"></a><span data-ttu-id="bf376-102">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="bf376-102">How to: Bind a Windows Forms Control to a Type</span></span>
<span data-ttu-id="bf376-103">在生成与数据交互的控件时，有时需要将控件绑定到类型而非对象。</span><span class="sxs-lookup"><span data-stu-id="bf376-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to a type, rather than an object.</span></span> <span data-ttu-id="bf376-104">在设计时，如果数据不可用但数据绑定控件仍需要显示类型的公共接口中的信息，则尤其可能出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="bf376-104">This situation arises especially at design time, when data may not be available, but your data-bound controls still need to display information from a type's public interface.</span></span> <span data-ttu-id="bf376-105">例如，你可以将 <xref:System.Windows.Forms.DataGridView> 控件绑定到由 Web 服务公开的对象，并希望 <xref:System.Windows.Forms.DataGridView> 控件在设计时用自定义类型的成员名称标记其列。</span><span class="sxs-lookup"><span data-stu-id="bf376-105">For example, you may bind a <xref:System.Windows.Forms.DataGridView> control to an object exposed by a Web service and want the <xref:System.Windows.Forms.DataGridView> control to label its columns at design time with the member names of a custom type.</span></span>  
  
 <span data-ttu-id="bf376-106">你可以使用 <xref:System.Windows.Forms.BindingSource> 组件轻松将控件绑定到某一类型。</span><span class="sxs-lookup"><span data-stu-id="bf376-106">You can easily bind a control to a type with the <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bf376-107">示例</span><span class="sxs-lookup"><span data-stu-id="bf376-107">Example</span></span>  
 <span data-ttu-id="bf376-108">下面的代码示例演示如何利用 <xref:System.Windows.Forms.BindingSource> 组件将 <xref:System.Windows.Forms.DataGridView> 控件绑定到一个自定义类型。</span><span class="sxs-lookup"><span data-stu-id="bf376-108">The following code example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a custom type by using a <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="bf376-109">运行该示例时，你会注意到，在用数据填充控件之前，<xref:System.Windows.Forms.DataGridView> 具有反映 `Customer` 对象属性的标记列。</span><span class="sxs-lookup"><span data-stu-id="bf376-109">When you run the example, you'll notice the <xref:System.Windows.Forms.DataGridView> has labeled columns that reflect the properties of a `Customer` object, before the control is populated with data.</span></span> <span data-ttu-id="bf376-110">本示例具有“添加客户”按钮，用于将数据添加到 <xref:System.Windows.Forms.DataGridView> 控件。</span><span class="sxs-lookup"><span data-stu-id="bf376-110">The example has an Add Customer button to add data to the <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="bf376-111">单击该按钮时，一个新的 `Customer` 对象即添加到 <xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="bf376-111">When you click the button, a new `Customer` object is added to the <xref:System.Windows.Forms.BindingSource>.</span></span> <span data-ttu-id="bf376-112">在实际情况中，可以通过调用 Web 服务或其他数据源来获取数据。</span><span class="sxs-lookup"><span data-stu-id="bf376-112">In a real-world scenario, the data might be obtained by a call to a Web service or other data source.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindingToType#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindingToType/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="bf376-113">编译代码</span><span class="sxs-lookup"><span data-stu-id="bf376-113">Compiling the Code</span></span>  
 <span data-ttu-id="bf376-114">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="bf376-114">This example requires:</span></span>  
  
-   <span data-ttu-id="bf376-115">对 System 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="bf376-115">References to the System and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="bf376-116">有关从 [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] 或 [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)] 的命令行生成此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[在命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="bf376-116">For information about building this example from the command line for [!INCLUDE[vbprvb](../../../../includes/vbprvb-md.md)] or [!INCLUDE[csprcs](../../../../includes/csprcs-md.md)], see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="bf376-117">还可以通过将代码粘贴到新项目，在 [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] 中生成此示例。</span><span class="sxs-lookup"><span data-stu-id="bf376-117">You can also build this example in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] by pasting the code into a new project.</span></span>  <span data-ttu-id="bf376-118">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="bf376-118">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf376-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="bf376-119">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="bf376-120">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="bf376-120">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
