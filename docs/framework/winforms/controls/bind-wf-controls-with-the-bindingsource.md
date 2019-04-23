---
title: 如何：使用设计器将 Windows 窗体控件与 BindingSource 组件进行绑定
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: a4f87303954494e8e32d32e68fb3f1244f25680a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59304553"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="f6d26-102">如何：使用设计器将 Windows 窗体控件与 BindingSource 组件进行绑定</span><span class="sxs-lookup"><span data-stu-id="f6d26-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="f6d26-103">在已向窗体添加控件并为你的应用程序确定的用户界面后，可以将控件绑定到数据源，以便在运行时，用户可以更改和保存到应用程序相关的数据。</span><span class="sxs-lookup"><span data-stu-id="f6d26-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>  
  
 <span data-ttu-id="f6d26-104">在 Windows 窗体中绑定的控件的一系列使用非常轻松地实现<xref:System.Windows.Forms.BindingSource>控件作为窗体上的控件和数据源之间的桥梁。</span><span class="sxs-lookup"><span data-stu-id="f6d26-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>  
  
 <span data-ttu-id="f6d26-105">在窗体上的一个或多个控件可以绑定到数据;在下面的过程，<xref:System.Windows.Forms.TextBox>控件绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="f6d26-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>  
  
 <span data-ttu-id="f6d26-106">若要完成该过程，假定您将绑定到派生自数据库的数据源。</span><span class="sxs-lookup"><span data-stu-id="f6d26-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="f6d26-107">从其他存储的数据创建数据源的详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。</span><span class="sxs-lookup"><span data-stu-id="f6d26-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f6d26-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="f6d26-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="f6d26-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="f6d26-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="f6d26-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="f6d26-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="f6d26-111">若要将控件绑定在设计时</span><span class="sxs-lookup"><span data-stu-id="f6d26-111">To bind a control at design time</span></span>  
  
1. <span data-ttu-id="f6d26-112">拖动<xref:System.Windows.Forms.TextBox>到窗体控件。</span><span class="sxs-lookup"><span data-stu-id="f6d26-112">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>  
  
2. <span data-ttu-id="f6d26-113">在中**属性**窗口：</span><span class="sxs-lookup"><span data-stu-id="f6d26-113">In the **Properties** window:</span></span>  
  
    1.  <span data-ttu-id="f6d26-114">展开 **(DataBindings)** 节点。</span><span class="sxs-lookup"><span data-stu-id="f6d26-114">Expand the **(DataBindings)** node.</span></span>  
  
    2.  <span data-ttu-id="f6d26-115">单击箭头旁边<xref:System.Windows.Forms.TextBox.Text%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="f6d26-115">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>  
  
         <span data-ttu-id="f6d26-116">**数据源**UI 类型编辑器将打开。</span><span class="sxs-lookup"><span data-stu-id="f6d26-116">The **DataSource** UI type editor opens.</span></span>  
  
         <span data-ttu-id="f6d26-117">如果以前已为项目或窗体配置数据源，它将出现。</span><span class="sxs-lookup"><span data-stu-id="f6d26-117">If a data source has previously been configured for the project or form, it will appear.</span></span>  
  
3. <span data-ttu-id="f6d26-118">单击“添加项目数据源”以连接到数据并创建一个数据源。</span><span class="sxs-lookup"><span data-stu-id="f6d26-118">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
4. <span data-ttu-id="f6d26-119">在“数据源配置向导”欢迎页上，单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="f6d26-119">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
5. <span data-ttu-id="f6d26-120">上**选择数据源类型**页上，选择**数据库**。</span><span class="sxs-lookup"><span data-stu-id="f6d26-120">On the **Choose a Data Source Type** page, select **Database**.</span></span>  
  
6. <span data-ttu-id="f6d26-121">上**选择数据连接**页上，从可用连接列表中选择一个数据连接。</span><span class="sxs-lookup"><span data-stu-id="f6d26-121">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="f6d26-122">如果所需的数据连接不可用，请选择**新的连接**若要创建新的数据连接。</span><span class="sxs-lookup"><span data-stu-id="f6d26-122">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>  
  
7. <span data-ttu-id="f6d26-123">选择**是，将连接保存**应用程序配置文件中保存连接字符串。</span><span class="sxs-lookup"><span data-stu-id="f6d26-123">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
8. <span data-ttu-id="f6d26-124">选择要放置到应用程序中的数据库对象。</span><span class="sxs-lookup"><span data-stu-id="f6d26-124">Select the database objects to bring into your application.</span></span> <span data-ttu-id="f6d26-125">在这种情况下，选择你想的表中的一个字段<xref:System.Windows.Forms.TextBox>显示。</span><span class="sxs-lookup"><span data-stu-id="f6d26-125">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>  
  
9. <span data-ttu-id="f6d26-126">如果愿意，可以替换默认的数据集名称。</span><span class="sxs-lookup"><span data-stu-id="f6d26-126">Replace the default dataset name if you want.</span></span>  
  
10. <span data-ttu-id="f6d26-127">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="f6d26-127">Click **Finish**.</span></span>  
  
11. <span data-ttu-id="f6d26-128">在中**属性**窗口中，单击旁边的箭头<xref:System.Windows.Forms.TextBox.Text%2A>试属性。</span><span class="sxs-lookup"><span data-stu-id="f6d26-128">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="f6d26-129">在中**数据源**UI 类型编辑器中，选择要绑定的字段名称<xref:System.Windows.Forms.TextBox>到。</span><span class="sxs-lookup"><span data-stu-id="f6d26-129">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>  
  
     <span data-ttu-id="f6d26-130">**数据源**UI 类型编辑器将关闭并且数据集，<xref:System.Windows.Forms.BindingSource>和特定于数据连接添加到你的窗体的表适配器。</span><span class="sxs-lookup"><span data-stu-id="f6d26-130">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6d26-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6d26-131">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="f6d26-132">添加新数据源</span><span class="sxs-lookup"><span data-stu-id="f6d26-132">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="f6d26-133">[数据源窗口](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="f6d26-133">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>