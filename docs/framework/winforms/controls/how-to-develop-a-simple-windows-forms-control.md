---
title: 如何：开发简单的 Windows 窗体控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- controls [Windows Forms]
- custom controls [Windows Forms], creating simple controls using code
- Control class [Windows Forms], Windows Forms
ms.assetid: 86cbe435-45b7-4cb4-9b5a-47418369758d
ms.openlocfilehash: 457069cd7ac5af62e08115d84060c9c7fb25beee
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59328135"
---
# <a name="how-to-develop-a-simple-windows-forms-control"></a><span data-ttu-id="1c509-102">如何：开发简单的 Windows 窗体控件</span><span class="sxs-lookup"><span data-stu-id="1c509-102">How to: Develop a Simple Windows Forms Control</span></span>
<span data-ttu-id="1c509-103">本部分演示创建自定义 Windows 窗体控件的关键步骤。</span><span class="sxs-lookup"><span data-stu-id="1c509-103">This section walks you through the key steps for authoring a custom Windows Forms control.</span></span> <span data-ttu-id="1c509-104">在本演练中开发的简单控件允许的对齐方式及其<xref:System.Windows.Forms.Control.Text%2A>要更改属性。</span><span class="sxs-lookup"><span data-stu-id="1c509-104">The simple control developed in this walkthrough allows the alignment of its <xref:System.Windows.Forms.Control.Text%2A> property to be changed.</span></span> <span data-ttu-id="1c509-105">它不会引发或处理事件。</span><span class="sxs-lookup"><span data-stu-id="1c509-105">It does not raise or handle events.</span></span>  
  
### <a name="to-create-a-simple-custom-control"></a><span data-ttu-id="1c509-106">创建简单的自定义控件</span><span class="sxs-lookup"><span data-stu-id="1c509-106">To create a simple custom control</span></span>  
  
1. <span data-ttu-id="1c509-107">定义一个从 <xref:System.Windows.Forms.Control?displayProperty=nameWithType> 派生的类。</span><span class="sxs-lookup"><span data-stu-id="1c509-107">Define a class that derives from <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
    ```vb  
    Public Class FirstControl  
       Inherits Control  
  
    End Class  
    ```  
  
    ```csharp  
    public class FirstControl:Control {}  
    ```  
  
