---
title: 属性网格扩展性
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3530c3a3-756d-4712-9f10-fb2897414d3a
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9393947420709590312200e8f142092c95b91b1f
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="property-grid-extensibliity"></a><span data-ttu-id="d2e88-102">属性网格扩展性</span><span class="sxs-lookup"><span data-stu-id="d2e88-102">Property Grid Extensibliity</span></span>
<span data-ttu-id="d2e88-103">开发人员可以自定义属性网格，此网格将在设计器中选择给定活动时显示。</span><span class="sxs-lookup"><span data-stu-id="d2e88-103">A developer can customize the property grid that is displayed when a given activity is selected within the designer.</span></span> <span data-ttu-id="d2e88-104">执行此操作可获得丰富的编辑体验。</span><span class="sxs-lookup"><span data-stu-id="d2e88-104">This can be done to create a rich editing experience.</span></span> <span data-ttu-id="d2e88-105">此示例演示如何完成此操作。</span><span class="sxs-lookup"><span data-stu-id="d2e88-105">This sample shows how this can be done.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="d2e88-106">演示</span><span class="sxs-lookup"><span data-stu-id="d2e88-106">Demonstrates</span></span>  
 <span data-ttu-id="d2e88-107">工作流设计器属性网格的扩展性。</span><span class="sxs-lookup"><span data-stu-id="d2e88-107">Workflow designer property grid extensibility.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2e88-108">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="d2e88-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d2e88-109">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="d2e88-109">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d2e88-110">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="d2e88-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d2e88-111">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="d2e88-111">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`  
  
## <a name="discussion"></a><span data-ttu-id="d2e88-112">讨论</span><span class="sxs-lookup"><span data-stu-id="d2e88-112">Discussion</span></span>  
 <span data-ttu-id="d2e88-113">若要扩展属性网格，开发人员可以选择自定义属性网格编辑器的内联外观或提供一个为更高级的编辑图面显示的对话框。</span><span class="sxs-lookup"><span data-stu-id="d2e88-113">To extend the property grid, a developer has options to customize the inline appearance of a property grid editor or provide a dialog that appears for a more advanced editing surface.</span></span> <span data-ttu-id="d2e88-114">此示例中演示了两类不同的编辑器；即内联编辑器和对话框编辑器。</span><span class="sxs-lookup"><span data-stu-id="d2e88-114">There are two different editors demonstrated in this sample; an inline editor and a dialog editor.</span></span>  
  
## <a name="inline-editor"></a><span data-ttu-id="d2e88-115">内联编辑器</span><span class="sxs-lookup"><span data-stu-id="d2e88-115">Inline Editor</span></span>  
 <span data-ttu-id="d2e88-116">内联编辑器示例将演示如下内容：</span><span class="sxs-lookup"><span data-stu-id="d2e88-116">The inline editor sample demonstrates the following:</span></span>  
  
-   <span data-ttu-id="d2e88-117">创建一个从 <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor> 派生的类型。</span><span class="sxs-lookup"><span data-stu-id="d2e88-117">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor>.</span></span>  
  
-   <span data-ttu-id="d2e88-118">在构造函数中，<xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A>使用 Windows Presentation Foundation (WPF) 数据模板设置值。</span><span class="sxs-lookup"><span data-stu-id="d2e88-118">In the constructor, the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value is set with a Windows Presentation Foundation (WPF) data template.</span></span> <span data-ttu-id="d2e88-119">虽然可以将其绑定到 XAML 模板，但在此示例中，代码用于初始化数据绑定。</span><span class="sxs-lookup"><span data-stu-id="d2e88-119">This can be bound to a XAML template, but in this sample, code is used to initialize data binding.</span></span>  
  
-   <span data-ttu-id="d2e88-120">数据模板具有在属性网格中呈现的项的 <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> 的数据上下文。</span><span class="sxs-lookup"><span data-stu-id="d2e88-120">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="d2e88-121">请注意，在下面的代码（此代码来自 CustomInlineEditor.cs）中，稍后会将此上下文绑定到 `Value` 属性。</span><span class="sxs-lookup"><span data-stu-id="d2e88-121">Note in the following code (from CustomInlineEditor.cs) that this context then binds to the `Value` property.</span></span>  
  
    ```csharp  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    FrameworkElementFactory slider = new FrameworkElementFactory(typeof(Slider));  
    Binding sliderBinding = new Binding("Value");  
    sliderBinding.Mode = BindingMode.TwoWay;  
    slider.SetValue(Slider.MinimumProperty, 0.0);  
    slider.SetValue(Slider.MaximumProperty, 100.0);  
    slider.SetValue(Slider.ValueProperty, sliderBinding);  
    stack.AppendChild(slider);  
    ```  
  
-   <span data-ttu-id="d2e88-122">由于活动和设计器位于同一个程序集中，因此将在活动自身的静态构造函数中完成对活动设计器特性的注册，如 SimpleCodeActivity.cs 中的以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="d2e88-122">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="dialog-editor"></a><span data-ttu-id="d2e88-123">对话框编辑器</span><span class="sxs-lookup"><span data-stu-id="d2e88-123">Dialog Editor</span></span>  
 <span data-ttu-id="d2e88-124">对话框编辑器示例将演示如下内容：</span><span class="sxs-lookup"><span data-stu-id="d2e88-124">The dialog editor sample demonstrates the following:</span></span>  
  
1.  <span data-ttu-id="d2e88-125">创建一个从 <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor> 派生的类型。</span><span class="sxs-lookup"><span data-stu-id="d2e88-125">Creates a type that derives from <xref:System.Activities.Presentation.PropertyEditing.DialogPropertyValueEditor>.</span></span>  
  
2.  <span data-ttu-id="d2e88-126">在构造函数中，使用 <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> 数据模板设置 [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] 值。</span><span class="sxs-lookup"><span data-stu-id="d2e88-126">Sets the <xref:System.Activities.Presentation.PropertyEditing.PropertyValueEditor.InlineEditorTemplate%2A> value in the constructor with a [!INCLUDE[avalon2](../../../../includes/avalon2-md.md)] data template.</span></span> <span data-ttu-id="d2e88-127">可以在 XAML 中创建该值，但在此示例中，将在代码中创建它。</span><span class="sxs-lookup"><span data-stu-id="d2e88-127">This can be created in XAML, but in this sample, this is created in code.</span></span>  
  
3.  <span data-ttu-id="d2e88-128">数据模板具有在属性网格中呈现的项的 <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> 的数据上下文。</span><span class="sxs-lookup"><span data-stu-id="d2e88-128">The data template has a data context of the <xref:System.Activities.Presentation.PropertyEditing.PropertyValue> of the item rendered in the property grid.</span></span> <span data-ttu-id="d2e88-129">在下面的代码中，稍后会将其绑定到 `Value` 属性。</span><span class="sxs-lookup"><span data-stu-id="d2e88-129">In the following code, this then binds to the `Value` property.</span></span> <span data-ttu-id="d2e88-130">此外，包含 <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> 以提供引发 FilePickerEditor.cs 中的对话框的按钮也很重要。</span><span class="sxs-lookup"><span data-stu-id="d2e88-130">It is critical to also include an <xref:System.Activities.Presentation.PropertyEditing.EditModeSwitchButton> to provide the button that raises the dialog in FilePickerEditor.cs.</span></span>  
  
    ```  
    this.InlineEditorTemplate = new DataTemplate();  
  
    FrameworkElementFactory stack = new FrameworkElementFactory(typeof(StackPanel));  
    stack.SetValue(StackPanel.OrientationProperty, Orientation.Horizontal);  
    FrameworkElementFactory label = new FrameworkElementFactory(typeof(Label));  
    Binding labelBinding = new Binding("Value");  
    label.SetValue(Label.ContentProperty, labelBinding);  
    label.SetValue(Label.MaxWidthProperty, 90.0);  
  
    stack.AppendChild(label);  
  
    FrameworkElementFactory editModeSwitch = new FrameworkElementFactory(typeof(EditModeSwitchButton));  
  
    editModeSwitch.SetValue(EditModeSwitchButton.TargetEditModeProperty, PropertyContainerEditMode.Dialog);  
  
    stack.AppendChild(editModeSwitch);  
  
    this.InlineEditorTemplate.VisualTree = stack;  
    ```  
  
4.  <span data-ttu-id="d2e88-131">重写<!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>-->`Microsoft.Windows.Design.PropertyEditing.ShowDialog`设计器的类型，以处理对话框的显示中的方法。</span><span class="sxs-lookup"><span data-stu-id="d2e88-131">Overrides the <!--zz <xref:Microsoft.Windows.Design.PropertyEditing.ShowDialog%2A>--> `Microsoft.Windows.Design.PropertyEditing.ShowDialog` method in the designer type to handle the display of the dialog.</span></span> <span data-ttu-id="d2e88-132">在此示例中，显示了基本 <xref:System.Windows.Forms.FileDialog>。</span><span class="sxs-lookup"><span data-stu-id="d2e88-132">In this sample, a basic <xref:System.Windows.Forms.FileDialog> is shown.</span></span>  
  
    ```  
    public override void ShowDialog(PropertyValue propertyValue, IInputElement commandSource)  
    {  
        Microsoft.Win32.OpenFileDialog ofd = new Microsoft.Win32.OpenFileDialog();  
        if (ofd.ShowDialog() == true)  
        {  
            propertyValue.Value = ofd.FileName;  
        }  
    }  
    ```  
  
5.  <span data-ttu-id="d2e88-133">由于活动和设计器位于同一个程序集中，因此将在活动自身的静态构造函数中完成对活动设计器特性的注册，如 SimpleCodeActivity.cs 中的以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="d2e88-133">Because the activity and the designer are in the same assembly, registration of the activity designer attributes are accomplished in the static constructor of the activity itself, as shown in the following example from SimpleCodeActivity.cs.</span></span>  
  
    ```  
    static SimpleCodeActivity()  
    {  
        AttributeTableBuilder builder = new AttributeTableBuilder();  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "RepeatCount", new EditorAttribute(typeof(CustomInlineEditor), typeof(PropertyValueEditor)));  
        builder.AddCustomAttributes(typeof(SimpleCodeActivity), "FileName", new EditorAttribute(typeof(FilePickerEditor), typeof(DialogPropertyValueEditor)));  
        MetadataStore.AddAttributeTable(builder.CreateTable());  
    }  
    ```  
  
## <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d2e88-134">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="d2e88-134">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="d2e88-135">生成解决方案，然后打开 Workflow1.xaml。</span><span class="sxs-lookup"><span data-stu-id="d2e88-135">Build the solution, and then open Workflow1.xaml.</span></span>  
  
2.  <span data-ttu-id="d2e88-136">拖动**SimpleCodeActivity**从工具箱拖动到设计器画布。</span><span class="sxs-lookup"><span data-stu-id="d2e88-136">Drag a **SimpleCodeActivity** from the toolbox onto the designer canvas.</span></span>  
  
3.  <span data-ttu-id="d2e88-137">单击**SimpleCodeActivity** ，然后打开滑块控件和文件选取控件的属性网格。</span><span class="sxs-lookup"><span data-stu-id="d2e88-137">Click the **SimpleCodeActivity** and then open the property grid where there is a slider control and a file picking control.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="d2e88-138">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="d2e88-138">The samples may already be installed on your machine.</span></span> <span data-ttu-id="d2e88-139">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="d2e88-139">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="d2e88-140">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="d2e88-140">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d2e88-141">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="d2e88-141">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Designer\PropertyGridExtensibility`
