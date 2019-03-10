---
title: 如何：为 Windows 窗体 ComboBox、 ListBox 或 CheckedListBox 控件创建查找表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- CheckedListBox control [Windows Forms], creating lookup tables
- lookup tables
- list boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], lookup tables
- ComboBox control [Windows Forms], lookup table
- lookup tables [Windows Forms], creating for controls
- combo boxes [Windows Forms], lookup tables
- ListBox control [Windows Forms], creating lookup tables
ms.assetid: 4ce35f12-1f4e-4317-92d1-af8686a8cfaa
ms.openlocfilehash: eaa92c2b95d8dd8578b46e44a948127e201bb351
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57724604"
---
# <a name="how-to-create-a-lookup-table-for-a-windows-forms-combobox-listbox-or-checkedlistbox-control"></a><span data-ttu-id="e2cb4-102">如何：为 Windows 窗体 ComboBox、 ListBox 或 CheckedListBox 控件创建查找表</span><span class="sxs-lookup"><span data-stu-id="e2cb4-102">How to: Create a Lookup Table for a Windows Forms ComboBox, ListBox, or CheckedListBox Control</span></span>
<span data-ttu-id="e2cb4-103">有时，在 Windows 窗体上以用户友好格式显示数据，但存储数据时使用对程序而言更有意义的格式会很有帮助。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-103">Sometimes it is useful to display data in a user-friendly format on a Windows Form, but store the data in a format that is more meaningful to your program.</span></span> <span data-ttu-id="e2cb4-104">例如，食品订单窗体可能按列表框中的名称显示菜单项。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-104">For example, an order form for food might display the menu items by name in a list box.</span></span> <span data-ttu-id="e2cb4-105">但是，记录订单的数据表将包含代表该食品的唯一 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-105">However, the data table recording the order would contain the unique ID numbers representing the food.</span></span> <span data-ttu-id="e2cb4-106">下表显示如何存储和显示食品订单窗体数据的示例。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-106">The following tables show an example of how to store and display order-form data for food.</span></span>  
  
### <a name="orderdetailstable"></a><span data-ttu-id="e2cb4-107">OrderDetailsTable</span><span class="sxs-lookup"><span data-stu-id="e2cb4-107">OrderDetailsTable</span></span>  
  
|<span data-ttu-id="e2cb4-108">OrderID</span><span class="sxs-lookup"><span data-stu-id="e2cb4-108">OrderID</span></span>|<span data-ttu-id="e2cb4-109">ItemID</span><span class="sxs-lookup"><span data-stu-id="e2cb4-109">ItemID</span></span>|<span data-ttu-id="e2cb4-110">Quantity</span><span class="sxs-lookup"><span data-stu-id="e2cb4-110">Quantity</span></span>|  
|-------------|------------|--------------|  
|<span data-ttu-id="e2cb4-111">4085</span><span class="sxs-lookup"><span data-stu-id="e2cb4-111">4085</span></span>|<span data-ttu-id="e2cb4-112">12</span><span class="sxs-lookup"><span data-stu-id="e2cb4-112">12</span></span>|<span data-ttu-id="e2cb4-113">1</span><span class="sxs-lookup"><span data-stu-id="e2cb4-113">1</span></span>|  
|<span data-ttu-id="e2cb4-114">4086</span><span class="sxs-lookup"><span data-stu-id="e2cb4-114">4086</span></span>|<span data-ttu-id="e2cb4-115">13</span><span class="sxs-lookup"><span data-stu-id="e2cb4-115">13</span></span>|<span data-ttu-id="e2cb4-116">3</span><span class="sxs-lookup"><span data-stu-id="e2cb4-116">3</span></span>|  
  
### <a name="itemtable"></a><span data-ttu-id="e2cb4-117">ItemTable</span><span class="sxs-lookup"><span data-stu-id="e2cb4-117">ItemTable</span></span>  
  
