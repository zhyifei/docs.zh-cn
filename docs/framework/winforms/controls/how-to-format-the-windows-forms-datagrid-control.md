---
title: 如何：设置 Windows 窗体 DataGrid 控件的格式
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- columns [Windows Forms], DataGrid control
- colors [Windows Forms], applying to DataGrid controls
- DataGrid control [Windows Forms], formatting
- columns [Windows Forms], formatting in DataGrid control
- DataGrid control [Windows Forms], default styles
- tables [Windows Forms], formatting in DataGrid control
- formatting [Windows Forms]
ms.assetid: a50fcc3b-8abf-47ec-9029-7f268af4ddb1
ms.openlocfilehash: 8e5c41d6f146e6abef8d7670e6191b587ac86c92
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61941357"
---
# <a name="how-to-format-the-windows-forms-datagrid-control"></a><span data-ttu-id="ccd26-102">如何：设置 Windows 窗体 DataGrid 控件的格式</span><span class="sxs-lookup"><span data-stu-id="ccd26-102">How to: Format the Windows Forms DataGrid Control</span></span>
> [!NOTE]
>  <span data-ttu-id="ccd26-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="ccd26-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ccd26-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd26-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="ccd26-105">将不同的颜色应用到的各个部分<xref:System.Windows.Forms.DataGrid>控件来帮助简化在它的信息更轻松地阅读和理解。</span><span class="sxs-lookup"><span data-stu-id="ccd26-105">Applying different colors to various parts of a <xref:System.Windows.Forms.DataGrid> control can help to make the information in it easier to read and interpret.</span></span> <span data-ttu-id="ccd26-106">颜色可以应用于行和列。</span><span class="sxs-lookup"><span data-stu-id="ccd26-106">Color can be applied to rows and columns.</span></span> <span data-ttu-id="ccd26-107">行和列可以还显示或隐藏您自行决定。</span><span class="sxs-lookup"><span data-stu-id="ccd26-107">Rows and columns can also be hidden or shown at your discretion.</span></span>  
  
 <span data-ttu-id="ccd26-108">有三个基本方面的格式设置<xref:System.Windows.Forms.DataGrid>控件。</span><span class="sxs-lookup"><span data-stu-id="ccd26-108">There are three basic aspects of formatting the <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="ccd26-109">您可以设置属性来建立数据显示为默认样式。</span><span class="sxs-lookup"><span data-stu-id="ccd26-109">You can set properties to establish a default style in which data is displayed.</span></span> <span data-ttu-id="ccd26-110">以此为基础，你可以然后自定义在运行时显示某些表的方式。</span><span class="sxs-lookup"><span data-stu-id="ccd26-110">From that base, you can then customize the way certain tables are displayed at run time.</span></span> <span data-ttu-id="ccd26-111">最后，您可以修改哪些列显示在数据网格和颜色，并显示了其他格式设置。</span><span class="sxs-lookup"><span data-stu-id="ccd26-111">Finally, you can modify which columns are displayed in the data grid as well as the colors and other formatting that is shown.</span></span>  
  
 <span data-ttu-id="ccd26-112">作为在格式设置数据网格中的初始步骤，可以设置的属性<xref:System.Windows.Forms.DataGrid>本身。</span><span class="sxs-lookup"><span data-stu-id="ccd26-112">As an initial step in formatting a data grid, you can set the properties of the <xref:System.Windows.Forms.DataGrid> itself.</span></span> <span data-ttu-id="ccd26-113">这些颜色和格式选择窗体从其然后可以进行更改，具体取决于数据的表和列显示的基础。</span><span class="sxs-lookup"><span data-stu-id="ccd26-113">These color and format choices form a base from which you can then make changes depending on the data tables and columns displayed.</span></span>  
  
### <a name="to-establish-a-default-style-for-the-datagrid-control"></a><span data-ttu-id="ccd26-114">若要建立的 DataGrid 控件的默认样式</span><span class="sxs-lookup"><span data-stu-id="ccd26-114">To establish a default style for the DataGrid control</span></span>  
  
