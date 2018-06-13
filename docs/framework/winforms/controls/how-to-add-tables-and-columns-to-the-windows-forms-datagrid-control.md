---
title: 如何：向 Windows 窗体 DataGrid 控件添加表和列
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], adding to DataGrid control
- tables [Windows Forms], adding to DataGrid control
- DataGrid control [Windows Forms], adding tables and columns
ms.assetid: 2fe661b9-aa06-49b9-a314-a0d3cbfdcb4d
ms.openlocfilehash: fc8161ea29da92f5dcc2e76f956f3fecd6140acc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33527714"
---
# <a name="how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control"></a><span data-ttu-id="64a0e-102">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="64a0e-102">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="64a0e-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="64a0e-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="64a0e-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="64a0e-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="64a0e-105">你可以在 Windows 窗体中显示数据<xref:System.Windows.Forms.DataGrid>中表和列通过创建控件**DataGridTableStyle**对象并将它们添加到**GridTableStylesCollection**对象，它是通过访问<xref:System.Windows.Forms.DataGrid>控件的**TableStyles**属性。</span><span class="sxs-lookup"><span data-stu-id="64a0e-105">You can display data in the Windows Forms <xref:System.Windows.Forms.DataGrid> control in tables and columns by creating **DataGridTableStyle** objects and adding them to the **GridTableStylesCollection** object, which is accessed through the <xref:System.Windows.Forms.DataGrid> control's **TableStyles** property.</span></span> <span data-ttu-id="64a0e-106">每个表样式显示任何数据表中指定的内容**DataGridTableStyle**对象的**MappingName**属性。</span><span class="sxs-lookup"><span data-stu-id="64a0e-106">Each table style displays the contents of whatever data table is specified in the **DataGridTableStyle** object's **MappingName** property.</span></span> <span data-ttu-id="64a0e-107">默认情况下，具有未指定的列样式的表样式将显示该数据表中的所有列。</span><span class="sxs-lookup"><span data-stu-id="64a0e-107">By default, a table style with no column styles specified will display all the columns within that data table.</span></span> <span data-ttu-id="64a0e-108">你可以限制表中的哪些列显示通过添加**DataGridColumnStyle**对象添加到**GridColumnStylesCollection**对象，可通过**GridColumnStyles**每个属性**DataGridTableStyle**对象。</span><span class="sxs-lookup"><span data-stu-id="64a0e-108">You can restrict which columns from the table appear by adding **DataGridColumnStyle** objects to the **GridColumnStylesCollection** object, which is accessed through the **GridColumnStyles** property of each **DataGridTableStyle** object.</span></span>  
  
### <a name="to-add-a-table-and-column-to-a-datagrid-programmatically"></a><span data-ttu-id="64a0e-109">以编程方式将表和列添加到数据网格</span><span class="sxs-lookup"><span data-stu-id="64a0e-109">To add a table and column to a DataGrid programmatically</span></span>  
  
