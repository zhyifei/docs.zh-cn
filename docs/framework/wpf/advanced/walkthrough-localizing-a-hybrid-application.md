---
title: 演练：本地化混合应用程序
ms.date: 08/18/2018
helpviewer_keywords:
- localization [WPF interoperability]
- hybrid applications [WPF interoperability]
ms.assetid: fbc0c54e-930a-4c13-8e9c-27b83665010a
ms.openlocfilehash: 01530d4ae9779934948bbaff60fbbd392de6e701
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59329292"
---
# <a name="walkthrough-localizing-a-hybrid-application"></a><span data-ttu-id="55ad8-102">演练：本地化混合应用程序</span><span class="sxs-lookup"><span data-stu-id="55ad8-102">Walkthrough: Localizing a Hybrid Application</span></span>

<span data-ttu-id="55ad8-103">本演练演示如何将本地化[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]中的元素[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-基于混合应用程序。</span><span class="sxs-lookup"><span data-stu-id="55ad8-103">This walkthrough shows you how to localize [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] elements in a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]-based hybrid application.</span></span>

<span data-ttu-id="55ad8-104">本演练涉及以下任务：</span><span class="sxs-lookup"><span data-stu-id="55ad8-104">Tasks illustrated in this walkthrough include:</span></span>

-   <span data-ttu-id="55ad8-105">创建[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]宿主项目。</span><span class="sxs-lookup"><span data-stu-id="55ad8-105">Creating the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] host project.</span></span>

-   <span data-ttu-id="55ad8-106">添加可本地化的内容。</span><span class="sxs-lookup"><span data-stu-id="55ad8-106">Adding localizable content.</span></span>

-   <span data-ttu-id="55ad8-107">启用本地化。</span><span class="sxs-lookup"><span data-stu-id="55ad8-107">Enabling localization.</span></span>

-   <span data-ttu-id="55ad8-108">分配资源标识符。</span><span class="sxs-lookup"><span data-stu-id="55ad8-108">Assigning resource identifiers.</span></span>

-   <span data-ttu-id="55ad8-109">使用 LocBaml 工具生成附属程序集。</span><span class="sxs-lookup"><span data-stu-id="55ad8-109">Using the LocBaml tool to produce a satellite assembly.</span></span>

<span data-ttu-id="55ad8-110">在本演练中所涉及任务的完整代码列表，请参阅[本地化混合应用程序示例](https://go.microsoft.com/fwlink/?LinkID=160015)。</span><span class="sxs-lookup"><span data-stu-id="55ad8-110">For a complete code listing of the tasks illustrated in this walkthrough, see [Localizing a Hybrid Application Sample](https://go.microsoft.com/fwlink/?LinkID=160015).</span></span>

<span data-ttu-id="55ad8-111">完成后，你将拥有一个本地化的混合应用程序。</span><span class="sxs-lookup"><span data-stu-id="55ad8-111">When you are finished, you will have a localized hybrid application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="55ad8-112">系统必备</span><span class="sxs-lookup"><span data-stu-id="55ad8-112">Prerequisites</span></span>

<span data-ttu-id="55ad8-113">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="55ad8-113">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="55ad8-114">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="55ad8-114">Visual Studio 2017</span></span>

## <a name="creating-the-windows-forms-host-project"></a><span data-ttu-id="55ad8-115">创建 Windows 窗体宿主项目</span><span class="sxs-lookup"><span data-stu-id="55ad8-115">Creating the Windows Forms Host Project</span></span>

<span data-ttu-id="55ad8-116">第一步是创建[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]应用程序项目，并添加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]包含要本地化的内容元素。</span><span class="sxs-lookup"><span data-stu-id="55ad8-116">The first step is to create the [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] application project and add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element with content that you will localize.</span></span>

### <a name="to-create-the-host-project"></a><span data-ttu-id="55ad8-117">创建宿主项目</span><span class="sxs-lookup"><span data-stu-id="55ad8-117">To create the host project</span></span>

