---
title: "如何：向 Windows 窗体添加无用户界面的控件"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
f1_keywords: NonVisualSelection
helpviewer_keywords:
- invisible controls [Windows Forms]
- Windows Forms controls, adding to form
- controls [Windows Forms], nonvisual
- Windows Forms controls, nonvisual
- nonvisual controls [Windows Forms]
ms.assetid: 52134d9c-cff6-4eed-8e2b-3d5eb3bd494e
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3abbf931cff9ad459e8c9221f91430ecccefa9cc
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-add-controls-without-a-user-interface-to-windows-forms"></a><span data-ttu-id="7dbee-102">如何：向 Windows 窗体添加无用户界面的控件</span><span class="sxs-lookup"><span data-stu-id="7dbee-102">How to: Add Controls Without a User Interface to Windows Forms</span></span>
<span data-ttu-id="7dbee-103">非可视控件 （或组件） 功能提供给你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7dbee-103">A nonvisual control (or component) provides functionality to your application.</span></span> <span data-ttu-id="7dbee-104">不同于其他控件，组件不向用户提供的用户界面并因此不需要在 Windows 窗体设计器图面上显示。</span><span class="sxs-lookup"><span data-stu-id="7dbee-104">Unlike other controls, components do not provide a user interface to the user and thus do not need to be displayed on the Windows Forms Designer surface.</span></span> <span data-ttu-id="7dbee-105">后一个组件添加到窗体中，Windows 窗体设计器将在所有组件将都显示的窗体的底部显示可调整大小的任务栏。</span><span class="sxs-lookup"><span data-stu-id="7dbee-105">When a component is added to a form, the Windows Forms Designer displays a resizable tray at the bottom of the form where all components are displayed.</span></span> <span data-ttu-id="7dbee-106">控件现已添加到组件栏中后，你可选择的组件，设置其属性，就像任何其他控件在窗体上。</span><span class="sxs-lookup"><span data-stu-id="7dbee-106">Once a control has been added to the component tray, you can select the component and set its properties as you would any other control on the form.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7dbee-107">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="7dbee-107">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7dbee-108">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="7dbee-108">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7dbee-109">有关详细信息，请参阅[在 Visual Studio 中自定义开发设置](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3)。</span><span class="sxs-lookup"><span data-stu-id="7dbee-109">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/library/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-add-a-component-to-a-windows-form"></a><span data-ttu-id="7dbee-110">若要将组件添加到 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="7dbee-110">To add a component to a Windows Form</span></span>  
  
