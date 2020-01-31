---
title: 使用设计器将控件绑定到 BindingSource 组件
ms.date: 03/30/2017
helpviewer_keywords:
- controls [Windows Forms], binding
- BindingSource component [Windows Forms], binding controls
- data binding [Windows Forms], BindingSource component
ms.assetid: 391ae170-de5c-40f8-8233-91cb2ee4683a
ms.openlocfilehash: 35b3fb7b9884f07dd6e2aef311a01d3090c44227
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744393"
---
# <a name="how-to-bind-windows-forms-controls-with-the-bindingsource-component-using-the-designer"></a><span data-ttu-id="d0ebf-102">방법: 디자이너를 사용하여 Windows Forms 컨트롤에 BindingSource 구성 요소 바인딩</span><span class="sxs-lookup"><span data-stu-id="d0ebf-102">How to: Bind Windows Forms Controls with the BindingSource Component Using the Designer</span></span>
<span data-ttu-id="d0ebf-103">将控件添加到窗体并确定应用程序的用户界面后，可以将控件绑定到数据源，以便在运行时，用户可以更改和保存与应用程序相关的数据。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-103">After you have added controls to your form and determined the user interface for your application, you can bind the controls to a data source, so that, at run time, users can alter and save data related to the application.</span></span>

 <span data-ttu-id="d0ebf-104">使用 <xref:System.Windows.Forms.BindingSource> 控件作为窗体上的控件与数据源之间的桥梁，可以轻松地在 Windows 窗体中绑定控件或一系列控件。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-104">Binding a control or series of controls in Windows Forms is most easily accomplished using the <xref:System.Windows.Forms.BindingSource> control as a bridge between the controls on the form and the data source.</span></span>

 <span data-ttu-id="d0ebf-105">窗体上的一个或多个控件可以绑定到数据;在下面的过程中，<xref:System.Windows.Forms.TextBox> 控件绑定到数据源。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-105">One or more controls on a form can be bound to data; in the following procedure, a <xref:System.Windows.Forms.TextBox> control is bound to a data source.</span></span>

 <span data-ttu-id="d0ebf-106">若要完成该过程，假设您将绑定到从数据库派生的数据源。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-106">To complete the procedure, it is assumed that you will bind to a data source derived from a database.</span></span> <span data-ttu-id="d0ebf-107">有关从其他数据存储创建数据源的详细信息，请参阅[添加新数据源](/visualstudio/data-tools/add-new-data-sources)。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-107">For more information on creating data sources from other stores of data, see [Add new data sources](/visualstudio/data-tools/add-new-data-sources).</span></span>

## <a name="to-bind-a-control-at-design-time"></a><span data-ttu-id="d0ebf-108">在设计时绑定控件</span><span class="sxs-lookup"><span data-stu-id="d0ebf-108">To bind a control at design time</span></span>

1. <span data-ttu-id="d0ebf-109">将 <xref:System.Windows.Forms.TextBox> 控件拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-109">Drag a <xref:System.Windows.Forms.TextBox> control on to the form.</span></span>

2. <span data-ttu-id="d0ebf-110">在 "**属性**" 窗口中：</span><span class="sxs-lookup"><span data-stu-id="d0ebf-110">In the **Properties** window:</span></span>

    1. <span data-ttu-id="d0ebf-111">展开 " **（databinding）** " 节点。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-111">Expand the **(DataBindings)** node.</span></span>

    2. <span data-ttu-id="d0ebf-112">单击 "<xref:System.Windows.Forms.TextBox.Text%2A>" 属性旁边的箭头。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-112">Click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property.</span></span>

         <span data-ttu-id="d0ebf-113">"**数据源**UI 类型编辑器" 随即打开。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-113">The **DataSource** UI type editor opens.</span></span>

         <span data-ttu-id="d0ebf-114">如果以前已经为项目或窗体配置了数据源，则将显示该数据源。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-114">If a data source has previously been configured for the project or form, it will appear.</span></span>

3. <span data-ttu-id="d0ebf-115">**프로젝트 데이터 소스 추가**를 클릭하여 데이터에 연결한 다음 데이터 소스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d0ebf-115">Click **Add Project Data Source** to connect to data and create a data source.</span></span>

4. <span data-ttu-id="d0ebf-116">**데이터 소스 구성 마법사** 시작 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0ebf-116">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>

5. <span data-ttu-id="d0ebf-117">在 "**选择数据源类型**" 页上，选择 "**数据库**"。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-117">On the **Choose a Data Source Type** page, select **Database**.</span></span>

6. <span data-ttu-id="d0ebf-118">在 "**选择你的数据连接**" 页上，从可用连接的列表中选择一个数据连接。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-118">On the **Choose Your Data Connection** page, select a data connection from the list of available connections.</span></span> <span data-ttu-id="d0ebf-119">如果所需的数据连接不可用，请选择 "**新建连接**" 以创建新的数据连接。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-119">If your desired data connection is not available select **New Connection** to create a new data connection.</span></span>

7. <span data-ttu-id="d0ebf-120">选择 **"是，保存连接"，** 将连接字符串保存到应用程序配置文件中。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-120">Select **Yes, save the connection** to save the connection string in the application configuration file.</span></span>

8. <span data-ttu-id="d0ebf-121">애플리케이션에 바인딩할 데이터베이스 개체를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d0ebf-121">Select the database objects to bring into your application.</span></span> <span data-ttu-id="d0ebf-122">在这种情况下，请在表中选择希望 <xref:System.Windows.Forms.TextBox> 显示的字段。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-122">In this case, select a field in a table that you would like the <xref:System.Windows.Forms.TextBox> to display.</span></span>

9. <span data-ttu-id="d0ebf-123">원하는 경우 기본 데이터 세트 이름을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="d0ebf-123">Replace the default dataset name if you want.</span></span>

10. <span data-ttu-id="d0ebf-124">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0ebf-124">Click **Finish**.</span></span>

11. <span data-ttu-id="d0ebf-125">在 "**属性**" 窗口中，再次单击 <xref:System.Windows.Forms.TextBox.Text%2A> 属性旁的箭头。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-125">In the **Properties** window, click the arrow next to the <xref:System.Windows.Forms.TextBox.Text%2A> property again.</span></span> <span data-ttu-id="d0ebf-126">在 "**数据源**UI 类型编辑器" 中，选择要将 <xref:System.Windows.Forms.TextBox> 绑定到的字段的名称。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-126">In the **DataSource** UI type editor, select the name of the field to bind the <xref:System.Windows.Forms.TextBox> to.</span></span>

     <span data-ttu-id="d0ebf-127">数据**源**UI 类型编辑器将关闭，并将特定于该数据连接的数据集、<xref:System.Windows.Forms.BindingSource> 和表适配器添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="d0ebf-127">The **DataSource** UI type editor closes and the data set, <xref:System.Windows.Forms.BindingSource> and table adapter specific to that data connection are added to your form.</span></span>

## <a name="see-also"></a><span data-ttu-id="d0ebf-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0ebf-128">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- <xref:System.Windows.Forms.BindingNavigator>
- [<span data-ttu-id="d0ebf-129">새 데이터 소스 추가</span><span class="sxs-lookup"><span data-stu-id="d0ebf-129">Add new data sources</span></span>](/visualstudio/data-tools/add-new-data-sources)
- <span data-ttu-id="d0ebf-130">[数据源窗口](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="d0ebf-130">[Data Sources Window](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/6ckyxa83(v=vs.120))</span></span>