1. <span data-ttu-id="ccd26-115">根据需要设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="ccd26-115">Set the following properties as appropriate:</span></span>  
  
    |<span data-ttu-id="ccd26-116">属性</span><span class="sxs-lookup"><span data-stu-id="ccd26-116">Property</span></span>|<span data-ttu-id="ccd26-117">描述</span><span class="sxs-lookup"><span data-stu-id="ccd26-117">Description</span></span>|  
    |--------------|-----------------|  
    |<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>|<span data-ttu-id="ccd26-118"><xref:System.Windows.Forms.DataGrid.BackColor%2A>属性定义的网格中偶数行的颜色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-118">The <xref:System.Windows.Forms.DataGrid.BackColor%2A> property defines the color of the even-numbered rows of the grid.</span></span> <span data-ttu-id="ccd26-119">当您将设置<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>为不同的颜色的属性，所有其他行设置为此新的颜色 （行 1、 3、 5 和等等）。</span><span class="sxs-lookup"><span data-stu-id="ccd26-119">When you set the <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> property to a different color, every other row is set to this new color (rows 1, 3, 5, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackColor%2A>|<span data-ttu-id="ccd26-120">在网格中偶数的行的背景色 （0、 2、 4、 6 和等等的行）。</span><span class="sxs-lookup"><span data-stu-id="ccd26-120">The background color of the even-numbered rows of the grid (rows 0, 2, 4, 6, and so on).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>|<span data-ttu-id="ccd26-121">而<xref:System.Windows.Forms.DataGrid.BackColor%2A>并<xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A>属性确定在网格中，行的颜色<xref:System.Windows.Forms.DataGrid.BackgroundColor%2A>属性确定非行区域，才会显示在网格滚动到底部，或如果只有少量的行中包含的颜色在网格中。</span><span class="sxs-lookup"><span data-stu-id="ccd26-121">Whereas the <xref:System.Windows.Forms.DataGrid.BackColor%2A> and <xref:System.Windows.Forms.DataGrid.AlternatingBackColor%2A> properties determines the color of rows in the grid, the <xref:System.Windows.Forms.DataGrid.BackgroundColor%2A> property determines the color of the nonrow area, which is only visible when the grid is scrolled to the bottom, or if only a few rows are contained in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.BorderStyle%2A>|<span data-ttu-id="ccd26-122">网格的边框样式，其中一个<xref:System.Windows.Forms.BorderStyle>枚举值。</span><span class="sxs-lookup"><span data-stu-id="ccd26-122">The grid's border style, one of the <xref:System.Windows.Forms.BorderStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionBackColor%2A>|<span data-ttu-id="ccd26-123">正上方网格的网格窗口标题的背景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-123">The background color of the grid's window caption which appears immediately above the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionFont%2A>|<span data-ttu-id="ccd26-124">在网格的顶部的标题的字体。</span><span class="sxs-lookup"><span data-stu-id="ccd26-124">The font of the caption at the top of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.CaptionForeColor%2A>|<span data-ttu-id="ccd26-125">网格的窗口标题的背景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-125">The background color of the grid's window caption.</span></span>|  
    |<xref:System.Windows.Forms.Control.Font%2A>|<span data-ttu-id="ccd26-126">用于在网格中显示文本的字体。</span><span class="sxs-lookup"><span data-stu-id="ccd26-126">The font used to display the text in the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ForeColor%2A>|<span data-ttu-id="ccd26-127">数据网格行中的数据所显示的字体颜色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-127">The color of the font displayed by the data in the rows of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineColor%2A>|<span data-ttu-id="ccd26-128">数据网格的网格线的颜色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-128">The color of the grid lines of the data grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.GridLineStyle%2A>|<span data-ttu-id="ccd26-129">网格中的一个单元格进行分隔线的样式<xref:System.Windows.Forms.DataGridLineStyle>枚举值。</span><span class="sxs-lookup"><span data-stu-id="ccd26-129">The style of the lines separating the cells of the grid, one of the <xref:System.Windows.Forms.DataGridLineStyle> enumeration values.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderBackColor%2A>|<span data-ttu-id="ccd26-130">行和列标题的背景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-130">The background color of row and column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderFont%2A>|<span data-ttu-id="ccd26-131">用于列标题的字体。</span><span class="sxs-lookup"><span data-stu-id="ccd26-131">The font used for the column headers.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.HeaderForeColor%2A>|<span data-ttu-id="ccd26-132">网格的列标题，其中包括列标题文本和加/减标志符号 （若要显示多个相关的表时，请展开行） 的前景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-132">The foreground color of the grid's column headers, including the column header text and the plus/minus glyphs (to expand rows when multiple related tables are displayed).</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.LinkColor%2A>|<span data-ttu-id="ccd26-133">在数据网格中，其中包括指向子表、 关系名称和等等的所有链接的文本的颜色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-133">The color of text of all the links in the data grid, including links to child tables, the relation name, and so on.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsBackColor%2A>|<span data-ttu-id="ccd26-134">在子表中，这是父行的背景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-134">In a child table, this is the background color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsForeColor%2A>|<span data-ttu-id="ccd26-135">在子表中，这是父行的前景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-135">In a child table, this is the foreground color of the parent rows.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.ParentRowsLabelStyle%2A>|<span data-ttu-id="ccd26-136">确定表和列名称在父行中，通过显示<xref:System.Windows.Forms.DataGridParentRowsLabelStyle>枚举。</span><span class="sxs-lookup"><span data-stu-id="ccd26-136">Determines whether the table and column names are displayed in the parent row, by means of the <xref:System.Windows.Forms.DataGridParentRowsLabelStyle> enumeration.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredColumnWidth%2A>|<span data-ttu-id="ccd26-137">网格中列的默认宽度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="ccd26-137">The default width (in pixels) of columns in the grid.</span></span> <span data-ttu-id="ccd26-138">设置此属性才能重置<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性 (可以单独或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法)，或者该属性将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ccd26-138">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="ccd26-139">属性不能设置为小于 0 的值。</span><span class="sxs-lookup"><span data-stu-id="ccd26-139">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.PreferredRowHeight%2A>|<span data-ttu-id="ccd26-140">行的高度 （以像素为单位） 的网格中的行。</span><span class="sxs-lookup"><span data-stu-id="ccd26-140">The row height (in pixels) of rows in the grid.</span></span> <span data-ttu-id="ccd26-141">设置此属性才能重置<xref:System.Windows.Forms.DataGrid.DataSource%2A>和<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性 (可以单独或通过<xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>方法)，或者该属性将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ccd26-141">Set this property before resetting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties (either separately, or through the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method), or the property will have no effect.</span></span><br /><br /> <span data-ttu-id="ccd26-142">属性不能设置为小于 0 的值。</span><span class="sxs-lookup"><span data-stu-id="ccd26-142">The property cannot be set to a value less than 0.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.RowHeaderWidth%2A>|<span data-ttu-id="ccd26-143">网格的行标题的宽度。</span><span class="sxs-lookup"><span data-stu-id="ccd26-143">The width of the row headers of the grid.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionBackColor%2A>|<span data-ttu-id="ccd26-144">选择行或单元格后，这是背景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-144">When a row or cell is selected, this is the background color.</span></span>|  
    |<xref:System.Windows.Forms.DataGrid.SelectionForeColor%2A>|<span data-ttu-id="ccd26-145">选择行或单元格后，这是的前景色。</span><span class="sxs-lookup"><span data-stu-id="ccd26-145">When a row or cell is selected, this is the foreground color.</span></span>|  
  
    > [!NOTE]
    >  <span data-ttu-id="ccd26-146">请注意，自定义控件，就可以使控件由于较差的颜色选择 （例如，红色和绿色） 而无法访问的颜色时。</span><span class="sxs-lookup"><span data-stu-id="ccd26-146">Keep in mind, when customizing the colors of controls, that it is possible to make the control inaccessible, due to poor color choice (for example, red and green).</span></span> <span data-ttu-id="ccd26-147">使用提供的颜色**种系统颜色**调色板，若要避免此问题。</span><span class="sxs-lookup"><span data-stu-id="ccd26-147">Use the colors available on the **System Colors** palette to avoid this issue.</span></span>  
  
     <span data-ttu-id="ccd26-148">下面的过程假定窗体具有<xref:System.Windows.Forms.DataGrid>控件绑定到数据表。</span><span class="sxs-lookup"><span data-stu-id="ccd26-148">The following procedures assume your form has a <xref:System.Windows.Forms.DataGrid> control bound to a data table.</span></span> <span data-ttu-id="ccd26-149">有关详细信息，请参阅[Windows 窗体 DataGrid 控件绑定到数据源](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)。</span><span class="sxs-lookup"><span data-stu-id="ccd26-149">For more information, see [Binding the Windows Forms DataGrid Control to a Data Source](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md).</span></span>  
  
