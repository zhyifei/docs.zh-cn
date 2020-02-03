---
title: 处理 DataGridView 控件中的数据输入过程中出现的错误
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- error handling [Windows Forms], dataGridView control
- data grids [Windows Forms], error handling
- DataGridView control [Windows Forms], error handling
- data entry [Windows Forms], error handling
- error handling [Windows Forms], data entry
ms.assetid: 9004e72f-fdec-4264-a37d-2c99764efc13
ms.openlocfilehash: 03a13957c80b0ab62afb11efc57cf31e059e5942
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745615"
---
# <a name="how-to-handle-errors-that-occur-during-data-entry-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="d7b7c-102">如何：处理在 Windows 窗体 DataGridView 控件中输入数据时发生的错误</span><span class="sxs-lookup"><span data-stu-id="d7b7c-102">How to: Handle Errors That Occur During Data Entry in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="d7b7c-103">下面的代码示例演示如何使用 <xref:System.Windows.Forms.DataGridView> 控件将数据输入错误报告给用户。</span><span class="sxs-lookup"><span data-stu-id="d7b7c-103">The following code example demonstrates how to use the <xref:System.Windows.Forms.DataGridView> control to report data entry errors to the user.</span></span>  
  
 <span data-ttu-id="d7b7c-104">有关此代码示例的完整说明，请参阅[演练：处理 Windows 窗体 DataGridView 控件中的数据输入期间发生的错误](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b7c-104">For a complete explanation of this code example, see [Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control](handling-errors-that-occur-during-data-entry-in-the-datagrid.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d7b7c-105">示例</span><span class="sxs-lookup"><span data-stu-id="d7b7c-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/CS/errorhandling.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridView.DataError#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridView.DataError/VB/errorhandling.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="d7b7c-106">编译代码</span><span class="sxs-lookup"><span data-stu-id="d7b7c-106">Compiling the Code</span></span>  
 <span data-ttu-id="d7b7c-107">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="d7b7c-107">This example requires:</span></span>  
  
- <span data-ttu-id="d7b7c-108">引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。</span><span class="sxs-lookup"><span data-stu-id="d7b7c-108">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="d7b7c-109">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="d7b7c-109">.NET Framework Security</span></span>  
 <span data-ttu-id="d7b7c-110">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="d7b7c-110">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="d7b7c-111">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="d7b7c-111">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="d7b7c-112">有关详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="d7b7c-112">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b7c-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d7b7c-113">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="d7b7c-114">演练：处理在 Windows 窗体 DataGridView 控件有数据输入时发生的错误</span><span class="sxs-lookup"><span data-stu-id="d7b7c-114">Walkthrough: Handling Errors that Occur During Data Entry in the Windows Forms DataGridView Control</span></span>](handling-errors-that-occur-during-data-entry-in-the-datagrid.md)
- [<span data-ttu-id="d7b7c-115">Windows 窗体 DataGridView 控件中的数据输入</span><span class="sxs-lookup"><span data-stu-id="d7b7c-115">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d7b7c-116">演练：在 Windows 窗体 DataGridView 控件中验证数据</span><span class="sxs-lookup"><span data-stu-id="d7b7c-116">Walkthrough: Validating Data in the Windows Forms DataGridView Control</span></span>](walkthrough-validating-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="d7b7c-117">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="d7b7c-117">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
