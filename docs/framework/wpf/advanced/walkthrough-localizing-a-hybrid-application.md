---
title: 演练：本地化混合应用程序
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: bef296d5de4735780c839af312b5d4fe7eeeb960
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197857"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="a7e70-102">演练：本地化混合应用程序</span><span class="sxs-lookup"><span data-stu-id="a7e70-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="a7e70-103">本演练演示如何在基于 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]的混合应用程序中本地化 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素。</span><span class="sxs-lookup"><span data-stu-id="a7e70-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="a7e70-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="a7e70-104">Tasks illustrated in this walkthrough include:</span></span>

- <span data-ttu-id="a7e70-105">正在创建 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 主机项目。</span><span class="sxs-lookup"><span data-stu-id="a7e70-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

- <span data-ttu-id="a7e70-106">添加可本地化的内容。</span><span class="sxs-lookup"><span data-stu-id="a7e70-106">Adding localizable content.</span></span>

- <span data-ttu-id="a7e70-107">启用本地化。</span><span class="sxs-lookup"><span data-stu-id="a7e70-107">Enabling localization.</span></span>

- <span data-ttu-id="a7e70-108">分配资源标识符。</span><span class="sxs-lookup"><span data-stu-id="a7e70-108">Assigning resource identifiers.</span></span>

- <span data-ttu-id="a7e70-109">使用 LocBaml 工具生成附属程序集。</span><span class="sxs-lookup"><span data-stu-id="a7e70-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="a7e70-110">有关本演练中所述任务的完整代码列表，请参阅[本地化混合应用程序示例](https://go.microsoft.com/fwlink/?LinkID=160015)。</span><span class="sxs-lookup"><span data-stu-id="a7e70-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="a7e70-111">完成后，你将拥有一个本地化的混合应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7e70-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a7e70-112">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="a7e70-112">Prerequisites</span></span>

<span data-ttu-id="a7e70-113">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="a7e70-113">You need the following components to complete this walkthrough:</span></span>

- <span data-ttu-id="a7e70-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="a7e70-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="a7e70-115">创建 Windows 窗体宿主项目</span><span class="sxs-lookup"><span data-stu-id="a7e70-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="a7e70-116">第一步是创建 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] 应用程序项目，并添加包含要本地化的内容的 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素。</span><span class="sxs-lookup"><span data-stu-id="a7e70-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="a7e70-117">创建宿主项目</span><span class="sxs-lookup"><span data-stu-id="a7e70-117">To create the host project</span></span>

