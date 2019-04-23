---
title: 如何：使用 （Windows 窗体） MenuStrip 创建 MDI 窗口列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: ec0d8af81e320bea3d9d69305f91bd56666ba7cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59299639"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="1ef42-102">如何：使用 （Windows 窗体） MenuStrip 创建 MDI 窗口列表</span><span class="sxs-lookup"><span data-stu-id="1ef42-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="1ef42-103">使用多文档界面 (MDI) 创建的应用程序可以打开多个文档在同一时间和复制并粘贴到另一个文档内容。</span><span class="sxs-lookup"><span data-stu-id="1ef42-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="1ef42-104">此过程演示如何创建父级的窗口菜单上的所有活动子窗体的列表。</span><span class="sxs-lookup"><span data-stu-id="1ef42-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="1ef42-105">若要在 MenuStrip 创建 MDI 窗口列表</span><span class="sxs-lookup"><span data-stu-id="1ef42-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="1ef42-106">创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="1ef42-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="1ef42-107">在窗体上添加一个 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="1ef42-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="1ef42-108">添加到两个顶级菜单项<xref:System.Windows.Forms.MenuStrip>并设置其<xref:System.Windows.Forms.Control.Text%2A>属性设置为`&File`和`&Window`。</span><span class="sxs-lookup"><span data-stu-id="1ef42-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="1ef42-109">将子菜单项添加到 `&File` 菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Open`。</span><span class="sxs-lookup"><span data-stu-id="1ef42-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="1ef42-110">设置<xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A>的属性<xref:System.Windows.Forms.MenuStrip>到`&Window` <xref:System.Windows.Forms.ToolStripMenuItem>。</span><span class="sxs-lookup"><span data-stu-id="1ef42-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="1ef42-111">向项目添加窗体并将所需的控件添加到它，例如另一个<xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="1ef42-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="1ef42-112">为 `&New`<xref:System.Windows.Forms.ToolStripMenuItem> 的 <xref:System.Windows.Forms.Control.Click> 事件创建一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1ef42-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="1ef42-113">事件处理程序中插入类似于以下内容，以创建和显示的新实例的代码`Form2`作为的 MDI 子级`Form1`。</span><span class="sxs-lookup"><span data-stu-id="1ef42-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="1ef42-114">将放置在以下代码`&New`<xref:System.Windows.Forms.ToolStripMenuItem>注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="1ef42-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="1ef42-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="1ef42-115">Compiling the Code</span></span>  
 <span data-ttu-id="1ef42-116">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="1ef42-116">This example requires:</span></span>  
  
-   <span data-ttu-id="1ef42-117">名为 `Form1` 和 `Form2` 的两个 <xref:System.Windows.Forms.Form> 控件。</span><span class="sxs-lookup"><span data-stu-id="1ef42-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
-   <span data-ttu-id="1ef42-118">`Form1` 上名为 `menuStrip1` 的 <xref:System.Windows.Forms.MenuStrip> 控件和 `Form2` 上名为 `menuStrip2` 的 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="1ef42-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
-   <span data-ttu-id="1ef42-119">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="1ef42-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ef42-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="1ef42-120">See also</span></span>

- [<span data-ttu-id="1ef42-121">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="1ef42-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="1ef42-122">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="1ef42-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="1ef42-123">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="1ef42-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
