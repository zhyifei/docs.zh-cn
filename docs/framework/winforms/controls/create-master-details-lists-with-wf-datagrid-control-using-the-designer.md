---
title: "如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- master-details lists
- DataGrid control [Windows Forms], master-details lists
- related tables [Windows Forms], displaying in DataGrid control
ms.assetid: 19438ba2-f687-4417-a2fb-ab1cd69d4ded
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 471d76450b2a14620773cbeb8982da43f130ac59
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-master-details-lists-with-the-windows-forms-datagrid-control-using-the-designer"></a><span data-ttu-id="e60cd-102">如何：使用设计器用 Windows 窗体 DataGrid 控件创建主/详细信息列表</span><span class="sxs-lookup"><span data-stu-id="e60cd-102">How to: Create Master-Details Lists with the Windows Forms DataGrid Control Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="e60cd-103"><xref:System.Windows.Forms.DataGridView> 控件取代了 <xref:System.Windows.Forms.DataGrid> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.DataGrid> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="e60cd-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="e60cd-104">有关详细信息，请参阅 [Windows 窗体 DataGridView 控件与 DataGrid 控件之间的区别](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)。</span><span class="sxs-lookup"><span data-stu-id="e60cd-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="e60cd-105">如果你<xref:System.Data.DataSet>包含一系列相关表，则可以使用两个<xref:System.Windows.Forms.DataGrid>控件以显示主-详细信息格式中的数据。</span><span class="sxs-lookup"><span data-stu-id="e60cd-105">If your <xref:System.Data.DataSet> contains a series of related tables, you can use two <xref:System.Windows.Forms.DataGrid> controls to display the data in a master-detail format.</span></span> <span data-ttu-id="e60cd-106">一个<xref:System.Windows.Forms.DataGrid>指定为将主网格，和第二个指定为详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="e60cd-106">One <xref:System.Windows.Forms.DataGrid> is designated to be the master grid, and the second is designated to be the details grid.</span></span> <span data-ttu-id="e60cd-107">后在主列表中选择一个条目，所有相关的子项将显示在详细信息列表。</span><span class="sxs-lookup"><span data-stu-id="e60cd-107">When you select an entry in the master list, all of the related child entries are shown in the details list.</span></span> <span data-ttu-id="e60cd-108">例如，如果你<xref:System.Data.DataSet>包含 Customers 表和相关的 Orders 表，则会指定要将主网格的 Customers 表和 Orders 表的详细信息网格。</span><span class="sxs-lookup"><span data-stu-id="e60cd-108">For example, if your <xref:System.Data.DataSet> contains a Customers table and a related Orders table, you would specify the Customers table to be the master grid and the Orders table to be the details grid.</span></span> <span data-ttu-id="e60cd-109">时从主网格中选择某个客户时，将在详细信息网格中显示所有与 Orders 表中的客户的订单。</span><span class="sxs-lookup"><span data-stu-id="e60cd-109">When a customer is selected from the master grid, all of the orders associated with that customer in the Orders table would be displayed in the details grid.</span></span>  
  
 <span data-ttu-id="e60cd-110">下面的过程需要**Windows 应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="e60cd-110">The following procedure requires a **Windows Application** project.</span></span> <span data-ttu-id="e60cd-111">有关设置此类项目的信息，请参阅[如何： 创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)。</span><span class="sxs-lookup"><span data-stu-id="e60cd-111">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e60cd-112">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="e60cd-112">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="e60cd-113">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="e60cd-113">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="e60cd-114">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="e60cd-114">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-create-a-master-details-list-in-the-designer"></a><span data-ttu-id="e60cd-115">在设计器中创建主-详细信息列表</span><span class="sxs-lookup"><span data-stu-id="e60cd-115">To create a master-details list in the designer</span></span>  
  
