---
title: 如何：使用 Windows 窗体创建多窗格用户界面
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
ms.openlocfilehash: 8650ba3b8011e50779080e31d94727609f2d08f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59315149"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a><span data-ttu-id="dc252-102">如何：使用 Windows 窗体创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="dc252-102">How to: Create a Multipane User Interface with Windows Forms</span></span>
<span data-ttu-id="dc252-103">在下面的过程中，将创建类似于在 Microsoft Outlook 中使用与多窗格用户界面**文件夹**列表中，**消息**窗格中，和一个**预览**窗格。</span><span class="sxs-lookup"><span data-stu-id="dc252-103">In the following procedure, you will create a multipane user interface that is similar to the one used in Microsoft Outlook, with a **Folder** list, a **Messages** pane, and a **Preview** pane.</span></span> <span data-ttu-id="dc252-104">这种排列方式被实现主要通过处理该窗体控件停靠。</span><span class="sxs-lookup"><span data-stu-id="dc252-104">This arrangement is achieved chiefly through docking controls with the form.</span></span>  
  
 <span data-ttu-id="dc252-105">停靠控件时，您可以确定控件固定的父容器的边缘。</span><span class="sxs-lookup"><span data-stu-id="dc252-105">When you dock a control, you determine which edge of the parent container a control is fastened to.</span></span> <span data-ttu-id="dc252-106">因此，如果您设置<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性设置为<xref:System.Windows.Forms.DockStyle.Right>，将在该控件的右边缘停靠到其父控件的右边缘。</span><span class="sxs-lookup"><span data-stu-id="dc252-106">Thus, if you set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Right>, the right edge of the control will be docked to the right edge of its parent control.</span></span> <span data-ttu-id="dc252-107">此外，该控件的停靠的边缘调整大小以匹配的它的容器控件。</span><span class="sxs-lookup"><span data-stu-id="dc252-107">Additionally, the docked edge of the control is resized to match that of its container control.</span></span> <span data-ttu-id="dc252-108">详细了解如何<xref:System.Windows.Forms.SplitContainer.Dock%2A>属性的工作原理，请参阅[如何：在 Windows 窗体上停靠控件](how-to-dock-controls-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="dc252-108">For more information about how the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property works, see [How to: Dock Controls on Windows Forms](how-to-dock-controls-on-windows-forms.md).</span></span>  
  
 <span data-ttu-id="dc252-109">此过程重点介绍排列<xref:System.Windows.Forms.SplitContainer>和其他控件在窗体上，而不上添加功能以使应用程序模仿 Microsoft Outlook。</span><span class="sxs-lookup"><span data-stu-id="dc252-109">This procedure focuses on arranging the <xref:System.Windows.Forms.SplitContainer> and the other controls on the form, not on adding functionality to make the application mimic Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="dc252-110">若要创建此用户界面，您将中的所有控件<xref:System.Windows.Forms.SplitContainer>控件，它包含<xref:System.Windows.Forms.TreeView>左侧面板中的控件。</span><span class="sxs-lookup"><span data-stu-id="dc252-110">To create this user interface, you place all the controls within a <xref:System.Windows.Forms.SplitContainer> control, which contains a <xref:System.Windows.Forms.TreeView> control in the left-hand panel.</span></span> <span data-ttu-id="dc252-111">右侧面板中的<xref:System.Windows.Forms.SplitContainer>控件包含第二个<xref:System.Windows.Forms.SplitContainer>控件替换<xref:System.Windows.Forms.ListView>控制上述<xref:System.Windows.Forms.RichTextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="dc252-111">The right-hand panel of the <xref:System.Windows.Forms.SplitContainer> control contains a second <xref:System.Windows.Forms.SplitContainer> control with a <xref:System.Windows.Forms.ListView> control above a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="dc252-112">这些<xref:System.Windows.Forms.SplitContainer>控件启用独立调整大小的窗体上的其他控件。</span><span class="sxs-lookup"><span data-stu-id="dc252-112">These <xref:System.Windows.Forms.SplitContainer> controls enable independent resizing of the other controls on the form.</span></span> <span data-ttu-id="dc252-113">您可以改写此过程，以制作出的您自己的自定义用户界面中的技术。</span><span class="sxs-lookup"><span data-stu-id="dc252-113">You can adapt the techniques in this procedure to craft custom user interfaces of your own.</span></span>  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a><span data-ttu-id="dc252-114">若要以编程方式创建的 Outlook 样式用户界面</span><span class="sxs-lookup"><span data-stu-id="dc252-114">To create an Outlook-style user interface programmatically</span></span>  
  
1. <span data-ttu-id="dc252-115">在窗体中声明每个控件组成用户界面。</span><span class="sxs-lookup"><span data-stu-id="dc252-115">Within a form, declare each control that comprises your user interface.</span></span> <span data-ttu-id="dc252-116">对于此示例中，使用<xref:System.Windows.Forms.TreeView>， <xref:System.Windows.Forms.ListView>， <xref:System.Windows.Forms.SplitContainer>，和<xref:System.Windows.Forms.RichTextBox>控件来模拟 Microsoft Outlook 用户界面。</span><span class="sxs-lookup"><span data-stu-id="dc252-116">For this example, use the <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, and <xref:System.Windows.Forms.RichTextBox> controls to mimic the Microsoft Outlook user interface.</span></span>  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
    ```  
  
2. <span data-ttu-id="dc252-117">创建一个定义用户界面的过程。</span><span class="sxs-lookup"><span data-stu-id="dc252-117">Create a procedure that defines your user interface.</span></span> <span data-ttu-id="dc252-118">下面的代码，以便窗体将类似于 Microsoft Outlook 中的用户界面设置的属性。</span><span class="sxs-lookup"><span data-stu-id="dc252-118">The following code sets the properties so that the form will resemble the user interface in Microsoft Outlook.</span></span> <span data-ttu-id="dc252-119">但是，通过使用其他控件，或以不同的方式将它们停靠在一起，将只需创建其他同样灵活的用户界面一样简单。</span><span class="sxs-lookup"><span data-stu-id="dc252-119">However, by using other controls or docking them differently, it is just as easy to create other user interfaces that are equally flexible.</span></span>  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
    ```  
  
3. <span data-ttu-id="dc252-120">在 Visual Basic 中，添加对刚刚创建的过程的调用`New()`过程。</span><span class="sxs-lookup"><span data-stu-id="dc252-120">In Visual Basic, add a call to the procedure you just created in the `New()` procedure.</span></span> <span data-ttu-id="dc252-121">视觉对象中C#，将这行代码添加到窗体类的构造函数。</span><span class="sxs-lookup"><span data-stu-id="dc252-121">In Visual C#, add this line of code to the constructor for the form class.</span></span>  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="dc252-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc252-122">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="dc252-123">SplitContainer 控件</span><span class="sxs-lookup"><span data-stu-id="dc252-123">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
- [<span data-ttu-id="dc252-124">如何：用 Windows 窗体使用设计器创建多窗格用户界面</span><span class="sxs-lookup"><span data-stu-id="dc252-124">How to: Create a Multipane User Interface with Windows Forms Using the Designer</span></span>](create-a-multipane-user-interface-with-wf-using-the-designer.md)
