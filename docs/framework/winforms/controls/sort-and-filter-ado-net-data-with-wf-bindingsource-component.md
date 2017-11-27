---
title: "如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选"
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
- sorting data
- data sorting [Windows Forms], ADO.NET
- data [Windows Forms], filtering
- BindingSource component [Windows Forms], sorting and filtering data
- filtering [Windows Forms], ADO.NET
- data [Windows Forms], sorting
- ADO.NET [Windows Forms]
ms.assetid: 6c206daf-d706-4602-9dbe-435343052063
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 46947e314394d56b5ef0439f33910bb493012db3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-sort-and-filter-adonet-data-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="a0176-102">如何：使用 Windows 窗体 BindingSource 组件对 ADO.NET 数据进行排序和筛选</span><span class="sxs-lookup"><span data-stu-id="a0176-102">How to: Sort and Filter ADO.NET Data with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="a0176-103">排序和筛选功能可以公开<xref:System.Windows.Forms.BindingSource>通过控制<xref:System.Windows.Forms.BindingSource.Sort%2A>和<xref:System.Windows.Forms.BindingSource.Filter%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="a0176-103">You can expose the sorting and filtering capability of <xref:System.Windows.Forms.BindingSource> control through the <xref:System.Windows.Forms.BindingSource.Sort%2A> and <xref:System.Windows.Forms.BindingSource.Filter%2A> properties.</span></span> <span data-ttu-id="a0176-104">你可以将简单排序的基础数据源时应用<xref:System.ComponentModel.IBindingList>，并可以应用筛选和高级排序数据源时<xref:System.ComponentModel.IBindingListView>。</span><span class="sxs-lookup"><span data-stu-id="a0176-104">You can apply simple sorting when the underlying data source is an <xref:System.ComponentModel.IBindingList>, and you can apply filtering and advanced sorting when the data source is an <xref:System.ComponentModel.IBindingListView>.</span></span> <span data-ttu-id="a0176-105"><xref:System.Windows.Forms.BindingSource.Sort%2A>属性需要标准[!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]语法： 表示的数据源中的数据列名称的字符串跟`ASC`或`DESC`以指示是按升序或降序对列表进行排序。</span><span class="sxs-lookup"><span data-stu-id="a0176-105">The <xref:System.Windows.Forms.BindingSource.Sort%2A> property requires standard [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] syntax: a string representing the name of a column of data in the data source followed by `ASC` or `DESC` to indicate whether the list should be sorted in ascending or descending order.</span></span> <span data-ttu-id="a0176-106">你可以设置高级排序，或用逗号分隔符分隔每个列的多个列排序。</span><span class="sxs-lookup"><span data-stu-id="a0176-106">You can set advanced sorting or multiple-column sorting by separating each column with a comma separator.</span></span> <span data-ttu-id="a0176-107"><xref:System.Windows.Forms.BindingSource.Filter%2A>属性采用字符串表达式。</span><span class="sxs-lookup"><span data-stu-id="a0176-107">The <xref:System.Windows.Forms.BindingSource.Filter%2A> property takes a string expression.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0176-108">将敏感信息（如密码）存储在连接字符串中可能会影响应用程序的安全性。</span><span class="sxs-lookup"><span data-stu-id="a0176-108">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="a0176-109">若要控制对数据库的访问，一种较为安全的方法是使用 Windows 身份验证（也称为集成安全性）。</span><span class="sxs-lookup"><span data-stu-id="a0176-109">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="a0176-110">有关详细信息，请参阅[保护连接信息](../../../../docs/framework/data/adonet/protecting-connection-information.md)。</span><span class="sxs-lookup"><span data-stu-id="a0176-110">For more information, see [Protecting Connection Information](../../../../docs/framework/data/adonet/protecting-connection-information.md).</span></span>  
  
### <a name="to-filter-data-with-the-bindingsource"></a><span data-ttu-id="a0176-111">若要筛选数据使用 BindingSource</span><span class="sxs-lookup"><span data-stu-id="a0176-111">To filter data with the BindingSource</span></span>  
  
