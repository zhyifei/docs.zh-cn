---
title: 如何：使用 Windows 窗体 DataGrid 控件创建母版-详细信息列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 20388c6a-94f9-4d96-be18-8c200491247f
ms.openlocfilehash: 6ff13264709c4557d698435ac05b7759be58f1e8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54712887"
---
# <a name="how-to-create-masterdetail-lists-with-the-windows-forms-datagrid-control"></a><span data-ttu-id="69cd2-102">如何：使用 Windows 窗体 DataGrid 控件创建主/详细信息列表</span><span class="sxs-lookup"><span data-stu-id="69cd2-102">How to: Create Master/Detail Lists with the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="69cd2-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="69cd2-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="69cd2-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="69cd2-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="69cd2-105">如果你<xref:System.Data.DataSet>包含一系列相关表，则可以使用两个<xref:System.Windows.Forms.DataGrid>控件以显示母版/详细信息格式的数据。</span><span class="sxs-lookup"><span data-stu-id="69cd2-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master/detail format.</span></span> <span data-ttu-id="69cd2-106">一个<xref:System.Windows.Forms.DataGrid>指定主网格中，且第二个指定要在详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="69cd2-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="69cd2-107">当在主列表中选择一个条目时，所有相关的子条目所示详细信息列表。</span><span class="sxs-lookup"><span data-stu-id="69cd2-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="69cd2-108">例如，如果你<xref:System.Data.DataSet>包含 Customers 表和相关的 Orders 表，需要指定要将主网格客户表和 Orders 表中，会在详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="69cd2-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="69cd2-109">在主网格中选择客户后，将详细信息网格中显示所有关联订单表中与该客户的订单。</span><span class="sxs-lookup"><span data-stu-id="69cd2-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
### <a name="to-set-a-masterdetail-relationship-programmatically"></a><span data-ttu-id="69cd2-110">若要以编程方式设置主/从关系</span><span class="sxs-lookup"><span data-stu-id="69cd2-110">To set a master/detail relationship programmatically</span></span>  
  
1.  <span data-ttu-id="69cd2-111">创建两个新<xref:System.Windows.Forms.DataGrid>控制并设置其属性。</span><span class="sxs-lookup"><span data-stu-id="69cd2-111">Create two new <xref:System.Windows.Forms.DataGrid> controls and set their properties.</span></span>  
  
2.  <span data-ttu-id="69cd2-112">将表添加到数据集。</span><span class="sxs-lookup"><span data-stu-id="69cd2-112">Add tables to the dataset.</span></span>  
  
3.  <span data-ttu-id="69cd2-113">声明类型的变量<xref:System.Data.DataRelation>来表示你想要创建的关系。</span><span class="sxs-lookup"><span data-stu-id="69cd2-113">Declare a variable of type <xref:System.Data.DataRelation> to represent the relation you want to create.</span></span>  
  
4.  <span data-ttu-id="69cd2-114">实例化该关系指定为关系的名称，并指定表、 列和两个表将起到关联的项。</span><span class="sxs-lookup"><span data-stu-id="69cd2-114">Instantiate the relationship by specifying a name for the relationship and specifying the table, column, and item that will tie the two tables.</span></span>  
  
5.  <span data-ttu-id="69cd2-115">添加到关系<xref:System.Data.DataSet>对象的<xref:System.Data.DataSet.Relations%2A>集合。</span><span class="sxs-lookup"><span data-stu-id="69cd2-115">Add the relationship to the <xref:System.Data.DataSet> object's <xref:System.Data.DataSet.Relations%2A> collection.</span></span>  
  
6.  <span data-ttu-id="69cd2-116">使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法<xref:System.Windows.Forms.DataGrid>要绑定到网格的每个<xref:System.Data.DataSet>。</span><span class="sxs-lookup"><span data-stu-id="69cd2-116">Use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method of the <xref:System.Windows.Forms.DataGrid> to bind each of the grids to the <xref:System.Data.DataSet>.</span></span>  
  
     <span data-ttu-id="69cd2-117">下面的示例演示如何设置中以前生成的 Customers 和 Orders 表之间的主/从关系<xref:System.Data.DataSet>(`ds`)。</span><span class="sxs-lookup"><span data-stu-id="69cd2-117">The following example shows how to set a master/detail relationship between the Customers and Orders tables in a previously generated <xref:System.Data.DataSet> (`ds`).</span></span>  
  
    ```vb  
    Dim myDataRelation As DataRelation  
    myDataRelation = New DataRelation _  
       ("CustOrd", ds.Tables("Customers").Columns("CustomerID"), _  
       ds.Tables("Orders").Columns("CustomerID"))  
    ' Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation)  
    GridOrders.SetDataBinding(ds, "Customers")  
    GridDetails.SetDataBinding(ds, "Customers.CustOrd")  
    ```  
  
    ```csharp  
    DataRelation myDataRelation;  
    myDataRelation = new DataRelation("CustOrd", ds.Tables["Customers"].Columns["CustomerID"], ds.Tables["Orders"].Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds.Relations.Add(myDataRelation);  
    GridOrders.SetDataBinding(ds,"Customers");  
    GridDetails.SetDataBinding(ds,"Customers.CustOrd");  
    ```  
  
    ```cpp  
    DataRelation^ myDataRelation;  
    myDataRelation = gcnew DataRelation("CustOrd",  
       ds->Tables["Customers"]->Columns["CustomerID"],  
       ds->Tables["Orders"]->Columns["CustomerID"]);  
    // Add the relation to the DataSet.  
    ds->Relations->Add(myDataRelation);  
    GridOrders->SetDataBinding(ds, "Customers");  
    GridDetails->SetDataBinding(ds, "Customers.CustOrd");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="69cd2-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="69cd2-118">See also</span></span>
- [<span data-ttu-id="69cd2-119">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="69cd2-119">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)
- [<span data-ttu-id="69cd2-120">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="69cd2-120">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="69cd2-121">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="69cd2-121">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
