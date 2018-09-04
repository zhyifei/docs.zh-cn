---
title: 如何：将 Windows 窗体控件绑定到 Factory 对象
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- controls [Windows Forms], binding
- factory objects [Windows Forms], binding to
- BindingSource component [Windows Forms], binding to a factory object
- BindingSource component [Windows Forms], examples
ms.assetid: 7d59af89-ff82-41d8-a48a-f1fbae788b0d
ms.openlocfilehash: f085e7b7d20f958a90777ddb820924a07a5e2d8d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43534985"
---
# <a name="how-to-bind-a-windows-forms-control-to-a-factory-object"></a><span data-ttu-id="74df6-102">如何：将 Windows 窗体控件绑定到 Factory 对象</span><span class="sxs-lookup"><span data-stu-id="74df6-102">How to: Bind a Windows Forms Control to a Factory Object</span></span>
<span data-ttu-id="74df6-103">生成与数据交互的控件时，有时需要将控件绑定到生成其他对象的对象或方法。</span><span class="sxs-lookup"><span data-stu-id="74df6-103">When you are building controls that interact with data, you will sometimes find it necessary to bind a control to an object or method that generates other objects.</span></span> <span data-ttu-id="74df6-104">此类对象或方法被称为 Factory。</span><span class="sxs-lookup"><span data-stu-id="74df6-104">Such an object or method is called a factory.</span></span> <span data-ttu-id="74df6-105">例如，数据源可能是方法调用的返回值，而不是内存中的对象或类型。</span><span class="sxs-lookup"><span data-stu-id="74df6-105">Your data source might be, for example, the return value from a method call, instead of an object in memory or a type.</span></span> <span data-ttu-id="74df6-106">只要源返回集合，即可将控件绑定到此类数据源。</span><span class="sxs-lookup"><span data-stu-id="74df6-106">You can bind a control to this kind of data source as long as the source returns a collection.</span></span>  
  
 <span data-ttu-id="74df6-107">借助 <xref:System.Windows.Forms.BindingSource> 控件可轻松将控件绑定到工厂对象。</span><span class="sxs-lookup"><span data-stu-id="74df6-107">You can easily bind a control to a factory object by using the <xref:System.Windows.Forms.BindingSource> control.</span></span>  
  
## <a name="example"></a><span data-ttu-id="74df6-108">示例</span><span class="sxs-lookup"><span data-stu-id="74df6-108">Example</span></span>  
 <span data-ttu-id="74df6-109">下面的示例演示了如何使用 <xref:System.Windows.Forms.BindingSource> 控件将 <xref:System.Windows.Forms.DataGridView> 控件绑定到工厂方法。</span><span class="sxs-lookup"><span data-stu-id="74df6-109">The following example demonstrates how to bind a <xref:System.Windows.Forms.DataGridView> control to a factory method by using a <xref:System.Windows.Forms.BindingSource> control.</span></span> <span data-ttu-id="74df6-110">Factory 方法命名为 `GetOrdersByCustomerId`，并返回 Northwind 数据库中给定客户的所有订单。</span><span class="sxs-lookup"><span data-stu-id="74df6-110">The factory method is named `GetOrdersByCustomerId`, and it returns all the orders for a given customer in the Northwind database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CPP/form1.cpp#1)]
 [!code-csharp[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnector.BindToFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnector.BindToFactory/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="74df6-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="74df6-111">Compiling the Code</span></span>  
 <span data-ttu-id="74df6-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="74df6-112">This example requires:</span></span>  
  
-   <span data-ttu-id="74df6-113">对 System、System.Data、System.Drawing 和 System.Windows.Forms 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="74df6-113">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
 <span data-ttu-id="74df6-114">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="74df6-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="74df6-115">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="74df6-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="74df6-116">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="74df6-116">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74df6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="74df6-117">See Also</span></span>  
 <xref:System.Windows.Forms.BindingNavigator>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="74df6-118">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="74df6-118">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)  
 [<span data-ttu-id="74df6-119">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="74df6-119">How to: Bind a Windows Forms Control to a Type</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-a-windows-forms-control-to-a-type.md)
