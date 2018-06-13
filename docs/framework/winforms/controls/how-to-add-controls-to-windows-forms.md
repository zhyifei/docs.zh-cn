---
title: 如何：向 Windows 窗体添加控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, adding to form
- controls [Windows Forms], adding
ms.assetid: 2af86001-9d62-4154-87fb-66db2c3cd9fd
ms.openlocfilehash: 2dd048fb074d1ec5bb7bc0a67f196d5d51281545
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33528472"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="aff75-102">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="aff75-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="aff75-103">大多数窗体旨在通过将控件添加到窗体表面，以定义用户界面 (UI) 中。</span><span class="sxs-lookup"><span data-stu-id="aff75-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="aff75-104">A*控件*是用于显示信息或接受用户输入的窗体上的组件。</span><span class="sxs-lookup"><span data-stu-id="aff75-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="aff75-105">有关控件的详细信息，请参阅[Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="aff75-105">For more information about controls, see [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aff75-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="aff75-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="aff75-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="aff75-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="aff75-108">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="aff75-108">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="aff75-109">若要绘制窗体上控件</span><span class="sxs-lookup"><span data-stu-id="aff75-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="aff75-110">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="aff75-110">Open the form.</span></span> <span data-ttu-id="aff75-111">有关详细信息，请参阅[如何： 显示 Windows 窗体设计器中](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。</span><span class="sxs-lookup"><span data-stu-id="aff75-111">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="aff75-112">在**工具箱**，单击你想要添加到你的窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="aff75-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="aff75-113">在表单上，单击希望要位于，该控件的左上角拖到所需的控件，使其位于右下角的位置。</span><span class="sxs-lookup"><span data-stu-id="aff75-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="aff75-114">该控件添加到具有指定的位置和大小的窗体。</span><span class="sxs-lookup"><span data-stu-id="aff75-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aff75-115">每个控件具有定义的默认大小。</span><span class="sxs-lookup"><span data-stu-id="aff75-115">Each control has a default size defined.</span></span> <span data-ttu-id="aff75-116">你可以向窗体控件的默认大小添加控件，通过拖动从**工具箱**到窗体。</span><span class="sxs-lookup"><span data-stu-id="aff75-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="aff75-117">若要将控件拖动到窗体</span><span class="sxs-lookup"><span data-stu-id="aff75-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="aff75-118">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="aff75-118">Open the form.</span></span> <span data-ttu-id="aff75-119">有关详细信息，请参阅[如何： 显示 Windows 窗体设计器中](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。</span><span class="sxs-lookup"><span data-stu-id="aff75-119">For more information, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="aff75-120">在**工具箱**，单击所需的控件并将其拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="aff75-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="aff75-121">该控件添加到窗体中在其默认大小中的指定位置。</span><span class="sxs-lookup"><span data-stu-id="aff75-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aff75-122">你可以双击中的控件**工具箱**将其添加到在其默认大小的窗体的左上角。</span><span class="sxs-lookup"><span data-stu-id="aff75-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="aff75-123">你可以在运行时动态将控件添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="aff75-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="aff75-124">在下面的代码示例中，<xref:System.Windows.Forms.TextBox>控件将被添加到窗体时<xref:System.Windows.Forms.Button>控件被单击。</span><span class="sxs-lookup"><span data-stu-id="aff75-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="aff75-125">以下过程，则需要存在带有的窗体**按钮**控件， `Button1`、 已放置在其上。</span><span class="sxs-lookup"><span data-stu-id="aff75-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="aff75-126">以编程方式添加到窗体控件</span><span class="sxs-lookup"><span data-stu-id="aff75-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="aff75-127">处理按钮的方法中`Click`设置控件的窗体的类，类似于以下要添加到您的控制变量的引用插入代码中的事件`Location`，然后添加该控件。</span><span class="sxs-lookup"><span data-stu-id="aff75-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles Button1.Click  
       Dim MyText As New TextBox()  
       MyText.Location = New Point(25, 25)  
       Me.Controls.Add(MyText)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)   
    {  
       TextBox myText = new TextBox();  
       myText.Location = new Point(25,25);  
       this.Controls.Add (myText);  
    }  
    ```  
  
    ```cpp  
    private:  
      System::Void button1_Click(System::Object ^  sender,  
        System::EventArgs ^  e)  
      {  
        TextBox ^ myText = gcnew TextBox();  
        myText->Location = Point(25,25);  
        this->Controls->Add(myText);  
      }  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="aff75-128">你还可以添加代码以初始化控件的其他属性。</span><span class="sxs-lookup"><span data-stu-id="aff75-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="aff75-129">通过引用了恶意，您可能会公开您的本地计算机通过网络安全风险`UserControl`。</span><span class="sxs-lookup"><span data-stu-id="aff75-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="aff75-130">这仅会在恶意的用户创建破坏性的自定义控件，跟你错误地将其添加到你的项目的情况下是问题。</span><span class="sxs-lookup"><span data-stu-id="aff75-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aff75-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="aff75-131">See Also</span></span>  
 [<span data-ttu-id="aff75-132">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="aff75-132">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="aff75-133">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="aff75-133">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="aff75-134">如何：重设 Windows 窗体上控件的大小</span><span class="sxs-lookup"><span data-stu-id="aff75-134">How to: Resize Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [<span data-ttu-id="aff75-135">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="aff75-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="aff75-136">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="aff75-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
