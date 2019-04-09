---
title: 如何：从现有 Windows 窗体控件继承
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- inheritance [Windows Forms], Windows Forms custom controls
- custom controls [Windows Forms], inheritance
ms.assetid: 1e1fc8ea-c615-4cf0-a356-16d6df7444ab
ms.openlocfilehash: 90008b00c95906ba43364c5a4ae3f85d9fdf0e22
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59087867"
---
# <a name="how-to-inherit-from-existing-windows-forms-controls"></a><span data-ttu-id="bd6d5-102">如何：从现有 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="bd6d5-102">How to: Inherit from Existing Windows Forms Controls</span></span>
<span data-ttu-id="bd6d5-103">如果想要扩展现有控件的功能，可以通过继承创建一个派生自现有控件的控件。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-103">If you want to extend the functionality of an existing control, you can create a control derived from an existing control through inheritance.</span></span> <span data-ttu-id="bd6d5-104">从现有控件继承时，将继承该控件的的所有功能和可视属性。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-104">When inheriting from an existing control, you inherit all of the functionality and visual properties of that control.</span></span> <span data-ttu-id="bd6d5-105">例如，如果已创建的控件继承自<xref:System.Windows.Forms.Button>、 新控件看起来和 act 完全一样标准<xref:System.Windows.Forms.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-105">For example, if you were creating a control that inherited from <xref:System.Windows.Forms.Button>, your new control would look and act exactly like a standard <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="bd6d5-106">然后可以通过实现自定义方法和属性来扩展或修改新控件的功能。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-106">You could then extend or modify the functionality of your new control through the implementation of custom methods and properties.</span></span> <span data-ttu-id="bd6d5-107">在某些控件中，您还可以更改继承的控件的可视外观通过重写其<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-107">In some controls, you can also change the visual appearance of your inherited control by overriding its <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd6d5-108">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-108">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="bd6d5-109">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-109">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="bd6d5-110">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-110">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-an-inherited-control"></a><span data-ttu-id="bd6d5-111">创建继承的控件</span><span class="sxs-lookup"><span data-stu-id="bd6d5-111">To create an inherited control</span></span>  
  
1.  <span data-ttu-id="bd6d5-112">创建新的 **Windows 窗体应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-112">Create a new **Windows Forms Application** project.</span></span>  
  
2.  <span data-ttu-id="bd6d5-113">从“项目”菜单中选择“添加新项”。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-113">From the **Project** menu, choose **Add New Item**.</span></span>  
  
     <span data-ttu-id="bd6d5-114">“添加新项”对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-114">The **Add New Item** dialog box appears.</span></span>  
  
3.  <span data-ttu-id="bd6d5-115">在“添加新项”对话框中，双击“自定义控件”。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-115">In the **Add New Item** dialog box, double-click **Custom Control**.</span></span>  
  
     <span data-ttu-id="bd6d5-116">一个新的自定义控件将被添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-116">A new custom control is added to your project.</span></span>  
  
4.  <span data-ttu-id="bd6d5-117">如果使用的是 Visual Basic，则在“解决方案资源管理器”的顶部单击“显示所有文件”。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-117">If you using Visual Basic, at the top of **Solution Explorer**, click **Show All Files**.</span></span> <span data-ttu-id="bd6d5-118">展开 CustomControl1.vb，然后在“代码编辑器”中打开 CustomControl1.Designer.vb。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-118">Expand CustomControl1.vb and then open CustomControl1.Designer.vb in the Code Editor.</span></span>  
  
5.  <span data-ttu-id="bd6d5-119">如果使用的 C#，则在“代码编辑器”中打开CustomControl1.cs。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-119">If you are using C#, open CustomControl1.cs in the Code Editor.</span></span>  
  
6.  <span data-ttu-id="bd6d5-120">找到的类声明，该类继承自<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-120">Locate the class declaration, which inherits from <xref:System.Windows.Forms.Control>.</span></span>  
  
7.  <span data-ttu-id="bd6d5-121">将基类更改为要从中继承的控件。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-121">Change the base class to the control that you want to inherit from.</span></span>  
  
     <span data-ttu-id="bd6d5-122">例如，如果你想要从继承<xref:System.Windows.Forms.Button>，将类声明更改为以下：</span><span class="sxs-lookup"><span data-stu-id="bd6d5-122">For example, if you want to inherit from <xref:System.Windows.Forms.Button>, change the class declaration to the following:</span></span>  
  
    ```vb  
    Partial Class CustomControl1  
        Inherits System.Windows.Forms.Button  
    ```  
  
    ```csharp  
    public partial class CustomControl1 : System.Windows.Forms.Button  
    ```  
  
8.  <span data-ttu-id="bd6d5-123">如果使用的是 Visual Basic，则保存并关闭 CustomControl1.Designer.vb。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-123">If you are using Visual Basic, save and close CustomControl1.Designer.vb.</span></span> <span data-ttu-id="bd6d5-124">在“代码编辑器”中打开 CustomControl1.vb。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-124">Open CustomControl1.vb in the Code Editor.</span></span>  
  
