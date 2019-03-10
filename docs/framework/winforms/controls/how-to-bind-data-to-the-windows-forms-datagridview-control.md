---
title: 如何：将数据绑定到 Windows 窗体 DataGridView 控件
ms.date: 02/08/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [Windows Forms], grids
- data binding [Windows Forms], DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 1660f69c-5711-45d2-abc1-e25bc6779124
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cbcc04625a14ebc23cacfb567951bf8f76f14985
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57725098"
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control"></a><span data-ttu-id="875b7-102">如何：将数据绑定到 Windows 窗体 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="875b7-102">How to: Bind data to the Windows Forms DataGridView control</span></span>

<span data-ttu-id="875b7-103"><xref:System.Windows.Forms.DataGridView>控件支持标准 Windows 窗体数据绑定模型，因此它可以绑定到各种数据源。</span><span class="sxs-lookup"><span data-stu-id="875b7-103">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it can bind to a variety of data sources.</span></span> <span data-ttu-id="875b7-104">通常情况下，您将绑定到<xref:System.Windows.Forms.BindingSource>的管理与数据源的交互。</span><span class="sxs-lookup"><span data-stu-id="875b7-104">Usually, you bind to a <xref:System.Windows.Forms.BindingSource> that manages the interaction with the data source.</span></span> <span data-ttu-id="875b7-105"><xref:System.Windows.Forms.BindingSource>可以是任何 Windows 窗体数据源，这将使您能非常灵活地选择或修改数据的位置时。</span><span class="sxs-lookup"><span data-stu-id="875b7-105">The <xref:System.Windows.Forms.BindingSource> can be any Windows Forms data source, which gives you great flexibility when choosing or modifying your data's location.</span></span> <span data-ttu-id="875b7-106">有关数据源的详细信息<xref:System.Windows.Forms.DataGridView>控件支持，请参阅[DataGridView 控件概述](datagridview-control-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="875b7-106">For more information about data sources the <xref:System.Windows.Forms.DataGridView> control supports, see the [DataGridView control overview](datagridview-control-overview-windows-forms.md).</span></span>  

<span data-ttu-id="875b7-107">Visual Studio 可以绑定到 DataGridView 控件的数据的广泛支持。</span><span class="sxs-lookup"><span data-stu-id="875b7-107">Visual Studio has extensive support for data binding to the DataGridView control.</span></span> <span data-ttu-id="875b7-108">有关详细信息，请参阅[如何：将数据绑定到使用设计器在 Windows 窗体 DataGridView 控件](bind-data-to-the-datagrid-using-the-designer.md)。</span><span class="sxs-lookup"><span data-stu-id="875b7-108">For more information, see [How to: Bind data to the Windows Forms DataGridView control using the Designer](bind-data-to-the-datagrid-using-the-designer.md).</span></span>  

<span data-ttu-id="875b7-109">DataGridView 控件连接到数据：</span><span class="sxs-lookup"><span data-stu-id="875b7-109">To connect a DataGridView control to data:</span></span>

1. <span data-ttu-id="875b7-110">实现方法来处理检索数据的详细信息。</span><span class="sxs-lookup"><span data-stu-id="875b7-110">Implement a method to handle the details of retrieving the data.</span></span> <span data-ttu-id="875b7-111">下面的代码示例实现`GetData`方法初始化<xref:System.Data.SqlClient.SqlDataAdapter>，并使用它来填充<xref:System.Data.DataTable>。</span><span class="sxs-lookup"><span data-stu-id="875b7-111">The following code example implements a `GetData` method that initializes a <xref:System.Data.SqlClient.SqlDataAdapter>, and uses it to populate a <xref:System.Data.DataTable>.</span></span> <span data-ttu-id="875b7-112">然后将绑定<xref:System.Data.DataTable>到<xref:System.Windows.Forms.BindingSource>。</span><span class="sxs-lookup"><span data-stu-id="875b7-112">It then binds the <xref:System.Data.DataTable> to the <xref:System.Windows.Forms.BindingSource>.</span></span> 

