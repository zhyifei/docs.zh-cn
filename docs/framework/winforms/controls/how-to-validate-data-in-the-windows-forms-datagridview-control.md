---
title: 在 DataGridView 控件中验证数据
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
ms.openlocfilehash: 5fd881829f87fa1dec135d936f22996f196b0594
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76728304"
---
# <a name="how-to-validate-data-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="f907d-102">如何：验证 Windows 窗体 DataGridView 控件中的数据</span><span class="sxs-lookup"><span data-stu-id="f907d-102">How to: Validate Data in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="f907d-103">下面的代码示例演示如何验证由用户输入到 <xref:System.Windows.Forms.DataGridView> 控件中的数据。</span><span class="sxs-lookup"><span data-stu-id="f907d-103">The following code example demonstrates how to validate data entered by a user into a <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="f907d-104">在此示例中，使用 Northwind 示例数据的 `Customers` 表中的行填充 <xref:System.Windows.Forms.DataGridView>。</span><span class="sxs-lookup"><span data-stu-id="f907d-104">In this example, the <xref:System.Windows.Forms.DataGridView> is populated with rows from the `Customers` table of the Northwind sample database.</span></span> <span data-ttu-id="f907d-105">用户编辑 `CompanyName` 列中的单元格时，通过检查单元格不为空而测试其值的有效性。</span><span class="sxs-lookup"><span data-stu-id="f907d-105">When the user edits a cell in the `CompanyName` column, its value is tested for validity by checking that it is not empty.</span></span> <span data-ttu-id="f907d-106">如果 <xref:System.Windows.Forms.DataGridView.CellValidating> 事件的事件处理程序发现该值为空字符串，<xref:System.Windows.Forms.DataGridView> 会阻止用户退出单元格，直到输入了一个非空字符串。</span><span class="sxs-lookup"><span data-stu-id="f907d-106">If the event handler for the <xref:System.Windows.Forms.DataGridView.CellValidating> event finds that the value is an empty string, the <xref:System.Windows.Forms.DataGridView> prevents the user from exiting the cell until a non-empty string is entered.</span></span>  
  
 <span data-ttu-id="f907d-107">有关此代码示例的完整说明，请参阅[演练：验证 Windows 窗体 DataGridView 控件中的数据](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)。</span><span class="sxs-lookup"><span data-stu-id="f907d-107">For a complete explanation of this code example, see [Walkthrough: Validating Data in the Windows Forms DataGridView Control](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f907d-108">示例</span><span class="sxs-lookup"><span data-stu-id="f907d-108">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/CS/datavalidation.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewDataValidation#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewDataValidation/VB/datavalidation.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f907d-109">编译代码</span><span class="sxs-lookup"><span data-stu-id="f907d-109">Compiling the Code</span></span>  
 <span data-ttu-id="f907d-110">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="f907d-110">This example requires:</span></span>  
  
- <span data-ttu-id="f907d-111">引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。</span><span class="sxs-lookup"><span data-stu-id="f907d-111">References to the System, System.Data, System.Windows.Forms and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f907d-112">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="f907d-112">.NET Framework Security</span></span>  
 <span data-ttu-id="f907d-113">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="f907d-113">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="f907d-114">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="f907d-114">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="f907d-115">有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="f907d-115">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f907d-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f907d-116">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="f907d-117">演练：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="f907d-117">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f907d-118">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="f907d-118">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="f907d-119">演练：处理在 Windows 窗体 DataGridView 控件有数据输入时发生的错误</span><span class="sxs-lookup"><span data-stu-id="f907d-119">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="f907d-120">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="f907d-120">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