2. <span data-ttu-id="1c509-108">定义属性。</span><span class="sxs-lookup"><span data-stu-id="1c509-108">Define properties.</span></span> <span data-ttu-id="1c509-109">(不需要定义属性，因为控件继承许多属性从<xref:System.Windows.Forms.Control>类，但大多数自定义控件通常会定义其他属性。)以下代码片段定义名为的属性`TextAlignment`该`FirstControl`使用的显示格式<xref:System.Windows.Forms.Control.Text%2A>属性继承自<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="1c509-109">(You are not required to define properties, because a control inherits many properties from the <xref:System.Windows.Forms.Control> class, but most custom controls generally do define additional properties.) The following code fragment defines a property named `TextAlignment` that `FirstControl` uses to format the display of the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control>.</span></span> <span data-ttu-id="1c509-110">有关定义属性的详细信息，请参阅[属性概述](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120))。</span><span class="sxs-lookup"><span data-stu-id="1c509-110">For more information about defining properties, see [Properties Overview](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/65zdfbdt(v%3dvs.120)).</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#3)]
     [!code-vb[System.Windows.Forms.FirstControl#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#3)]  
  
     <span data-ttu-id="1c509-111">当设置属性，可更改控件的可视显示时，必须调用<xref:System.Windows.Forms.Control.Invalidate%2A>方法来重绘控件。</span><span class="sxs-lookup"><span data-stu-id="1c509-111">When you set a property that changes the visual display of the control, you must invoke the <xref:System.Windows.Forms.Control.Invalidate%2A> method to redraw the control.</span></span> <xref:System.Windows.Forms.Control.Invalidate%2A> <span data-ttu-id="1c509-112">在基类中定义<xref:System.Windows.Forms.Control>。</span><span class="sxs-lookup"><span data-stu-id="1c509-112">is defined in the base class <xref:System.Windows.Forms.Control>.</span></span>  
  
3. <span data-ttu-id="1c509-113">重写受保护<xref:System.Windows.Forms.Control.OnPaint%2A>方法继承自<xref:System.Windows.Forms.Control>提供到您的控件的呈现逻辑。</span><span class="sxs-lookup"><span data-stu-id="1c509-113">Override the protected <xref:System.Windows.Forms.Control.OnPaint%2A> method inherited from <xref:System.Windows.Forms.Control> to provide rendering logic to your control.</span></span> <span data-ttu-id="1c509-114">如果您不会重写<xref:System.Windows.Forms.Control.OnPaint%2A>，控件将不能自我绘制。</span><span class="sxs-lookup"><span data-stu-id="1c509-114">If you do not override <xref:System.Windows.Forms.Control.OnPaint%2A>, your control will not be able to draw itself.</span></span> <span data-ttu-id="1c509-115">在以下代码片段中，<xref:System.Windows.Forms.Control.OnPaint%2A>方法将显示<xref:System.Windows.Forms.Control.Text%2A>属性继承自<xref:System.Windows.Forms.Control>与由指定的对齐方式`alignmentValue`字段。</span><span class="sxs-lookup"><span data-stu-id="1c509-115">In the following code fragment, the <xref:System.Windows.Forms.Control.OnPaint%2A> method displays the <xref:System.Windows.Forms.Control.Text%2A> property inherited from <xref:System.Windows.Forms.Control> with the alignment specified by the `alignmentValue` field.</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#4)]
     [!code-vb[System.Windows.Forms.FirstControl#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#4)]  
  
4. <span data-ttu-id="1c509-116">为控件提供属性。</span><span class="sxs-lookup"><span data-stu-id="1c509-116">Provide attributes for your control.</span></span> <span data-ttu-id="1c509-117">特性让视觉设计器能够在设计时适当显示控件及其属性和事件。</span><span class="sxs-lookup"><span data-stu-id="1c509-117">Attributes enable a visual designer to display your control and its properties and events appropriately at design time.</span></span> <span data-ttu-id="1c509-118">以下代码片段将特性应用于 `TextAlignment` 属性。</span><span class="sxs-lookup"><span data-stu-id="1c509-118">The following code fragment applies attributes to the `TextAlignment` property.</span></span> <span data-ttu-id="1c509-119">在设计器中 Visual Studio 中，如<xref:System.ComponentModel.CategoryAttribute.Category%2A>属性 （如代码段所示） 会导致在逻辑类别下显示的属性。</span><span class="sxs-lookup"><span data-stu-id="1c509-119">In a designer such as Visual Studio, the <xref:System.ComponentModel.CategoryAttribute.Category%2A> attribute (shown in the code fragment) causes the property to be displayed under a logical category.</span></span> <span data-ttu-id="1c509-120"><xref:System.ComponentModel.DescriptionAttribute.Description%2A>属性使描述性字符串显示在底部**属性**窗口时`TextAlignment`选择属性。</span><span class="sxs-lookup"><span data-stu-id="1c509-120">The <xref:System.ComponentModel.DescriptionAttribute.Description%2A> attribute causes a descriptive string to be displayed at the bottom of the **Properties** window when the `TextAlignment` property is selected.</span></span> <span data-ttu-id="1c509-121">有关属性的详细信息，请参阅[组件的设计时属性](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="1c509-121">For more information about attributes, see [Design-Time Attributes for Components](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/tk67c2t8(v=vs.120)).</span></span>  
  
     [!code-csharp[System.Windows.Forms.FirstControl#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#5)]
     [!code-vb[System.Windows.Forms.FirstControl#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#5)]  
  
5. <span data-ttu-id="1c509-122">（可选）为控件提供资源。</span><span class="sxs-lookup"><span data-stu-id="1c509-122">(optional) Provide resources for your control.</span></span> <span data-ttu-id="1c509-123">可通过使用编译器选项（对于 C#，为 `/res`）将资源和控件进行打包，从而为控件提供资源（如位图）。</span><span class="sxs-lookup"><span data-stu-id="1c509-123">You can provide a resource, such as a bitmap, for your control by using a compiler option (`/res` for C#) to package resources with your control.</span></span> <span data-ttu-id="1c509-124">在运行时，可以使用检索资源的方法<xref:System.Resources.ResourceManager>类。</span><span class="sxs-lookup"><span data-stu-id="1c509-124">At run time, the resource can be retrieved using the methods of the <xref:System.Resources.ResourceManager> class.</span></span> <span data-ttu-id="1c509-125">有关创建和使用资源的详细信息，请参阅[桌面应用中的资源](../../resources/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1c509-125">For more information about creating and using resources, see the [Resources in Desktop Apps](../../resources/index.md).</span></span>  
  
6. <span data-ttu-id="1c509-126">编译和部署控件。</span><span class="sxs-lookup"><span data-stu-id="1c509-126">Compile and deploy your control.</span></span> <span data-ttu-id="1c509-127">要编译和部署 `FirstControl,`，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1c509-127">To compile and deploy `FirstControl,` execute the following steps:</span></span>  
  
    1.  <span data-ttu-id="1c509-128">将以下示例中的代码保存到源文件（如 FirstControl.cs 或 FirstControl.vb）。</span><span class="sxs-lookup"><span data-stu-id="1c509-128">Save the code in the following sample to a source file (such as FirstControl.cs or FirstControl.vb).</span></span>  
  
    2.  <span data-ttu-id="1c509-129">将源代码编译成程序集并将其保存在应用程序的目录中。</span><span class="sxs-lookup"><span data-stu-id="1c509-129">Compile the source code into an assembly and save it in your application's directory.</span></span> <span data-ttu-id="1c509-130">要完成此操作，请从包含源文件的目录执行以下命令。</span><span class="sxs-lookup"><span data-stu-id="1c509-130">To accomplish this, execute the following command from the directory that contains the source file.</span></span>  
  
        ```console  
        vbc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.vb  
        ```  
  
        ```console 
        csc -t:library -out:[path to your application's directory]/CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll FirstControl.cs  
        ```  
  
         <span data-ttu-id="1c509-131">`/t:library` 编译器选项会告知编译器正在创建的程序集是库（而不是可执行文件）。</span><span class="sxs-lookup"><span data-stu-id="1c509-131">The `/t:library` compiler option tells the compiler that the assembly you are creating is a library (and not an executable).</span></span> <span data-ttu-id="1c509-132">`/out` 选项指定程序集的路径和名称。</span><span class="sxs-lookup"><span data-stu-id="1c509-132">The `/out` option specifies the path and name of the assembly.</span></span> <span data-ttu-id="1c509-133">`/r` 选项提供代码引用的程序集的名称。</span><span class="sxs-lookup"><span data-stu-id="1c509-133">The`/r` option provides the name of the assemblies that are referenced by your code.</span></span> <span data-ttu-id="1c509-134">在此示例中，将创建只有你的应用程序可以使用的私有程序集。</span><span class="sxs-lookup"><span data-stu-id="1c509-134">In this example, you create a private assembly that only your applications can use.</span></span> <span data-ttu-id="1c509-135">因此，必须将其保存在应用程序的目录中。</span><span class="sxs-lookup"><span data-stu-id="1c509-135">Hence, you have to save it in your application's directory.</span></span> <span data-ttu-id="1c509-136">有关打包和部署控件以进行分发的详细信息，请参阅[部署](../../deployment/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1c509-136">For more information about packaging and deploying a control for distribution, see [Deployment](../../deployment/index.md).</span></span>  
  
 <span data-ttu-id="1c509-137">此示例演示了 `FirstControl` 的代码。</span><span class="sxs-lookup"><span data-stu-id="1c509-137">The following sample shows the code for `FirstControl`.</span></span> <span data-ttu-id="1c509-138">控件包含在命名空间 `CustomWinControls` 中。</span><span class="sxs-lookup"><span data-stu-id="1c509-138">The control is enclosed in the namespace `CustomWinControls`.</span></span> <span data-ttu-id="1c509-139">命名空间提供相关类型的逻辑分组。</span><span class="sxs-lookup"><span data-stu-id="1c509-139">A namespace provides a logical grouping of related types.</span></span> <span data-ttu-id="1c509-140">可在新的或现有命名空间中创建控件。</span><span class="sxs-lookup"><span data-stu-id="1c509-140">You can create your control in a new or existing namespace.</span></span> <span data-ttu-id="1c509-141">在 C# 中，`using` 声明（在 Visual Basic 中，为 `Imports`）允许从命名空间访问类型，而无需使用类型的完全限定名称。</span><span class="sxs-lookup"><span data-stu-id="1c509-141">In C#, the `using` declaration (in Visual Basic, `Imports`) allows types to be accessed from a namespace without using the fully qualified name of the type.</span></span> <span data-ttu-id="1c509-142">在以下示例中，`using`声明允许代码访问的类<xref:System.Windows.Forms.Control>从<xref:System.Windows.Forms?displayProperty=nameWithType>简单地<xref:System.Windows.Forms.Control>而无需使用完全限定的名称<xref:System.Windows.Forms.Control?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="1c509-142">In the following example, the `using` declaration allows code to access the class <xref:System.Windows.Forms.Control> from <xref:System.Windows.Forms?displayProperty=nameWithType> as simply <xref:System.Windows.Forms.Control> instead of having to use the fully qualified name <xref:System.Windows.Forms.Control?displayProperty=nameWithType>.</span></span>  
  
 [!code-csharp[System.Windows.Forms.FirstControl#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/FirstControl.cs#1)]
 [!code-vb[System.Windows.Forms.FirstControl#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/FirstControl.vb#1)]  
  
## <a name="using-the-custom-control-on-a-form"></a><span data-ttu-id="1c509-143">在窗体上使用自定义控件</span><span class="sxs-lookup"><span data-stu-id="1c509-143">Using the Custom Control on a Form</span></span>  
 <span data-ttu-id="1c509-144">以下示例显示使用 `FirstControl` 的简单窗体。</span><span class="sxs-lookup"><span data-stu-id="1c509-144">The following example shows a simple form that uses `FirstControl`.</span></span> <span data-ttu-id="1c509-145">它会创建 `FirstControl` 的三个实例，每个实例具有一个不同的 `TextAlignment` 属性值。</span><span class="sxs-lookup"><span data-stu-id="1c509-145">It creates three instances of `FirstControl`, each with a different value for the `TextAlignment` property.</span></span>  
  
#### <a name="to-compile-and-run-this-sample"></a><span data-ttu-id="1c509-146">编译和运行此示例</span><span class="sxs-lookup"><span data-stu-id="1c509-146">To compile and run this sample</span></span>  
  
1. <span data-ttu-id="1c509-147">将以下示例中的代码保存到源文件（SimpleForm.cs 或 SimpleForms.vb）。</span><span class="sxs-lookup"><span data-stu-id="1c509-147">Save the code in the following example to a source file (SimpleForm.cs or SimpleForms.vb).</span></span>  
  
2. <span data-ttu-id="1c509-148">通过从包含源文件的目录执行以下命令，将源代码编译成可执行程序集。</span><span class="sxs-lookup"><span data-stu-id="1c509-148">Compile the source code into an executable assembly by executing the following command from the directory that contains the source file.</span></span>  
  
    ```console  
    vbc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.vb  
    ```  
  
    ```console 
    csc -r:CustomWinControls.dll -r:System.dll -r:System.Windows.Forms.dll -r:System.Drawing.dll SimpleForm.cs  
    ```  
  
     <span data-ttu-id="1c509-149">CustomWinControls.dll 是包含类的程序集`FirstControl`。</span><span class="sxs-lookup"><span data-stu-id="1c509-149">CustomWinControls.dll is the assembly that contains the class `FirstControl`.</span></span> <span data-ttu-id="1c509-150">此程序集必须与访问程序集的窗体的源文件（SimpleForm.cs或SimpleForms.vb）位于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="1c509-150">This assembly must be in the same directory as the source file for the form that accesses it (SimpleForm.cs or SimpleForms.vb).</span></span>  
  
3. <span data-ttu-id="1c509-151">使用以下命令执行 SimpleForm.exe。</span><span class="sxs-lookup"><span data-stu-id="1c509-151">Execute SimpleForm.exe using the following command.</span></span>  
  
    ```console
    SimpleForm  
    ```  
  
 [!code-csharp[System.Windows.Forms.FirstControl#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/CS/SimpleForm.cs#10)]
 [!code-vb[System.Windows.Forms.FirstControl#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.FirstControl/VB/SimpleForm.vb#10)]  
  
## <a name="see-also"></a><span data-ttu-id="1c509-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="1c509-152">See also</span></span>

- [<span data-ttu-id="1c509-153">Windows 窗体控件中的属性</span><span class="sxs-lookup"><span data-stu-id="1c509-153">Properties in Windows Forms Controls</span></span>](properties-in-windows-forms-controls.md)
- [<span data-ttu-id="1c509-154">Windows 窗体控件中的事件</span><span class="sxs-lookup"><span data-stu-id="1c509-154">Events in Windows Forms Controls</span></span>](events-in-windows-forms-controls.md)