-   <span data-ttu-id="a0176-112">设置<xref:System.Windows.Forms.BindingSource.Filter%2A>到所需的表达式的属性。</span><span class="sxs-lookup"><span data-stu-id="a0176-112">Set the <xref:System.Windows.Forms.BindingSource.Filter%2A> property to expression that you want.</span></span>  
  
     <span data-ttu-id="a0176-113">在下面的代码示例中，表达式是列名称后跟所需的列的值。</span><span class="sxs-lookup"><span data-stu-id="a0176-113">In the following code example, the expression is a column name followed by value that you want for the column.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#11)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#11)]  
  
### <a name="to-sort-data-with-the-bindingsource"></a><span data-ttu-id="a0176-114">若要使用 BindingSource 对数据排序</span><span class="sxs-lookup"><span data-stu-id="a0176-114">To sort data with the BindingSource</span></span>  
  
1.  <span data-ttu-id="a0176-115">设置<xref:System.Windows.Forms.BindingSource.Sort%2A>属性列名称所需跟`ASC`或`DESC`以指示按升序或降序排列。</span><span class="sxs-lookup"><span data-stu-id="a0176-115">Set the <xref:System.Windows.Forms.BindingSource.Sort%2A> property to the column name that you want followed by `ASC` or `DESC` to indicate the ascending or descending order.</span></span>  
  
2.  <span data-ttu-id="a0176-116">用逗号分隔多个列。</span><span class="sxs-lookup"><span data-stu-id="a0176-116">Separate multiple columns with a comma.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#12)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#12](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#12)]  
  
## <a name="example"></a><span data-ttu-id="a0176-117">示例</span><span class="sxs-lookup"><span data-stu-id="a0176-117">Example</span></span>  
 <span data-ttu-id="a0176-118">下面的代码示例将数据加载到 Northwind 示例数据库的 Customers 表从<xref:System.Windows.Forms.DataGridView>控制，并筛选器和对显示的数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="a0176-118">The following code example loads data from the Customers table of the Northwind sample database into a <xref:System.Windows.Forms.DataGridView> control, and filters and sorts the displayed data.</span></span>  
  
 [!code-csharp[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.DataConnectorFilterAndSort#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataConnectorFilterAndSort/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a0176-119">编译代码</span><span class="sxs-lookup"><span data-stu-id="a0176-119">Compiling the Code</span></span>  
 <span data-ttu-id="a0176-120">若要运行此示例，请将代码粘贴到一个包含窗体<xref:System.Windows.Forms.BindingSource>名为`BindingSource1`和<xref:System.Windows.Forms.DataGridView>名为`dataGridView1`。</span><span class="sxs-lookup"><span data-stu-id="a0176-120">To run this example, paste the code into a form that contains a <xref:System.Windows.Forms.BindingSource> named `BindingSource1` and a <xref:System.Windows.Forms.DataGridView> named `dataGridView1`.</span></span> <span data-ttu-id="a0176-121">处理<xref:System.Windows.Forms.Form.Load>事件对于窗体和调用`InitializeSortedFilteredBindingSource`负载事件处理程序方法中。</span><span class="sxs-lookup"><span data-stu-id="a0176-121">Handle the <xref:System.Windows.Forms.Form.Load> event for the form and call `InitializeSortedFilteredBindingSource` in the load event handler method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0176-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0176-122">See Also</span></span>  
 <xref:System.Windows.Forms.BindingSource.Sort%2A>  
 <xref:System.Windows.Forms.BindingSource.Filter%2A>  
 [<span data-ttu-id="a0176-123">如何：安装示例数据库</span><span class="sxs-lookup"><span data-stu-id="a0176-123">How to: Install Sample Databases</span></span>](http://msdn.microsoft.com/library/ed1291f6-604c-4972-ae22-0345c6dea12e)  
 [<span data-ttu-id="a0176-124">BindingSource 组件</span><span class="sxs-lookup"><span data-stu-id="a0176-124">BindingSource Component</span></span>](../../../../docs/framework/winforms/controls/bindingsource-component.md)
