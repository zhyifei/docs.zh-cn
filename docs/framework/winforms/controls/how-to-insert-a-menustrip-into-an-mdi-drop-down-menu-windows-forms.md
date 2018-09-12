---
title: 如何：将 MenuStrip 插入 MDI 下拉菜单（Windows 窗体）
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 64e7e7875a635bcd4fbafb62d3ee7b7018214ee4
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2018
ms.locfileid: "44494117"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="2824e-102">如何：将 MenuStrip 插入 MDI 下拉菜单（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="2824e-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="2824e-103">在某些应用程序中，多文档界面 (MDI) 子窗口的类型可以不同于 MDI 父窗口。</span><span class="sxs-lookup"><span data-stu-id="2824e-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="2824e-104">例如，MDI 父窗口可能为电子表格，而 MDI 子窗口可能为图表。</span><span class="sxs-lookup"><span data-stu-id="2824e-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="2824e-105">在这种情况下，由于激活了不同类型的 MDI 子窗口，你想用 MDI 子菜单上的内容更新 MDI 父菜单的内容。</span><span class="sxs-lookup"><span data-stu-id="2824e-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="2824e-106">以下过程使用<xref:System.Windows.Forms.Form.IsMdiContainer%2A>， <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>， <xref:System.Windows.Forms.MergeAction>，和<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>属性，以从 MDI 子菜单中的一组菜单项插入 MDI 父菜单的下拉部分。</span><span class="sxs-lookup"><span data-stu-id="2824e-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="2824e-107">关闭 MDI 子窗口从 MDI 父删除插入的菜单项。</span><span class="sxs-lookup"><span data-stu-id="2824e-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="2824e-108">若要将 MenuStrip 插入 MDI 下拉菜单</span><span class="sxs-lookup"><span data-stu-id="2824e-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1.  <span data-ttu-id="2824e-109">创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2824e-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2.  <span data-ttu-id="2824e-110">将 <xref:System.Windows.Forms.MenuStrip> 添加到 `Form1` 并将 <xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2824e-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3.  <span data-ttu-id="2824e-111">将顶级菜单项添加到 `Form1`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `&File`。</span><span class="sxs-lookup"><span data-stu-id="2824e-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4.  <span data-ttu-id="2824e-112">添加到的三个子菜单项`&File`菜单项并设置其<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性设置为`&Open`， `&Import from`，和`E&xit`。</span><span class="sxs-lookup"><span data-stu-id="2824e-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5.  <span data-ttu-id="2824e-113">添加到的两个子菜单项`&Import from`子菜单项并设置其<xref:System.Windows.Forms.ToolStripItem.Text%2A>属性设置为`&Word`和`&Excel`。</span><span class="sxs-lookup"><span data-stu-id="2824e-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6.  <span data-ttu-id="2824e-114">将窗体添加到项目，将 <xref:System.Windows.Forms.MenuStrip> 添加该窗体，并将 `Form2`<xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="2824e-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7.  <span data-ttu-id="2824e-115">将顶级菜单项添加到 `Form2`<xref:System.Windows.Forms.MenuStrip> 并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&File`。</span><span class="sxs-lookup"><span data-stu-id="2824e-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8.  <span data-ttu-id="2824e-116">添加到的子菜单项`&File`菜单`Form2`按以下顺序： <xref:System.Windows.Forms.ToolStripSeparator>， `&Save`， `Save and &Close`，，另一个<xref:System.Windows.Forms.ToolStripSeparator>。</span><span class="sxs-lookup"><span data-stu-id="2824e-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="2824e-117">设置<xref:System.Windows.Forms.MergeAction>并<xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A>的属性`Form2`下表中所示的菜单项。</span><span class="sxs-lookup"><span data-stu-id="2824e-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="2824e-118">Form2 的菜单项</span><span class="sxs-lookup"><span data-stu-id="2824e-118">Form2 menu item</span></span>|<span data-ttu-id="2824e-119">MergeAction 值</span><span class="sxs-lookup"><span data-stu-id="2824e-119">MergeAction value</span></span>|<span data-ttu-id="2824e-120">MergeIndex 值</span><span class="sxs-lookup"><span data-stu-id="2824e-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="2824e-121">文件</span><span class="sxs-lookup"><span data-stu-id="2824e-121">File</span></span>|<span data-ttu-id="2824e-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="2824e-122">MatchOnly</span></span>|<span data-ttu-id="2824e-123">-1</span><span class="sxs-lookup"><span data-stu-id="2824e-123">-1</span></span>|  
    |<span data-ttu-id="2824e-124">Separator</span><span class="sxs-lookup"><span data-stu-id="2824e-124">Separator</span></span>|<span data-ttu-id="2824e-125">Insert</span><span class="sxs-lookup"><span data-stu-id="2824e-125">Insert</span></span>|<span data-ttu-id="2824e-126">2</span><span class="sxs-lookup"><span data-stu-id="2824e-126">2</span></span>|  
    |<span data-ttu-id="2824e-127">保存</span><span class="sxs-lookup"><span data-stu-id="2824e-127">Save</span></span>|<span data-ttu-id="2824e-128">Insert</span><span class="sxs-lookup"><span data-stu-id="2824e-128">Insert</span></span>|<span data-ttu-id="2824e-129">3</span><span class="sxs-lookup"><span data-stu-id="2824e-129">3</span></span>|  
    |<span data-ttu-id="2824e-130">保存并关闭</span><span class="sxs-lookup"><span data-stu-id="2824e-130">Save and Close</span></span>|<span data-ttu-id="2824e-131">Insert</span><span class="sxs-lookup"><span data-stu-id="2824e-131">Insert</span></span>|<span data-ttu-id="2824e-132">4</span><span class="sxs-lookup"><span data-stu-id="2824e-132">4</span></span>|  
    |<span data-ttu-id="2824e-133">Separator</span><span class="sxs-lookup"><span data-stu-id="2824e-133">Separator</span></span>|<span data-ttu-id="2824e-134">Insert</span><span class="sxs-lookup"><span data-stu-id="2824e-134">Insert</span></span>|<span data-ttu-id="2824e-135">5</span><span class="sxs-lookup"><span data-stu-id="2824e-135">5</span></span>|  
  
