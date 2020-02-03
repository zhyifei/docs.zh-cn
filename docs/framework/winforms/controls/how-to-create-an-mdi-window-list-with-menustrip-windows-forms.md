---
title: 如何：使用 MenuStrip 创建 MDI 窗口列表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731010"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="a905a-102">如何：使用 MenuStrip 创建 MDI 窗口列表（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="a905a-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="a905a-103">使用多文档界面（MDI）来创建可同时打开多个文档并将内容从一个文档复制并粘贴到另一个文档的应用程序。</span><span class="sxs-lookup"><span data-stu-id="a905a-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="a905a-104">此过程说明如何在父窗口菜单上创建所有活动子窗体的列表。</span><span class="sxs-lookup"><span data-stu-id="a905a-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="a905a-105">在 MenuStrip 上创建 MDI 窗口列表</span><span class="sxs-lookup"><span data-stu-id="a905a-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="a905a-106">创建一个窗体并将其 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a905a-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="a905a-107">在窗体上添加一个 <xref:System.Windows.Forms.MenuStrip> 控件。</span><span class="sxs-lookup"><span data-stu-id="a905a-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="a905a-108">将两个顶级菜单项添加到 <xref:System.Windows.Forms.MenuStrip>，并将其 <xref:System.Windows.Forms.Control.Text%2A> 属性设置为 `&File` 和 `&Window`。</span><span class="sxs-lookup"><span data-stu-id="a905a-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="a905a-109">将子菜单项添加到 `&File` 菜单项，并将其 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 属性设置为 `&Open`。</span><span class="sxs-lookup"><span data-stu-id="a905a-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="a905a-110">将 <xref:System.Windows.Forms.MenuStrip> 的 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 属性设置为 `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>。</span><span class="sxs-lookup"><span data-stu-id="a905a-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="a905a-111">向项目中添加一个窗体，并向其添加所需的控件，如另一个 <xref:System.Windows.Forms.MenuStrip>。</span><span class="sxs-lookup"><span data-stu-id="a905a-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="a905a-112">为 <xref:System.Windows.Forms.Control.Click>`&New` 的 <xref:System.Windows.Forms.ToolStripMenuItem> 事件创建一个事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a905a-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="a905a-113">在事件处理程序中，插入与下面类似的代码，以创建和显示 `Form1`的 MDI 子级 `Form2` 的新实例。</span><span class="sxs-lookup"><span data-stu-id="a905a-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
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
  
9. <span data-ttu-id="a905a-114">将代码放在 `&New`<xref:System.Windows.Forms.ToolStripMenuItem> 中，以注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a905a-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="a905a-115">编译代码</span><span class="sxs-lookup"><span data-stu-id="a905a-115">Compiling the Code</span></span>  
 <span data-ttu-id="a905a-116">此示例需要：</span><span class="sxs-lookup"><span data-stu-id="a905a-116">This example requires:</span></span>  
  
- <span data-ttu-id="a905a-117">名为 <xref:System.Windows.Forms.Form> 和 `Form1` 的两个 `Form2` 控件。</span><span class="sxs-lookup"><span data-stu-id="a905a-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="a905a-118"><xref:System.Windows.Forms.MenuStrip> 上名为 `Form1` 的 `menuStrip1` 控件和 <xref:System.Windows.Forms.MenuStrip> 上名为 `Form2` 的 `menuStrip2` 控件。</span><span class="sxs-lookup"><span data-stu-id="a905a-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="a905a-119">对 <xref:System?displayProperty=nameWithType> 和 <xref:System.Windows.Forms?displayProperty=nameWithType> 程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="a905a-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a905a-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a905a-120">See also</span></span>

- [<span data-ttu-id="a905a-121">如何：创建 MDI 父窗体</span><span class="sxs-lookup"><span data-stu-id="a905a-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="a905a-122">如何：创建 MDI 子窗体</span><span class="sxs-lookup"><span data-stu-id="a905a-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="a905a-123">MenuStrip 控件</span><span class="sxs-lookup"><span data-stu-id="a905a-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