9. <span data-ttu-id="bd6d5-125">实现控件将纳入的任何自定义方法或属性。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-125">Implement any custom methods or properties that your control will incorporate.</span></span>  
  
10. <span data-ttu-id="bd6d5-126">如果你想要修改您的控件的图形外观，重写<xref:System.Windows.Forms.Control.OnPaint%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-126">If you want to modify the graphical appearance of your control, override the <xref:System.Windows.Forms.Control.OnPaint%2A> method.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="bd6d5-127">重写<xref:System.Windows.Forms.Control.OnPaint%2A>将不允许您修改所有控件的外观。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-127">Overriding <xref:System.Windows.Forms.Control.OnPaint%2A> will not allow you to modify the appearance of all controls.</span></span> <span data-ttu-id="bd6d5-128">所有由 Windows 完成其绘制这些控件 (例如， <xref:System.Windows.Forms.TextBox>) 永远不会调用其<xref:System.Windows.Forms.Control.OnPaint%2A>方法，因此将永远不会使用自定义代码。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-128">Those controls that have all of their painting done by Windows (for example, <xref:System.Windows.Forms.TextBox>) never call their <xref:System.Windows.Forms.Control.OnPaint%2A> method, and thus will never use the custom code.</span></span> <span data-ttu-id="bd6d5-129">你想要修改以查看是否特定控件的帮助文档，请参阅<xref:System.Windows.Forms.Control.OnPaint%2A>方法不可用。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-129">Refer to the Help documentation for the particular control you want to modify to see if the <xref:System.Windows.Forms.Control.OnPaint%2A> method is available.</span></span> <span data-ttu-id="bd6d5-130">有关所有 Windows 窗体控件的列表，请参阅[在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-130">For a list of all the Windows Form Controls, see [Controls to Use on Windows Forms](controls-to-use-on-windows-forms.md).</span></span> <span data-ttu-id="bd6d5-131">如果控件不具有<xref:System.Windows.Forms.Control.OnPaint%2A>列为成员方法，您不能通过重写此方法更改其外观。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-131">If a control does not have <xref:System.Windows.Forms.Control.OnPaint%2A> listed as a member method, you cannot alter its appearance by overriding this method.</span></span> <span data-ttu-id="bd6d5-132">有关自定义绘制的详细信息，请参阅[自定义控件的绘制和呈现](custom-control-painting-and-rendering.md)。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-132">For more information about custom painting, see [Custom Control Painting and Rendering](custom-control-painting-and-rendering.md).</span></span>  
  
    ```vb  
    Protected Overrides Sub OnPaint(ByVal e As _  
       System.Windows.Forms.PaintEventArgs)  
       MyBase.OnPaint(e)  
       ' Insert code to do custom painting.   
       ' If you want to completely change the appearance of your control,  
       ' do not call MyBase.OnPaint(e).  
    End Sub  
    ```  
  
    ```csharp  
    protected override void OnPaint(PaintEventArgs pe)  
    {  
       base.OnPaint(pe);  
       // Insert code to do custom painting.  
       // If you want to completely change the appearance of your control,  
       // do not call base.OnPaint(pe).  
    }  
    ```  
  
11. <span data-ttu-id="bd6d5-133">保存并测试控件。</span><span class="sxs-lookup"><span data-stu-id="bd6d5-133">Save and test your control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd6d5-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd6d5-134">See also</span></span>

- [<span data-ttu-id="bd6d5-135">各种自定义控件</span><span class="sxs-lookup"><span data-stu-id="bd6d5-135">Varieties of Custom Controls</span></span>](varieties-of-custom-controls.md)
- [<span data-ttu-id="bd6d5-136">如何：从 Control 类继承</span><span class="sxs-lookup"><span data-stu-id="bd6d5-136">How to: Inherit from the Control Class</span></span>](how-to-inherit-from-the-control-class.md)
- [<span data-ttu-id="bd6d5-137">如何：从 UserControl 类继承</span><span class="sxs-lookup"><span data-stu-id="bd6d5-137">How to: Inherit from the UserControl Class</span></span>](how-to-inherit-from-the-usercontrol-class.md)
- [<span data-ttu-id="bd6d5-138">如何：创作 Windows 窗体的控件</span><span class="sxs-lookup"><span data-stu-id="bd6d5-138">How to: Author Controls for Windows Forms</span></span>](how-to-author-controls-for-windows-forms.md)
- [<span data-ttu-id="bd6d5-139">有关 Visual Basic 中继承的事件处理程序的疑难解答</span><span class="sxs-lookup"><span data-stu-id="bd6d5-139">Troubleshooting Inherited Event Handlers in Visual Basic</span></span>](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
- [<span data-ttu-id="bd6d5-140">演练：使用 Visual Basic 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="bd6d5-140">Walkthrough: Inheriting from a Windows Forms Control with Visual Basic</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-basic.md)
- [<span data-ttu-id="bd6d5-141">演练：使用 Visual C# 从 Windows 窗体控件继承</span><span class="sxs-lookup"><span data-stu-id="bd6d5-141">Walkthrough: Inheriting from a Windows Forms Control with Visual C#</span></span>](walkthrough-inheriting-from-a-windows-forms-control-with-visual-csharp.md)