1.  <span data-ttu-id="64a0e-110">为了在表中显示数据，必须首先将绑定<xref:System.Windows.Forms.DataGrid>控件添加到数据集。</span><span class="sxs-lookup"><span data-stu-id="64a0e-110">In order to display data in the table, you must first bind the <xref:System.Windows.Forms.DataGrid> control to a dataset.</span></span> <span data-ttu-id="64a0e-111">有关详细信息，请参阅[如何： 将 Windows 窗体 DataGrid 控件绑定到数据源](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。</span><span class="sxs-lookup"><span data-stu-id="64a0e-111">For more information, see [How to: Bind the Windows Forms DataGrid Control to a Data Source](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
    > [!CAUTION]
    >  <span data-ttu-id="64a0e-112">以编程方式指定列样式，将始终创建**DataGridColumnStyle**对象，并将其添加到**GridColumnStylesCollection**之前添加的对象**DataGridTableStyle**对象添加到**GridTableStylesCollection**对象。</span><span class="sxs-lookup"><span data-stu-id="64a0e-112">When programmatically specifying column styles, always create **DataGridColumnStyle** objects and add them to the **GridColumnStylesCollection** object before adding **DataGridTableStyle** objects to the **GridTableStylesCollection** object.</span></span> <span data-ttu-id="64a0e-113">当你将添加一个空**DataGridTableStyle**对象添加到收藏， **DataGridColumnStyle**自动为你生成的对象。</span><span class="sxs-lookup"><span data-stu-id="64a0e-113">When you add an empty **DataGridTableStyle** object to the collection, **DataGridColumnStyle** objects are automatically generated for you.</span></span> <span data-ttu-id="64a0e-114">如果你尝试添加新因此，将引发异常**DataGridColumnStyle**对象具有重复**MappingName**值复制到**GridColumnStylesCollection**对象。</span><span class="sxs-lookup"><span data-stu-id="64a0e-114">Consequently, an exception will be thrown if you try to add new **DataGridColumnStyle** objects with duplicate **MappingName** values to the **GridColumnStylesCollection** object.</span></span>  
  
2.  <span data-ttu-id="64a0e-115">声明一个新的表样式并设置其映射名称。</span><span class="sxs-lookup"><span data-stu-id="64a0e-115">Declare a new table style and set its mapping name.</span></span>  
  
    ```vb  
    Dim ts1 As New DataGridTableStyle()  
    ts1.MappingName = "Customers"  
    ```  
  
    ```csharp  
    DataGridTableStyle ts1 = new DataGridTableStyle();  
    ts1.MappingName = "Customers";  
    ```  
  
    ```cpp  
    DataGridTableStyle* ts1 = new DataGridTableStyle();  
    ts1->MappingName = S"Customers";  
    ```  
  
3.  <span data-ttu-id="64a0e-116">声明一个新列样式并设置其映射名称和其他属性。</span><span class="sxs-lookup"><span data-stu-id="64a0e-116">Declare a new column style and set its mapping name and other properties.</span></span>  
  
    ```vb  
    Dim myDataCol As New DataGridBoolColumn()  
    myDataCol.HeaderText = "My New Column"  
    myDataCol.MappingName = "Current"  
    ```  
  
    ```csharp  
    DataGridBoolColumn myDataCol = new DataGridBoolColumn();  
    myDataCol.HeaderText = "My New Column";  
    myDataCol.MappingName = "Current";  
    ```  
  
    ```cpp  
    DataGridBoolColumn^ myDataCol = gcnew DataGridBoolColumn();  
    myDataCol->HeaderText = "My New Column";  
    myDataCol->MappingName = "Current";  
    ```  
  
4.  <span data-ttu-id="64a0e-117">调用**添加**方法**GridColumnStylesCollection**对象向表样式添加列</span><span class="sxs-lookup"><span data-stu-id="64a0e-117">Call the **Add** method of the **GridColumnStylesCollection** object to add the column to the table style</span></span>  
  
    ```vb  
    ts1.GridColumnStyles.Add(myDataCol)  
    ```  
  
    ```csharp  
    ts1.GridColumnStyles.Add(myDataCol);  
    ```  
  
    ```cpp  
    ts1->GridColumnStyles->Add(myDataCol);  
    ```  
  
5.  <span data-ttu-id="64a0e-118">调用**添加**方法**GridTableStylesCollection**对象以将表样式添加到数据网格。</span><span class="sxs-lookup"><span data-stu-id="64a0e-118">Call the **Add** method of the **GridTableStylesCollection** object to add the table style to the data grid.</span></span>  
  
    ```vb  
    DataGrid1.TableStyles.Add(ts1)  
    ```  
  
    ```csharp  
    dataGrid1.TableStyles.Add(ts1);  
    ```  
  
    ```cpp  
    dataGrid1->TableStyles->Add(ts1);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="64a0e-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="64a0e-119">See Also</span></span>  
 [<span data-ttu-id="64a0e-120">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="64a0e-120">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="64a0e-121">如何：在 Windows 窗体 DataGrid 控件中删除或隐藏列</span><span class="sxs-lookup"><span data-stu-id="64a0e-121">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
