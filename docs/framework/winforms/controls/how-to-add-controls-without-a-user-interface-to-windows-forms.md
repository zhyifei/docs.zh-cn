---
title: 如何：向 Windows 窗体添加无用户界面的控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
ms.openlocfilehash: 9458fc7f3344a5692581485a0e5bd462e45551d9
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43881822"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="dc89a-102">如何：向 Windows 窗体添加无用户界面的控件</span><span class="sxs-lookup"><span data-stu-id="dc89a-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="dc89a-103">非可视控件 （或组件） 提供了与你的应用程序的功能。</span><span class="sxs-lookup"><span data-stu-id="dc89a-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="dc89a-104">不同于其他控件组件不向用户提供用户界面，因此不需要在 Windows 窗体设计器图面上显示。</span><span class="sxs-lookup"><span data-stu-id="dc89a-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="dc89a-105">当一个组件添加到窗体时，Windows 窗体设计器在其中显示所有组件的窗体的底部显示可调整大小的送纸器。</span><span class="sxs-lookup"><span data-stu-id="dc89a-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="dc89a-106">控件添加到组件栏后，你可以选择的组件，并设置其属性，就像任何其他控件在窗体上。</span><span class="sxs-lookup"><span data-stu-id="dc89a-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dc89a-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="dc89a-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="dc89a-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="dc89a-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="dc89a-109">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="dc89a-109">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="dc89a-110">若要将组件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="dc89a-110">To add a component to a Windows Form</span></span>  
  
1.  <span data-ttu-id="dc89a-111">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="dc89a-111">Open the form.</span></span> <span data-ttu-id="dc89a-112">有关详细信息，请参阅[如何： 在设计器中显示 Windows 窗体](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。</span><span class="sxs-lookup"><span data-stu-id="dc89a-112">For details, see [How to: Display Windows Forms in the Designer](https://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="dc89a-113">在中**工具箱**，单击一个组件，并将其拖动到窗体。</span><span class="sxs-lookup"><span data-stu-id="dc89a-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="dc89a-114">此组件将出现在组件栏中。</span><span class="sxs-lookup"><span data-stu-id="dc89a-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="dc89a-115">此外，组件可以在运行时添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="dc89a-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="dc89a-116">这是一种常见方案，特别是因为组件不具有直观的表达与具有用户界面的控件不同。</span><span class="sxs-lookup"><span data-stu-id="dc89a-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="dc89a-117">在以下示例中，<xref:System.Windows.Forms.Timer>在运行时添加组件。</span><span class="sxs-lookup"><span data-stu-id="dc89a-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="dc89a-118">(请注意，Visual Studio 包含多种不同的计时器; 在这种情况下，使用 Windows 窗体<xref:System.Windows.Forms.Timer>组件。</span><span class="sxs-lookup"><span data-stu-id="dc89a-118">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="dc89a-119">有关在 Visual Studio 中不同的计时器的详细信息，请参阅[基于服务器的计时器简介](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。)</span><span class="sxs-lookup"><span data-stu-id="dc89a-119">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="dc89a-120">组件通常具有必须为有效运行该组件设置的特定于控件的属性。</span><span class="sxs-lookup"><span data-stu-id="dc89a-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="dc89a-121">情况下<xref:System.Windows.Forms.Timer>下方的组件，您将设置`Interval`属性。</span><span class="sxs-lookup"><span data-stu-id="dc89a-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="dc89a-122">请确保，在将组件添加到项目中，您设置属性，该组件必需的。</span><span class="sxs-lookup"><span data-stu-id="dc89a-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="dc89a-123">若要以编程方式向 Windows 窗体添加组件</span><span class="sxs-lookup"><span data-stu-id="dc89a-123">To add a component to a Windows Form programmatically</span></span>  
  
1.  <span data-ttu-id="dc89a-124">创建的实例<xref:System.Windows.Forms.Timer>代码中的类。</span><span class="sxs-lookup"><span data-stu-id="dc89a-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2.  <span data-ttu-id="dc89a-125">设置`Interval`属性，以确定计时器的滴答之间的时间。</span><span class="sxs-lookup"><span data-stu-id="dc89a-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3.  <span data-ttu-id="dc89a-126">配置任何其他必要的属性，为您的组件。</span><span class="sxs-lookup"><span data-stu-id="dc89a-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="dc89a-127">下面的代码演示如何创建<xref:System.Windows.Forms.Timer>使用其`Interval`属性集。</span><span class="sxs-lookup"><span data-stu-id="dc89a-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
    ```vb  
    Public Sub CreateTimer()  
       Dim timerKeepTrack As New System.Windows.Forms.Timer  
       timerKeepTrack.Interval = 1000  
    End Sub  
    ```  
  
    ```csharp  
    public void createTimer()  
    {  
       System.Windows.Forms.Timer timerKeepTrack = new  
           System.Windows.Forms.Timer();  
       timerKeepTrack.Interval = 1000;  
    }  
    ```  
  
    ```cpp  
    public:  
       void createTimer()  
       {  
          System::Windows::Forms::Timer^ timerKeepTrack = gcnew  
             System::Windows::Forms::Timer();  
          timerKeepTrack->Interval = 1000;  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="dc89a-128">通过引用恶意 UserControl，可能会使您的本地计算机通过网络安全风险。</span><span class="sxs-lookup"><span data-stu-id="dc89a-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="dc89a-129">这只能在恶意的用户创建一个具有破坏性的自定义控件，跟您错误地将其添加到你的项目的情况下一个问题。</span><span class="sxs-lookup"><span data-stu-id="dc89a-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc89a-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="dc89a-130">See Also</span></span>  
 [<span data-ttu-id="dc89a-131">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="dc89a-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="dc89a-132">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="dc89a-132">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="dc89a-133">如何：向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="dc89a-133">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="dc89a-134">如何：在 Windows 窗体之间复制控件</span><span class="sxs-lookup"><span data-stu-id="dc89a-134">How to: Copy Controls Between Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [<span data-ttu-id="dc89a-135">将控件置于 Windows 窗体上</span><span class="sxs-lookup"><span data-stu-id="dc89a-135">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="dc89a-136">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="dc89a-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="dc89a-137">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="dc89a-137">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="dc89a-138">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="dc89a-138">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