### <a name="to-set-the-table-and-column-style-of-a-data-table-programmatically"></a><span data-ttu-id="ccd26-150">若要以编程方式设置数据表的表和列样式</span><span class="sxs-lookup"><span data-stu-id="ccd26-150">To set the table and column style of a data table programmatically</span></span>  
  
1. <span data-ttu-id="ccd26-151">创建一个新的表样式，并设置其属性。</span><span class="sxs-lookup"><span data-stu-id="ccd26-151">Create a new table style and set its properties.</span></span>  
  
2. <span data-ttu-id="ccd26-152">创建列样式并设置其属性。</span><span class="sxs-lookup"><span data-stu-id="ccd26-152">Create a column style and set its properties.</span></span>  
  
3. <span data-ttu-id="ccd26-153">向表样式的列样式集合添加列样式。</span><span class="sxs-lookup"><span data-stu-id="ccd26-153">Add the column style to the table style's column styles collection.</span></span>  
  
4. <span data-ttu-id="ccd26-154">将表样式添加到数据网格的表样式集合。</span><span class="sxs-lookup"><span data-stu-id="ccd26-154">Add the table style to the data grid's table styles collection.</span></span>  
  
5. <span data-ttu-id="ccd26-155">在下面的示例中，创建的新实例<xref:System.Windows.Forms.DataGridTableStyle>并设置其<xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ccd26-155">In the example below, create an instance of a new <xref:System.Windows.Forms.DataGridTableStyle> and set its <xref:System.Windows.Forms.DataGridTableStyle.MappingName%2A> property.</span></span>  
  
