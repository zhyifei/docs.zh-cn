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
ms.openlocfilehash: 1b803a93f865eaa4db6751187213c4bb01d2a5ee
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44065196"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="df404-102">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="df404-102">How to: Add Controls to Windows Forms</span></span>
<span data-ttu-id="df404-103">大多数窗体旨在通过将控件添加到窗体的面，用于定义用户界面 (UI) 中。</span><span class="sxs-lookup"><span data-stu-id="df404-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="df404-104">一个*控制*是用于显示信息或接受用户输入的窗体上的组件。</span><span class="sxs-lookup"><span data-stu-id="df404-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="df404-105">有关控件的详细信息，请参阅[Windows 窗体控件](../../../../docs/framework/winforms/controls/index.md)。</span><span class="sxs-lookup"><span data-stu-id="df404-105">For more information about controls, see [Windows Forms Controls](../../../../docs/framework/winforms/controls/index.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="df404-106">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="df404-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="df404-107">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="df404-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="df404-108">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="df404-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="df404-109">若要绘制的控件在窗体上</span><span class="sxs-lookup"><span data-stu-id="df404-109">To draw a control on a form</span></span>  
  
1.  <span data-ttu-id="df404-110">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="df404-110">Open the form.</span></span> <span data-ttu-id="df404-111">有关详细信息，请参阅[如何： 在设计器中显示 Windows 窗体](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。</span><span class="sxs-lookup"><span data-stu-id="df404-111">For more information, see [How to: Display Windows Forms in the Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="df404-112">在中**工具箱**，单击你想要添加到窗体的控件。</span><span class="sxs-lookup"><span data-stu-id="df404-112">In the **Toolbox**, click the control you want to add to your form.</span></span>  
  
3.  <span data-ttu-id="df404-113">在表单上，单击希望要定位，控件的左上角的位置和拖动到希望要定位的控件的右下角。</span><span class="sxs-lookup"><span data-stu-id="df404-113">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>  
  
     <span data-ttu-id="df404-114">该控件添加到具有指定的位置和大小的窗体。</span><span class="sxs-lookup"><span data-stu-id="df404-114">The control is added to the form with the specified location and size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="df404-115">每个控件具有定义的默认大小。</span><span class="sxs-lookup"><span data-stu-id="df404-115">Each control has a default size defined.</span></span> <span data-ttu-id="df404-116">可以向控件的默认大小在窗体添加控件，通过将其从**工具箱**到窗体。</span><span class="sxs-lookup"><span data-stu-id="df404-116">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>  
  
### <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="df404-117">若要将控件拖动到窗体</span><span class="sxs-lookup"><span data-stu-id="df404-117">To drag a control to a form</span></span>  
  
1.  <span data-ttu-id="df404-118">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="df404-118">Open the form.</span></span> <span data-ttu-id="df404-119">有关详细信息，请参阅[如何： 在设计器中显示 Windows 窗体](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。</span><span class="sxs-lookup"><span data-stu-id="df404-119">For more information, see [How to: Display Windows Forms in the Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="df404-120">在中**工具箱**，单击所需的控件并将其拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="df404-120">In the **Toolbox**, click the control you want and drag it to your form.</span></span>  
  
     <span data-ttu-id="df404-121">该控件添加到窗体，请在其默认大小的指定位置。</span><span class="sxs-lookup"><span data-stu-id="df404-121">The control is added to the form at the specified location in its default size.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="df404-122">你可以双击中的控件**工具箱**将其添加到其默认大小中的窗体的左上角。</span><span class="sxs-lookup"><span data-stu-id="df404-122">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>  
  
     <span data-ttu-id="df404-123">您可以在运行时动态地将控件添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="df404-123">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="df404-124">在下面的代码示例中，<xref:System.Windows.Forms.TextBox>控件将被添加到窗体时<xref:System.Windows.Forms.Button>单击控件。</span><span class="sxs-lookup"><span data-stu-id="df404-124">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="df404-125">下面的过程需要一个具有窗体是否存在**按钮**控件， `Button1`、 已放置在其上。</span><span class="sxs-lookup"><span data-stu-id="df404-125">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>  
  
### <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="df404-126">若要以编程方式向窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="df404-126">To add a control to a form programmatically</span></span>  
  
1.  <span data-ttu-id="df404-127">处理按钮的方法中`Click`事件在窗体的类，类似于以下内容，以添加到您的控制变量的引用插入代码中设置控件的`Location`，并添加控件。</span><span class="sxs-lookup"><span data-stu-id="df404-127">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>  
  
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
    >  <span data-ttu-id="df404-128">此外可以添加代码以初始化控件的其他属性。</span><span class="sxs-lookup"><span data-stu-id="df404-128">You can also add code to initialize other properties of the control.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="df404-129">可能会通过引用恶意公开您的本地计算机通过网络安全风险`UserControl`。</span><span class="sxs-lookup"><span data-stu-id="df404-129">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="df404-130">这只能在恶意的用户创建一个具有破坏性的自定义控件，跟您错误地将其添加到你的项目的情况下一个问题。</span><span class="sxs-lookup"><span data-stu-id="df404-130">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df404-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="df404-131">See Also</span></span>  
 [<span data-ttu-id="df404-132">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="df404-132">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="df404-133">在 Windows 窗体上排列控件</span><span class="sxs-lookup"><span data-stu-id="df404-133">Arranging Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/arranging-controls-on-windows-forms.md)  
 [<span data-ttu-id="df404-134">如何：重设 Windows 窗体上控件的大小</span><span class="sxs-lookup"><span data-stu-id="df404-134">How to: Resize Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-resize-controls-on-windows-forms.md)  
 [<span data-ttu-id="df404-135">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="df404-135">How to: Set the Text Displayed by a Windows Forms Control</span></span>](../../../../docs/framework/winforms/controls/how-to-set-the-text-displayed-by-a-windows-forms-control.md)  
 [<span data-ttu-id="df404-136">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="df404-136">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)
