---
title: 演练：在 WPF 应用程序中缓存应用程序数据
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a8d3fe2dbfe0b4b5fb9081d71cec080dfa54add8
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2018
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a><span data-ttu-id="4ef21-102">演练：在 WPF 应用程序中缓存应用程序数据</span><span class="sxs-lookup"><span data-stu-id="4ef21-102">Walkthrough: Caching Application Data in a WPF Application</span></span>
<span data-ttu-id="4ef21-103">缓存可以将数据存储在内存中以便快速访问。</span><span class="sxs-lookup"><span data-stu-id="4ef21-103">Caching enables you to store data in memory for rapid access.</span></span> <span data-ttu-id="4ef21-104">当再次访问数据时，应用程序可以从改为从原始源检索该缓存获取数据。</span><span class="sxs-lookup"><span data-stu-id="4ef21-104">When the data is accessed again, applications can get the data from the cache instead retrieving it from the original source.</span></span> <span data-ttu-id="4ef21-105">这可改善性能和可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="4ef21-105">This can improve performance and scalability.</span></span> <span data-ttu-id="4ef21-106">此外，数据源暂时不可用时，缓存可提供数据。</span><span class="sxs-lookup"><span data-stu-id="4ef21-106">In addition, caching makes data available when the data source is temporarily unavailable.</span></span>  
  
 <span data-ttu-id="4ef21-107">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]提供使你可以使用中的缓存类[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ef21-107">The [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] provides classes that enable you to use caching in [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="4ef21-108">这些类位于<xref:System.Runtime.Caching>命名空间。</span><span class="sxs-lookup"><span data-stu-id="4ef21-108">These classes are located in the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ef21-109"><xref:System.Runtime.Caching>命名空间是中的新增功能[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ef21-109">The <xref:System.Runtime.Caching> namespace is new in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="4ef21-110">此命名空间使缓存可供所有[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ef21-110">This namespace makes caching is available to all [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applications.</span></span> <span data-ttu-id="4ef21-111">[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 以前的版本中，缓存仅在 <xref:System.Web> 命名空间可用，因此，需要 ASP.NET 类上的一个依赖项。</span><span class="sxs-lookup"><span data-stu-id="4ef21-111">In previous versions of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], caching was available only in the <xref:System.Web> namespace and therefore required a dependency on ASP.NET classes.</span></span>  
  
 <span data-ttu-id="4ef21-112">本演练演示如何使用中提供的缓存功能[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]作为的一部分[!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ef21-112">This walkthrough shows you how to use the caching functionality that is available in the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] as part of a [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] application.</span></span> <span data-ttu-id="4ef21-113">在本演练中，你将缓存的文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="4ef21-113">In the walkthrough, you cache the contents of a text file.</span></span>  
  
 <span data-ttu-id="4ef21-114">本演练演示以下任务：</span><span class="sxs-lookup"><span data-stu-id="4ef21-114">Tasks illustrated in this walkthrough include the following:</span></span>  
  
-   <span data-ttu-id="4ef21-115">创建 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="4ef21-115">Creating a WPF application project.</span></span>  
  
-   <span data-ttu-id="4ef21-116">添加对引用[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ef21-116">Adding a reference to the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
-   <span data-ttu-id="4ef21-117">正在初始化缓存。</span><span class="sxs-lookup"><span data-stu-id="4ef21-117">Initializing a cache.</span></span>  
  
-   <span data-ttu-id="4ef21-118">添加包含的文本文件的内容的缓存项。</span><span class="sxs-lookup"><span data-stu-id="4ef21-118">Adding a cache entry that contains the contents of a text file.</span></span>  
  
-   <span data-ttu-id="4ef21-119">提供的缓存项的逐出策略。</span><span class="sxs-lookup"><span data-stu-id="4ef21-119">Providing an eviction policy for the cache entry.</span></span>  
  
-   <span data-ttu-id="4ef21-120">监视缓存的文件的路径和有关通知的缓存实例更改为受监视的项目。</span><span class="sxs-lookup"><span data-stu-id="4ef21-120">Monitoring the path of the cached file and notifying the cache instance about changes to the monitored item.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4ef21-121">系统必备</span><span class="sxs-lookup"><span data-stu-id="4ef21-121">Prerequisites</span></span>  
 <span data-ttu-id="4ef21-122">若要完成本演练，你将需要：</span><span class="sxs-lookup"><span data-stu-id="4ef21-122">In order to complete this walkthrough, you will need:</span></span>  
  
-   <span data-ttu-id="4ef21-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ef21-123">Microsoft [!INCLUDE[vs_dev10_long](../../../../includes/vs-dev10-long-md.md)].</span></span>  
  
-   <span data-ttu-id="4ef21-124">包含文本的少量的文本文件。</span><span class="sxs-lookup"><span data-stu-id="4ef21-124">A text file that contains a small amount of text.</span></span> <span data-ttu-id="4ef21-125">（将文本文件的内容在显示一个消息框。）在本演练中所示的代码假定你正在与以下文件：</span><span class="sxs-lookup"><span data-stu-id="4ef21-125">(You will display the contents of the text file in a message box.) The code illustrated in the walkthrough assumes that you are working with the following file:</span></span>  
  
     `c:\cache\cacheText.txt`  
  
     <span data-ttu-id="4ef21-126">但是，你可以使用任何文本文件并对此演练中的代码进行少量更改。</span><span class="sxs-lookup"><span data-stu-id="4ef21-126">However, you can use any text file and make small changes to the code in this walkthrough.</span></span>  
  
## <a name="creating-a-wpf-application-project"></a><span data-ttu-id="4ef21-127">创建 WPF 应用程序项目</span><span class="sxs-lookup"><span data-stu-id="4ef21-127">Creating a WPF Application Project</span></span>  
 <span data-ttu-id="4ef21-128">首先创建一个 WPF 应用程序项目。</span><span class="sxs-lookup"><span data-stu-id="4ef21-128">You will start by creating a WPF application project.</span></span>  
  
#### <a name="to-create-a-wpf-application"></a><span data-ttu-id="4ef21-129">创建 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="4ef21-129">To create a WPF application</span></span>  
  
1.  <span data-ttu-id="4ef21-130">启动 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="4ef21-130">Start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="4ef21-131">在**文件**菜单上，单击**新建**，然后单击**新项目**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-131">In the **File** menu, click **New**, and then click **New Project**.</span></span>  
  
     <span data-ttu-id="4ef21-132">随即显示“新建项目”对话框。</span><span class="sxs-lookup"><span data-stu-id="4ef21-132">The **New Project** dialog box is displayed.</span></span>  
  
3.  <span data-ttu-id="4ef21-133">下**已安装的模板**，选择你想要使用的编程语言 (**Visual Basic**或**Visual C#**)。</span><span class="sxs-lookup"><span data-stu-id="4ef21-133">Under **Installed Templates**, select the programming language you want to use (**Visual Basic** or **Visual C#**).</span></span>  
  
4.  <span data-ttu-id="4ef21-134">在**新项目**对话框中，选择**WPF 应用程序**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-134">In the **New Project** dialog box, select **WPF Application**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4ef21-135">如果看不到**WPF 应用程序**模板，请确保你面向的版本[!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]支持 WPF。</span><span class="sxs-lookup"><span data-stu-id="4ef21-135">If you do not see the **WPF Application** template, make sure that you are targeting a version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] that supports WPF.</span></span> <span data-ttu-id="4ef21-136">在**新项目**对话框中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]从列表中。</span><span class="sxs-lookup"><span data-stu-id="4ef21-136">In the **New Project** dialog box, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] from the list.</span></span>  
  
5.  <span data-ttu-id="4ef21-137">在**名称**文本框中，输入你的项目的名称。</span><span class="sxs-lookup"><span data-stu-id="4ef21-137">In the **Name** text box, enter a name for your project.</span></span> <span data-ttu-id="4ef21-138">例如，你可以输入**WPFCaching**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-138">For example, you can enter **WPFCaching**.</span></span>  
  
6.  <span data-ttu-id="4ef21-139">选择**创建解决方案的目录**复选框。</span><span class="sxs-lookup"><span data-stu-id="4ef21-139">Select the **Create directory for solution** check box.</span></span>  
  
7.  <span data-ttu-id="4ef21-140">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-140">Click **OK**.</span></span>  
  
     <span data-ttu-id="4ef21-141">WPF 设计器中打开**设计**查看，并显示 MainWindow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="4ef21-141">The WPF Designer opens in **Design** view and displays the MainWindow.xaml file.</span></span> <span data-ttu-id="4ef21-142">Visual Studio 将创建**我的项目**文件夹、 Application.xaml 文件和 MainWindow.xaml 文件。</span><span class="sxs-lookup"><span data-stu-id="4ef21-142">Visual Studio creates the **My Project** folder, the Application.xaml file, and the MainWindow.xaml file.</span></span>  
  
## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a><span data-ttu-id="4ef21-143">面向.NET Framework 和添加对缓存程序集的引用</span><span class="sxs-lookup"><span data-stu-id="4ef21-143">Targeting the .NET Framework and Adding a Reference to the Caching Assemblies</span></span>  
 <span data-ttu-id="4ef21-144">默认情况下，WPF 应用程序目标[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ef21-144">By default, WPF applications target the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].</span></span> <span data-ttu-id="4ef21-145">若要使用<xref:System.Runtime.Caching>在 WPF 应用程序的命名空间，应用程序必须指定目标[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (不[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) 并且必须包括对命名空间的引用。</span><span class="sxs-lookup"><span data-stu-id="4ef21-145">To use the <xref:System.Runtime.Caching> namespace in a WPF application, the application must target the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (not the [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) and must include a reference to the namespace.</span></span>  
  
 <span data-ttu-id="4ef21-146">因此下, 一步是以更改.NET Framework 目标并添加对的引用<xref:System.Runtime.Caching>命名空间。</span><span class="sxs-lookup"><span data-stu-id="4ef21-146">Therefore, the next step is to change the .NET Framework target and add a reference to the <xref:System.Runtime.Caching> namespace.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ef21-147">.NET Framework 将目标更改的过程是在 Visual Basic 项目和 Visual C# 项目不同。</span><span class="sxs-lookup"><span data-stu-id="4ef21-147">The procedure for changing the .NET Framework target is different in a Visual Basic project and in a Visual C# project.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-visual-basic"></a><span data-ttu-id="4ef21-148">若要更改的目标.NET Framework 在 Visual Basic 中</span><span class="sxs-lookup"><span data-stu-id="4ef21-148">To change the target .NET Framework in Visual Basic</span></span>  
  
1.  <span data-ttu-id="4ef21-149">在**解决方案资源管理器**，右键单击项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-149">In **Solutions Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
     <span data-ttu-id="4ef21-150">应用程序的属性窗口将显示。</span><span class="sxs-lookup"><span data-stu-id="4ef21-150">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="4ef21-151">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="4ef21-151">Click the **Compile** tab.</span></span>  
  
3.  <span data-ttu-id="4ef21-152">在窗口的底部，单击**高级编译选项...**.</span><span class="sxs-lookup"><span data-stu-id="4ef21-152">At the bottom of the window, click **Advanced Compile Options…**.</span></span>  
  
     <span data-ttu-id="4ef21-153">**高级编译器设置**对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="4ef21-153">The **Advanced Compiler Settings** dialog box is displayed.</span></span>  
  
4.  <span data-ttu-id="4ef21-154">在**目标 framework （所有配置）**列表中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ef21-154">In the **Target framework (all configurations)** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="4ef21-155">(不要选择[!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="4ef21-155">(Do not select [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)</span></span>  
  
5.  <span data-ttu-id="4ef21-156">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-156">Click **OK**.</span></span>  
  
     <span data-ttu-id="4ef21-157">**目标 Framework 更改**对话框随即显示。</span><span class="sxs-lookup"><span data-stu-id="4ef21-157">The **Target Framework Change** dialog box is displayed.</span></span>  
  
6.  <span data-ttu-id="4ef21-158">在**目标 Framework 更改**对话框中，单击**是**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-158">In the **Target Framework Change** dialog box, click **Yes**.</span></span>  
  
     <span data-ttu-id="4ef21-159">项目将关闭，然后重新打开。</span><span class="sxs-lookup"><span data-stu-id="4ef21-159">The project is closed and is then reopened.</span></span>  
  
7.  <span data-ttu-id="4ef21-160">通过执行以下步骤添加对缓存程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="4ef21-160">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="4ef21-161">在**解决方案资源管理器**，右键单击项目的名称，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-161">In **Solution Explorer**, right-click the name of the project and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="4ef21-162">选择 **.NET**选项卡上，选择`System.Runtime.Caching`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-162">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a><span data-ttu-id="4ef21-163">若要更改 Visual C# 项目中的目标.NET Framework</span><span class="sxs-lookup"><span data-stu-id="4ef21-163">To change the target .NET Framework in a Visual C# project</span></span>  
  
1.  <span data-ttu-id="4ef21-164">在**解决方案资源管理器**，右键单击项目名称，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-164">In **Solution Explorer**, right-click the project name and then click **Properties**.</span></span>  
  
     <span data-ttu-id="4ef21-165">应用程序的属性窗口将显示。</span><span class="sxs-lookup"><span data-stu-id="4ef21-165">The properties window for the application is displayed.</span></span>  
  
2.  <span data-ttu-id="4ef21-166">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="4ef21-166">Click the **Application** tab.</span></span>  
  
3.  <span data-ttu-id="4ef21-167">在**目标框架**列表中，选择[!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="4ef21-167">In the **Target framework** list, select [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span> <span data-ttu-id="4ef21-168">(不要选择 **.NET Framework 4 Client Profile**。)</span><span class="sxs-lookup"><span data-stu-id="4ef21-168">(Do not select **.NET Framework 4 Client Profile**.)</span></span>  
  
4.  <span data-ttu-id="4ef21-169">通过执行以下步骤添加对缓存程序集的引用：</span><span class="sxs-lookup"><span data-stu-id="4ef21-169">Add a reference to the caching assembly by following these steps:</span></span>  
  
    1.  <span data-ttu-id="4ef21-170">右键单击**引用**文件夹，然后单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-170">Right-click the **References** folder and then click **Add Reference**.</span></span>  
  
    2.  <span data-ttu-id="4ef21-171">选择 **.NET**选项卡上，选择`System.Runtime.Caching`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-171">Select the **.NET** tab, select `System.Runtime.Caching`, and then click **OK**.</span></span>  
  
## <a name="adding-a-button-to-the-wpf-window"></a><span data-ttu-id="4ef21-172">将按钮添加到作为 WPF 窗口</span><span class="sxs-lookup"><span data-stu-id="4ef21-172">Adding a Button to the WPF Window</span></span>  
 <span data-ttu-id="4ef21-173">接下来，你将添加一个按钮控件，并创建为按钮的事件处理程序`Click`事件。</span><span class="sxs-lookup"><span data-stu-id="4ef21-173">Next, you will add a button control and create an event handler for the button's `Click` event.</span></span> <span data-ttu-id="4ef21-174">稍后你将添加到的代码，因此单击按钮时，文本文件的内容是缓存，并且不显示。</span><span class="sxs-lookup"><span data-stu-id="4ef21-174">Later you will add code to so when you click the button, the contents of the text file are cached and displayed.</span></span>  
  
#### <a name="to-add-a-button-control"></a><span data-ttu-id="4ef21-175">若要添加一个按钮控件</span><span class="sxs-lookup"><span data-stu-id="4ef21-175">To add a button control</span></span>  
  
1.  <span data-ttu-id="4ef21-176">在**解决方案资源管理器**，双击 MainWindow.xaml 文件，以打开它。</span><span class="sxs-lookup"><span data-stu-id="4ef21-176">In **Solution Explorer**, double-click the MainWindow.xaml file to open it.</span></span>  
  
2.  <span data-ttu-id="4ef21-177">从**工具箱**下**公共 WPF 控件**，拖动`Button`控制转移到`MainWindow`窗口。</span><span class="sxs-lookup"><span data-stu-id="4ef21-177">From the **Toolbox**, under **Common WPF Controls**, drag a `Button` control to the `MainWindow` window.</span></span>  
  
3.  <span data-ttu-id="4ef21-178">在**属性**窗口中，设置`Content`属性`Button`控制转移到**获取缓存**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-178">In the **Properties** window, set the `Content` property of the `Button` control to **Get Cache**.</span></span>  
  
## <a name="initializing-the-cache-and-caching-an-entry"></a><span data-ttu-id="4ef21-179">正在初始化缓存和缓存条目</span><span class="sxs-lookup"><span data-stu-id="4ef21-179">Initializing the Cache and Caching an Entry</span></span>  
 <span data-ttu-id="4ef21-180">接下来，你将添加代码以执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="4ef21-180">Next, you will add the code to perform the following tasks:</span></span>  
  
-   <span data-ttu-id="4ef21-181">创建缓存类的实例 — 也就是说，你将实例化一个新<xref:System.Runtime.Caching.MemoryCache>对象。</span><span class="sxs-lookup"><span data-stu-id="4ef21-181">Create an instance of the cache class—that is, you will instantiate a new <xref:System.Runtime.Caching.MemoryCache> object.</span></span>  
  
-   <span data-ttu-id="4ef21-182">指定缓存使用<xref:System.Runtime.Caching.HostFileChangeMonitor>对象来监视的文本文件中的更改。</span><span class="sxs-lookup"><span data-stu-id="4ef21-182">Specify that the cache uses a <xref:System.Runtime.Caching.HostFileChangeMonitor> object to monitor changes in the text file.</span></span>  
  
-   <span data-ttu-id="4ef21-183">读取文本文件，以及为缓存条目缓存其内容。</span><span class="sxs-lookup"><span data-stu-id="4ef21-183">Read the text file and cache its contents as a cache entry.</span></span>  
  
-   <span data-ttu-id="4ef21-184">显示缓存的文本文件的内容。</span><span class="sxs-lookup"><span data-stu-id="4ef21-184">Display the contents of the cached text file.</span></span>  
  
#### <a name="to-create-the-cache-object"></a><span data-ttu-id="4ef21-185">若要创建缓存对象</span><span class="sxs-lookup"><span data-stu-id="4ef21-185">To create the cache object</span></span>  
  
1.  <span data-ttu-id="4ef21-186">双击你只是为了在 MainWindow.xaml.cs 或 MainWindow.Xaml.vb 文件创建一个事件处理程序添加的按钮。</span><span class="sxs-lookup"><span data-stu-id="4ef21-186">Double-click the button you just added in order to create an event handler in the MainWindow.xaml.cs or MainWindow.Xaml.vb file.</span></span>  
  
2.  <span data-ttu-id="4ef21-187">在该文件 （后再类声明中） 的顶部，添加以下`Imports`(Visual Basic 中) 或`using`(C#) 语句：</span><span class="sxs-lookup"><span data-stu-id="4ef21-187">At the top of the file (before the class declaration), add the following `Imports` (Visual Basic) or `using` (C#) statements:</span></span>  
  
    ```csharp  
    using System.Runtime.Caching;  
    using System.IO;  
    ```  
  
    ```vb  
    Imports System.Runtime.Caching  
    Imports System.IO  
    ```  
  
3.  <span data-ttu-id="4ef21-188">事件处理程序中，添加以下代码以实例化缓存对象：</span><span class="sxs-lookup"><span data-stu-id="4ef21-188">In the event handler, add the following code to instantiate the cache object:</span></span>  
  
    ```csharp  
    ObjectCache cache = MemoryCache.Default;  
    ```  
  
    ```vb  
    Dim cache As ObjectCache = MemoryCache.Default  
    ```  
  
     <span data-ttu-id="4ef21-189"><xref:System.Runtime.Caching.ObjectCache>类是一个内置的类，提供内存中对象缓存。</span><span class="sxs-lookup"><span data-stu-id="4ef21-189">The <xref:System.Runtime.Caching.ObjectCache> class is a built-in class that provides an in-memory object cache.</span></span>  
  
4.  <span data-ttu-id="4ef21-190">添加以下代码以读取名为某个缓存项的内容`filecontents`:</span><span class="sxs-lookup"><span data-stu-id="4ef21-190">Add the following code to read the contents of a cache entry named `filecontents`:</span></span>  
  
    ```vb  
    Dim fileContents As String = TryCast(cache("filecontents"), String)  
    ```  
  
    ```csharp  
    string fileContents = cache["filecontents"] as string;  
    ```  
  
5.  <span data-ttu-id="4ef21-191">添加以下代码以检查是否缓存条目名为`filecontents`存在：</span><span class="sxs-lookup"><span data-stu-id="4ef21-191">Add the following code to check whether the cache entry named `filecontents` exists:</span></span>  
  
    ```vb  
    If fileContents Is Nothing Then  
  
    End If  
    ```  
  
    ```csharp  
    if (fileContents == null)  
    {  
  
    }  
    ```  
  
     <span data-ttu-id="4ef21-192">如果指定的缓存条目不存在，必须读取该文本文件并将其作为某个缓存项添加到缓存。</span><span class="sxs-lookup"><span data-stu-id="4ef21-192">If the specified cache entry does not exist, you must read the text file and add it as a cache entry to the cache.</span></span>  
  
6.  <span data-ttu-id="4ef21-193">在`if/then`块中，添加以下代码以创建一个新<xref:System.Runtime.Caching.CacheItemPolicy>对象，它指定的缓存项将在 10 秒后过期。</span><span class="sxs-lookup"><span data-stu-id="4ef21-193">In the `if/then` block, add the following code to create a new <xref:System.Runtime.Caching.CacheItemPolicy> object that specifies that the cache entry expires after 10 seconds.</span></span>  
  
    ```vb  
    Dim policy As New CacheItemPolicy()  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)  
    ```  
  
    ```csharp  
    CacheItemPolicy policy = new CacheItemPolicy();  
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);  
    ```  
  
     <span data-ttu-id="4ef21-194">如果未不提供任何逐出或过期的信息，则默认将<xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>，这意味着的缓存项永远不会基于仅在过期绝对时间。</span><span class="sxs-lookup"><span data-stu-id="4ef21-194">If no eviction or expiration information is provided, the default is <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, which means the cache entries never expire based only on an absolute time.</span></span> <span data-ttu-id="4ef21-195">相反，缓存条目过期只有在没有内存压力时。</span><span class="sxs-lookup"><span data-stu-id="4ef21-195">Instead, cache entries expire only when there is memory pressure.</span></span> <span data-ttu-id="4ef21-196">作为最佳做法，应始终显式提供绝对或可调过期。</span><span class="sxs-lookup"><span data-stu-id="4ef21-196">As a best practice, you should always explicitly provide either an absolute or a siding expiration.</span></span>  
  
7.  <span data-ttu-id="4ef21-197">内部`if/then`块并在上一步中添加的代码，后面添加以下代码以创建你想要监视，并将该文本文件的路径添加到集合的文件路径的集合：</span><span class="sxs-lookup"><span data-stu-id="4ef21-197">Inside the `if/then` block and following the code you added in the previous step, add the following code to create a collection for the file paths that you want to monitor, and to add the path of the text file to the collection:</span></span>  
  
    ```vb  
    Dim filePaths As New List(Of String)()  
    filePaths.Add("c:\cache\cacheText.txt")  
    ```  
  
    ```csharp  
    List<string> filePaths = new List<string>();  
    filePaths.Add("c:\\cache\\cacheText.txt");  
    ```  
  
    > [!NOTE]
    >  <span data-ttu-id="4ef21-198">如果你想要使用的文本文件不是`c:\cache\cacheText.txt`，指定的文本文件是你想要使用的路径。</span><span class="sxs-lookup"><span data-stu-id="4ef21-198">If the text file you want to use is not `c:\cache\cacheText.txt`, specify the path where the text file is that you want to use.</span></span>  
  
8.  <span data-ttu-id="4ef21-199">在上一步骤中，添加的代码后面添加以下代码以添加新<xref:System.Runtime.Caching.HostFileChangeMonitor>到的更改集合的对象的缓存项监视：</span><span class="sxs-lookup"><span data-stu-id="4ef21-199">Following the code that you added in the previous step, add the following code to add a new <xref:System.Runtime.Caching.HostFileChangeMonitor> object to the collection of change monitors for the cache entry:</span></span>  
  
    ```vb  
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))  
    ```  
  
    ```csharp  
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));  
    ```  
  
     <span data-ttu-id="4ef21-200"><xref:System.Runtime.Caching.HostFileChangeMonitor>对象监视文本文件的路径，并通知缓存，如果未发生更改。</span><span class="sxs-lookup"><span data-stu-id="4ef21-200">The <xref:System.Runtime.Caching.HostFileChangeMonitor> object monitors the text file's path and notifies the cache if changes occur.</span></span> <span data-ttu-id="4ef21-201">在此示例中，如果文件的内容发生更改，将过期的缓存项。</span><span class="sxs-lookup"><span data-stu-id="4ef21-201">In this example, the cache entry will expire if the content of the file changes.</span></span>  
  
9. <span data-ttu-id="4ef21-202">后面的代码中添加上一步中，添加以下代码以读取文本文件的内容：</span><span class="sxs-lookup"><span data-stu-id="4ef21-202">Following the code that you added in the previous step, add the following code to read the contents of the text file:</span></span>  
  
    ```vb  
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()  
    ```  
  
    ```csharp  
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + + "\n" + DateTime.Now;   
    ```  
  
     <span data-ttu-id="4ef21-203">从而使你将能够看到该缓存条目到期时添加的日期和时间的时间戳。</span><span class="sxs-lookup"><span data-stu-id="4ef21-203">The date and time timestamp is added so that you will be able to see when the cache entry expires.</span></span>  
  
10. <span data-ttu-id="4ef21-204">在上一步骤中，添加的代码后面添加以下代码以将文件的内容插入到缓存对象作为<xref:System.Runtime.Caching.CacheItem>实例：</span><span class="sxs-lookup"><span data-stu-id="4ef21-204">Following the code that you added in the previous step, add the following code to insert the contents of the file into the cache object as a <xref:System.Runtime.Caching.CacheItem> instance:</span></span>  
  
    ```vb  
    cache.Set("filecontents", fileContents, policy)  
    ```  
  
    ```csharp  
    cache.Set("filecontents", fileContents, policy);  
    ```  
  
     <span data-ttu-id="4ef21-205">指定有关如何通过传递逐出缓存项的信息<xref:System.Runtime.Caching.CacheItemPolicy>作为参数前面创建的对象。</span><span class="sxs-lookup"><span data-stu-id="4ef21-205">You specify information about how the cache entry should be evicted by passing the <xref:System.Runtime.Caching.CacheItemPolicy> object that you created earlier as a parameter.</span></span>  
  
11. <span data-ttu-id="4ef21-206">后`if/then`块中，添加以下代码以在消息框中显示缓存的文件内容：</span><span class="sxs-lookup"><span data-stu-id="4ef21-206">After the `if/then` block, add the following code to display the cached file content in a message box:</span></span>  
  
    ```vb  
    MessageBox.Show(fileContents)  
    ```  
  
    ```csharp  
    MessageBox.Show(fileContents);  
    ```  
  
12. <span data-ttu-id="4ef21-207">在**生成**菜单上，单击**生成 WPFCaching**以生成项目。</span><span class="sxs-lookup"><span data-stu-id="4ef21-207">In the **Build** menu, click **Build WPFCaching** to build your project.</span></span>  
  
## <a name="testing-caching-in-the-wpf-application"></a><span data-ttu-id="4ef21-208">测试在 WPF 应用程序中缓存</span><span class="sxs-lookup"><span data-stu-id="4ef21-208">Testing Caching in the WPF Application</span></span>  
 <span data-ttu-id="4ef21-209">你现在可以测试应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ef21-209">You can now test the application.</span></span>  
  
#### <a name="to-test-caching-in-the-wpf-application"></a><span data-ttu-id="4ef21-210">若要测试缓存在 WPF 应用程序</span><span class="sxs-lookup"><span data-stu-id="4ef21-210">To test caching in the WPF application</span></span>  
  
1.  <span data-ttu-id="4ef21-211">按 Ctrl+F5 运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="4ef21-211">Press CTRL+F5 to run the application.</span></span>  
  
     <span data-ttu-id="4ef21-212">`MainWindow`显示窗口。</span><span class="sxs-lookup"><span data-stu-id="4ef21-212">The `MainWindow` window is displayed.</span></span>  
  
2.  <span data-ttu-id="4ef21-213">单击**获取缓存**。</span><span class="sxs-lookup"><span data-stu-id="4ef21-213">Click **Get Cache**.</span></span>  
  
     <span data-ttu-id="4ef21-214">在消息框中将显示文本文件中的缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="4ef21-214">The cached content from the text file is displayed in a message box.</span></span> <span data-ttu-id="4ef21-215">请注意该文件上的时间戳。</span><span class="sxs-lookup"><span data-stu-id="4ef21-215">Notice the timestamp on the file.</span></span>  
  
3.  <span data-ttu-id="4ef21-216">关闭消息框，然后单击**获取缓存**再次**。**</span><span class="sxs-lookup"><span data-stu-id="4ef21-216">Close the message box and then click **Get Cache** again **.**</span></span>  
  
     <span data-ttu-id="4ef21-217">时间戳保持不变。</span><span class="sxs-lookup"><span data-stu-id="4ef21-217">The timestamp is unchanged.</span></span> <span data-ttu-id="4ef21-218">这将指示显示缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="4ef21-218">This indicates the cached content is displayed.</span></span>  
  
4.  <span data-ttu-id="4ef21-219">等待 10 秒或几秒，然后单击**获取缓存**试。</span><span class="sxs-lookup"><span data-stu-id="4ef21-219">Wait 10 seconds or more and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="4ef21-220">此时将显示新时间戳。</span><span class="sxs-lookup"><span data-stu-id="4ef21-220">This time a new timestamp is displayed.</span></span> <span data-ttu-id="4ef21-221">这表示策略，让过期的缓存项，将显示新的缓存的内容。</span><span class="sxs-lookup"><span data-stu-id="4ef21-221">This indicates that the policy let the cache entry expire and that new cached content is displayed.</span></span>  
  
5.  <span data-ttu-id="4ef21-222">在文本编辑器中，打开您创建的文本文件。</span><span class="sxs-lookup"><span data-stu-id="4ef21-222">In a text editor, open the text file that you created.</span></span> <span data-ttu-id="4ef21-223">不进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="4ef21-223">Do not make any changes yet.</span></span>  
  
6.  <span data-ttu-id="4ef21-224">关闭消息框，然后单击**获取缓存**再次**。**</span><span class="sxs-lookup"><span data-stu-id="4ef21-224">Close the message box and then click **Get Cache** again **.**</span></span>  
  
     <span data-ttu-id="4ef21-225">再次注意时间戳。</span><span class="sxs-lookup"><span data-stu-id="4ef21-225">Notice the timestamp again.</span></span>  
  
7.  <span data-ttu-id="4ef21-226">对文本文件进行更改，然后保存该文件。</span><span class="sxs-lookup"><span data-stu-id="4ef21-226">Make a change to the text file and then save the file.</span></span>  
  
8.  <span data-ttu-id="4ef21-227">关闭消息框，然后单击**获取缓存**试。</span><span class="sxs-lookup"><span data-stu-id="4ef21-227">Close the message box and then click **Get Cache** again.</span></span>  
  
     <span data-ttu-id="4ef21-228">此消息框包含从文本文件和新时间戳的更新的内容。</span><span class="sxs-lookup"><span data-stu-id="4ef21-228">This message box contains the updated content from the text file and a new timestamp.</span></span> <span data-ttu-id="4ef21-229">这指示主机文件更改监视器逐出缓存条目立即时更改的文件，即使绝对超时时间尚未过期。</span><span class="sxs-lookup"><span data-stu-id="4ef21-229">This indicates that the host-file change monitor evicted the cache entry immediately when you changed the file, even though the absolute timeout period had not expired.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4ef21-230">你可以增加到 20 秒或更多以允许你进行更改，在文件中更多的时间的逐出时间。</span><span class="sxs-lookup"><span data-stu-id="4ef21-230">You can increase the eviction time to 20 seconds or more to allow more time for you to make a change in the file.</span></span>  
  
## <a name="code-example"></a><span data-ttu-id="4ef21-231">代码示例</span><span class="sxs-lookup"><span data-stu-id="4ef21-231">Code Example</span></span>  
 <span data-ttu-id="4ef21-232">完成本演练后，你创建的项目的代码将类似于下面的示例。</span><span class="sxs-lookup"><span data-stu-id="4ef21-232">After you have completed this walkthrough, the code for the project you created will resemble the following example.</span></span>  
  
 [!code-csharp[CachingWPFApplications#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="4ef21-233">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ef21-233">See Also</span></span>  
 <xref:System.Runtime.Caching.MemoryCache>  
 <xref:System.Runtime.Caching.ObjectCache>  
 <xref:System.Runtime.Caching>  
 [<span data-ttu-id="4ef21-234">在 .NET Framework 应用程序中缓存</span><span class="sxs-lookup"><span data-stu-id="4ef21-234">Caching in .NET Framework Applications</span></span>](../../../../docs/framework/performance/caching-in-net-framework-applications.md)