6. <span data-ttu-id="ccd26-156">创建的新实例**GridColumnStyle**并设置其**MappingName** （和一些其他布局和显示属性）。</span><span class="sxs-lookup"><span data-stu-id="ccd26-156">Create a new instance of a **GridColumnStyle** and set its **MappingName** (and some other layout and display properties).</span></span>  
  
7. <span data-ttu-id="ccd26-157">重复步骤 2 到 6 个你想要创建每个列样式。</span><span class="sxs-lookup"><span data-stu-id="ccd26-157">Repeat steps 2 through 6 for each column style you want to create.</span></span>  
  
     <span data-ttu-id="ccd26-158">下面的示例演示如何<xref:System.Windows.Forms.DataGridTextBoxColumn>创建，因为名称为要显示的列中。</span><span class="sxs-lookup"><span data-stu-id="ccd26-158">The following example illustrates how a <xref:System.Windows.Forms.DataGridTextBoxColumn> is created, because a name is to be displayed in the column.</span></span> <span data-ttu-id="ccd26-159">此外，还添加到列样式<xref:System.Windows.Forms.GridColumnStylesCollection>的表样式，并添加到的表样式<xref:System.Windows.Forms.GridTableStylesCollection>数据网格。</span><span class="sxs-lookup"><span data-stu-id="ccd26-159">Additionally, you add the column style to the <xref:System.Windows.Forms.GridColumnStylesCollection> of the table style, and you add the table style to the <xref:System.Windows.Forms.GridTableStylesCollection> of the data grid.</span></span>  
  
    ```vb  
    Private Sub CreateAuthorFirstNameColumn()  
       ' Add a GridTableStyle and set the MappingName   
       ' to the name of the DataTable.  
       Dim TSAuthors As New DataGridTableStyle()  
       TSAuthors.MappingName = "Authors"  
  
       ' Add a GridColumnStyle and set the MappingName   
       ' to the name of a DataColumn in the DataTable.   
       ' Set the HeaderText and Width properties.   
       Dim TCFirstName As New DataGridTextBoxColumn()  
       TCFirstName.MappingName = "AV_FName"  
       TCFirstName.HeaderText = "First Name"  
       TCFirstName.Width = 75  
       TSAuthors.GridColumnStyles.Add(TCFirstName)  
  
       ' Add the DataGridTableStyle instance to   
       ' the GridTableStylesCollection.   
       myDataGrid.TableStyles.Add(TSAuthors)  
    End Sub  
    ```  
  
    ```csharp  
    private void addCustomDataTableStyle()  
    {  
       // Add a GridTableStyle and set the MappingName   
       // to the name of the DataTable.  
       DataGridTableStyle TSAuthors = new DataGridTableStyle();  
       TSAuthors.MappingName = "Authors";  
  
       // Add a GridColumnStyle and set the MappingName   
       // to the name of a DataColumn in the DataTable.   
       // Set the HeaderText and Width properties.   
       DataGridColumnStyle TCFirstName = new DataGridTextBoxColumn();  
       TCFirstName.MappingName = " AV_FName";  
       TCFirstName.HeaderText = "First Name";  
       TCFirstName.Width = 75;  
       TSAuthors.GridColumnStyles.Add(TCFirstName);  
  
       // Add the DataGridTableStyle instance to   
       // the GridTableStylesCollection.   
       dataGrid1.TableStyles.Add(TSAuthors);  
    }  
    ```  
  
    ```cpp  
    private:  
       void addCustomDataTableStyle()  
       {  
          // Add a GridTableStyle and set the MappingName   
          // to the name of the DataTable.  
          DataGridTableStyle^ TSAuthors = new DataGridTableStyle();  
          TSAuthors->MappingName = "Authors";  
  
          // Add a GridColumnStyle and set the MappingName   
          // to the name of a DataColumn in the DataTable.   
          // Set the HeaderText and Width properties.   
          DataGridColumnStyle^ TCFirstName = gcnew DataGridTextBoxColumn();  
          TCFirstName->MappingName = "AV_FName";  
          TCFirstName->HeaderText = "First Name";  
          TCFirstName->Width = 75;  
          TSAuthors->GridColumnStyles->Add(TCFirstName);  
  
          // Add the DataGridTableStyle instance to   
          // the GridTableStylesCollection.   
          dataGrid1->TableStyles->Add(TSAuthors);  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="ccd26-160">请参阅</span><span class="sxs-lookup"><span data-stu-id="ccd26-160">See also</span></span>

- <xref:System.Windows.Forms.GridTableStylesCollection>
- <xref:System.Windows.Forms.GridColumnStylesCollection>
- <xref:System.Windows.Forms.DataGrid>
- [<span data-ttu-id="ccd26-161">如何：删除或隐藏 Windows 窗体 DataGrid 控件中的列</span><span class="sxs-lookup"><span data-stu-id="ccd26-161">How to: Delete or Hide Columns in the Windows Forms DataGrid Control</span></span>](how-to-delete-or-hide-columns-in-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="ccd26-162">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="ccd26-162">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