|<span data-ttu-id="e2cb4-118">Id</span><span class="sxs-lookup"><span data-stu-id="e2cb4-118">ID</span></span>|<span data-ttu-id="e2cb4-119">name</span><span class="sxs-lookup"><span data-stu-id="e2cb4-119">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="e2cb4-120">12</span><span class="sxs-lookup"><span data-stu-id="e2cb4-120">12</span></span>|<span data-ttu-id="e2cb4-121">Potato</span><span class="sxs-lookup"><span data-stu-id="e2cb4-121">Potato</span></span>|  
|<span data-ttu-id="e2cb4-122">13</span><span class="sxs-lookup"><span data-stu-id="e2cb4-122">13</span></span>|<span data-ttu-id="e2cb4-123">Chicken</span><span class="sxs-lookup"><span data-stu-id="e2cb4-123">Chicken</span></span>|  
  
 <span data-ttu-id="e2cb4-124">在此方案中，一个表中， **OrderDetailsTable**，存储您所关注显示和保存的实际信息。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-124">In this scenario, one table, **OrderDetailsTable**, stores the actual information you are concerned with displaying and saving.</span></span> <span data-ttu-id="e2cb4-125">但为了节省空间，它采用一种很隐秘的方式。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-125">But to save space, it does so in a fairly cryptic fashion.</span></span> <span data-ttu-id="e2cb4-126">另一个表**ItemTable**，包含有关哪个 ID 号等同于哪个食品名称，并执行任何操作有关的实际食品订单仅与外观相关的信息。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-126">The other table, **ItemTable**, contains only appearance-related information about which ID number is equivalent to which food name, and nothing about the actual food orders.</span></span>  
  
 <span data-ttu-id="e2cb4-127">**ItemTable**连接到<xref:System.Windows.Forms.ComboBox>， <xref:System.Windows.Forms.ListBox>，或<xref:System.Windows.Forms.CheckedListBox>控制通过三个属性。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-127">The **ItemTable** is connected to the <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control through three properties.</span></span> <span data-ttu-id="e2cb4-128">`DataSource`属性包含此表的名称。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-128">The `DataSource` property contains the name of this table.</span></span> <span data-ttu-id="e2cb4-129">`DisplayMember`属性包含你想要在控件 （食品名称） 中显示的表的数据列。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-129">The `DisplayMember` property contains the data column of that table that you want to display in the control (the food name).</span></span> <span data-ttu-id="e2cb4-130">`ValueMember`属性包含的数据列的表中具有存储信息 （ID 号）。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-130">The `ValueMember` property contains the data column of that table with the stored information (the ID number).</span></span>  
  
 <span data-ttu-id="e2cb4-131">**OrderDetailsTable**连接到控件通过其绑定集合，通过访问<xref:System.Windows.Forms.Control.DataBindings%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-131">The **OrderDetailsTable** is connected to the control by its bindings collection, accessed through the <xref:System.Windows.Forms.Control.DataBindings%2A> property.</span></span> <span data-ttu-id="e2cb4-132">时绑定对象添加到集合时，连接到数据源中的特定数据成员 （ID 号的列） 的控件属性 ( **OrderDetailsTable**)。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-132">When you add a binding object to the collection, you connect a control property to a specific data member (the column of ID numbers) in a data source (the **OrderDetailsTable**).</span></span> <span data-ttu-id="e2cb4-133">在控件中进行选择时，窗体输入将保存到此表。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-133">When a selection is made in the control, this table is where the form input is saved.</span></span>  
  
### <a name="to-create-a-lookup-table"></a><span data-ttu-id="e2cb4-134">创建查找表的步骤</span><span class="sxs-lookup"><span data-stu-id="e2cb4-134">To create a lookup table</span></span>  
  
1.  <span data-ttu-id="e2cb4-135">向窗体添加 <xref:System.Windows.Forms.ComboBox><xref:System.Windows.Forms.ListBox> 或 <xref:System.Windows.Forms.CheckedListBox> 控件。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-135">Add a <xref:System.Windows.Forms.ComboBox>, <xref:System.Windows.Forms.ListBox>, or <xref:System.Windows.Forms.CheckedListBox> control to the form.</span></span>  
  
2.  <span data-ttu-id="e2cb4-136">连接到数据源。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-136">Connect to your data source.</span></span>  
  
3.  <span data-ttu-id="e2cb4-137">在两张表之间建立数据关系。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-137">Establish a data relation between the two tables.</span></span> <span data-ttu-id="e2cb4-138">请参阅[DataRelation 对象介绍](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-138">See [Introduction to DataRelation Objects](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/0k21zcyx(v=vs.120)).</span></span>  
  
