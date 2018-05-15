---
title: 如何： 创建主 / 从窗体使用两个 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: 9aaa913dabd53f456650ae798d5f05e979d9876e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="cf184-102">如何：使用两个 Windows 窗体 DataGridView 控件创建一个主/从窗体</span><span class="sxs-lookup"><span data-stu-id="cf184-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="cf184-103">以下代码示例使用绑定到两个 <xref:System.Windows.Forms.BindingSource> 组件的两个 <xref:System.Windows.Forms.DataGridView> 控件创建主窗体/详细窗体。</span><span class="sxs-lookup"><span data-stu-id="cf184-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="cf184-104">数据源是一个 <xref:System.Data.DataSet>，其中包含来自 Northwind SQL Server 示例数据库的 `Customers` 和 `Orders` 表以及通过 `CustomerID` 列关联这两张表的 <xref:System.Data.DataRelation>。</span><span class="sxs-lookup"><span data-stu-id="cf184-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="cf184-105">一个 <xref:System.Windows.Forms.BindingSource> 被绑定到数据集中的父 `Customers` 表。</span><span class="sxs-lookup"><span data-stu-id="cf184-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="cf184-106">此数据在主 <xref:System.Windows.Forms.DataGridView> 控件中显示。</span><span class="sxs-lookup"><span data-stu-id="cf184-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="cf184-107">其他 <xref:System.Windows.Forms.BindingSource> 被绑定到第一个数据连接器。</span><span class="sxs-lookup"><span data-stu-id="cf184-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="cf184-108">第二个 <xref:System.Windows.Forms.BindingSource> 的 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 属性被设置为 <xref:System.Data.DataRelation> 名称。</span><span class="sxs-lookup"><span data-stu-id="cf184-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="cf184-109">这将导致相关联的详细 <xref:System.Windows.Forms.DataGridView> 控件显示子 `Orders` 表中与主 <xref:System.Windows.Forms.DataGridView> 控件中当前行相对应的行。</span><span class="sxs-lookup"><span data-stu-id="cf184-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="cf184-110">此代码示例的完整说明，请参阅[演练： 创建主/从窗体使用两个 Windows 窗体 DataGridView 控件](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)。</span><span class="sxs-lookup"><span data-stu-id="cf184-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="cf184-111">示例</span><span class="sxs-lookup"><span data-stu-id="cf184-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="cf184-112">编译代码</span><span class="sxs-lookup"><span data-stu-id="cf184-112">Compiling the Code</span></span>  
 <span data-ttu-id="cf184-113">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="cf184-113">This example requires:</span></span>  
  
 <span data-ttu-id="cf184-114">引用 System、System.Data、System.Windows.Forms 和 System.XML 程序集。</span><span class="sxs-lookup"><span data-stu-id="cf184-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
-   <span data-ttu-id="cf184-115">为 Visual Basic 或 Visual C# 中生成此示例从命令行有关的信息，请参阅[从命令行生成](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md)或[命令行上使用 csc.exe 生成](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="cf184-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](~/docs/visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](~/docs/csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="cf184-116">你也可以通过将代码粘贴到新项目中生成 Visual Studio 中的此示例。</span><span class="sxs-lookup"><span data-stu-id="cf184-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  <span data-ttu-id="cf184-117">另请参阅 [如何：使用 Visual Studio 编译和运行完整的 Windows 窗体代码示例](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\))。</span><span class="sxs-lookup"><span data-stu-id="cf184-117">Also see [How to: Compile and Run a Complete Windows Forms Code Example Using Visual Studio](http://msdn.microsoft.com/library/Bb129228\(v=vs.110\)).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="cf184-118">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="cf184-118">.NET Framework Security</span></span>  
 <span data-ttu-id="cf184-119">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="cf184-119">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="cf184-120">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="cf184-120">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="cf184-121">有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="cf184-121">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf184-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="cf184-122">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="cf184-123">演练：使用两个 Windows 窗体 DataGridView 控件创建主窗体/详细信息窗体</span><span class="sxs-lookup"><span data-stu-id="cf184-123">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](../../../../docs/framework/winforms/controls/creating-a-master-detail-form-using-two-datagridviews.md)  
 [<span data-ttu-id="cf184-124">在 Windows 窗体 DataGridView 控件中显示数据</span><span class="sxs-lookup"><span data-stu-id="cf184-124">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="cf184-125">保护连接信息</span><span class="sxs-lookup"><span data-stu-id="cf184-125">Protecting Connection Information</span></span>](../../../../docs/framework/data/adonet/protecting-connection-information.md)
