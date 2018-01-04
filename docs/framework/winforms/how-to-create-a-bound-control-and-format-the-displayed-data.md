---
title: "如何：创建绑定控件并设置显示数据的格式"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data [Windows Forms], formatting
- bound controls [Windows Forms], creating
- bound controls [Windows Forms], formatting data
ms.assetid: d5a56228-899d-41d9-8af8-87b3f4ec2f94
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 33d5491feccacba7f7b010b57e890ff7543a46f8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-bound-control-and-format-the-displayed-data"></a><span data-ttu-id="098f8-102">如何：创建绑定控件并设置显示数据的格式</span><span class="sxs-lookup"><span data-stu-id="098f8-102">How to: Create a Bound Control and Format the Displayed Data</span></span>
<span data-ttu-id="098f8-103">使用 Windows 窗体数据绑定，你可以设置使用数据绑定控件中显示的数据格式**格式设置和高级绑定**对话框。</span><span class="sxs-lookup"><span data-stu-id="098f8-103">With Windows Forms data binding, you can format the data displayed in a data-bound control by using the **Formatting and Advanced Binding** dialog box.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="098f8-104">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="098f8-104">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="098f8-105">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="098f8-105">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="098f8-106">有关详细信息，请参阅 [在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="098f8-106">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-bind-a-control-and-format-the-displayed-data"></a><span data-ttu-id="098f8-107">绑定控件并设置显示的数据的格式</span><span class="sxs-lookup"><span data-stu-id="098f8-107">To bind a control and format the displayed data</span></span>  
  
1.  <span data-ttu-id="098f8-108">连接到数据源。</span><span class="sxs-lookup"><span data-stu-id="098f8-108">Connect to a data source.</span></span>  
  
     <span data-ttu-id="098f8-109">有关详细信息，请参阅[连接到数据源](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)。</span><span class="sxs-lookup"><span data-stu-id="098f8-109">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="098f8-110">在窗体中，选择控件，然后打开“属性”窗口。</span><span class="sxs-lookup"><span data-stu-id="098f8-110">In the form, select the control, and then open the Properties window.</span></span>  
  
3.  <span data-ttu-id="098f8-111">展开**(DataBindings)**属性，然后在**（高级）**框中，单击省略号按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 以显示**格式设置和高级绑定**对话框中，具有该控件的属性的完整列表。</span><span class="sxs-lookup"><span data-stu-id="098f8-111">Expand the **(DataBindings)** property, and then in the **(Advanced)** box, click the ellipsis button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) to display the **Formatting and Advanced Binding** dialog box, which has a complete list of properties for that control.</span></span>  
  
4.  <span data-ttu-id="098f8-112">选择你想要将绑定，然后单击的属性**绑定**箭头。</span><span class="sxs-lookup"><span data-stu-id="098f8-112">Select the property you want to bind, and then click the **Binding** arrow.</span></span>  
  
     <span data-ttu-id="098f8-113">此时将显示可用数据源的列表。</span><span class="sxs-lookup"><span data-stu-id="098f8-113">A list of available data sources is displayed.</span></span>  
  
5.  <span data-ttu-id="098f8-114">展开要绑定到的数据源，直到找到所需的单个数据元素。</span><span class="sxs-lookup"><span data-stu-id="098f8-114">Expand the data source you want to bind to until you find the single data element you want.</span></span>  
  
     <span data-ttu-id="098f8-115">例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。</span><span class="sxs-lookup"><span data-stu-id="098f8-115">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
6.  <span data-ttu-id="098f8-116">单击要绑定到的元素的名称。</span><span class="sxs-lookup"><span data-stu-id="098f8-116">Click the name of an element to bind to.</span></span>  
  