1.  <span data-ttu-id="7dbee-111">打开窗体。</span><span class="sxs-lookup"><span data-stu-id="7dbee-111">Open the form.</span></span> <span data-ttu-id="7dbee-112">有关详细信息，请参阅[如何： 显示 Windows 窗体设计器中](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5)。</span><span class="sxs-lookup"><span data-stu-id="7dbee-112">For details, see [How to: Display Windows Forms in the Designer](http://msdn.microsoft.com/library/bf3f1e5b-ea07-4529-85c6-6af3ded0cec5).</span></span>  
  
2.  <span data-ttu-id="7dbee-113">在**工具箱**，单击某个组件，并将其拖到窗体。</span><span class="sxs-lookup"><span data-stu-id="7dbee-113">In the **Toolbox**, click a component and drag it to your form.</span></span>  
  
     <span data-ttu-id="7dbee-114">此组件将出现在组件栏中。</span><span class="sxs-lookup"><span data-stu-id="7dbee-114">Your component appears in the component tray.</span></span>  
  
 <span data-ttu-id="7dbee-115">而且，组件可以在运行时添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="7dbee-115">Furthermore, components can be added to a form at run time.</span></span> <span data-ttu-id="7dbee-116">这是常见的方案中，尤其是因为组件不具有 visual 表达式，不同于具有用户界面的控件。</span><span class="sxs-lookup"><span data-stu-id="7dbee-116">This is a common scenario, especially because components do not have a visual expression, unlike controls that have a user interface.</span></span> <span data-ttu-id="7dbee-117">在示例中，<xref:System.Windows.Forms.Timer>在运行时添加组件。</span><span class="sxs-lookup"><span data-stu-id="7dbee-117">In the example below, a <xref:System.Windows.Forms.Timer> component is added at run time.</span></span> <span data-ttu-id="7dbee-118">(请注意，[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]包含大量不同的计时器; 在这种情况下，使用 Windows 窗体<xref:System.Windows.Forms.Timer>组件。</span><span class="sxs-lookup"><span data-stu-id="7dbee-118">(Note that [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)] contains a number of different timers; in this case, use a Windows Forms <xref:System.Windows.Forms.Timer> component.</span></span> <span data-ttu-id="7dbee-119">有关在不同的计时器[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]，请参阅[基于服务器的计时器简介](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc)。)</span><span class="sxs-lookup"><span data-stu-id="7dbee-119">For more information about the different timers in [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)], see [Introduction to Server-Based Timers](http://msdn.microsoft.com/library/adc0bc0a-a519-4812-bafc-fb9d1a5801fc).)</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7dbee-120">组件通常具有必须为该组件可有效地工作设置的特定于控件的属性。</span><span class="sxs-lookup"><span data-stu-id="7dbee-120">Components often have control-specific properties that must be set for the component to function effectively.</span></span> <span data-ttu-id="7dbee-121">情况下<xref:System.Windows.Forms.Timer>下方的组件，你将设置`Interval`属性。</span><span class="sxs-lookup"><span data-stu-id="7dbee-121">In the case of the <xref:System.Windows.Forms.Timer> component below, you set the `Interval` property.</span></span> <span data-ttu-id="7dbee-122">请确保，将组件添加到你的项目，你设置的属性需要该组件时。</span><span class="sxs-lookup"><span data-stu-id="7dbee-122">Be sure, when adding components to your project, that you set the properties necessary for that component.</span></span>  
  
#### <a name="to-add-a-component-to-a-windows-form-programmatically"></a><span data-ttu-id="7dbee-123">若要以编程方式向 Windows 窗体添加一个组件</span><span class="sxs-lookup"><span data-stu-id="7dbee-123">To add a component to a Windows Form programmatically</span></span>  
  
1.  <span data-ttu-id="7dbee-124">创建的实例<xref:System.Windows.Forms.Timer>在代码中的类。</span><span class="sxs-lookup"><span data-stu-id="7dbee-124">Create an instance of the <xref:System.Windows.Forms.Timer> class in code.</span></span>  
  
2.  <span data-ttu-id="7dbee-125">设置`Interval`属性来确定的计时器刻度之间的时间。</span><span class="sxs-lookup"><span data-stu-id="7dbee-125">Set the `Interval` property to determine the time between ticks of the timer.</span></span>  
  
3.  <span data-ttu-id="7dbee-126">配置任何其他必需的属性，为你的组件。</span><span class="sxs-lookup"><span data-stu-id="7dbee-126">Configure any other necessary properties for your component.</span></span>  
  
     <span data-ttu-id="7dbee-127">下面的代码演示如何创建<xref:System.Windows.Forms.Timer>与其`Interval`属性集。</span><span class="sxs-lookup"><span data-stu-id="7dbee-127">The following code shows the creation of a <xref:System.Windows.Forms.Timer> with its `Interval` property set.</span></span>  
  
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
    >  <span data-ttu-id="7dbee-128">通过引用恶意用户控件，则可能会公开您的本地计算机通过网络安全风险。</span><span class="sxs-lookup"><span data-stu-id="7dbee-128">You might expose your local computer to a security risk through the network by referencing a malicious UserControl.</span></span> <span data-ttu-id="7dbee-129">这仅会在恶意的用户创建破坏性的自定义控件，跟你错误地将其添加到你的项目的情况下是问题。</span><span class="sxs-lookup"><span data-stu-id="7dbee-129">This would only be a concern in the case of a malicious person creating a damaging custom control, followed by you mistakenly adding it to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dbee-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="7dbee-130">See Also</span></span>  
 [<span data-ttu-id="7dbee-131">Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7dbee-131">Windows Forms Controls</span></span>](../../../../docs/framework/winforms/controls/index.md)  
 [<span data-ttu-id="7dbee-132">如何：向 Windows 窗体添加控件</span><span class="sxs-lookup"><span data-stu-id="7dbee-132">How to: Add Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md)  
 [<span data-ttu-id="7dbee-133">如何：向 Windows 窗体添加 ActiveX 控件</span><span class="sxs-lookup"><span data-stu-id="7dbee-133">How to: Add ActiveX Controls to Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-add-activex-controls-to-windows-forms.md)  
 [<span data-ttu-id="7dbee-134">如何：在 Windows 窗体之间复制控件</span><span class="sxs-lookup"><span data-stu-id="7dbee-134">How to: Copy Controls Between Windows Forms</span></span>](../../../../docs/framework/winforms/controls/how-to-copy-controls-between-windows-forms.md)  
 [<span data-ttu-id="7dbee-135">将控件置于 Windows 窗体上</span><span class="sxs-lookup"><span data-stu-id="7dbee-135">Putting Controls on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/putting-controls-on-windows-forms.md)  
 [<span data-ttu-id="7dbee-136">标记各个 Windows 窗体控件并创建它们的快捷键</span><span class="sxs-lookup"><span data-stu-id="7dbee-136">Labeling Individual Windows Forms Controls and Providing Shortcuts to Them</span></span>](../../../../docs/framework/winforms/controls/labeling-individual-windows-forms-controls-and-providing-shortcuts-to-them.md)  
 [<span data-ttu-id="7dbee-137">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="7dbee-137">Controls to Use on Windows Forms</span></span>](../../../../docs/framework/winforms/controls/controls-to-use-on-windows-forms.md)  
 [<span data-ttu-id="7dbee-138">按功能列出的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="7dbee-138">Windows Forms Controls by Function</span></span>](../../../../docs/framework/winforms/controls/windows-forms-controls-by-function.md)
