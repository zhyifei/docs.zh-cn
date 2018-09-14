---
title: 如何：将数据绑定到 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
ms.openlocfilehash: 4064ef26ee550c02ac8825ac4c1a417472b64de6
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2018
ms.locfileid: "45594816"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="9e0d9-102">如何：将数据绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="9e0d9-102">How to: Bind Data to the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="9e0d9-103"><xref:System.Windows.Forms.DataGridView> 控件支持标准 Windows 窗体数据绑定模型，因此它可以绑定到各种数据源。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to a variety of data sources.</span></span> <span data-ttu-id="9e0d9-104">但在多数情况下，该控件将会绑定到用于管理数据源交互详细信息的 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-104">In most circumstances, however, you will bind to a <xref:System.Windows.Forms.BindingSource> component which will manage the details of interacting with the data source.</span></span> <span data-ttu-id="9e0d9-105"><xref:System.Windows.Forms.BindingSource> 组件可表示任何 Windows 窗体数据源，并在选择或修改数据位置时提供很大的灵活性。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-105">The <xref:System.Windows.Forms.BindingSource> component can represent any Windows Forms data source and gives you great flexibility when choosing or modifying the location of your data.</span></span> <span data-ttu-id="9e0d9-106">有关支持的数据源的详细信息<xref:System.Windows.Forms.DataGridView>控件，请参阅[DataGridView 控件概述](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-106">For more information about the data sources supported by the <xref:System.Windows.Forms.DataGridView> control, see [DataGridView Control Overview](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md).</span></span>  
  
 <span data-ttu-id="9e0d9-107">Visual Studio 中对此任务提供广泛支持。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-107">There is extensive support for this task in Visual Studio.</span></span>  <span data-ttu-id="9e0d9-108">另请参阅[如何：使用设计器将数据绑定到 Windows 窗体的 DataGridView 控件](https://msdn.microsoft.com/library/33w255ac\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-108">Also see [How to: Bind Data to the Windows Forms DataGridView Control Using the Designer](https://msdn.microsoft.com/library/33w255ac\(v=vs.110\)).</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="9e0d9-109">过程</span><span class="sxs-lookup"><span data-stu-id="9e0d9-109">Procedure</span></span>  
  
#### <a name="to-connect-a-datagridview-control-to-data"></a><span data-ttu-id="9e0d9-110">将 DataGridView 控件连接到数据</span><span class="sxs-lookup"><span data-stu-id="9e0d9-110">To connect a DataGridView control to data</span></span>  
  
1.  <span data-ttu-id="9e0d9-111">实现方法以处理有关从数据库检索数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-111">Implement a method to handle the details of retrieving data from a database.</span></span> <span data-ttu-id="9e0d9-112">下面的代码示例实现一个 `GetData` 方法，该方法对一个 <xref:System.Data.SqlClient.SqlDataAdapter> 组件进行初始化，并使用该组件填充 <xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-112">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter> component and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="9e0d9-113">然后，将 <xref:System.Data.DataTable> 绑定到 <xref:System.Windows.Forms.BindingSource> 组件。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-113">The <xref:System.Data.DataTable> is then bound to the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="9e0d9-114">请确保将 `connectionString` 变量设置为适合数据库的值。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-114">Be sure to set the `connectionString` variable to a value that is appropriate for your database.</span></span> <span data-ttu-id="9e0d9-115">将需要访问安装了 Northwind SQL Server 示例数据库的服务器。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-115">You will need access to a server with the Northwind SQL Server sample database installed.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#20)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#20)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#20](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#20)]  
  
2.  <span data-ttu-id="9e0d9-116">在窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序中，将 <xref:System.Windows.Forms.DataGridView> 控件绑定到 <xref:System.Windows.Forms.BindingSource> 组件，并调用 `GetData` 方法，以从数据库检索数据。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-116">In your form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource> component and call the `GetData` method to retrieve the data from the database.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#10)]
     [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#10)]
     [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#10)]  
  
## <a name="example"></a><span data-ttu-id="9e0d9-117">示例</span><span class="sxs-lookup"><span data-stu-id="9e0d9-117">Example</span></span>  
 <span data-ttu-id="9e0d9-118">下面的完整代码示例提供的按钮用于从数据库重新加载数据和向数据库提交更改。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-118">The following complete code example provides buttons for reloading data from the database and submitting changes to the database.</span></span>  
  
 [!code-cpp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/cpp/datagridviewboundeditable.cpp#00)]
 [!code-csharp[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewBoundEditable#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="9e0d9-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="9e0d9-119">Compiling the Code</span></span>  
 <span data-ttu-id="9e0d9-120">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="9e0d9-120">This example requires:</span></span>  
  
-   <span data-ttu-id="9e0d9-121">对 System、System.Windows.Forms、System.Data 和 System.XML 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-121">References to the System, System.Windows.Forms, System.Data, and System.XML assemblies.</span></span>  
  
 <span data-ttu-id="9e0d9-122">Visual Basic 或 Visual C# 生成命令行中的此示例的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-122">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="9e0d9-123">也可以通过将代码粘贴到新的项目中生成此示例在 Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-123">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="9e0d9-124">另请参阅[如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-124">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](https://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="9e0d9-125">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="9e0d9-125">.NET Framework Security</span></span>  
 <span data-ttu-id="9e0d9-126">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-126">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="9e0d9-127">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-127">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="9e0d9-128">有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="9e0d9-128">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e0d9-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9e0d9-129">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="9e0d9-130">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="9e0d9-130">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="9e0d9-131">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="9e0d9-131">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
