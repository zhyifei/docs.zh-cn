---
title: 演练：缓存在 WPF 应用程序的应用程序数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 886a436f845aa4ba9662e75cbc9e534e915a4cfa
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57361169"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="d5165-102">演练：缓存在 WPF 应用程序的应用程序数据</span><span class="sxs-lookup"><span data-stu-id="d5165-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="d5165-103">缓存可以将数据存储在内存中以便快速访问。</span><span class="sxs-lookup"><span data-stu-id="d5165-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="d5165-104">再次访问数据时，应用程序可以从缓存获取数据，而不是从原始源检索数据。</span><span class="sxs-lookup"><span data-stu-id="d5165-104">When the data is accessed again, applications can get the data from the cache instead of retrieving it from the original source.</span></span> <span data-ttu-id="d5165-105">这可改善性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="d5165-105">This can improve performance and scalability.</span></span> <span data-ttu-id="d5165-106">此外，数据源暂时不可用时，缓存可提供数据。</span><span class="sxs-lookup"><span data-stu-id="d5165-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>

 <span data-ttu-id="d5165-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]提供了使你能够使用缓存中的类[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5165-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="d5165-108">这些类都位于<xref:System.Runtime.Caching>命名空间。</span><span class="sxs-lookup"><span data-stu-id="d5165-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="d5165-109"><xref:System.Runtime.Caching>命名空间是中的新增功能[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5165-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="d5165-110">此命名空间使缓存可供所有[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5165-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="d5165-111">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 以前的版本中，缓存仅在 <xref:System.Web> 命名空间可用，因此，需要 ASP.NET 类上的一个依赖项。</span><span class="sxs-lookup"><span data-stu-id="d5165-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>

 <span data-ttu-id="d5165-112">本演练演示如何使用缓存功能，现已推出[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]作为的一部分[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5165-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="d5165-113">在本演练中，你将缓存的文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-113">In the walkthrough, you cache the contents of a text file.</span></span>

 <span data-ttu-id="d5165-114">本演练演示以下任务：</span><span class="sxs-lookup"><span data-stu-id="d5165-114">Tasks illustrated in this walkthrough include the following:</span></span>

-   <span data-ttu-id="d5165-115">创建 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="d5165-115">Creating a WPF application project.</span></span>

-   <span data-ttu-id="d5165-116">添加对引用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5165-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>

-   <span data-ttu-id="d5165-117">正在初始化缓存。</span><span class="sxs-lookup"><span data-stu-id="d5165-117">Initializing a cache.</span></span>

-   <span data-ttu-id="d5165-118">正在添加的缓存项的包含文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-118">Adding a cache entry that contains the contents of a text file.</span></span>

-   <span data-ttu-id="d5165-119">提供的缓存项的逐出策略。</span><span class="sxs-lookup"><span data-stu-id="d5165-119">Providing an eviction policy for the cache entry.</span></span>

-   <span data-ttu-id="d5165-120">监视缓存的文件的路径和通知的缓存实例更改为受监视的项目。</span><span class="sxs-lookup"><span data-stu-id="d5165-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d5165-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="d5165-121">Prerequisites</span></span>
 <span data-ttu-id="d5165-122">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="d5165-122">In order to complete this walkthrough, you will need:</span></span>

-   <span data-ttu-id="d5165-123">Microsoft Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="d5165-123">Microsoft Visual Studio 2010.</span></span>

-   <span data-ttu-id="d5165-124">包含少量的文本的文本文件。</span><span class="sxs-lookup"><span data-stu-id="d5165-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="d5165-125">（您将显示文本文件的内容在消息框中。）在本演练中所示的代码假定正在使用以下文件：</span><span class="sxs-lookup"><span data-stu-id="d5165-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>

     `c:\cache\cacheText.txt`

     <span data-ttu-id="d5165-126">但是，可以使用任何文本文件，并为本演练中的代码进行微小的更改。</span><span class="sxs-lookup"><span data-stu-id="d5165-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>

## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="d5165-127">创建 WPF 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="d5165-127">Creating a WPF Application Project</span></span>
 <span data-ttu-id="d5165-128">您将首先创建一个 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="d5165-128">You will start by creating a WPF application project.</span></span>

#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="d5165-129">创建 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="d5165-129">To create a WPF application</span></span>

1.  <span data-ttu-id="d5165-130">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="d5165-130">Start Visual Studio.</span></span>

2.  <span data-ttu-id="d5165-131">在中**文件**菜单上，单击**新建**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="d5165-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>

     <span data-ttu-id="d5165-132">随即显示“新建项目”对话框。</span><span class="sxs-lookup"><span data-stu-id="d5165-132">The **New Project** dialog box is displayed.</span></span>

3.  <span data-ttu-id="d5165-133">下**已安装的模板**，选择你想要使用的编程语言 (**Visual Basic**或**Visual C#**)。</span><span class="sxs-lookup"><span data-stu-id="d5165-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>

4.  <span data-ttu-id="d5165-134">在中**新的项目**对话框中，选择**WPF 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d5165-134">In the **New Project** dialog box, select **WPF Application**.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d5165-135">如果没有看到**WPF 应用程序**模板，请确保您的目标版本的[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]支持 WPF。</span><span class="sxs-lookup"><span data-stu-id="d5165-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="d5165-136">在中**新的项目**对话框中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]从列表中。</span><span class="sxs-lookup"><span data-stu-id="d5165-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>

5.  <span data-ttu-id="d5165-137">在中**名称**文字框中，输入你的项目的名称。</span><span class="sxs-lookup"><span data-stu-id="d5165-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="d5165-138">例如，可以输入**WPFCaching**。</span><span class="sxs-lookup"><span data-stu-id="d5165-138">For example, you can enter **WPFCaching**.</span></span>

6.  <span data-ttu-id="d5165-139">选择“为解决方案创建目录”复选框。</span><span class="sxs-lookup"><span data-stu-id="d5165-139">Select the **Create directory for solution** check box.</span></span>

7.  <span data-ttu-id="d5165-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d5165-140">Click **OK**.</span></span>

     <span data-ttu-id="d5165-141">WPF 设计器中打开**设计**查看，并显示 MainWindow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="d5165-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="d5165-142">Visual Studio 将创建**我的项目**文件夹、 Application.xaml 文件和 MainWindow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="d5165-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="d5165-143">面向.NET Framework 并添加对缓存程序集的引用</span><span class="sxs-lookup"><span data-stu-id="d5165-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>
 <span data-ttu-id="d5165-144">默认情况下，WPF 应用程序目标[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5165-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="d5165-145">若要使用<xref:System.Runtime.Caching>WPF 应用程序中的命名空间，该应用程序必须面向[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)](不[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)])，并且必须包括对命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="d5165-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>

 <span data-ttu-id="d5165-146">因此下, 一步将更改.NET Framework 目标，并添加对引用<xref:System.Runtime.Caching>命名空间。</span><span class="sxs-lookup"><span data-stu-id="d5165-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>

> [!NOTE]
>  <span data-ttu-id="d5165-147">.NET Framework 目标更改的过程是不同的 Visual Basic 项目中并在 Visual C# 项目中。</span><span class="sxs-lookup"><span data-stu-id="d5165-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="d5165-148">若要更改的目标在 Visual Basic 中的.NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5165-148">To change the target .NET Framework in Visual Basic</span></span>

1.  <span data-ttu-id="d5165-149">在中**解决方案资源管理器**，右键单击项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d5165-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>

     <span data-ttu-id="d5165-150">显示应用程序的属性窗口。</span><span class="sxs-lookup"><span data-stu-id="d5165-150">The properties window for the application is displayed.</span></span>

2.  <span data-ttu-id="d5165-151">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="d5165-151">Click the **Compile** tab.</span></span>

3.  <span data-ttu-id="d5165-152">在窗口的底部，单击**高级编译选项...**.</span><span class="sxs-lookup"><span data-stu-id="d5165-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>

     <span data-ttu-id="d5165-153">**高级编译器设置**显示对话框。</span><span class="sxs-lookup"><span data-stu-id="d5165-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>

4.  <span data-ttu-id="d5165-154">在中**目标框架 （所有配置）** 列表中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5165-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="d5165-155">(不要选择[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="d5165-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>

5.  <span data-ttu-id="d5165-156">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d5165-156">Click **OK**.</span></span>

     <span data-ttu-id="d5165-157">随即显示“目标框架更改”对话框。</span><span class="sxs-lookup"><span data-stu-id="d5165-157">The **Target Framework Change** dialog box is displayed.</span></span>

6.  <span data-ttu-id="d5165-158">在中**目标 Framework 更改**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="d5165-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>

     <span data-ttu-id="d5165-159">项目已关闭，然后重新打开它。</span><span class="sxs-lookup"><span data-stu-id="d5165-159">The project is closed and is then reopened.</span></span>

7.  <span data-ttu-id="d5165-160">通过执行以下步骤添加对缓存程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="d5165-160">Add a reference to the caching assembly by following these steps:</span></span>

    1.  <span data-ttu-id="d5165-161">在中**解决方案资源管理器**，右键单击项目的名称，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d5165-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>

    2.  <span data-ttu-id="d5165-162">选择 **.NET**选项卡上，选择`System.Runtime.Caching`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d5165-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="d5165-163">若要更改 Visual C# 项目中的目标.NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5165-163">To change the target .NET Framework in a Visual C# project</span></span>

1.  <span data-ttu-id="d5165-164">在中**解决方案资源管理器**，右键单击项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="d5165-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>

     <span data-ttu-id="d5165-165">显示应用程序的属性窗口。</span><span class="sxs-lookup"><span data-stu-id="d5165-165">The properties window for the application is displayed.</span></span>

2.  <span data-ttu-id="d5165-166">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="d5165-166">Click the **Application** tab.</span></span>

3.  <span data-ttu-id="d5165-167">在中**目标框架**列表中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5165-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="d5165-168">(不要选择 **.NET Framework 4 Client Profile**。)</span><span class="sxs-lookup"><span data-stu-id="d5165-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>

4.  <span data-ttu-id="d5165-169">通过执行以下步骤添加对缓存程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="d5165-169">Add a reference to the caching assembly by following these steps:</span></span>

    1.  <span data-ttu-id="d5165-170">右键单击**引用**文件夹，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="d5165-170">Right-click the **References** folder and then click **Add Reference**.</span></span>

    2.  <span data-ttu-id="d5165-171">选择 **.NET**选项卡上，选择`System.Runtime.Caching`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d5165-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>

## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="d5165-172">将按钮添加到 WPF 窗口</span><span class="sxs-lookup"><span data-stu-id="d5165-172">Adding a Button to the WPF Window</span></span>
 <span data-ttu-id="d5165-173">接下来，您将添加一个按钮控件，并创建为按钮的事件处理程序`Click`事件。</span><span class="sxs-lookup"><span data-stu-id="d5165-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="d5165-174">更高版本将添加代码，以便当单击按钮时，缓存并显示文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>

#### <a name="to-add-a-button-control"></a><span data-ttu-id="d5165-175">若要添加一个按钮控件</span><span class="sxs-lookup"><span data-stu-id="d5165-175">To add a button control</span></span>

1.  <span data-ttu-id="d5165-176">在中**解决方案资源管理器**，双击 MainWindow.xaml 文件以将其打开。</span><span class="sxs-lookup"><span data-stu-id="d5165-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>

2.  <span data-ttu-id="d5165-177">从**工具箱**下**常用 WPF 控件**，将`Button`控制对`MainWindow`窗口。</span><span class="sxs-lookup"><span data-stu-id="d5165-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>

3.  <span data-ttu-id="d5165-178">在中**属性**窗口中，将`Content`的属性`Button`控制对**获取缓存**。</span><span class="sxs-lookup"><span data-stu-id="d5165-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>

## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="d5165-179">正在初始化缓存和缓存条目</span><span class="sxs-lookup"><span data-stu-id="d5165-179">Initializing the Cache and Caching an Entry</span></span>
 <span data-ttu-id="d5165-180">接下来，将添加代码以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="d5165-180">Next, you will add the code to perform the following tasks:</span></span>

-   <span data-ttu-id="d5165-181">创建缓存类的实例 — 也就是说，您将实例化一个新<xref:System.Runtime.Caching.MemoryCache>对象。</span><span class="sxs-lookup"><span data-stu-id="d5165-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>

-   <span data-ttu-id="d5165-182">指定缓存使用<xref:System.Runtime.Caching.HostFileChangeMonitor>对象来监视在文本文件中的更改。</span><span class="sxs-lookup"><span data-stu-id="d5165-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>

-   <span data-ttu-id="d5165-183">读取该文本文件并缓存其内容作为缓存项。</span><span class="sxs-lookup"><span data-stu-id="d5165-183">Read the text file and cache its contents as a cache entry.</span></span>

-   <span data-ttu-id="d5165-184">显示缓存的文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-184">Display the contents of the cached text file.</span></span>

#### <a name="to-create-the-cache-object"></a><span data-ttu-id="d5165-185">若要创建缓存对象</span><span class="sxs-lookup"><span data-stu-id="d5165-185">To create the cache object</span></span>

1.  <span data-ttu-id="d5165-186">双击您只是为了在 MainWindow.xaml.cs 或 MainWindow.Xaml.vb 文件创建一个事件处理程序添加的按钮。</span><span class="sxs-lookup"><span data-stu-id="d5165-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>

2.  <span data-ttu-id="d5165-187">（在类声明中） 的文件的顶部添加以下`Imports`(Visual Basic) 或`using`(C#) 语句：</span><span class="sxs-lookup"><span data-stu-id="d5165-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3.  <span data-ttu-id="d5165-188">事件处理程序中，添加以下代码以实例化的缓存对象：</span><span class="sxs-lookup"><span data-stu-id="d5165-188">In the event handler, add the following code to instantiate the cache object:</span></span>

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <span data-ttu-id="d5165-189"><xref:System.Runtime.Caching.ObjectCache>类是一个内置的类，提供内存中对象缓存。</span><span class="sxs-lookup"><span data-stu-id="d5165-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>

4.  <span data-ttu-id="d5165-190">添加以下代码以读取内容的名为某个缓存项`filecontents`:</span><span class="sxs-lookup"><span data-stu-id="d5165-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5.  <span data-ttu-id="d5165-191">添加以下代码以检查是否为命名的缓存项`filecontents`存在：</span><span class="sxs-lookup"><span data-stu-id="d5165-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     <span data-ttu-id="d5165-192">如果指定的缓存条目不存在，必须读取该文本文件并将其作为某个缓存项添加到缓存。</span><span class="sxs-lookup"><span data-stu-id="d5165-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>

6.  <span data-ttu-id="d5165-193">在中`if/then`块中，添加以下代码以创建一个新<xref:System.Runtime.Caching.CacheItemPolicy>对象，它指定缓存项将在 10 秒后过期。</span><span class="sxs-lookup"><span data-stu-id="d5165-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     <span data-ttu-id="d5165-194">如果未不提供任何逐出或过期的信息，默认值是<xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>，这意味着缓存项永远不会过期时间取决于只有一个绝对时间。</span><span class="sxs-lookup"><span data-stu-id="d5165-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="d5165-195">相反，缓存条目过期仅当内存压力时。</span><span class="sxs-lookup"><span data-stu-id="d5165-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="d5165-196">作为最佳做法，应始终显式提供绝对或可调到期。</span><span class="sxs-lookup"><span data-stu-id="d5165-196">As a best practice, you should always explicitly provide either an absolute or a sliding expiration.</span></span>

7.  <span data-ttu-id="d5165-197">内部`if/then`阻止和上一步中添加的代码，添加以下代码以创建你想要监视，并将文本文件的路径添加到集合的文件路径的集合：</span><span class="sxs-lookup"><span data-stu-id="d5165-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  <span data-ttu-id="d5165-198">如果不是你想要使用的文本文件`c:\cache\cacheText.txt`，指定的文本文件是你想要使用的路径。</span><span class="sxs-lookup"><span data-stu-id="d5165-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>

8.  <span data-ttu-id="d5165-199">在上一步骤中，添加的代码后面添加以下代码以添加新<xref:System.Runtime.Caching.HostFileChangeMonitor>到更改的集合对象监视缓存项：</span><span class="sxs-lookup"><span data-stu-id="d5165-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <span data-ttu-id="d5165-200"><xref:System.Runtime.Caching.HostFileChangeMonitor>对象可监视文本文件的路径并通知缓存，如果在发生更改。</span><span class="sxs-lookup"><span data-stu-id="d5165-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="d5165-201">在此示例中，如果文件的内容发生更改，将过期的缓存项。</span><span class="sxs-lookup"><span data-stu-id="d5165-201">In this example, the cache entry will expire if the content of the file changes.</span></span>

9. <span data-ttu-id="d5165-202">在上一步中添加该代码之后添加以下代码以读取文本文件的内容：</span><span class="sxs-lookup"><span data-stu-id="d5165-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     <span data-ttu-id="d5165-203">以便你将能够看到该缓存项过期时添加的日期和时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="d5165-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>

10. <span data-ttu-id="d5165-204">在上一步骤中，添加的代码后面添加以下代码以将该文件的内容插入到缓存对象作为<xref:System.Runtime.Caching.CacheItem>实例：</span><span class="sxs-lookup"><span data-stu-id="d5165-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     <span data-ttu-id="d5165-205">指定有关如何通过将传递逐出缓存项的信息<xref:System.Runtime.Caching.CacheItemPolicy>作为参数前面创建的对象。</span><span class="sxs-lookup"><span data-stu-id="d5165-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>

11. <span data-ttu-id="d5165-206">之后`if/then`块中，添加以下代码以在消息框中显示缓存的文件内容：</span><span class="sxs-lookup"><span data-stu-id="d5165-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. <span data-ttu-id="d5165-207">在中**构建**菜单上，单击**生成 WPFCaching**生成项目。</span><span class="sxs-lookup"><span data-stu-id="d5165-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>

## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="d5165-208">测试在缓存中的 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="d5165-208">Testing Caching in the WPF Application</span></span>
 <span data-ttu-id="d5165-209">现在可以测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5165-209">You can now test the application.</span></span>

#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="d5165-210">若要测试的 WPF 应用程序中的缓存</span><span class="sxs-lookup"><span data-stu-id="d5165-210">To test caching in the WPF application</span></span>

1.  <span data-ttu-id="d5165-211">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="d5165-211">Press CTRL+F5 to run the application.</span></span>

     <span data-ttu-id="d5165-212">`MainWindow`显示窗口。</span><span class="sxs-lookup"><span data-stu-id="d5165-212">The `MainWindow` window is displayed.</span></span>

2.  <span data-ttu-id="d5165-213">单击**中获取缓存**。</span><span class="sxs-lookup"><span data-stu-id="d5165-213">Click **Get Cache**.</span></span>

     <span data-ttu-id="d5165-214">在消息框中显示文本文件中缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="d5165-215">请注意，该文件上的时间戳。</span><span class="sxs-lookup"><span data-stu-id="d5165-215">Notice the timestamp on the file.</span></span>

3.  <span data-ttu-id="d5165-216">关闭消息框，然后单击**获取缓存**试。</span><span class="sxs-lookup"><span data-stu-id="d5165-216">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d5165-217">时间戳保持不变。</span><span class="sxs-lookup"><span data-stu-id="d5165-217">The timestamp is unchanged.</span></span> <span data-ttu-id="d5165-218">这将指示显示缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-218">This indicates the cached content is displayed.</span></span>

4.  <span data-ttu-id="d5165-219">等待 10 秒或更长，然后单击**获取缓存**试。</span><span class="sxs-lookup"><span data-stu-id="d5165-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d5165-220">此时将显示新时间戳。</span><span class="sxs-lookup"><span data-stu-id="d5165-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="d5165-221">这表示该策略允许缓存项过期，并且将显示新缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>

5.  <span data-ttu-id="d5165-222">在文本编辑器中，打开您创建的文本文件。</span><span class="sxs-lookup"><span data-stu-id="d5165-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="d5165-223">不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="d5165-223">Do not make any changes yet.</span></span>

6.  <span data-ttu-id="d5165-224">关闭消息框，然后单击**获取缓存**试。</span><span class="sxs-lookup"><span data-stu-id="d5165-224">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d5165-225">请再次注意时间戳。</span><span class="sxs-lookup"><span data-stu-id="d5165-225">Notice the timestamp again.</span></span>

7.  <span data-ttu-id="d5165-226">对文本文件进行更改，然后保存该文件。</span><span class="sxs-lookup"><span data-stu-id="d5165-226">Make a change to the text file and then save the file.</span></span>

8.  <span data-ttu-id="d5165-227">关闭消息框，然后单击**获取缓存**试。</span><span class="sxs-lookup"><span data-stu-id="d5165-227">Close the message box and then click **Get Cache** again.</span></span>

     <span data-ttu-id="d5165-228">此消息框包含中的文本文件和新的时间戳的已更新的内容。</span><span class="sxs-lookup"><span data-stu-id="d5165-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="d5165-229">这指示主文件的更改监视器逐出缓存项后更改该文件，将立即即使绝对超时时间尚未过期。</span><span class="sxs-lookup"><span data-stu-id="d5165-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>

    > [!NOTE]
    >  <span data-ttu-id="d5165-230">可以增加到 20 秒或更多用于允许更多时间，以便在文件中进行更改的逐出时间。</span><span class="sxs-lookup"><span data-stu-id="d5165-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>

## <a name="code-example"></a><span data-ttu-id="d5165-231">代码示例</span><span class="sxs-lookup"><span data-stu-id="d5165-231">Code Example</span></span>
 <span data-ttu-id="d5165-232">完成本演练后，你创建的项目的代码将类似于下面的示例。</span><span class="sxs-lookup"><span data-stu-id="d5165-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a><span data-ttu-id="d5165-233">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5165-233">See also</span></span>

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [<span data-ttu-id="d5165-234">在 .NET Framework 应用程序中缓存</span><span class="sxs-lookup"><span data-stu-id="d5165-234">Caching in .NET Framework Applications</span></span>](../../performance/caching-in-net-framework-applications.md)