1. <span data-ttu-id="a7e70-118">创建一个名为 `LocalizingWpfInWf`的**WPF 应用程序**项目。</span><span class="sxs-lookup"><span data-stu-id="a7e70-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="a7e70-119">（**文件** > **新**的 \*\* > 项目\*\* > **视觉对象C#** 或**Visual Basic** > **经典桌面** > **WPF 应用程序**）。</span><span class="sxs-lookup"><span data-stu-id="a7e70-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="a7e70-120">将名为 `SimpleControl` [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> 元素添加到项目。</span><span class="sxs-lookup"><span data-stu-id="a7e70-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="a7e70-121">使用 <xref:System.Windows.Forms.Integration.ElementHost> 控件将 `SimpleControl` 元素放置在窗体上。</span><span class="sxs-lookup"><span data-stu-id="a7e70-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="a7e70-122">有关详细信息，请参阅[演练：在 Windows 窗体中承载 3-D WPF 复合控件](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e70-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="a7e70-123">添加可本地化的内容</span><span class="sxs-lookup"><span data-stu-id="a7e70-123">Adding Localizable Content</span></span>

<span data-ttu-id="a7e70-124">接下来，您将添加一个 [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] "标签" 控件，并将 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 元素的内容设置为可本地化的字符串。</span><span class="sxs-lookup"><span data-stu-id="a7e70-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="a7e70-125">添加可本地化的内容</span><span class="sxs-lookup"><span data-stu-id="a7e70-125">To add localizable content</span></span>

1. <span data-ttu-id="a7e70-126">在**解决方案资源管理器**中，双击**simplecontrol.xaml**以在 [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]中打开它。</span><span class="sxs-lookup"><span data-stu-id="a7e70-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="a7e70-127">使用以下代码设置 <xref:System.Windows.Controls.Button> 控件的内容。</span><span class="sxs-lookup"><span data-stu-id="a7e70-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="a7e70-128">在**解决方案资源管理器**中，双击 " **Form1** " 以在 Windows 窗体设计器中打开它。</span><span class="sxs-lookup"><span data-stu-id="a7e70-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="a7e70-129">打开 "**工具箱**"，然后双击 "**标签**"，将 "标签" 控件添加到窗体中。</span><span class="sxs-lookup"><span data-stu-id="a7e70-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="a7e70-130">将其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值设置为 `"Hello"`。</span><span class="sxs-lookup"><span data-stu-id="a7e70-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="a7e70-131">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="a7e70-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="a7e70-132">`SimpleControl` 元素和标签控件都显示文本 **"Hello"** 。</span><span class="sxs-lookup"><span data-stu-id="a7e70-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="a7e70-133">启用本地化</span><span class="sxs-lookup"><span data-stu-id="a7e70-133">Enabling Localization</span></span>

<span data-ttu-id="a7e70-134">Windows 窗体设计器提供用于在附属程序集中启用本地化的设置。</span><span class="sxs-lookup"><span data-stu-id="a7e70-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="a7e70-135">启用本地化</span><span class="sxs-lookup"><span data-stu-id="a7e70-135">To enable localization</span></span>

1. <span data-ttu-id="a7e70-136">在**解决方案资源管理器**中，双击 " **Form1.cs** " 以在 Windows 窗体设计器中打开它。</span><span class="sxs-lookup"><span data-stu-id="a7e70-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="a7e70-137">在 "**属性**" 窗口中，将窗体的可**本地化**属性的值设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="a7e70-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="a7e70-138">在 "**属性**" 窗口中，将 "**语言**" 属性的值设置为 "**西班牙语（西班牙）** "。</span><span class="sxs-lookup"><span data-stu-id="a7e70-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="a7e70-139">在 Windows 窗体设计器中，选择标签控件。</span><span class="sxs-lookup"><span data-stu-id="a7e70-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="a7e70-140">在 "**属性**" 窗口中，将 "<xref:System.Windows.Forms.Control.Text%2A>" 属性的值设置为 "`"Hola"`"。</span><span class="sxs-lookup"><span data-stu-id="a7e70-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="a7e70-141">一个名为 Form1.es-ES.resx 的新资源文件会添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="a7e70-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="a7e70-142">在**解决方案资源管理器**中，右键单击**Form1.cs** ，然后单击 "**查看代码**" 以在代码编辑器中打开它。</span><span class="sxs-lookup"><span data-stu-id="a7e70-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="a7e70-143">将以下代码复制到 `Form1` 构造函数中，在调用 `InitializeComponent`之前。</span><span class="sxs-lookup"><span data-stu-id="a7e70-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="a7e70-144">在**解决方案资源管理器**中，右键单击**LocalizingWpfInWf** ，然后单击 "**卸载项目**"。</span><span class="sxs-lookup"><span data-stu-id="a7e70-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="a7e70-145">项目名称标记为 "**不可用**"。</span><span class="sxs-lookup"><span data-stu-id="a7e70-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="a7e70-146">右键单击 " **LocalizingWpfInWf**"，然后单击 "**编辑 LocalizingWpfInWf**"。</span><span class="sxs-lookup"><span data-stu-id="a7e70-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="a7e70-147">项目文件将在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="a7e70-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="a7e70-148">将以下行复制到项目文件中的第一个 `PropertyGroup`。</span><span class="sxs-lookup"><span data-stu-id="a7e70-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="a7e70-149">保存项目文件并将其关闭。</span><span class="sxs-lookup"><span data-stu-id="a7e70-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="a7e70-150">在**解决方案资源管理器**中，右键单击**LocalizingWpfInWf** ，然后单击 "**重新加载项目**"。</span><span class="sxs-lookup"><span data-stu-id="a7e70-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="a7e70-151">分配资源标识符</span><span class="sxs-lookup"><span data-stu-id="a7e70-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="a7e70-152">可以通过使用资源标识符将可本地化内容映射到资源程序集。</span><span class="sxs-lookup"><span data-stu-id="a7e70-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="a7e70-153">当你指定 `updateuid` 选项时，Msbuild.exe 应用程序会自动分配资源标识符。</span><span class="sxs-lookup"><span data-stu-id="a7e70-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="a7e70-154">分配资源标识符</span><span class="sxs-lookup"><span data-stu-id="a7e70-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="a7e70-155">从 "开始" 菜单中，打开 Visual Studio 的开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="a7e70-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="a7e70-156">使用以下命令将资源标识符分配到可本地化内容。</span><span class="sxs-lookup"><span data-stu-id="a7e70-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```console
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="a7e70-157">在**解决方案资源管理器**中，双击**Simplecontrol.xaml**以在代码编辑器中打开它。</span><span class="sxs-lookup"><span data-stu-id="a7e70-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="a7e70-158">你将看到 `msbuild` 命令已将 `Uid` 特性添加到了所有元素。</span><span class="sxs-lookup"><span data-stu-id="a7e70-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="a7e70-159">这有助于通过分配资源标识符进行本地化。</span><span class="sxs-lookup"><span data-stu-id="a7e70-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="a7e70-160">按**F6**生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="a7e70-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="a7e70-161">使用 LocBaml 生成附属程序集</span><span class="sxs-lookup"><span data-stu-id="a7e70-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="a7e70-162">本地化内容存储在仅限资源的*附属程序集中*。</span><span class="sxs-lookup"><span data-stu-id="a7e70-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="a7e70-163">使用命令行工具 LocBaml 生成 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 内容的本地化程序集。</span><span class="sxs-lookup"><span data-stu-id="a7e70-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="a7e70-164">生成附属程序集</span><span class="sxs-lookup"><span data-stu-id="a7e70-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="a7e70-165">将 LocBaml.exe 复制到项目的 obj\Debug 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a7e70-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="a7e70-166">有关详细信息，请参阅对[应用程序进行本地化](how-to-localize-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a7e70-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="a7e70-167">在“命令提示符”窗口中，使用以下命令将资源字符串提取到临时文件中。</span><span class="sxs-lookup"><span data-stu-id="a7e70-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```console
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="a7e70-168">用 Visual Studio 或其他文本编辑器打开 temp .csv 文件。</span><span class="sxs-lookup"><span data-stu-id="a7e70-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="a7e70-169">将字符串 `"Hello"` 替换为其西班牙语翻译，`"Hola"`。</span><span class="sxs-lookup"><span data-stu-id="a7e70-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="a7e70-170">保存 temp.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="a7e70-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="a7e70-171">使用以下命令生成本地化资源文件。</span><span class="sxs-lookup"><span data-stu-id="a7e70-171">Use the following command to generate the localized resource file.</span></span>

    ```console
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="a7e70-172">将在 obj\Debug 文件夹中创建 LocalizingWpfInWf.g.es-ES.resources 文件。</span><span class="sxs-lookup"><span data-stu-id="a7e70-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="a7e70-173">使用以下命令生成本地化附属程序集。</span><span class="sxs-lookup"><span data-stu-id="a7e70-173">Use the following command to build the localized satellite assembly.</span></span>

    ```console
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="a7e70-174">将在 obj\Debug 文件夹中创建 LocalizingWpfInWf.resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="a7e70-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="a7e70-175">将 LocalizingWpfInWf.resources.dll 文件复制到项目的 bin\Debug\es-ES 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a7e70-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="a7e70-176">替换现有文件。</span><span class="sxs-lookup"><span data-stu-id="a7e70-176">Replace the existing file.</span></span>

8. <span data-ttu-id="a7e70-177">运行 LocalizingWpfInWf.exe，它位于项目的 bin\Debug 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="a7e70-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="a7e70-178">不要重新生成应用程序，否则附属程序集将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="a7e70-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="a7e70-179">应用程序显示本地化后的字符串，而不是英语字符串。</span><span class="sxs-lookup"><span data-stu-id="a7e70-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="a7e70-180">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7e70-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="a7e70-181">对应用程序进行本地化</span><span class="sxs-lookup"><span data-stu-id="a7e70-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- <span data-ttu-id="a7e70-182">[演练：本地化 Windows 窗体](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a7e70-182">[Walkthrough: Localizing Windows Forms](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))</span></span>
- [<span data-ttu-id="a7e70-183">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="a7e70-183">Design XAML in Visual Studio</span></span>](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)