4.  <span data-ttu-id="e2cb4-139">设置以下属性：</span><span class="sxs-lookup"><span data-stu-id="e2cb4-139">Set the following properties.</span></span> <span data-ttu-id="e2cb4-140">以下属性可在代码或设计器中设置。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-140">They can be set in code or in the designer.</span></span>  
  
    |<span data-ttu-id="e2cb4-141">属性</span><span class="sxs-lookup"><span data-stu-id="e2cb4-141">Property</span></span>|<span data-ttu-id="e2cb4-142">设置</span><span class="sxs-lookup"><span data-stu-id="e2cb4-142">Setting</span></span>|  
    |--------------|-------------|  
    |<xref:System.Windows.Forms.ListControl.DataSource%2A>|<span data-ttu-id="e2cb4-143">包含有关哪个 ID 号等同于哪一项的信息的表。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-143">The table that contains information about which ID number is equivalent to which item.</span></span> <span data-ttu-id="e2cb4-144">在前面的方案，这是`ItemTable`。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-144">In the previous scenario, this is `ItemTable`.</span></span>|  
    |<xref:System.Windows.Forms.ListControl.DisplayMember%2A>|<span data-ttu-id="e2cb4-145">你想要在控件中显示的源数据表的列。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-145">The column of the data source table that you want to display in the control.</span></span> <span data-ttu-id="e2cb4-146">在前面的方案，这是`"Name"`（若要在代码中设置，使用引号）。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-146">In the previous scenario, this is `"Name"` (to set in code, use quotation marks).</span></span>|  
    |<xref:System.Windows.Forms.ListControl.ValueMember%2A>|<span data-ttu-id="e2cb4-147">包含所存储信息的源数据表的列。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-147">The column of the data source table that contains the stored information.</span></span> <span data-ttu-id="e2cb4-148">在前面的方案，这是`"ID"`（若要在代码中设置，使用引号）。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-148">In the previous scenario, this is `"ID"` (to set in code, use quotation marks).</span></span>|  
  
5.  <span data-ttu-id="e2cb4-149">在过程中，调用 <xref:System.Windows.Forms.ControlBindingsCollection> 类的 <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> 方法，以将控件的 <xref:System.Windows.Forms.ListControl.SelectedValue%2A> 属性绑定到记录窗体输入的表。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-149">In a procedure, call the <xref:System.Windows.Forms.ControlBindingsCollection.Add%2A> method of the <xref:System.Windows.Forms.ControlBindingsCollection> class to bind the control's <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property to the table recording the form input.</span></span> <span data-ttu-id="e2cb4-150">您可以执行此操作而不是在代码中，在设计器中访问控件的<xref:System.Windows.Forms.Control.DataBindings%2A>中的属性**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-150">You can also do this in the Designer instead of in code, by accessing the control's <xref:System.Windows.Forms.Control.DataBindings%2A> property in the **Properties** window.</span></span> <span data-ttu-id="e2cb4-151">在前面的方案，这是`OrderDetailsTable`，且列是`"ItemID"`。</span><span class="sxs-lookup"><span data-stu-id="e2cb4-151">In the previous scenario, this is `OrderDetailsTable`, and the column is `"ItemID"`.</span></span>  
  
    ```vb  
    ListBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID")  
    ```  
  
    ```csharp  
    listBox1.DataBindings.Add("SelectedValue", OrderDetailsTable, "ItemID");  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e2cb4-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2cb4-152">See also</span></span>
- [<span data-ttu-id="e2cb4-153">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="e2cb4-153">Data Binding and Windows Forms</span></span>](../data-binding-and-windows-forms.md)
- [<span data-ttu-id="e2cb4-154">ListBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="e2cb4-154">ListBox Control Overview</span></span>](listbox-control-overview-windows-forms.md)
- [<span data-ttu-id="e2cb4-155">ComboBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="e2cb4-155">ComboBox Control Overview</span></span>](combobox-control-overview-windows-forms.md)
- [<span data-ttu-id="e2cb4-156">CheckedListBox 控件概述</span><span class="sxs-lookup"><span data-stu-id="e2cb4-156">CheckedListBox Control Overview</span></span>](checkedlistbox-control-overview-windows-forms.md)
- [<span data-ttu-id="e2cb4-157">用于列出选项的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="e2cb4-157">Windows Forms Controls Used to List Options</span></span>](windows-forms-controls-used-to-list-options.md)
