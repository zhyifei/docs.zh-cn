---
title: "如何：使用设计器将数据绑定到 Windows 窗体的 DataGridView 控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Forms controls, binding to a data source
- data sources [Windows Forms], binding to Windows Forms controls
- DataGridView control [Windows Forms], data binding
ms.assetid: f4f46009-cec2-441b-8668-6b5af057558b
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a31b407360467f37c2e60b1a3f4f4c72e80e13a1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-data-to-the-windows-forms-datagridview-control-using-the-designer"></a><span data-ttu-id="18f64-102">如何：使用设计器将数据绑定到 Windows 窗体的 DataGridView 控件</span><span class="sxs-lookup"><span data-stu-id="18f64-102">How to: Bind Data to the Windows Forms DataGridView Control Using the Designer</span></span>
<span data-ttu-id="18f64-103">你可以使用设计器连接<xref:System.Windows.Forms.DataGridView>控件添加到数据源的多个不同的类型，包括数据库、 业务对象或 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="18f64-103">You can use the designer to connect a <xref:System.Windows.Forms.DataGridView> control to data sources of several different varieties, including databases, business objects, or Web services.</span></span> <span data-ttu-id="18f64-104">当将控件绑定到数据源使用设计器中时，控件将自动绑定到<xref:System.Windows.Forms.BindingSource>表示数据源的组件。</span><span class="sxs-lookup"><span data-stu-id="18f64-104">When you bind the control to a data source using the designer, the control is automatically bound to a <xref:System.Windows.Forms.BindingSource> component that represents the data source.</span></span> <span data-ttu-id="18f64-105">此外，会在控件中自动生成列以匹配数据源提供的架构信息。</span><span class="sxs-lookup"><span data-stu-id="18f64-105">Additionally, columns are automatically generated in the control to match the schema information provided by the data source.</span></span>  
  
 <span data-ttu-id="18f64-106">生成列后，可根据需要对其进行修改。</span><span class="sxs-lookup"><span data-stu-id="18f64-106">After columns have been generated, you can modify them to meet your needs.</span></span> <span data-ttu-id="18f64-107">例如，可删除或隐藏不不想显示的列、重新排列各列或修改列的类型。</span><span class="sxs-lookup"><span data-stu-id="18f64-107">For example, you can remove or hide columns you are not interested in displaying, you can rearrange the columns, or you can modify the column types.</span></span> <span data-ttu-id="18f64-108">有关修改列的详细信息，请参阅“另请参阅”部分中列出的主题。</span><span class="sxs-lookup"><span data-stu-id="18f64-108">For more information about modifying columns, see the topics listed in the See Also section.</span></span>  
  
 <span data-ttu-id="18f64-109">你也可以将绑定多个<xref:System.Windows.Forms.DataGridView>控件添加到相关表来创建主/从关系。</span><span class="sxs-lookup"><span data-stu-id="18f64-109">You can also bind multiple <xref:System.Windows.Forms.DataGridView> controls to related tables to create master/detail relationships.</span></span> <span data-ttu-id="18f64-110">在此配置中，一个控件显示父表，另一个控件只显示子表中与父表中的当前行相关的行。</span><span class="sxs-lookup"><span data-stu-id="18f64-110">In this configuration, one control displays a parent table and another control displays only those rows from a child table that are related to the current row in the parent table.</span></span> <span data-ttu-id="18f64-111">有关详细信息，请参阅[如何：在 Windows 窗体应用程序中显示相关数据](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)。</span><span class="sxs-lookup"><span data-stu-id="18f64-111">For more information, see [How to: Display Related Data in a Windows Forms Application](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd).</span></span>  
  
 <span data-ttu-id="18f64-112">下面的过程需要**Windows 应用程序**具有一个包含窗体项目<xref:System.Windows.Forms.DataGridView>控件或主/从关系的两个控件。</span><span class="sxs-lookup"><span data-stu-id="18f64-112">The following procedure requires a **Windows Application** project with a form that contains a <xref:System.Windows.Forms.DataGridView> control or two controls for a master/detail relationship.</span></span> <span data-ttu-id="18f64-113">有关启动此类项目的信息，请参阅[如何：创建 Windows 应用程序项目](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)和[如何：向 Windows 窗体添加控件](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="18f64-113">For information about starting such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="18f64-114">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="18f64-114">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="18f64-115">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="18f64-115">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="18f64-116">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="18f64-116">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-the-control-to-a-data-source"></a><span data-ttu-id="18f64-117">将控件绑定到数据源</span><span class="sxs-lookup"><span data-stu-id="18f64-117">To bind the control to a data source</span></span>  
  
1.  <span data-ttu-id="18f64-118">单击智能标记标志符号 (![智能标记标志符号](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) 右上角<xref:System.Windows.Forms.DataGridView>控件。</span><span class="sxs-lookup"><span data-stu-id="18f64-118">Click the smart tag glyph (![Smart Tag Glyph](../../../../docs/framework/winforms/controls/media/vs-winformsmttagglyph.gif "VS_WinFormSmtTagGlyph")) on the upper-right corner of the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
2.  <span data-ttu-id="18f64-119">单击“选择数据源”选项的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="18f64-119">Click the drop-down arrow for the **Choose Data Source** option.</span></span>  
  
3.  <span data-ttu-id="18f64-120">如果项目尚没有数据源，请单击“添加项目数据源”，按照向导指示的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="18f64-120">If your project does not already have a data source, click **Add Project Data Source** and follow the steps indicated by the wizard.</span></span>  
  
     <span data-ttu-id="18f64-121">有关详细信息，请参阅[数据源配置向导](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f)。</span><span class="sxs-lookup"><span data-stu-id="18f64-121">For more information, see [Data Source Configuration Wizard](http://msdn.microsoft.com/library/c4df7de5-5da0-4064-940c-761dd6d9e28f).</span></span> <span data-ttu-id="18f64-122">新数据源将显示在“选择数据源”下拉窗口中。</span><span class="sxs-lookup"><span data-stu-id="18f64-122">Your new data source will appear in the **Choose Data Source** drop-down window.</span></span> <span data-ttu-id="18f64-123">如果新数据源只包含一个成员（例如单个数据库表），控件将自动绑定到该成员。</span><span class="sxs-lookup"><span data-stu-id="18f64-123">If your new data source contains only one member, such as a single database table, the control will automatically bind to that member.</span></span> <span data-ttu-id="18f64-124">否则，请记住执行下一步。</span><span class="sxs-lookup"><span data-stu-id="18f64-124">Otherwise, continue to the next step.</span></span>  
  
4.  <span data-ttu-id="18f64-125">如果尚未展开，则展开“其他数据源”和“项目数据源”节点，然后选择绑定控件的数据源。</span><span class="sxs-lookup"><span data-stu-id="18f64-125">Expand the **Other Data Sources** and **Project Data Sources** nodes if they are not already expanded, and then select the data source to bind the control to.</span></span>  
  
5.  <span data-ttu-id="18f64-126">如果您的数据源包含多个成员，例如，如果你具有创建<xref:System.Data.DataSet?displayProperty=nameWithType>包含多个表，展开数据源，然后选择要绑定到的特定成员。</span><span class="sxs-lookup"><span data-stu-id="18f64-126">If your data source contains more than one member, such as if you have created a <xref:System.Data.DataSet?displayProperty=nameWithType> that contains multiple tables, expand the data source, and then select the specific member to bind to.</span></span>  
  
6.  <span data-ttu-id="18f64-127">若要在创建主/从关系，**选择数据源**第二个下拉窗口<xref:System.Windows.Forms.DataGridView>控件中，展开<xref:System.Windows.Forms.BindingSource>为父表中，创建，然后从列表中选择相关的子表所示。</span><span class="sxs-lookup"><span data-stu-id="18f64-127">To create a master/detail relationship, in the **Choose Data Source** drop-down window for a second <xref:System.Windows.Forms.DataGridView> control, expand the <xref:System.Windows.Forms.BindingSource> created for the parent table, and then select the related child table from the list shown.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18f64-128">如果项目已有数据源，还可以使用“数据源”窗口创建数据窗体。</span><span class="sxs-lookup"><span data-stu-id="18f64-128">If your project already has a data source, you can also use the **Data Sources** window to create a data form.</span></span> <span data-ttu-id="18f64-129">有关详细信息，请参阅[数据源窗口](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)。</span><span class="sxs-lookup"><span data-stu-id="18f64-129">For more information, see [Data Sources Window](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18f64-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="18f64-130">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 <xref:System.Windows.Forms.DataGridView.DataMember%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.DataSource%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="18f64-131">如何：连接到数据库中的数据</span><span class="sxs-lookup"><span data-stu-id="18f64-131">How to: Connect to Data in a Database</span></span>](http://msdn.microsoft.com/library/6c56e54e-8834-4297-85aa-cc1a443ba556)  
 [<span data-ttu-id="18f64-132">如何：使用设计器在 Windows 窗体 DataGridView 控件中添加和删除列</span><span class="sxs-lookup"><span data-stu-id="18f64-132">How to: Add and Remove Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/add-and-remove-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="18f64-133">如何：使用设计器更改 Windows 窗体 DataGridView 控件中的列顺序</span><span class="sxs-lookup"><span data-stu-id="18f64-133">How to: Change the Order of Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-order-of-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="18f64-134">如何：使用设计器更改 Windows 窗体 DataGridView 列类型</span><span class="sxs-lookup"><span data-stu-id="18f64-134">How to: Change the Type of a Windows Forms DataGridView Column Using the Designer</span></span>](../../../../docs/framework/winforms/controls/change-the-type-of-a-wf-datagridview-column-using-the-designer.md)  
 [<span data-ttu-id="18f64-135">如何：使用设计器在 Windows 窗体 DataGridView 控件中冻结列</span><span class="sxs-lookup"><span data-stu-id="18f64-135">How to: Freeze Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/freeze-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="18f64-136">如何：使用设计器在 Windows 窗体 DataGridView 控件中隐藏列</span><span class="sxs-lookup"><span data-stu-id="18f64-136">How to: Hide Columns in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/hide-columns-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="18f64-137">如何：使用设计器在 Windows 窗体 DataGridView 控件中将列设为只读</span><span class="sxs-lookup"><span data-stu-id="18f64-137">How to: Make Columns Read-Only in the Windows Forms DataGridView Control Using the Designer</span></span>](../../../../docs/framework/winforms/controls/make-columns-read-only-in-the-datagrid-using-the-designer.md)  
 [<span data-ttu-id="18f64-138">如何： 创建 Windows 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="18f64-138">How to: Create a Windows Application Project</span></span>](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa)  
 [<span data-ttu-id="18f64-139">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="18f64-139">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="18f64-140">数据源窗口</span><span class="sxs-lookup"><span data-stu-id="18f64-140">Data Sources Window</span></span>](http://msdn.microsoft.com/library/0d20f699-cc95-45b3-8ecb-c7edf1f67992)  
 [<span data-ttu-id="18f64-141">如何：在 Windows 窗体应用程序中显示相关数据</span><span class="sxs-lookup"><span data-stu-id="18f64-141">How to: Display Related Data in a Windows Forms Application</span></span>](http://msdn.microsoft.com/library/60b1f1ec-6257-42ab-83f0-06d54ed364fd)
