---
title: 如何：通过使用设计器使用 Windows 窗体 DataGrid 控件创建主/详细信息列表
ms.date: 03/30/2017
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
ms.openlocfilehash: d1e598831954f17bdf3bc03ab880c344ca36aa5a
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "69039944"
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a><span data-ttu-id="c7c86-102">如何：通过使用设计器使用 Windows 窗体 DataGrid 控件创建主/详细信息列表</span><span class="sxs-lookup"><span data-stu-id="c7c86-102">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>

> [!NOTE]
>  <span data-ttu-id="c7c86-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="c7c86-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="c7c86-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="c7c86-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="c7c86-105">如果您<xref:System.Data.DataSet>包含一系列相关的表, 则可以使用两<xref:System.Windows.Forms.DataGrid>个控件以主-详细信息格式显示数据。</span><span class="sxs-lookup"><span data-stu-id="c7c86-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master-detail format.</span></span> <span data-ttu-id="c7c86-106">将<xref:System.Windows.Forms.DataGrid>一个网格指定为主网格, 并将第二个指定为详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="c7c86-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="c7c86-107">当你在 "主列表" 中选择条目时, 所有相关的子项都显示在 "详细信息" 列表中。</span><span class="sxs-lookup"><span data-stu-id="c7c86-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="c7c86-108">例如, 如果您<xref:System.Data.DataSet>包含 customers 表和相关订单表, 则您可以将 customers 表指定为主网格, 将 Orders 表指定为详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="c7c86-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="c7c86-109">从主网格中选择客户时, "订单" 表中与该客户关联的所有订单都将显示在 "详细信息" 网格中。</span><span class="sxs-lookup"><span data-stu-id="c7c86-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>

 <span data-ttu-id="c7c86-110">下面的过程需要一个**Windows 应用程序**项目 **(文件** > **新** > **项目** > **视觉对象C#** 或**Visual Basic**  >  **经典桌面** > **Windows 窗体应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="c7c86-110">The following procedure requires a **Windows Application** project (**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **Windows Forms Application**).</span></span>

## <a name="to-create-a-master-details-list-in-the-designer"></a><span data-ttu-id="c7c86-111">在设计器中创建主-详细信息列表</span><span class="sxs-lookup"><span data-stu-id="c7c86-111">To create a master-details list in the designer</span></span>

1. <span data-ttu-id="c7c86-112">向窗<xref:System.Windows.Forms.DataGrid>体添加两个控件。</span><span class="sxs-lookup"><span data-stu-id="c7c86-112">Add two <xref:System.Windows.Forms.DataGrid> controls to the form.</span></span> <span data-ttu-id="c7c86-113">有关详细信息，请参阅[如何：将控件添加到](how-to-add-controls-to-windows-forms.md)Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="c7c86-113">For more information, see [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="c7c86-114">在 Visual Studio 2005 中, <xref:System.Windows.Forms.DataGrid>默认情况下控件不在**工具箱**中。</span><span class="sxs-lookup"><span data-stu-id="c7c86-114">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="c7c86-115">有关详细信息，请参阅[如何：向 "工具箱](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100))" 添加项。</span><span class="sxs-lookup"><span data-stu-id="c7c86-115">For more information, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span>

    > [!NOTE]
    >  <span data-ttu-id="c7c86-116">以下步骤不适用于 Visual Studio 2005, 后者使用 "**数据源**" 窗口进行设计时数据绑定。</span><span class="sxs-lookup"><span data-stu-id="c7c86-116">The following steps are not applicable to Visual Studio 2005, which uses the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="c7c86-117">有关详细信息, 请参阅[在 Visual Studio 中将控件绑定到数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)和[如何:在 Windows 窗体应用程序](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120))中显示相关数据。</span><span class="sxs-lookup"><span data-stu-id="c7c86-117">For more information, see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) and [How to: Display Related Data in a Windows Forms Application](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/57tx3hhe(v=vs.120)).</span></span>

2. <span data-ttu-id="c7c86-118">将两个或多个表从**服务器资源管理器**拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="c7c86-118">Drag two or more tables from **Server Explorer** to the form.</span></span>

3. <span data-ttu-id="c7c86-119">从 "**数据**" 菜单中, 选择 "**生成数据集**"。</span><span class="sxs-lookup"><span data-stu-id="c7c86-119">From the **Data** menu, select **Generate DataSet**.</span></span>

4. <span data-ttu-id="c7c86-120">使用 "XML 设计器" 设置表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="c7c86-120">Set the relationships between the tables using the XML Designer.</span></span> <span data-ttu-id="c7c86-121">有关详细信息, 请参阅 "如何:在 MSDN 上的 XML 架构和数据集创建一对多关系。</span><span class="sxs-lookup"><span data-stu-id="c7c86-121">For details, see "How to: Create One-to-Many Relationships in XML Schemas and Datasets" on MSDN.</span></span>

5. <span data-ttu-id="c7c86-122">通过从 "**文件**" 菜单中选择 "**全部保存**" 来保存关系。</span><span class="sxs-lookup"><span data-stu-id="c7c86-122">Save the relationships by selecting **Save All** from the **File** menu.</span></span>

6. <span data-ttu-id="c7c86-123">配置要指定主网格的控件,如下所示:<xref:System.Windows.Forms.DataGrid></span><span class="sxs-lookup"><span data-stu-id="c7c86-123">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the master grid, as follows:</span></span>

    1. <span data-ttu-id="c7c86-124"><xref:System.Data.DataSet>从<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性的下拉列表中选择。</span><span class="sxs-lookup"><span data-stu-id="c7c86-124">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>

    2. <span data-ttu-id="c7c86-125">从<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性的下拉列表中选择主表 (例如 "客户")。</span><span class="sxs-lookup"><span data-stu-id="c7c86-125">Select the master table (for example, "Customers") from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span>

7. <span data-ttu-id="c7c86-126">配置要指定详细信息网格的控件,如下所示:<xref:System.Windows.Forms.DataGrid></span><span class="sxs-lookup"><span data-stu-id="c7c86-126">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the details grid, as follows:</span></span>

    1. <span data-ttu-id="c7c86-127"><xref:System.Data.DataSet>从<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性的下拉列表中选择。</span><span class="sxs-lookup"><span data-stu-id="c7c86-127">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>

    2. <span data-ttu-id="c7c86-128">从<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性的下拉列表中选择主表和详细信息表之间的关系 (例如 "CustOrd")。</span><span class="sxs-lookup"><span data-stu-id="c7c86-128">Select the relationship (for example, "Customers.CustOrd") between the master and detail tables from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span> <span data-ttu-id="c7c86-129">若要查看关系, 请通过单击下拉列表中的 "主表" **+** 旁边的加号 () 展开该节点。</span><span class="sxs-lookup"><span data-stu-id="c7c86-129">In order to see the relationship, expand the node by clicking on the plus (**+**) sign next to the master table in the drop-down list.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7c86-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="c7c86-130">See also</span></span>

- [<span data-ttu-id="c7c86-131">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="c7c86-131">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="c7c86-132">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="c7c86-132">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="c7c86-133">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="c7c86-133">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)
- [<span data-ttu-id="c7c86-134">在 Visual Studio 中将控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="c7c86-134">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
