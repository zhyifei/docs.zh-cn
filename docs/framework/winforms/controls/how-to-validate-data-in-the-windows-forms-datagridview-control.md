---
title: 如何：验证 Windows 窗体 DataGridView 控件中的数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data [Windows Forms], validation
- DataGridView control [Windows Forms], data validation
- data grids [Windows Forms], validating data
- data validation [Windows Forms], Windows Forms
ms.assetid: d10aef35-701e-4a3c-a684-2a2ed1aeaca6
ms.openlocfilehash: dae254c14790841b37162fca9f998be429006125
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61785731"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="6b1dd-102">如何：验证 Windows 窗体 DataGridView 控件中的数据</span><span class="sxs-lookup"><span data-stu-id="6b1dd-102">How to: Validate Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="6b1dd-103">下面的代码示例演示如何验证由用户输入到 <xref:System.Windows.Forms.DataGridView> 控件中的数据。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-103">The following code example demonstrates how to validate data entered by a user into a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="6b1dd-104">在此示例中，使用 Northwind 示例数据的 `Customers` 表中的行填充 <xref:System.Windows.Forms.DataGridView>。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-104">In this example, the <xref:System.Windows.Forms.DataGridView> is populated with rows from the `Customers` table of the Northwind sample database.</span></span> <span data-ttu-id="6b1dd-105">用户编辑 `CompanyName` 列中的单元格时，通过检查单元格不为空而测试其值的有效性。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-105">When the user edits a cell in the `CompanyName` column, its value is tested for validity by checking that it is not empty.</span></span> <span data-ttu-id="6b1dd-106">如果 <xref:System.Windows.Forms.DataGridView.CellValidating> 事件的事件处理程序发现该值为空字符串，<xref:System.Windows.Forms.DataGridView> 会阻止用户退出单元格，直到输入了一个非空字符串。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-106">If the event handler for the <xref:System.Windows.Forms.DataGridView.CellValidating> event finds that the value is an empty string, the <xref:System.Windows.Forms.DataGridView> prevents the user from exiting the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="6b1dd-107">此代码示例的完整说明，请参阅[演练：验证 Windows 中的数据窗体 DataGridView 控件](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-107">For a complete explanation of this code example, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6b1dd-108">示例</span><span class="sxs-lookup"><span data-stu-id="6b1dd-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6b1dd-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="6b1dd-109">Compiling the Code</span></span>  
 <span data-ttu-id="6b1dd-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="6b1dd-110">This example requires:</span></span>  
  
- <span data-ttu-id="6b1dd-111">引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-111">References to the System, System.Data, System.Windows.Forms and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="6b1dd-112">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-112">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="6b1dd-113">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-113">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="6b1dd-114">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="6b1dd-114">.NET Framework Security</span></span>  
 <span data-ttu-id="6b1dd-115">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-115">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="6b1dd-116">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-116">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="6b1dd-117">有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="6b1dd-117">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b1dd-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="6b1dd-118">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="6b1dd-119">演练：验证 Windows 窗体 DataGridView 控件中的数据</span><span class="sxs-lookup"><span data-stu-id="6b1dd-119">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6b1dd-120">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="6b1dd-120">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="6b1dd-121">演练：Windows 窗体 DataGridView 控件中的数据输入时发生的错误处理</span><span class="sxs-lookup"><span data-stu-id="6b1dd-121">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="6b1dd-122">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="6b1dd-122">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
