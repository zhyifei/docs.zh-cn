---
title: 如何：使用 Windows 窗体 BindingNavigator 控件浏览数据集
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- datasets [Windows Forms], moving through
- BindingNavigator control [Windows Forms], moving through datasets
- examples [Windows Forms], BindingNavigator control
ms.assetid: 146d97be-3d97-400e-accb-860bbf47729d
ms.openlocfilehash: 3f9759eab464d0f66712358705e2481532412162
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649215"
---
# <a name="how-to-move-through-a-dataset-with-the-windows-forms-bindingnavigator-control"></a><span data-ttu-id="80672-102">如何：使用 Windows 窗体 BindingNavigator 控件浏览数据集</span><span class="sxs-lookup"><span data-stu-id="80672-102">How to: Move Through a DataSet with the Windows Forms BindingNavigator Control</span></span>
<span data-ttu-id="80672-103">生成数据驱动的应用程序时，经常需要向用户显示数据集合。</span><span class="sxs-lookup"><span data-stu-id="80672-103">As you build data-driven applications, you will often need to display collections of data to users.</span></span> <span data-ttu-id="80672-104"><xref:System.Windows.Forms.BindingNavigator> 控件与 <xref:System.Windows.Forms.BindingSource> 组件一起为滚动集合并按顺序显示其中的项提供方便的可扩展解决方案。</span><span class="sxs-lookup"><span data-stu-id="80672-104">The <xref:System.Windows.Forms.BindingNavigator> control, in conjunction with the <xref:System.Windows.Forms.BindingSource> component, provides a convenient and extensible solution for moving through a collection and displaying items sequentially.</span></span>  
  
## <a name="example"></a><span data-ttu-id="80672-105">示例</span><span class="sxs-lookup"><span data-stu-id="80672-105">Example</span></span>  
 <span data-ttu-id="80672-106">下面的代码示例演示如何使用 <xref:System.Windows.Forms.BindingNavigator> 控件来浏览数据。</span><span class="sxs-lookup"><span data-stu-id="80672-106">The following code example demonstrates how to use a <xref:System.Windows.Forms.BindingNavigator> control to move through data.</span></span> <span data-ttu-id="80672-107">集合包含在 <xref:System.Data.DataView> 中，后者使用 <xref:System.Windows.Forms.BindingSource> 组件绑定到 <xref:System.Windows.Forms.TextBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="80672-107">The set is contained in a <xref:System.Data.DataView>, which is bound to a <xref:System.Windows.Forms.TextBox> control with a <xref:System.Windows.Forms.BindingSource> component.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="80672-108">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="80672-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="80672-109">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="80672-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="80672-110">有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="80672-110">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataNavigator#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataNavigator#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataNavigator/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="80672-111">编译代码</span><span class="sxs-lookup"><span data-stu-id="80672-111">Compiling the Code</span></span>  
 <span data-ttu-id="80672-112">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="80672-112">This example requires:</span></span>  
  
- <span data-ttu-id="80672-113">对 System、System.Data、System.Drawing、System.Windows.Forms 和 System.Xml 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="80672-113">References to the System, System.Data, System.Drawing, System.Windows.Forms and System.Xml assemblies.</span></span>  
  
 <span data-ttu-id="80672-114">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="80672-114">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="80672-115">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="80672-115">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80672-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="80672-116">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="80672-117">BindingNavigator 控件</span><span class="sxs-lookup"><span data-stu-id="80672-117">BindingNavigator Control</span></span>](bindingnavigator-control-windows-forms.md)
- [<span data-ttu-id="80672-118">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="80672-118">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="80672-119">如何：将 Windows 窗体控件绑定到类型</span><span class="sxs-lookup"><span data-stu-id="80672-119">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
