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
ms.openlocfilehash: bfe9449ecc862c361719d27dba2f5ed9af563957
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046054"
---
# <a name="how-to-add-controls-to-windows-forms"></a><span data-ttu-id="74ce6-102">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="74ce6-102">How to: Add Controls to Windows Forms</span></span>

<span data-ttu-id="74ce6-103">大多数窗体都是通过将控件添加到窗体的图面来定义用户界面 (UI) 而设计的。</span><span class="sxs-lookup"><span data-stu-id="74ce6-103">Most forms are designed by adding controls to the surface of the form to define a user interface (UI).</span></span> <span data-ttu-id="74ce6-104">*控件*是窗体上用于显示信息或接受用户输入的组件。</span><span class="sxs-lookup"><span data-stu-id="74ce6-104">A *control* is a component on a form used to display information or accept user input.</span></span> <span data-ttu-id="74ce6-105">有关控件的详细信息, 请参阅[Windows 窗体控件](index.md)。</span><span class="sxs-lookup"><span data-stu-id="74ce6-105">For more information about controls, see [Windows Forms Controls](index.md).</span></span>

## <a name="to-draw-a-control-on-a-form"></a><span data-ttu-id="74ce6-106">在窗体上绘制控件</span><span class="sxs-lookup"><span data-stu-id="74ce6-106">To draw a control on a form</span></span>

1. <span data-ttu-id="74ce6-107">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="74ce6-107">Open the form.</span></span> <span data-ttu-id="74ce6-108">有关详细信息，请参阅[如何：在设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))中显示 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="74ce6-108">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="74ce6-109">在 "**工具箱**" 中, 单击要添加到窗体中的控件。</span><span class="sxs-lookup"><span data-stu-id="74ce6-109">In the **Toolbox**, click the control you want to add to your form.</span></span>

3. <span data-ttu-id="74ce6-110">在窗体上, 单击要放置控件的左上角的位置, 然后拖动到控件右下角所处的位置。</span><span class="sxs-lookup"><span data-stu-id="74ce6-110">On the form, click where you want the upper-left corner of the control to be located, and drag to where you want the lower-right corner of the control to be located.</span></span>

    <span data-ttu-id="74ce6-111">控件将添加到具有指定位置和大小的窗体中。</span><span class="sxs-lookup"><span data-stu-id="74ce6-111">The control is added to the form with the specified location and size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74ce6-112">每个控件都定义了默认大小。</span><span class="sxs-lookup"><span data-stu-id="74ce6-112">Each control has a default size defined.</span></span> <span data-ttu-id="74ce6-113">您可以通过将控件从 "**工具箱**" 拖到窗体上, 将控件添加到控件的默认大小。</span><span class="sxs-lookup"><span data-stu-id="74ce6-113">You can add a control to your form in the control's default size by dragging it from the **Toolbox** to the form.</span></span>

## <a name="to-drag-a-control-to-a-form"></a><span data-ttu-id="74ce6-114">将控件拖动到窗体</span><span class="sxs-lookup"><span data-stu-id="74ce6-114">To drag a control to a form</span></span>

1. <span data-ttu-id="74ce6-115">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="74ce6-115">Open the form.</span></span> <span data-ttu-id="74ce6-116">有关详细信息，请参阅[如何：在设计器](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))中显示 Windows 窗体。</span><span class="sxs-lookup"><span data-stu-id="74ce6-116">For more information, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="74ce6-117">在 "**工具箱**" 中, 单击所需的控件并将其拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="74ce6-117">In the **Toolbox**, click the control you want and drag it to your form.</span></span>

    <span data-ttu-id="74ce6-118">控件将添加到窗体中指定位置的默认大小。</span><span class="sxs-lookup"><span data-stu-id="74ce6-118">The control is added to the form at the specified location in its default size.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74ce6-119">您可以双击**工具箱**中的控件, 将其以其默认大小添加到窗体的左上角。</span><span class="sxs-lookup"><span data-stu-id="74ce6-119">You can double-click a control in the **Toolbox** to add it to the upper-left corner of the form in its default size.</span></span>

    <span data-ttu-id="74ce6-120">您还可以在运行时将控件动态添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="74ce6-120">You can also add controls dynamically to a form at run time.</span></span> <span data-ttu-id="74ce6-121">在下面的代码示例中, <xref:System.Windows.Forms.TextBox> <xref:System.Windows.Forms.Button>当单击控件时, 控件将添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="74ce6-121">In the following code example, a <xref:System.Windows.Forms.TextBox> control will be added to the form when a <xref:System.Windows.Forms.Button> control is clicked.</span></span>

    > [!NOTE]
    > <span data-ttu-id="74ce6-122">下面的过程要求存在具有**按钮**控件`Button1`的窗体。</span><span class="sxs-lookup"><span data-stu-id="74ce6-122">The following procedure requires the existence of a form with a **Button** control, `Button1`, already placed on it.</span></span>

## <a name="to-add-a-control-to-a-form-programmatically"></a><span data-ttu-id="74ce6-123">以编程方式将控件添加到窗体</span><span class="sxs-lookup"><span data-stu-id="74ce6-123">To add a control to a form programmatically</span></span>

1. <span data-ttu-id="74ce6-124">在处理窗体的类中的`Click`按钮事件的方法中, 插入类似于下面的代码以添加对控件变量的引用、设置控件的`Location`, 然后添加控件。</span><span class="sxs-lookup"><span data-stu-id="74ce6-124">In the method that handles the button's `Click` event within your form's class, insert code similar to the following to add a reference to your control variable, set the control's `Location`, and add the control.</span></span>

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
    > <span data-ttu-id="74ce6-125">你还可以添加代码以初始化控件的其他属性。</span><span class="sxs-lookup"><span data-stu-id="74ce6-125">You can also add code to initialize other properties of the control.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="74ce6-126">你可能会通过引用恶意`UserControl`网络来使你的本地计算机遭受网络安全风险。</span><span class="sxs-lookup"><span data-stu-id="74ce6-126">You might expose your local computer to a security risk through the network by referencing a malicious `UserControl`.</span></span> <span data-ttu-id="74ce6-127">这只是在恶意用户创建有破坏性的自定义控件时, 然后错误地将其添加到项目中时需要注意的问题。</span><span class="sxs-lookup"><span data-stu-id="74ce6-127">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="74ce6-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="74ce6-128">See also</span></span>

- [<span data-ttu-id="74ce6-129">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="74ce6-129">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="74ce6-130">如何：Windows 窗体上的调整控件大小</span><span class="sxs-lookup"><span data-stu-id="74ce6-130">How to: Resize Controls on Windows Forms</span></span>](how-to-resize-controls-on-windows-forms.md)
- [<span data-ttu-id="74ce6-131">如何：设置 Windows 窗体控件显示的文本</span><span class="sxs-lookup"><span data-stu-id="74ce6-131">How to: Set the Text Displayed by a Windows Forms Control</span></span>](how-to-set-the-text-displayed-by-a-windows-forms-control.md)
- [<span data-ttu-id="74ce6-132">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="74ce6-132">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
