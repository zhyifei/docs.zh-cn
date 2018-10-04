---
title: 如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: c528e95b37abb230e761ce93e5f5c7bcb27d30d3
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48780292"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="9211f-102">如何：使用设计器将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="9211f-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="9211f-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="9211f-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="9211f-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="9211f-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="9211f-105">Windows 窗体<xref:System.Windows.Forms.DataGrid>控件专门设计用于显示数据源中的信息。</span><span class="sxs-lookup"><span data-stu-id="9211f-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="9211f-106">将控件在设计时绑定通过设置<xref:System.Windows.Forms.DataGrid.DataSource%2A>并<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性，或在运行时通过调用<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9211f-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="9211f-107">尽管可以显示来自各种数据源的数据，最典型的源是数据集和数据视图。</span><span class="sxs-lookup"><span data-stu-id="9211f-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="9211f-108">如果在设计时数据源，例如，如果该窗体包含一个数据集或数据视图的实例，则可以在设计时将网格绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="9211f-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="9211f-109">您可以预览数据网格中的显示效果。</span><span class="sxs-lookup"><span data-stu-id="9211f-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="9211f-110">此外可以在运行时以编程方式，绑定网格。</span><span class="sxs-lookup"><span data-stu-id="9211f-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="9211f-111">当你想要设置基于在运行时获取的信息的数据源时，这很有用。</span><span class="sxs-lookup"><span data-stu-id="9211f-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="9211f-112">例如，应用程序可能会让用户指定要查看的表的名称。</span><span class="sxs-lookup"><span data-stu-id="9211f-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="9211f-113">还有必要在数据源位置不存在在设计时的情况下。</span><span class="sxs-lookup"><span data-stu-id="9211f-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="9211f-114">这包括如数组、 集合、 非类型化数据集和数据读取器的数据源。</span><span class="sxs-lookup"><span data-stu-id="9211f-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="9211f-115">下面的过程需要**Windows 应用程序**包含一个窗体，其中包含项目<xref:System.Windows.Forms.DataGrid>控件。</span><span class="sxs-lookup"><span data-stu-id="9211f-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="9211f-116">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa)并[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9211f-116">For information about setting up such a project, see [How to: Create a Windows Application Project](https://msdn.microsoft.com/library/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="9211f-117">在 Visual Studio 2005 中，<xref:System.Windows.Forms.DataGrid>控件不在**工具箱**默认情况下。</span><span class="sxs-lookup"><span data-stu-id="9211f-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="9211f-118">考虑将其添加信息，请参阅[如何： 将项添加到工具箱](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)。</span><span class="sxs-lookup"><span data-stu-id="9211f-118">For information about adding it, see [How to: Add Items to the Toolbox](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span> <span data-ttu-id="9211f-119">此外在 Visual Studio 2005 中，你可以使用**数据源**设计时数据绑定的窗口。</span><span class="sxs-lookup"><span data-stu-id="9211f-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="9211f-120">有关详细信息请参阅[将控件绑定到 Visual Studio 中的数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)。</span><span class="sxs-lookup"><span data-stu-id="9211f-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9211f-121">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="9211f-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="9211f-122">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="9211f-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="9211f-123">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="9211f-123">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="9211f-124">若要对单个表设计器中数据绑定的 DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="9211f-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1.  <span data-ttu-id="9211f-125">设置控件的<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性设置为包含你想要将绑定到的数据项目的对象。</span><span class="sxs-lookup"><span data-stu-id="9211f-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="9211f-126">如果数据集数据源，则设置<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性设置为要绑定到的表的名称。</span><span class="sxs-lookup"><span data-stu-id="9211f-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3.  <span data-ttu-id="9211f-127">如果数据源的数据集或数据视图基于数据集表，将代码添加到窗体来填充数据集。</span><span class="sxs-lookup"><span data-stu-id="9211f-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="9211f-128">所使用的确切代码取决于数据集从何处获取数据。</span><span class="sxs-lookup"><span data-stu-id="9211f-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="9211f-129">如果要直接从数据库填充数据集，则通常会调用`Fill`的数据适配器，如下面的代码示例使用一个称为数据集来填充中所示方法`DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="9211f-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  <span data-ttu-id="9211f-130">（可选）将适当的表样式和列样式添加到网格中。</span><span class="sxs-lookup"><span data-stu-id="9211f-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="9211f-131">如果没有表样式，您将看到表中，但其格式设置很少，且所有列均可见。</span><span class="sxs-lookup"><span data-stu-id="9211f-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="9211f-132">若要对多个表中的数据集设计器中数据绑定的 DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="9211f-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1.  <span data-ttu-id="9211f-133">设置控件的<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性设置为包含你想要将绑定到的数据项目的对象。</span><span class="sxs-lookup"><span data-stu-id="9211f-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="9211f-134">如果数据集包含相关的表 （即，如果它包含关系对象），请将<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性设置为父表的名称。</span><span class="sxs-lookup"><span data-stu-id="9211f-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3.  <span data-ttu-id="9211f-135">编写代码以填充数据集。</span><span class="sxs-lookup"><span data-stu-id="9211f-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9211f-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="9211f-136">See Also</span></span>  
 [<span data-ttu-id="9211f-137">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="9211f-137">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="9211f-138">如何：向 Windows 窗体 DataGrid 控件添加表和列</span><span class="sxs-lookup"><span data-stu-id="9211f-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="9211f-139">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="9211f-139">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="9211f-140">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="9211f-140">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="9211f-141">在 Visual Studio 中访问数据</span><span class="sxs-lookup"><span data-stu-id="9211f-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