2. <span data-ttu-id="875b7-113">在窗体的<xref:System.Windows.Forms.Form.Load>事件处理程序中，绑定<xref:System.Windows.Forms.DataGridView>控制对<xref:System.Windows.Forms.BindingSource>，并调用`GetData`方法来检索数据。</span><span class="sxs-lookup"><span data-stu-id="875b7-113">In the form's <xref:System.Windows.Forms.Form.Load> event handler, bind the <xref:System.Windows.Forms.DataGridView> control to the <xref:System.Windows.Forms.BindingSource>, and call the `GetData` method to retrieve the data.</span></span>  

## <a name="example"></a><span data-ttu-id="875b7-114">示例</span><span class="sxs-lookup"><span data-stu-id="875b7-114">Example</span></span>

<span data-ttu-id="875b7-115">此完整的代码示例从数据库填充在 Windows 窗体 DataGridView 控件中检索数据。</span><span class="sxs-lookup"><span data-stu-id="875b7-115">This complete code example retrieves data from a database to populate a DataGridView control in a Windows form.</span></span> <span data-ttu-id="875b7-116">窗体还提供按钮以重新加载数据并将更改提交到数据库。</span><span class="sxs-lookup"><span data-stu-id="875b7-116">The form also has buttons to reload data and submit changes to the database.</span></span>  

<span data-ttu-id="875b7-117">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="875b7-117">This example requires:</span></span> 

- <span data-ttu-id="875b7-118">访问 Northwind SQL Server 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="875b7-118">Access to a Northwind SQL Server sample database.</span></span> <span data-ttu-id="875b7-119">有关安装 Northwind 示例数据库的详细信息，请参阅[获取这些示例数据库的 ADO.NET 代码示例](../../data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="875b7-119">For more information about installing the Northwind sample database, see [Get the sample databases for ADO.NET code samples](../../data/adonet/sql/linq/downloading-sample-databases.md).</span></span> 

- <span data-ttu-id="875b7-120">引用 System、 System.Windows.Forms、 System.Data 和 System.Xml 程序集。</span><span class="sxs-lookup"><span data-stu-id="875b7-120">References to the System, System.Windows.Forms, System.Data, and System.Xml assemblies.</span></span>  

<span data-ttu-id="875b7-121">若要生成并运行此示例中，粘贴到代码*Form1*中新的 Windows 窗体项目代码文件。</span><span class="sxs-lookup"><span data-stu-id="875b7-121">To build and run this example, paste the code into the *Form1* code file in a new Windows Forms project.</span></span> <span data-ttu-id="875b7-122">有关从生成的信息C#或 Visual Basic 命令行，请参阅[命令行上使用 csc.exe 生成](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)或[中的命令行生成](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="875b7-122">For information about building from the C# or Visual Basic command line, see [Command-line building with csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md) or [Build from the command line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
<span data-ttu-id="875b7-123">填充`connectionString`变量中的示例使用 Northwind SQL Server 示例数据库连接的值。</span><span class="sxs-lookup"><span data-stu-id="875b7-123">Populate the `connectionString` variable in the example with the values for your Northwind SQL Server sample database connection.</span></span> <span data-ttu-id="875b7-124">Windows 身份验证，也称为集成的安全性，是更安全的方式连接到比将密码存储在连接字符串中的数据库。</span><span class="sxs-lookup"><span data-stu-id="875b7-124">Windows Authentication, also called integrated security, is a more secure way to connect to the database than storing a password in the connection string.</span></span> <span data-ttu-id="875b7-125">有关连接安全性的详细信息，请参阅[保护连接信息](../../data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="875b7-125">For more information about connection security, see [Protect connection information](../../data/adonet/protecting-connection-information.md).</span></span>  

[!code-csharp[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/CS/datagridviewboundeditable.cs)]
[!code-vb[System.Windows.Forms.DataGridViewBoundEditable](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewBoundEditable/VB/datagridviewboundeditable.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="875b7-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="875b7-126">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="875b7-127">Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="875b7-127">Display data in the Windows Forms DataGridView control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="875b7-128">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="875b7-128">Protect connection information</span></span>](../../data/adonet/protecting-connection-information.md)
