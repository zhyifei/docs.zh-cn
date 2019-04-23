---
title: 如何：将 Windows 窗体 DataGrid 控件绑定到数据源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- bound controls [Windows Forms], DataGrid control
- Windows Forms controls, data binding
- bound controls [Windows Forms]
- data-bound controls [Windows Forms], DataGrid
ms.assetid: 128cdb07-dfd3-4d60-9d6a-902847667c36
ms.openlocfilehash: 920a93894cc126f85bc6b618efbe6e9cedea4881
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59332568"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source"></a><span data-ttu-id="0fc40-102">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="0fc40-102">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>
> [!NOTE]
>  <span data-ttu-id="0fc40-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="0fc40-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="0fc40-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="0fc40-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="0fc40-105">Windows 窗体<xref:System.Windows.Forms.DataGrid>控件专门设计用于显示数据源中的信息。</span><span class="sxs-lookup"><span data-stu-id="0fc40-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="0fc40-106">将控件在运行时绑定通过调用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0fc40-106">You bind the control at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="0fc40-107">尽管可以显示来自各种数据源的数据，最典型的源是数据集和数据视图。</span><span class="sxs-lookup"><span data-stu-id="0fc40-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-programmatically"></a><span data-ttu-id="0fc40-108">若要进行数据绑定的 DataGrid 控件以编程方式</span><span class="sxs-lookup"><span data-stu-id="0fc40-108">To data-bind the DataGrid control programmatically</span></span>  
  
1. <span data-ttu-id="0fc40-109">编写代码以填充数据集。</span><span class="sxs-lookup"><span data-stu-id="0fc40-109">Write code to fill the dataset.</span></span>  
  
     <span data-ttu-id="0fc40-110">如果数据源的数据集或数据视图基于数据集表，将代码添加到窗体来填充数据集。</span><span class="sxs-lookup"><span data-stu-id="0fc40-110">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="0fc40-111">所使用的确切代码取决于数据集从何处获取数据。</span><span class="sxs-lookup"><span data-stu-id="0fc40-111">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="0fc40-112">如果要直接从数据库填充数据集，则通常会调用`Fill`的数据适配器，如以下示例，其中填充数据集调用中所示方法`DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="0fc40-112">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
     <span data-ttu-id="0fc40-113">如果从 XML Web 服务填充数据集时，您通常在代码中创建的服务实例，然后调用其方法返回数据集之一。</span><span class="sxs-lookup"><span data-stu-id="0fc40-113">If the dataset is being filled from an XML Web service, you typically create an instance of the service in your code and then call one of its methods to return a dataset.</span></span> <span data-ttu-id="0fc40-114">您然后合并到本地数据集的 XML Web 服务的数据集。</span><span class="sxs-lookup"><span data-stu-id="0fc40-114">You then merge the dataset from the XML Web service into your local dataset.</span></span> <span data-ttu-id="0fc40-115">下面的示例演示如何创建名为 XML Web 服务的实例`CategoriesService`，调用其`GetCategories`方法，并合并到本地数据集生成的数据集调用`DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="0fc40-115">The following example shows how you can create an instance of an XML Web service called `CategoriesService`, call its `GetCategories` method, and merge the resulting dataset into a local dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    Dim ws As New MyProject.localhost.CategoriesService()  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials  
    DsCategories1.Merge(ws.GetCategories())  
    ```  
  
    ```csharp  
    MyProject.localhost.CategoriesService ws = new MyProject.localhost.CategoriesService();  
    ws.Credentials = System.Net.CredentialCache.DefaultCredentials;  
    DsCategories1.Merge(ws.GetCategories());  
    ```  
  
    ```cpp  
    MyProject::localhost::CategoriesService^ ws =   
       new MyProject::localhost::CategoriesService();  
    ws->Credentials = System::Net::CredentialCache::DefaultCredentials;  
    dsCategories1->Merge(ws->GetCategories());  
    ```  
  
2. <span data-ttu-id="0fc40-116">调用<xref:System.Windows.Forms.DataGrid>控件的<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法，将其传递的数据源和数据成员。</span><span class="sxs-lookup"><span data-stu-id="0fc40-116">Call the <xref:System.Windows.Forms.DataGrid> control's <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method, passing it the data source and a data member.</span></span> <span data-ttu-id="0fc40-117">如果不需要显式传递的数据成员，则传递空字符串。</span><span class="sxs-lookup"><span data-stu-id="0fc40-117">If you do not need to explicitly pass a data member, pass an empty string.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="0fc40-118">如果第一次绑定网格，可以设置控件的<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="0fc40-118">If you are binding the grid for the first time, you can set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties.</span></span> <span data-ttu-id="0fc40-119">但是，在完成设置之后无法重置这些属性。</span><span class="sxs-lookup"><span data-stu-id="0fc40-119">However, you cannot reset these properties once they have been set.</span></span> <span data-ttu-id="0fc40-120">因此，建议始终使用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="0fc40-120">Therefore, it is recommended that you always use the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span>  
  
     <span data-ttu-id="0fc40-121">下面的示例演示如何可以以编程方式绑定到数据集调用中的 Customers 表`DsCustomers1`:</span><span class="sxs-lookup"><span data-stu-id="0fc40-121">The following example shows how you can programmatically bind to the Customers table in a dataset called `DsCustomers1`:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "Customers");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "Customers");  
    ```  
  
     <span data-ttu-id="0fc40-122">如果客户表中数据集的唯一表，您或者可以绑定网格这种方式：</span><span class="sxs-lookup"><span data-stu-id="0fc40-122">If the Customers table is the only table in the dataset, you could alternatively bind the grid this way:</span></span>  
  
    ```vb  
    DataGrid1.SetDataBinding(DsCustomers1, "")  
    ```  
  
    ```csharp  
    DataGrid1.SetDataBinding(DsCustomers1, "");  
    ```  
  
    ```cpp  
    dataGrid1->SetDataBinding(dsCustomers1, "");  
    ```  
  
3. <span data-ttu-id="0fc40-123">（可选）将适当的表样式和列样式添加到网格中。</span><span class="sxs-lookup"><span data-stu-id="0fc40-123">(Optional) Add the appropriate table styles and column styles to the grid.</span></span> <span data-ttu-id="0fc40-124">如果没有表样式，您将看到表中，但其格式设置很少，且所有列均可见。</span><span class="sxs-lookup"><span data-stu-id="0fc40-124">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc40-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fc40-125">See also</span></span>

- [<span data-ttu-id="0fc40-126">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="0fc40-126">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="0fc40-127">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="0fc40-127">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="0fc40-128">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="0fc40-128">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="0fc40-129">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="0fc40-129">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
