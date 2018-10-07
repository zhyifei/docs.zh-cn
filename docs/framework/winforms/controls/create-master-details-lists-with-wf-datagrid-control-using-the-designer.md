---
title: 如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: aec02e38fbe80302108397543144b1cc9c3ea346
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837136"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a><span data-ttu-id="ad137-102">如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表</span><span class="sxs-lookup"><span data-stu-id="ad137-102">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="ad137-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="ad137-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ad137-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="ad137-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="ad137-105">如果你<xref:System.Data.DataSet>包含一系列相关表，则可以使用两个<xref:System.Windows.Forms.DataGrid>控件以显示母版-详细信息格式的数据。</span><span class="sxs-lookup"><span data-stu-id="ad137-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master-detail format.</span></span> <span data-ttu-id="ad137-106">一个<xref:System.Windows.Forms.DataGrid>指定主网格中，且第二个指定要在详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="ad137-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="ad137-107">当在主列表中选择一个条目时，所有相关的子条目所示详细信息列表。</span><span class="sxs-lookup"><span data-stu-id="ad137-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="ad137-108">例如，如果你<xref:System.Data.DataSet>包含 Customers 表和相关的 Orders 表，需要指定要将主网格客户表和 Orders 表中，会在详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="ad137-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="ad137-109">在主网格中选择客户后，将详细信息网格中显示所有关联订单表中与该客户的订单。</span><span class="sxs-lookup"><span data-stu-id="ad137-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
 <span data-ttu-id="ad137-110">下面的过程需要**Windows 应用程序**项目 (**文件** > **新建** > **项目** >  **Visual C#** 或**Visual Basic** > **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="ad137-110">The following procedure requires a **Windows Application** project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad137-111">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="ad137-111">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="ad137-112">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="ad137-112">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="ad137-113">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="ad137-113">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a><span data-ttu-id="ad137-114">若要在设计器中创建母版-详细信息列表</span><span class="sxs-lookup"><span data-stu-id="ad137-114">To create a master-details list in the designer</span></span>  
  
1.  <span data-ttu-id="ad137-115">添加两个<xref:System.Windows.Forms.DataGrid>到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="ad137-115">Add two <xref:System.Windows.Forms.DataGrid> controls to the form.</span></span> <span data-ttu-id="ad137-116">有关详细信息，请参阅[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="ad137-116">For more information, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="ad137-117">在 Visual Studio 2005 中，<xref:System.Windows.Forms.DataGrid>控件不在**工具箱**默认情况下。</span><span class="sxs-lookup"><span data-stu-id="ad137-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="ad137-118">有关详细信息，请参阅[如何： 将项添加到工具箱](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0)。</span><span class="sxs-lookup"><span data-stu-id="ad137-118">For more information, see [How to: Add Items to the Toolbox](https://msdn.microsoft.com/library/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ad137-119">以下步骤不是适用于 Visual Studio 2005 中，使用**数据源**设计时数据绑定的窗口。</span><span class="sxs-lookup"><span data-stu-id="ad137-119">The following steps are not applicable to Visual Studio 2005, which uses the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="ad137-120">有关详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)并[如何： 在 Windows 窗体应用程序中显示相关数据](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)。</span><span class="sxs-lookup"><span data-stu-id="ad137-120">For more information, see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) and [How to: Display Related Data in a Windows Forms Application](https://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).</span></span>  
  
2.  <span data-ttu-id="ad137-121">将从两个或多个表拖**服务器资源管理器**到窗体。</span><span class="sxs-lookup"><span data-stu-id="ad137-121">Drag two or more tables from **Server Explorer** to the form.</span></span>  
  
3.  <span data-ttu-id="ad137-122">从**数据**菜单中，选择**生成数据集**。</span><span class="sxs-lookup"><span data-stu-id="ad137-122">From the **Data** menu, select **Generate DataSet**.</span></span>  
  
4.  <span data-ttu-id="ad137-123">设置使用在 XML 设计器在表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="ad137-123">Set the relationships between the tables using the XML Designer.</span></span> <span data-ttu-id="ad137-124">有关详细信息，请参阅"如何： 创建一个对多关系中的 XML 架构和数据集"MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="ad137-124">For details, see "How to: Create One-to-Many Relationships in XML Schemas and Datasets" on MSDN.</span></span>  
  
5.  <span data-ttu-id="ad137-125">通过选择保存关系**全部保存**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="ad137-125">Save the relationships by selecting **Save All** from the **File** menu.</span></span>  
  
6.  <span data-ttu-id="ad137-126">配置<xref:System.Windows.Forms.DataGrid>控制你想要指定主网格中，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad137-126">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the master grid, as follows:</span></span>  
  
    1.  <span data-ttu-id="ad137-127">选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ad137-127">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2.  <span data-ttu-id="ad137-128">从下拉列表中选择主表 （例如，"客户"）<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ad137-128">Select the master table (for example, "Customers") from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span>  
  
7.  <span data-ttu-id="ad137-129">配置<xref:System.Windows.Forms.DataGrid>控件指定详细信息网格中，按如下所示：</span><span class="sxs-lookup"><span data-stu-id="ad137-129">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the details grid, as follows:</span></span>  
  
    1.  <span data-ttu-id="ad137-130">选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ad137-130">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2.  <span data-ttu-id="ad137-131">选择从下拉列表中的母版和详细信息表之间的关系 (例如，"Customers.CustOrd")<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="ad137-131">Select the relationship (for example, "Customers.CustOrd") between the master and detail tables from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span> <span data-ttu-id="ad137-132">若要查看的关系，通过单击加号展开节点 (**+**) 旁边的下拉列表中的主表。</span><span class="sxs-lookup"><span data-stu-id="ad137-132">In order to see the relationship, expand the node by clicking on the plus (**+**) sign next to the master table in the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad137-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="ad137-133">See Also</span></span>  
 [<span data-ttu-id="ad137-134">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="ad137-134">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="ad137-135">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="ad137-135">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="ad137-136">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="ad137-136">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [<span data-ttu-id="ad137-137">在 Visual Studio 中将控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="ad137-137">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