1.  <span data-ttu-id="e60cd-116">添加两个<xref:System.Windows.Forms.DataGrid>到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="e60cd-116">Add two <xref:System.Windows.Forms.DataGrid> controls to the form.</span></span> <span data-ttu-id="e60cd-117">有关详细信息，请参阅[如何： 向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="e60cd-117">For more information, see [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="e60cd-118">在[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]、<xref:System.Windows.Forms.DataGrid>控件将不处于**工具箱**默认情况下。</span><span class="sxs-lookup"><span data-stu-id="e60cd-118">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="e60cd-119">有关详细信息，请参阅[如何： 将项添加到工具箱](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0)。</span><span class="sxs-lookup"><span data-stu-id="e60cd-119">For more information, see [How to: Add Items to the Toolbox](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="e60cd-120">以下步骤不适用于[!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)]，它使用**数据源**设计时数据绑定的窗口。</span><span class="sxs-lookup"><span data-stu-id="e60cd-120">The following steps are not applicable to [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], which uses the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="e60cd-121">有关详细信息，请参阅[将控件绑定到 Visual Studio 中的数据](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)和[如何： 在 Windows 窗体应用程序中显示相关数据](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)。</span><span class="sxs-lookup"><span data-stu-id="e60cd-121">For more information, see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio) and [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).</span></span>  
  
2.  <span data-ttu-id="e60cd-122">将两个或多个表从**服务器资源管理器**到窗体。</span><span class="sxs-lookup"><span data-stu-id="e60cd-122">Drag two or more tables from **Server Explorer** to the form.</span></span>  
  
3.  <span data-ttu-id="e60cd-123">从**数据**菜单上，选择**生成数据集**。</span><span class="sxs-lookup"><span data-stu-id="e60cd-123">From the **Data** menu, select **Generate DataSet**.</span></span>  
  
4.  <span data-ttu-id="e60cd-124">设置使用 XML 设计器的表之间的关系。</span><span class="sxs-lookup"><span data-stu-id="e60cd-124">Set the relationships between the tables using the XML Designer.</span></span> <span data-ttu-id="e60cd-125">有关详细信息，请参阅"如何： 创建一个对多关系中 XML 架构和数据集"MSDN 上。</span><span class="sxs-lookup"><span data-stu-id="e60cd-125">For details, see "How to: Create One-to-Many Relationships in XML Schemas and Datasets" on MSDN.</span></span>  
  
5.  <span data-ttu-id="e60cd-126">通过选择保存关系**保存所有**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="e60cd-126">Save the relationships by selecting **Save All** from the **File** menu.</span></span>  
  
6.  <span data-ttu-id="e60cd-127">配置<xref:System.Windows.Forms.DataGrid>你想要将主网格中，指定，如下所示的控件：</span><span class="sxs-lookup"><span data-stu-id="e60cd-127">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the master grid, as follows:</span></span>  
  
    1.  <span data-ttu-id="e60cd-128">选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e60cd-128">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2.  <span data-ttu-id="e60cd-129">从下拉列表中选择的主表 （例如，"客户"）<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e60cd-129">Select the master table (for example, "Customers") from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span>  
  
7.  <span data-ttu-id="e60cd-130">配置<xref:System.Windows.Forms.DataGrid>你想要如下所示指定详细信息网格中的控件：</span><span class="sxs-lookup"><span data-stu-id="e60cd-130">Configure the <xref:System.Windows.Forms.DataGrid> control that you want to designate the details grid, as follows:</span></span>  
  
    1.  <span data-ttu-id="e60cd-131">选择<xref:System.Data.DataSet>从下拉列表中<xref:System.Windows.Forms.DataGrid.DataSource%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e60cd-131">Select the <xref:System.Data.DataSet> from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataSource%2A> property.</span></span>  
  
    2.  <span data-ttu-id="e60cd-132">选择从下拉列表中的 master 和详细信息表之间的关系 (例如，"Customers.CustOrd")<xref:System.Windows.Forms.DataGrid.DataMember%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e60cd-132">Select the relationship (for example, "Customers.CustOrd") between the master and detail tables from the drop-down list in the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property.</span></span> <span data-ttu-id="e60cd-133">若要查看的关系，通过单击加号展开的节点 (**+**) 旁边的下拉列表中的主表。</span><span class="sxs-lookup"><span data-stu-id="e60cd-133">In order to see the relationship, expand the node by clicking on the plus (**+**) sign next to the master table in the drop-down list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e60cd-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="e60cd-134">See Also</span></span>  
 [<span data-ttu-id="e60cd-135">DataGrid 控件</span><span class="sxs-lookup"><span data-stu-id="e60cd-135">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="e60cd-136">DataGrid 控件概述</span><span class="sxs-lookup"><span data-stu-id="e60cd-136">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="e60cd-137">如何：将 Windows 窗体 DataGrid 控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="e60cd-137">How to: Bind the Windows Forms DataGrid Control to a Data Source</span></span>](../../../../docs/framework/winforms/controls/how-to-bind-the-windows-forms-datagrid-control-to-a-data-source.md)  
 [<span data-ttu-id="e60cd-138">在 Visual Studio 中将控件绑定到数据</span><span class="sxs-lookup"><span data-stu-id="e60cd-138">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