10. <span data-ttu-id="2824e-136">为 `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> 的 <xref:System.Windows.Forms.Control.Click> 事件创建一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2824e-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="2824e-137">在事件处理程序内，插入类似于以下示例代码的代码，从而将 `Form2` 的新实例创建和显示为 `Form1` 的 MDI 子级。</span><span class="sxs-lookup"><span data-stu-id="2824e-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="2824e-138">将类似于以下示例代码的代码放在 `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> 中以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2824e-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2824e-139">编译代码</span><span class="sxs-lookup"><span data-stu-id="2824e-139">Compiling the Code</span></span>  
 <span data-ttu-id="2824e-140">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="2824e-140">This example requires:</span></span>  
  
-   <span data-ttu-id="2824e-141">名为 `Form1` 和 `Form2` 的两个 <xref:System.Windows.Forms.Form> 控件。</span><span class="sxs-lookup"><span data-stu-id="2824e-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="2824e-142">`Form1` 上名为 `menuStrip1` 的 <xref:System.Windows.Forms.MenuStrip> 控件和 `Form2` 上名为 `menuStrip2` 的 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="2824e-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="2824e-143">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="2824e-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2824e-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="2824e-144">See Also</span></span>  
 [<span data-ttu-id="2824e-145">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="2824e-145">How to: Create MDI Parent Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-parent-forms.md)  
 [<span data-ttu-id="2824e-146">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="2824e-146">How to: Create MDI Child Forms</span></span>](../../../../docs/framework/winforms/advanced/how-to-create-mdi-child-forms.md)  
 [<span data-ttu-id="2824e-147">MenuStrip 控件概述</span><span class="sxs-lookup"><span data-stu-id="2824e-147">MenuStrip Control Overview</span></span>](../../../../docs/framework/winforms/controls/menustrip-control-overview-windows-forms.md)