1. <span data-ttu-id="55ad8-118">创建**WPF 应用程序**名为项目`LocalizingWpfInWf`。</span><span class="sxs-lookup"><span data-stu-id="55ad8-118">Create a **WPF App** project named `LocalizingWpfInWf`.</span></span>  <span data-ttu-id="55ad8-119">(**文件** > **新** > **项目** > **Visual C#** 或**Visual Basic**  > **经典桌面** > **WPF 应用程序**)。</span><span class="sxs-lookup"><span data-stu-id="55ad8-119">(**File** > **New** > **Project** > **Visual C#** or **Visual Basic** > **Classic Desktop** > **WPF Application**).</span></span>

2. <span data-ttu-id="55ad8-120">添加[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl>元素称为`SimpleControl`到项目。</span><span class="sxs-lookup"><span data-stu-id="55ad8-120">Add a [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]<xref:System.Windows.Controls.UserControl> element called `SimpleControl` to the project.</span></span>

3. <span data-ttu-id="55ad8-121">使用<xref:System.Windows.Forms.Integration.ElementHost>控件中放置`SimpleControl`窗体上的元素。</span><span class="sxs-lookup"><span data-stu-id="55ad8-121">Use the <xref:System.Windows.Forms.Integration.ElementHost> control to place a `SimpleControl` element on the form.</span></span> <span data-ttu-id="55ad8-122">有关详细信息，请参见[演练：承载 3-D WPF 复合控件在 Windows 窗体中的](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="55ad8-122">For more information, see [Walkthrough: Hosting a 3-D WPF Composite Control in Windows Forms](walkthrough-hosting-a-3-d-wpf-composite-control-in-windows-forms.md).</span></span>

## <a name="adding-localizable-content"></a><span data-ttu-id="55ad8-123">添加可本地化的内容</span><span class="sxs-lookup"><span data-stu-id="55ad8-123">Adding Localizable Content</span></span>

<span data-ttu-id="55ad8-124">接下来，您将添加[!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)]标签控件，并设置[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]到可本地化的字符串的元素的内容。</span><span class="sxs-lookup"><span data-stu-id="55ad8-124">Next, you will add a [!INCLUDE[TLA#tla_winforms](../../../../includes/tlasharptla-winforms-md.md)] label control and set the [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] element's content to a localizable string.</span></span>

### <a name="to-add-localizable-content"></a><span data-ttu-id="55ad8-125">添加可本地化的内容</span><span class="sxs-lookup"><span data-stu-id="55ad8-125">To add localizable content</span></span>

1. <span data-ttu-id="55ad8-126">在中**解决方案资源管理器**，双击**SimpleControl.xaml**中打开[!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="55ad8-126">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the [!INCLUDE[wpfdesigner_current_short](../../../../includes/wpfdesigner-current-short-md.md)].</span></span>

2. <span data-ttu-id="55ad8-127">设置的内容<xref:System.Windows.Controls.Button>控制是通过使用下面的代码。</span><span class="sxs-lookup"><span data-stu-id="55ad8-127">Set the content of the <xref:System.Windows.Controls.Button> control using the following code.</span></span>

     [!code-xaml[LocalizingWpfInWf#10](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl0.xaml#10)]

3. <span data-ttu-id="55ad8-128">在中**解决方案资源管理器**，双击**Form1**若要在 Windows 窗体设计器中打开它。</span><span class="sxs-lookup"><span data-stu-id="55ad8-128">In **Solution Explorer**, double-click **Form1** to open it in the Windows Forms Designer.</span></span>

4. <span data-ttu-id="55ad8-129">打开**工具箱**，然后双击**标签**标签控件添加到窗体。</span><span class="sxs-lookup"><span data-stu-id="55ad8-129">Open the **Toolbox** and double-click **Label** to add a label control to the form.</span></span> <span data-ttu-id="55ad8-130">将其 <xref:System.Windows.Forms.Control.Text%2A> 属性的值设置为 `"Hello"`。</span><span class="sxs-lookup"><span data-stu-id="55ad8-130">Set the value of its <xref:System.Windows.Forms.Control.Text%2A> property to `"Hello"`.</span></span>

5. <span data-ttu-id="55ad8-131">按 F5 生成并运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="55ad8-131">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="55ad8-132">这两个`SimpleControl`元素和标签控件显示文本 **"Hello"**。</span><span class="sxs-lookup"><span data-stu-id="55ad8-132">Both the `SimpleControl` element and the label control display the text **"Hello"**.</span></span>

## <a name="enabling-localization"></a><span data-ttu-id="55ad8-133">启用本地化</span><span class="sxs-lookup"><span data-stu-id="55ad8-133">Enabling Localization</span></span>

<span data-ttu-id="55ad8-134">Windows 窗体设计器提供用于在附属程序集中启用本地化的设置。</span><span class="sxs-lookup"><span data-stu-id="55ad8-134">The Windows Forms Designer provides settings for enabling localization in a satellite assembly.</span></span>

### <a name="to-enable-localization"></a><span data-ttu-id="55ad8-135">启用本地化</span><span class="sxs-lookup"><span data-stu-id="55ad8-135">To enable localization</span></span>

1. <span data-ttu-id="55ad8-136">在中**解决方案资源管理器**，双击**Form1.cs**若要在 Windows 窗体设计器中打开它。</span><span class="sxs-lookup"><span data-stu-id="55ad8-136">In **Solution Explorer**, double-click **Form1.cs** to open it in the Windows Forms Designer.</span></span>

2. <span data-ttu-id="55ad8-137">在中**属性**窗口中，将窗体的值**Localizable**属性设置为`true`。</span><span class="sxs-lookup"><span data-stu-id="55ad8-137">In the **Properties** window, set the value of the form's **Localizable** property to `true`.</span></span>

3. <span data-ttu-id="55ad8-138">在中**属性**窗口中，设置的值**语言**属性设置为**西班牙语 （西班牙）**。</span><span class="sxs-lookup"><span data-stu-id="55ad8-138">In the **Properties** window, set the value of the **Language** property to **Spanish (Spain)**.</span></span>

4. <span data-ttu-id="55ad8-139">在 Windows 窗体设计器中，选择标签控件。</span><span class="sxs-lookup"><span data-stu-id="55ad8-139">In the Windows Forms Designer, select the label control.</span></span>

5. <span data-ttu-id="55ad8-140">在中**属性**窗口中，设置的值<xref:System.Windows.Forms.Control.Text%2A>属性设置为`"Hola"`。</span><span class="sxs-lookup"><span data-stu-id="55ad8-140">In the **Properties** window, set the value of the <xref:System.Windows.Forms.Control.Text%2A> property to `"Hola"`.</span></span>

     <span data-ttu-id="55ad8-141">一个名为 Form1.es-ES.resx 的新资源文件会添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="55ad8-141">A new resource file named Form1.es-ES.resx is added to the project.</span></span>

6. <span data-ttu-id="55ad8-142">在中**解决方案资源管理器**，右键单击**Form1.cs**然后单击**查看代码**以在代码编辑器中打开它。</span><span class="sxs-lookup"><span data-stu-id="55ad8-142">In **Solution Explorer**, right-click **Form1.cs** and click **View Code** to open it in the Code Editor.</span></span>

7. <span data-ttu-id="55ad8-143">以下代码复制到`Form1`构造函数，然后调用`InitializeComponent`。</span><span class="sxs-lookup"><span data-stu-id="55ad8-143">Copy the following code into the `Form1` constructor, preceding the call to `InitializeComponent`.</span></span>

     [!code-csharp[LocalizingWpfInWf#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/Form1.cs#2)]

8. <span data-ttu-id="55ad8-144">在中**解决方案资源管理器**，右键单击**LocalizingWpfInWf**然后单击**卸载项目**。</span><span class="sxs-lookup"><span data-stu-id="55ad8-144">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Unload Project**.</span></span>

     <span data-ttu-id="55ad8-145">项目名称将标记为 **（不可用）**。</span><span class="sxs-lookup"><span data-stu-id="55ad8-145">The project name is labeled **(unavailable)**.</span></span>

9. <span data-ttu-id="55ad8-146">右键单击**LocalizingWpfInWf**，然后单击**编辑 LocalizingWpfInWf.csproj**。</span><span class="sxs-lookup"><span data-stu-id="55ad8-146">Right-click **LocalizingWpfInWf**, and click **Edit LocalizingWpfInWf.csproj**.</span></span>

     <span data-ttu-id="55ad8-147">项目文件将在代码编辑器中打开。</span><span class="sxs-lookup"><span data-stu-id="55ad8-147">The project file opens in the Code Editor.</span></span>

10. <span data-ttu-id="55ad8-148">将以下行复制到第一个`PropertyGroup`项目文件中。</span><span class="sxs-lookup"><span data-stu-id="55ad8-148">Copy the following line into the first `PropertyGroup` in the project file.</span></span>

    ```xml
    <UICulture>en-US</UICulture>
    ```

11. <span data-ttu-id="55ad8-149">保存项目文件并将其关闭。</span><span class="sxs-lookup"><span data-stu-id="55ad8-149">Save the project file and close it.</span></span>

12. <span data-ttu-id="55ad8-150">在中**解决方案资源管理器**，右键单击**LocalizingWpfInWf**然后单击**重新加载项目**。</span><span class="sxs-lookup"><span data-stu-id="55ad8-150">In **Solution Explorer**, right-click **LocalizingWpfInWf** and click **Reload Project**.</span></span>

## <a name="assigning-resource-identifiers"></a><span data-ttu-id="55ad8-151">分配资源标识符</span><span class="sxs-lookup"><span data-stu-id="55ad8-151">Assigning Resource Identifiers</span></span>

<span data-ttu-id="55ad8-152">可以通过使用资源标识符将可本地化内容映射到资源程序集。</span><span class="sxs-lookup"><span data-stu-id="55ad8-152">You can map your localizable content to resource assemblies by using resource identifiers.</span></span> <span data-ttu-id="55ad8-153">MsBuild.exe 应用程序会自动分配资源标识符，当您指定`updateuid`选项。</span><span class="sxs-lookup"><span data-stu-id="55ad8-153">The MsBuild.exe application automatically assigns resource identifiers when you specify the `updateuid` option.</span></span>

### <a name="to-assign-resource-identifiers"></a><span data-ttu-id="55ad8-154">分配资源标识符</span><span class="sxs-lookup"><span data-stu-id="55ad8-154">To assign resource identifiers</span></span>

1. <span data-ttu-id="55ad8-155">从开始菜单中，打开 Visual Studio 开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="55ad8-155">From the Start Menu, open the Developer Command Prompt for Visual Studio.</span></span>

2. <span data-ttu-id="55ad8-156">使用以下命令将资源标识符分配到可本地化内容。</span><span class="sxs-lookup"><span data-stu-id="55ad8-156">Use the following command to assign resource identifiers to your localizable content.</span></span>

    ```
    msbuild -t:updateuid LocalizingWpfInWf.csproj
    ```

3. <span data-ttu-id="55ad8-157">在中**解决方案资源管理器**，双击**SimpleControl.xaml**以在代码编辑器中打开它。</span><span class="sxs-lookup"><span data-stu-id="55ad8-157">In **Solution Explorer**, double-click **SimpleControl.xaml** to open it in the Code Editor.</span></span> <span data-ttu-id="55ad8-158">你将看到`msbuild`命令添加`Uid`所有元素的都属性。</span><span class="sxs-lookup"><span data-stu-id="55ad8-158">You will see that the `msbuild` command has added the `Uid` attribute to all the elements.</span></span> <span data-ttu-id="55ad8-159">这有助于通过分配资源标识符进行本地化。</span><span class="sxs-lookup"><span data-stu-id="55ad8-159">This facilitates localization through the assignment of resource identifiers.</span></span>

     [!code-xaml[LocalizingWpfInWf#20](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizingWpfInWf/CSharp/SimpleControl.xaml#20)]

4. <span data-ttu-id="55ad8-160">按**F6**以生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="55ad8-160">Press **F6** to build the solution.</span></span>

## <a name="using-locbaml-to-produce-a-satellite-assembly"></a><span data-ttu-id="55ad8-161">使用 LocBaml 生成附属程序集</span><span class="sxs-lookup"><span data-stu-id="55ad8-161">Using LocBaml to Produce a Satellite Assembly</span></span>

<span data-ttu-id="55ad8-162">本地化的内容存储在纯资源*附属程序集*。</span><span class="sxs-lookup"><span data-stu-id="55ad8-162">Your localized content is stored in a resource-only *satellite assembly*.</span></span> <span data-ttu-id="55ad8-163">使用命令行工具 LocBaml.exe 生成本地化程序集为你[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]内容。</span><span class="sxs-lookup"><span data-stu-id="55ad8-163">Use the command-line tool LocBaml.exe to produce a localized assembly for your [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] content.</span></span>

### <a name="to-produce-a-satellite-assembly"></a><span data-ttu-id="55ad8-164">生成附属程序集</span><span class="sxs-lookup"><span data-stu-id="55ad8-164">To produce a satellite assembly</span></span>

1. <span data-ttu-id="55ad8-165">将 LocBaml.exe 复制到项目的 obj\Debug 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55ad8-165">Copy LocBaml.exe to your project's obj\Debug folder.</span></span> <span data-ttu-id="55ad8-166">有关详细信息，请参阅[本地化应用程序](how-to-localize-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="55ad8-166">For more information, see [Localize an Application](how-to-localize-an-application.md).</span></span>

2. <span data-ttu-id="55ad8-167">在“命令提示符”窗口中，使用以下命令将资源字符串提取到临时文件中。</span><span class="sxs-lookup"><span data-stu-id="55ad8-167">In the Command Prompt window, use the following command to extract resource strings into a temporary file.</span></span>

    ```
    LocBaml /parse LocalizingWpfInWf.g.en-US.resources /out:temp.csv
    ```

3. <span data-ttu-id="55ad8-168">使用 Visual Studio 或其他文本编辑器打开 temp.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="55ad8-168">Open the temp.csv file with Visual Studio or another text editor.</span></span> <span data-ttu-id="55ad8-169">字符串替换为`"Hello"`使用其西班牙语翻译`"Hola"`。</span><span class="sxs-lookup"><span data-stu-id="55ad8-169">Replace the string `"Hello"` with its Spanish translation, `"Hola"`.</span></span>

4. <span data-ttu-id="55ad8-170">保存 temp.csv 文件。</span><span class="sxs-lookup"><span data-stu-id="55ad8-170">Save the temp.csv file.</span></span>

5. <span data-ttu-id="55ad8-171">使用以下命令生成本地化资源文件。</span><span class="sxs-lookup"><span data-stu-id="55ad8-171">Use the following command to generate the localized resource file.</span></span>

    ```
    LocBaml /generate /trans:temp.csv LocalizingWpfInWf.g.en-US.resources /out:. /cul:es-ES
    ```

     <span data-ttu-id="55ad8-172">将在 obj\Debug 文件夹中创建 LocalizingWpfInWf.g.es-ES.resources 文件。</span><span class="sxs-lookup"><span data-stu-id="55ad8-172">The LocalizingWpfInWf.g.es-ES.resources file is created in the obj\Debug folder.</span></span>

6. <span data-ttu-id="55ad8-173">使用以下命令生成本地化附属程序集。</span><span class="sxs-lookup"><span data-stu-id="55ad8-173">Use the following command to build the localized satellite assembly.</span></span>

    ```
    Al.exe /out:LocalizingWpfInWf.resources.dll /culture:es-ES /embed:LocalizingWpfInWf.Form1.es-ES.resources /embed:LocalizingWpfInWf.g.es-ES.resources
    ```

     <span data-ttu-id="55ad8-174">将在 obj\Debug 文件夹中创建 LocalizingWpfInWf.resources.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="55ad8-174">The LocalizingWpfInWf.resources.dll file is created in the obj\Debug folder.</span></span>

7. <span data-ttu-id="55ad8-175">将 LocalizingWpfInWf.resources.dll 文件复制到项目的 bin\Debug\es-ES 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55ad8-175">Copy the LocalizingWpfInWf.resources.dll file to the project's bin\Debug\es-ES folder.</span></span> <span data-ttu-id="55ad8-176">替换现有文件。</span><span class="sxs-lookup"><span data-stu-id="55ad8-176">Replace the existing file.</span></span>

8. <span data-ttu-id="55ad8-177">运行 LocalizingWpfInWf.exe，它位于项目的 bin\Debug 文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55ad8-177">Run LocalizingWpfInWf.exe, which is located in your project's bin\Debug folder.</span></span> <span data-ttu-id="55ad8-178">不要重新生成应用程序，否则附属程序集将被覆盖。</span><span class="sxs-lookup"><span data-stu-id="55ad8-178">Do not rebuild the application or the satellite assembly will be overwritten.</span></span>

     <span data-ttu-id="55ad8-179">应用程序显示本地化后的字符串，而不是英语字符串。</span><span class="sxs-lookup"><span data-stu-id="55ad8-179">The application shows the localized strings instead of the English strings.</span></span>

## <a name="see-also"></a><span data-ttu-id="55ad8-180">请参阅</span><span class="sxs-lookup"><span data-stu-id="55ad8-180">See also</span></span>

- <xref:System.Windows.Forms.Integration.ElementHost>
- <xref:System.Windows.Forms.Integration.WindowsFormsHost>
- [<span data-ttu-id="55ad8-181">对应用程序进行本地化</span><span class="sxs-lookup"><span data-stu-id="55ad8-181">Localize an Application</span></span>](how-to-localize-an-application.md)
- [<span data-ttu-id="55ad8-182">演练：本地化 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="55ad8-182">Walkthrough: Localizing Windows Forms</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/y99d1cd3(v=vs.100))
- [<span data-ttu-id="55ad8-183">在 Visual Studio 中设计 XAML</span><span class="sxs-lookup"><span data-stu-id="55ad8-183">Design XAML in Visual Studio</span></span>](/visualstudio/designers/designing-xaml-in-visual-studio)
