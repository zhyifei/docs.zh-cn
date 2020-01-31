---
title: 사용자 인터페이스 없이 컨트롤 추가
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
ms.openlocfilehash: 43f13b4f009fcd6e5d82fa2c00113a77d48877b6
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744755"
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="5509d-102">방법: Windows Forms에 사용자 인터페이스가 없는 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="5509d-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>

<span data-ttu-id="5509d-103">非可视控件（或组件）为应用程序提供功能。</span><span class="sxs-lookup"><span data-stu-id="5509d-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="5509d-104">与其他控件不同，组件并不为用户提供用户界面，因此不需要在 Windows 窗体设计器表面上显示。</span><span class="sxs-lookup"><span data-stu-id="5509d-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="5509d-105">将组件添加到窗体时，Windows 窗体设计器将在显示所有组件的窗体底部显示可调整大小的托盘。</span><span class="sxs-lookup"><span data-stu-id="5509d-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="5509d-106">将控件添加到组件栏后，您可以选择该组件并设置其属性，就像对窗体上的任何其他控件一样。</span><span class="sxs-lookup"><span data-stu-id="5509d-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>

## <a name="add-a-component-to-a-windows-form"></a><span data-ttu-id="5509d-107">将组件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="5509d-107">Add a component to a Windows Form</span></span>

1. <span data-ttu-id="5509d-108">在 Visual Studio 中打开窗体。</span><span class="sxs-lookup"><span data-stu-id="5509d-108">Open the form in Visual Studio.</span></span> <span data-ttu-id="5509d-109">有关详细信息，请参阅[如何：在设计器中显示 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="5509d-109">For details, see [How to: Display Windows Forms in the Designer](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/w5yd62ts(v=vs.100)).</span></span>

2. <span data-ttu-id="5509d-110">在 "**工具箱**" 中，单击某个组件，然后将其拖到窗体上。</span><span class="sxs-lookup"><span data-stu-id="5509d-110">In the **Toolbox**, click a component and drag it to your form.</span></span>

     <span data-ttu-id="5509d-111">组件将出现在组件栏中。</span><span class="sxs-lookup"><span data-stu-id="5509d-111">Your component appears in the component tray.</span></span>

<span data-ttu-id="5509d-112">此外，可以在运行时将组件添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="5509d-112">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="5509d-113">这是一个常见方案，尤其是因为组件没有可视表达式，这不同于具有用户界面的控件。</span><span class="sxs-lookup"><span data-stu-id="5509d-113">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="5509d-114">在下面的示例中，将在运行时添加 <xref:System.Windows.Forms.Timer> 组件。</span><span class="sxs-lookup"><span data-stu-id="5509d-114">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="5509d-115">（请注意，Visual Studio 包含许多不同的计时器; 在这种情况下，请使用 Windows 窗体 <xref:System.Windows.Forms.Timer> 组件。</span><span class="sxs-lookup"><span data-stu-id="5509d-115">(Note that Visual Studio contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="5509d-116">有关 Visual Studio 中不同计时器的详细信息，请参阅[基于服务器的计时器简介](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90))。）</span><span class="sxs-lookup"><span data-stu-id="5509d-116">For more information about the different timers in Visual Studio, see [Introduction to Server-Based Timers](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/tb9yt5e6(v=vs.90)).)</span></span>

> [!CAUTION]
> <span data-ttu-id="5509d-117">组件通常具有特定于控件的属性，必须对其进行设置，组件才能有效工作。</span><span class="sxs-lookup"><span data-stu-id="5509d-117">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="5509d-118">对于下面的 <xref:System.Windows.Forms.Timer> 组件，将设置 `Interval` 属性。</span><span class="sxs-lookup"><span data-stu-id="5509d-118">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="5509d-119">在将组件添加到项目时，请确保为该组件设置必要的属性。</span><span class="sxs-lookup"><span data-stu-id="5509d-119">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>

## <a name="add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="5509d-120">以编程方式向 Windows 窗体添加组件</span><span class="sxs-lookup"><span data-stu-id="5509d-120">Add a component to a Windows Form programmatically</span></span>

1. <span data-ttu-id="5509d-121">在代码中创建 <xref:System.Windows.Forms.Timer> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="5509d-121">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>

2. <span data-ttu-id="5509d-122">设置 `Interval` 属性以确定计时器之间的时间刻度。</span><span class="sxs-lookup"><span data-stu-id="5509d-122">Set the `Interval` property to determine the time between ticks of the timer.</span></span>

3. <span data-ttu-id="5509d-123">配置组件的任何其他必要属性。</span><span class="sxs-lookup"><span data-stu-id="5509d-123">Configure any other necessary properties for your component.</span></span>

     <span data-ttu-id="5509d-124">下面的代码演示如何创建 <xref:System.Windows.Forms.Timer> 及其 `Interval` 属性集。</span><span class="sxs-lookup"><span data-stu-id="5509d-124">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>

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
    > <span data-ttu-id="5509d-125">通过引用恶意用户，你可以通过网络将你的本地计算机泄露给安全风险。</span><span class="sxs-lookup"><span data-stu-id="5509d-125">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="5509d-126">这只是在恶意用户创建有破坏性的自定义控件时，然后错误地将其添加到项目中时需要注意的问题。</span><span class="sxs-lookup"><span data-stu-id="5509d-126">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>

## <a name="see-also"></a><span data-ttu-id="5509d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5509d-127">See also</span></span>

- [<span data-ttu-id="5509d-128">Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5509d-128">Windows Forms Controls</span></span>](index.md)
- [<span data-ttu-id="5509d-129">방법: Windows Forms에 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="5509d-129">How to: Add Controls to Windows Forms</span></span>](how-to-add-controls-to-windows-forms.md)
- [<span data-ttu-id="5509d-130">방법: Windows Forms에 ActiveX 컨트롤 추가</span><span class="sxs-lookup"><span data-stu-id="5509d-130">How to: Add ActiveX Controls to Windows Forms</span></span>](how-to-add-activex-controls-to-windows-forms.md)
- [<span data-ttu-id="5509d-131">Windows Forms에 컨트롤 넣기</span><span class="sxs-lookup"><span data-stu-id="5509d-131">Putting Controls on Windows Forms</span></span>](putting-controls-on-windows-forms.md)
- [<span data-ttu-id="5509d-132">개별 Windows Forms 컨트롤 레이블 지정 및 바로 가기 제공</span><span class="sxs-lookup"><span data-stu-id="5509d-132">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)
- [<span data-ttu-id="5509d-133">Windows Forms에 사용할 수 있는 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5509d-133">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
- [<span data-ttu-id="5509d-134">기능별 Windows Forms 컨트롤</span><span class="sxs-lookup"><span data-stu-id="5509d-134">Windows Forms Controls by Function</span></span>](windows-forms-controls-by-function.md)