7.  <span data-ttu-id="098f8-117">在**格式化类型**框中，单击你想要应用于控件中显示的数据的格式。</span><span class="sxs-lookup"><span data-stu-id="098f8-117">In the **Format type** box, click the format you want to apply to the data displayed in the control.</span></span>  
  
     <span data-ttu-id="098f8-118">在任何情况下，如果数据源包含 <xref:System.DBNull>，都可以指定控件中显示的值。</span><span class="sxs-lookup"><span data-stu-id="098f8-118">In every case, you can specify the value displayed in the control if the data source contains <xref:System.DBNull>.</span></span> <span data-ttu-id="098f8-119">否则，选项会略有不同，具体取决于你选择的格式类型。</span><span class="sxs-lookup"><span data-stu-id="098f8-119">Otherwise, the options vary slightly, depending on the format type you choose.</span></span> <span data-ttu-id="098f8-120">下表显示了格式类型和选项。</span><span class="sxs-lookup"><span data-stu-id="098f8-120">The following table shows the format types and options.</span></span>  
  
    |<span data-ttu-id="098f8-121">格式类型</span><span class="sxs-lookup"><span data-stu-id="098f8-121">Format type</span></span>|<span data-ttu-id="098f8-122">格式选项</span><span class="sxs-lookup"><span data-stu-id="098f8-122">Formatting option</span></span>|  
    |-----------------|-----------------------|  
    |<span data-ttu-id="098f8-123">无格式</span><span class="sxs-lookup"><span data-stu-id="098f8-123">No Formatting</span></span>|<span data-ttu-id="098f8-124">无选项。</span><span class="sxs-lookup"><span data-stu-id="098f8-124">No options.</span></span>|  
    |<span data-ttu-id="098f8-125">Numeric</span><span class="sxs-lookup"><span data-stu-id="098f8-125">Numeric</span></span>|<span data-ttu-id="098f8-126">使用指定的小数位数**小数位数**up-down 控件。</span><span class="sxs-lookup"><span data-stu-id="098f8-126">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="098f8-127">货币</span><span class="sxs-lookup"><span data-stu-id="098f8-127">Currency</span></span>|<span data-ttu-id="098f8-128">使用指定的小数位数**小数位数**up-down 控件。</span><span class="sxs-lookup"><span data-stu-id="098f8-128">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="098f8-129">日期时间</span><span class="sxs-lookup"><span data-stu-id="098f8-129">Date Time</span></span>|<span data-ttu-id="098f8-130">选择的日期和时间应显示方式选择其中一个中的项**类型**选择框。</span><span class="sxs-lookup"><span data-stu-id="098f8-130">Select how the date and time should be displayed by selecting one of the items in the **Type** selection box.</span></span>|  
    |<span data-ttu-id="098f8-131">科学记数法</span><span class="sxs-lookup"><span data-stu-id="098f8-131">Scientific</span></span>|<span data-ttu-id="098f8-132">使用指定的小数位数**小数位数**up-down 控件。</span><span class="sxs-lookup"><span data-stu-id="098f8-132">Specify number of decimal places by using **Decimal places** up-down control.</span></span>|  
    |<span data-ttu-id="098f8-133">自定义</span><span class="sxs-lookup"><span data-stu-id="098f8-133">Custom</span></span>|<span data-ttu-id="098f8-134">指定一个自定义格式字符串用法。</span><span class="sxs-lookup"><span data-stu-id="098f8-134">Specify a custom format string using.</span></span><br /><br /> <span data-ttu-id="098f8-135">有关详细信息，请参阅[格式化类型](../../../docs/standard/base-types/formatting-types.md)。</span><span class="sxs-lookup"><span data-stu-id="098f8-135">For more information, see [Formatting Types](../../../docs/standard/base-types/formatting-types.md).</span></span> <span data-ttu-id="098f8-136">**注意：**自定义格式字符串不能保证可成功往返行程之间的数据源和绑定的控件。</span><span class="sxs-lookup"><span data-stu-id="098f8-136">**Note:**  Custom format strings are not guaranteed to successfully round trip between the data source and bound control.</span></span> <span data-ttu-id="098f8-137">请改为处理该绑定的 <xref:System.Windows.Forms.Binding.Parse> 或 <xref:System.Windows.Forms.Binding.Format> 事件，并在事件处理代码中应用自定义格式设置。</span><span class="sxs-lookup"><span data-stu-id="098f8-137">Instead handle the <xref:System.Windows.Forms.Binding.Parse> or <xref:System.Windows.Forms.Binding.Format> event for the binding and apply custom formatting in the event-handling code.</span></span>|  
  
8.  <span data-ttu-id="098f8-138">单击**确定**关闭**格式设置和高级绑定**对话框并返回到属性窗口。</span><span class="sxs-lookup"><span data-stu-id="098f8-138">Click **OK** to close the **Formatting and Advanced Binding** dialog box and return to the Properties window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="098f8-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="098f8-139">See Also</span></span>  
 [<span data-ttu-id="098f8-140">如何：在 Windows 窗体上创建简单绑定的控件</span><span class="sxs-lookup"><span data-stu-id="098f8-140">How to: Create a Simple-Bound Control on a Windows Form</span></span>](../../../docs/framework/winforms/how-to-create-a-simple-bound-control-on-a-windows-form.md)  
 [<span data-ttu-id="098f8-141">Windows 窗体中的用户输入验证</span><span class="sxs-lookup"><span data-stu-id="098f8-141">User Input Validation in Windows Forms</span></span>](../../../docs/framework/winforms/user-input-validation-in-windows-forms.md)  
 [<span data-ttu-id="098f8-142">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="098f8-142">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
