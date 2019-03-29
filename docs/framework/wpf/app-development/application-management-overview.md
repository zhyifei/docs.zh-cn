---
title: 应用程序管理概述
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application management [WPF]
ms.assetid: 32b1c054-5aca-423b-b4b5-ed8dc4dc637d
ms.openlocfilehash: 395077b7c82ee54a51b8086df0c59f731e3a2b70
ms.sourcegitcommit: d938c39afb9216db377d0f0ecdaa53936a851059
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2019
ms.locfileid: "58634214"
---
# <a name="application-management-overview"></a><span data-ttu-id="1bf2d-102">应用程序管理概述</span><span class="sxs-lookup"><span data-stu-id="1bf2d-102">Application Management Overview</span></span>
<span data-ttu-id="1bf2d-103">所有应用程序都可能会共享一组适用于实现和管理应用程序的常见功能。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-103">All applications tend to share a common set of functionality that applies to application implementation and management.</span></span> <span data-ttu-id="1bf2d-104">本主题概述中的功能的<xref:System.Windows.Application>类用于创建和管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-104">This topic provides an overview of the functionality in the <xref:System.Windows.Application> class for creating and managing applications.</span></span>  
   
  
## <a name="the-application-class"></a><span data-ttu-id="1bf2d-105">Application 类</span><span class="sxs-lookup"><span data-stu-id="1bf2d-105">The Application Class</span></span>  
 <span data-ttu-id="1bf2d-106">在 WPF 中，常见的应用程序范围的功能会封装在<xref:System.Windows.Application>类。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-106">In WPF, common application-scoped functionality is encapsulated in the <xref:System.Windows.Application> class.</span></span> <span data-ttu-id="1bf2d-107"><xref:System.Windows.Application>类包括以下功能：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-107">The <xref:System.Windows.Application> class includes the following functionality:</span></span>  
  
-   <span data-ttu-id="1bf2d-108">对应用程序的生存期进行跟踪并与之进行交互。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-108">Tracking and interacting with application lifetime.</span></span>  
  
-   <span data-ttu-id="1bf2d-109">检索和处理命令行参数。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-109">Retrieving and processing command-line parameters.</span></span>  
  
-   <span data-ttu-id="1bf2d-110">检测和响应未经处理的异常。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-110">Detecting and responding to unhandled exceptions.</span></span>  
  
-   <span data-ttu-id="1bf2d-111">共享应用程序范围的属性和资源。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-111">Sharing application-scope properties and resources.</span></span>  
  
-   <span data-ttu-id="1bf2d-112">管理独立应用程序中的窗口。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-112">Managing windows in standalone applications.</span></span>  
  
-   <span data-ttu-id="1bf2d-113">跟踪和管理导航。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-113">Tracking and managing navigation.</span></span>  
  
<a name="The_Application_Class"></a>   
## <a name="how-to-perform-common-tasks-using-the-application-class"></a><span data-ttu-id="1bf2d-114">如何使用 Application 类执行常见任务</span><span class="sxs-lookup"><span data-stu-id="1bf2d-114">How to Perform Common Tasks Using the Application Class</span></span>  
 <span data-ttu-id="1bf2d-115">如果您不感兴趣的详细信息的所有<xref:System.Windows.Application>类下, 表列出了一些常见任务<xref:System.Windows.Application>以及如何完成它们。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-115">If you are not interested in all of the details of the <xref:System.Windows.Application> class, the following table lists some of the common tasks for <xref:System.Windows.Application> and how to accomplish them.</span></span> <span data-ttu-id="1bf2d-116">通过查看相关的 API 和主题，可以找到详细信息和示例代码。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-116">By viewing the related API and topics, you can find more information and sample code.</span></span>  
  
|<span data-ttu-id="1bf2d-117">任务</span><span class="sxs-lookup"><span data-stu-id="1bf2d-117">Task</span></span>|<span data-ttu-id="1bf2d-118">方法</span><span class="sxs-lookup"><span data-stu-id="1bf2d-118">Approach</span></span>|  
|----------|--------------|  
|<span data-ttu-id="1bf2d-119">获取表示当前应用程序的对象</span><span class="sxs-lookup"><span data-stu-id="1bf2d-119">Get an object that represents the current application</span></span>|<span data-ttu-id="1bf2d-120">使用 <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-120">Use the <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="1bf2d-121">将启动屏幕添加到应用程序中</span><span class="sxs-lookup"><span data-stu-id="1bf2d-121">Add a startup screen to an application</span></span>|<span data-ttu-id="1bf2d-122">请参阅[将初始屏幕添加到 WPF 应用程序](how-to-add-a-splash-screen-to-a-wpf-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-122">See [Add a Splash Screen to a WPF Application](how-to-add-a-splash-screen-to-a-wpf-application.md).</span></span>|  
|<span data-ttu-id="1bf2d-123">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="1bf2d-123">Start an application</span></span>|<span data-ttu-id="1bf2d-124">使用 <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-124">Use the <xref:System.Windows.Application.Run%2A?displayProperty=nameWithType> method.</span></span>|  
|<span data-ttu-id="1bf2d-125">停止应用程序</span><span class="sxs-lookup"><span data-stu-id="1bf2d-125">Stop an application</span></span>|<span data-ttu-id="1bf2d-126">使用<xref:System.Windows.Application.Shutdown%2A>方法的<xref:System.Windows.Application.Current%2A?displayProperty=nameWithType>对象。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-126">Use the <xref:System.Windows.Application.Shutdown%2A> method of the <xref:System.Windows.Application.Current%2A?displayProperty=nameWithType> object.</span></span>|  
|<span data-ttu-id="1bf2d-127">从命令行获取参数</span><span class="sxs-lookup"><span data-stu-id="1bf2d-127">Get arguments from the command line</span></span>|<span data-ttu-id="1bf2d-128">处理<xref:System.Windows.Application.Startup?displayProperty=nameWithType>事件并使用<xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-128">Handle the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event and use the <xref:System.Windows.StartupEventArgs.Args%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="1bf2d-129">有关示例，请参阅<xref:System.Windows.Application.Startup?displayProperty=nameWithType>事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-129">For an example, see the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event.</span></span>|  
|<span data-ttu-id="1bf2d-130">获取和设置应用程序退出代码</span><span class="sxs-lookup"><span data-stu-id="1bf2d-130">Get and set the application exit code</span></span>|<span data-ttu-id="1bf2d-131">设置<xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType>中的属性<xref:System.Windows.Application.Exit?displayProperty=nameWithType>事件处理程序或调用<xref:System.Windows.Application.Shutdown%2A>方法并传入一个整数。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-131">Set the <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A?displayProperty=nameWithType> property in the <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event handler or call the <xref:System.Windows.Application.Shutdown%2A> method and pass in an integer.</span></span>|  
|<span data-ttu-id="1bf2d-132">检测和响应未经处理的异常</span><span class="sxs-lookup"><span data-stu-id="1bf2d-132">Detect and respond to unhandled exceptions</span></span>|<span data-ttu-id="1bf2d-133">处理<xref:System.Windows.Application.DispatcherUnhandledException>事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-133">Handle the <xref:System.Windows.Application.DispatcherUnhandledException> event.</span></span>|  
|<span data-ttu-id="1bf2d-134">获取和设置应用程序范围的资源</span><span class="sxs-lookup"><span data-stu-id="1bf2d-134">Get and set application-scoped resources</span></span>|<span data-ttu-id="1bf2d-135">使用 <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-135">Use the <xref:System.Windows.Application.Resources%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="1bf2d-136">使用应用程序范围的资源字典</span><span class="sxs-lookup"><span data-stu-id="1bf2d-136">Use an application-scope resource dictionary</span></span>|<span data-ttu-id="1bf2d-137">请参阅[使用应用程序范围的资源字典](how-to-use-an-application-scope-resource-dictionary.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-137">See [Use an Application-Scope Resource Dictionary](how-to-use-an-application-scope-resource-dictionary.md).</span></span>|  
|<span data-ttu-id="1bf2d-138">获取和设置应用程序范围的属性</span><span class="sxs-lookup"><span data-stu-id="1bf2d-138">Get and set application-scoped properties</span></span>|<span data-ttu-id="1bf2d-139">使用 <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> 属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-139">Use the <xref:System.Windows.Application.Properties%2A?displayProperty=nameWithType> property.</span></span>|  
|<span data-ttu-id="1bf2d-140">获取和保存应用程序的状态</span><span class="sxs-lookup"><span data-stu-id="1bf2d-140">Get and save an application's state</span></span>|<span data-ttu-id="1bf2d-141">请参阅[保持和还原应用程序作用域属性在应用程序会话之间](persist-and-restore-application-scope-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-141">See [Persist and Restore Application-Scope Properties Across Application Sessions](persist-and-restore-application-scope-properties.md).</span></span>|  
|<span data-ttu-id="1bf2d-142">管理非代码数据文件，包括资源文件、内容文件和源站点文件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-142">Manage non-code data files, including resource files, content files, and site-of-origin files.</span></span>|<span data-ttu-id="1bf2d-143">请参阅[WPF 应用程序资源、 内容和数据文件](wpf-application-resource-content-and-data-files.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-143">See [WPF Application Resource, Content, and Data Files](wpf-application-resource-content-and-data-files.md).</span></span>|  
|<span data-ttu-id="1bf2d-144">管理独立应用程序中的窗口</span><span class="sxs-lookup"><span data-stu-id="1bf2d-144">Manage windows in standalone applications</span></span>|<span data-ttu-id="1bf2d-145">请参阅 [WPF 窗口概述](wpf-windows-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-145">See [WPF Windows Overview](wpf-windows-overview.md).</span></span>|  
|<span data-ttu-id="1bf2d-146">跟踪和管理导航</span><span class="sxs-lookup"><span data-stu-id="1bf2d-146">Track and manage navigation</span></span>|<span data-ttu-id="1bf2d-147">请参阅[导航概述](navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-147">See [Navigation Overview](navigation-overview.md).</span></span>|  
  
<a name="The_Application_Definition"></a>   
## <a name="the-application-definition"></a><span data-ttu-id="1bf2d-148">应用程序定义</span><span class="sxs-lookup"><span data-stu-id="1bf2d-148">The Application Definition</span></span>  
 <span data-ttu-id="1bf2d-149">若要利用的功能<xref:System.Windows.Application>类，必须实现应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-149">To utilize the functionality of the <xref:System.Windows.Application> class, you must implement an application definition.</span></span> <span data-ttu-id="1bf2d-150">WPF 应用程序定义是一个类，派生自<xref:System.Windows.Application>使用特殊的 MSBuild 设置进行配置。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-150">A WPF application definition is a class that derives from <xref:System.Windows.Application> and is configured with a special MSBuild setting.</span></span>  

### <a name="implementing-an-application-definition"></a><span data-ttu-id="1bf2d-151">实现应用程序定义</span><span class="sxs-lookup"><span data-stu-id="1bf2d-151">Implementing an Application Definition</span></span>  
 <span data-ttu-id="1bf2d-152">使用标记和代码隐藏来实现典型的 WPF 应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-152">A typical WPF application definition is implemented using both markup and code-behind.</span></span> <span data-ttu-id="1bf2d-153">因此，可以使用标记以声明方式设置应用程序的属性、资源和注册事件，同时还能处理事件并在代码隐藏中实现特定于应用程序的行为。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-153">This allows you to use markup to declaratively set application properties, resources, and register events, while handling events and implementing application-specific behavior in code-behind.</span></span>  
  
 <span data-ttu-id="1bf2d-154">以下示例演示了如何使用标记和代码隐藏来实现应用程序定义：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-154">The following example shows how to implement an application definition using both markup and code-behind:</span></span>  
  
 [!code-xaml[ApplicationSnippets#ApplicationXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml#applicationxaml)]  
  
 [!code-csharp[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSnippets/CSharp/App.xaml.cs#applicationcodebehind)]
 [!code-vb[ApplicationSnippets#ApplicationCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSnippets/visualbasic/application.xaml.vb#applicationcodebehind)]  
  
 <span data-ttu-id="1bf2d-155">要允许标记文件和代码隐藏文件协同工作，需要进行以下配置：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-155">To allow a markup file and code-behind file to work together, the following needs to happen:</span></span>  
  
- <span data-ttu-id="1bf2d-156">在标记中，`Application`元素必须包括`x:Class`属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-156">In markup, the `Application` element must include the `x:Class` attribute.</span></span> <span data-ttu-id="1bf2d-157">应用程序生成时，是否存在`x:Class`文件的标记中，MSBuild 将创建`partial`类派生自<xref:System.Windows.Application>并且具有指定的名称`x:Class`属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-157">When the application is built, the existence of `x:Class` in the markup file causes MSBuild to create a `partial` class that derives from <xref:System.Windows.Application> and has the name that is specified by the `x:Class` attribute.</span></span> <span data-ttu-id="1bf2d-158">这需要 XAML 架构的 XML 命名空间声明添加 (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-158">This requires the addition of an XML namespace declaration for the XAML schema (`xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"`).</span></span>
  
-   <span data-ttu-id="1bf2d-159">在代码隐藏中，类必须是`partial`类指定的同名`x:Class`属性在标记中，必须派生自<xref:System.Windows.Application>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-159">In code-behind, the class must be a `partial` class with the same name that is specified by the `x:Class` attribute in markup and must derive from <xref:System.Windows.Application>.</span></span> <span data-ttu-id="1bf2d-160">这允许要与之关联的代码隐藏文件`partial`生成应用程序时，为标记文件生成的类 (请参阅[构建 WPF 应用程序](building-a-wpf-application-wpf.md))。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-160">This allows the code-behind file to be associated with the `partial` class that is generated for the markup file when the application is built (see [Building a WPF Application](building-a-wpf-application-wpf.md)).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-161">创建新的 WPF 应用程序项目或使用 Visual Studio 的 WPF 浏览器应用程序项目时，应用程序定义默认情况下包括和使用标记和代码隐藏定义。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-161">When you create a new WPF Application project or WPF Browser Application project using Visual Studio, an application definition is included by default and is defined using both markup and code-behind.</span></span>  
  
 <span data-ttu-id="1bf2d-162">至少要有这段代码，才能实现应用程序定义。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-162">This code is the minimum that is required to implement an application definition.</span></span> <span data-ttu-id="1bf2d-163">但是，需要对应用程序定义生成和运行应用程序之前进行其他的 MSBuild 配置。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-163">However, an additional MSBuild configuration needs to be made to the application definition before building and running the application.</span></span>  
  
### <a name="configuring-the-application-definition-for-msbuild"></a><span data-ttu-id="1bf2d-164">针对 MSBuild 配置应用程序定义</span><span class="sxs-lookup"><span data-stu-id="1bf2d-164">Configuring the Application Definition for MSBuild</span></span>  
 <span data-ttu-id="1bf2d-165">独立应用程序和 XAML 浏览器应用程序 (Xbap) 需要一定的基础结构的实现，才能运行。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-165">Standalone applications and XAML browser applications (XBAPs) require the implementation of a certain level of infrastructure before they can run.</span></span> <span data-ttu-id="1bf2d-166">在该基础结构中，入口点是最重要的一个部分。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-166">The most important part of this infrastructure is the entry point.</span></span> <span data-ttu-id="1bf2d-167">当用户启动某个应用程序时，操作系统会调用入口点，这是一个为人熟知的应用程序启动函数。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-167">When an application is launched by a user, the operating system calls the entry point, which is a well-known function for starting applications.</span></span>  
  
 <span data-ttu-id="1bf2d-168">通常，开发者需要自行编写其中的部分或全部代码（具体取决于所采用的技术）。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-168">Traditionally, developers have needed to write some or all of this code for themselves, depending on the technology.</span></span> <span data-ttu-id="1bf2d-169">但是，WPF 将生成此代码为你的应用程序定义的标记文件配置为 MSBuild 时`ApplicationDefinition`项，如以下 MSBuild 项目文件中所示：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-169">However, WPF generates this code for you when the markup file of your application definition is configured as an MSBuild `ApplicationDefinition` item, as shown in the following MSBuild project file:</span></span>  
  
```xml  
<Project   
  DefaultTargets="Build"  
                        xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  ...  
  <ApplicationDefinition Include="App.xaml" />  
  <Compile Include="App.xaml.cs" />  
  ...  
</Project>  
```  
  
 <span data-ttu-id="1bf2d-170">代码隐藏文件包含代码，因为它被标记为 MSBuild`Compile`项，按原样正常。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-170">Because the code-behind file contains code, it is marked as an MSBuild `Compile` item, as is normal.</span></span>  
  
 <span data-ttu-id="1bf2d-171">这些标记和代码隐藏文件的应用程序定义的 MSBuild 配置应用程序，MSBuild 将生成如下所示的代码：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-171">The application of these MSBuild configurations to the markup and code-behind files of an application definition causes MSBuild to generate code like the following:</span></span>  
  
 [!code-csharp[auto-generated-code](~/samples/snippets/csharp/VS_Snippets_Wpf/AppDefAugSnippets/CSharp/App.cs)]
 [!code-vb[auto-generated-code](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppDefAugSnippets/VisualBasic/App.vb)]  
  
 <span data-ttu-id="1bf2d-172">生成的代码扩充了应用程序定义与其他基础结构代码，其中包括入口点方法`Main`。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-172">The resulting code augments your application definition with additional infrastructure code, which includes the entry-point method `Main`.</span></span> <span data-ttu-id="1bf2d-173"><xref:System.STAThreadAttribute>特性应用于`Main`方法，以指示 WPF 应用程序的主 UI 线程是 STA 线程，所需的 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-173">The <xref:System.STAThreadAttribute> attribute is applied to the `Main` method to indicate that the main UI thread for the WPF application is an STA thread, which is required for WPF applications.</span></span> <span data-ttu-id="1bf2d-174">调用时，`Main`创建的新实例`App`然后才能调用`InitializeComponent`标记中实现方法来注册事件并设置属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-174">When called, `Main` creates a new instance of `App` before calling the `InitializeComponent` method to register the events and set the properties that are implemented in markup.</span></span> <span data-ttu-id="1bf2d-175">因为`InitializeComponent`生成，你无需显式调用`InitializeComponent`从应用程序定义像<xref:System.Windows.Controls.Page>和<xref:System.Windows.Window>实现。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-175">Because `InitializeComponent` is generated for you, you don't need to explicitly call `InitializeComponent` from an application definition like you do for <xref:System.Windows.Controls.Page> and <xref:System.Windows.Window> implementations.</span></span> <span data-ttu-id="1bf2d-176">最后，<xref:System.Windows.Application.Run%2A>调用方法来启动该应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-176">Finally, the <xref:System.Windows.Application.Run%2A> method is called to start the application.</span></span>  
  
<a name="Getting_the_Current_Application"></a>   
## <a name="getting-the-current-application"></a><span data-ttu-id="1bf2d-177">获取当前应用程序</span><span class="sxs-lookup"><span data-stu-id="1bf2d-177">Getting the Current Application</span></span>  
 <span data-ttu-id="1bf2d-178">因为的功能<xref:System.Windows.Application>类共享跨应用程序，可以只有一个实例<xref:System.Windows.Application>每个类<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-178">Because the functionality of the <xref:System.Windows.Application> class are shared across an application, there can be only one instance of the <xref:System.Windows.Application> class per <xref:System.AppDomain>.</span></span> <span data-ttu-id="1bf2d-179">若要强制执行此操作，请<xref:System.Windows.Application>类作为一个单独的类实现 (请参阅[C# 中实现单一实例](https://go.microsoft.com/fwlink/?LinkId=100567))，它创建其自身的单个实例，并提供了共享访问与它通信`static` <xref:System.Windows.Application.Current%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-179">To enforce this, the <xref:System.Windows.Application> class is implemented as a singleton class (see [Implementing Singleton in C#](https://go.microsoft.com/fwlink/?LinkId=100567)), which creates a single instance of itself and provides shared access to it with the `static`<xref:System.Windows.Application.Current%2A> property.</span></span>  
  
 <span data-ttu-id="1bf2d-180">下面的代码演示如何获取对的引用<xref:System.Windows.Application>对象当前<xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-180">The following code shows how to acquire a reference to the <xref:System.Windows.Application> object for the current <xref:System.AppDomain>.</span></span>  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getcurrentappcode)]  
  
 <span data-ttu-id="1bf2d-181"><xref:System.Windows.Application.Current%2A> 返回到的实例的引用<xref:System.Windows.Application>类。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-181"><xref:System.Windows.Application.Current%2A> returns a reference to an instance of the <xref:System.Windows.Application> class.</span></span> <span data-ttu-id="1bf2d-182">如果你想对您<xref:System.Windows.Application>派生的类必须强制转换的值<xref:System.Windows.Application.Current%2A>属性，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-182">If you want a reference to your <xref:System.Windows.Application> derived class you must cast the value of the <xref:System.Windows.Application.Current%2A> property, as shown in the following example.</span></span>  
  
 [!code-csharp[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/MainWindow.xaml.cs#getstcurrentappcode)]
 [!code-vb[ApplicationManagementOverviewSnippets#GetSTCurrentAppCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/VisualBasic/MainWindow.xaml.vb#getstcurrentappcode)]  
  
 <span data-ttu-id="1bf2d-183">您可以检查的值<xref:System.Windows.Application.Current%2A>中的生存期内随时<xref:System.Windows.Application>对象。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-183">You can inspect the value of <xref:System.Windows.Application.Current%2A> at any point in the lifetime of an <xref:System.Windows.Application> object.</span></span> <span data-ttu-id="1bf2d-184">但是，检查时要小心。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-184">However, you should be careful.</span></span> <span data-ttu-id="1bf2d-185">之后<xref:System.Windows.Application>实例化类时，在此期间一段内的状态<xref:System.Windows.Application>对象不一致。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-185">After the <xref:System.Windows.Application> class is instantiated, there is a period during which the state of the <xref:System.Windows.Application> object is inconsistent.</span></span> <span data-ttu-id="1bf2d-186">在此期间，<xref:System.Windows.Application>执行各项初始化任务所需的代码运行，包括建立应用程序基础结构、 设置属性，以及注册事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-186">During this period, <xref:System.Windows.Application> is performing the various initialization tasks that are required by your code to run, including establishing application infrastructure, setting properties, and registering events.</span></span> <span data-ttu-id="1bf2d-187">如果尝试使用<xref:System.Windows.Application>对象在此期间，您的代码可能具有意外的结果，尤其是当它依赖于各种<xref:System.Windows.Application>所设置的属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-187">If you try to use the <xref:System.Windows.Application> object during this period, your code may have unexpected results, particularly if it depends on the various <xref:System.Windows.Application> properties being set.</span></span>  
  
 <span data-ttu-id="1bf2d-188">当<xref:System.Windows.Application>完成其初始化工作，其生存期内才真正开始。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-188">When <xref:System.Windows.Application> completes its initialization work, its lifetime truly begins.</span></span>  
  
<a name="Application_Lifetime"></a>   
## <a name="application-lifetime"></a><span data-ttu-id="1bf2d-189">应用程序生存期</span><span class="sxs-lookup"><span data-stu-id="1bf2d-189">Application Lifetime</span></span>  
 <span data-ttu-id="1bf2d-190">WPF 应用程序的生存期标记的几个事件引发的<xref:System.Windows.Application>，告知你启动应用程序后，经过激活和停用，并已关闭。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-190">The lifetime of a WPF application is marked by several events that are raised by <xref:System.Windows.Application> to let you know when your application has started, has been activated and deactivated, and has been shut down.</span></span>  
  
  
<a name="Splash_Screen"></a>   
### <a name="splash-screen"></a><span data-ttu-id="1bf2d-191">初始屏幕</span><span class="sxs-lookup"><span data-stu-id="1bf2d-191">Splash Screen</span></span>  
 <span data-ttu-id="1bf2d-192">在中启动[!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)]，可以指定要在启动窗口中，使用的图像或*初始屏幕*。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-192">Starting in the [!INCLUDE[net_v35SP1_short](../../../../includes/net-v35sp1-short-md.md)], you can specify an image to be used in a startup window, or *splash screen*.</span></span> <span data-ttu-id="1bf2d-193"><xref:System.Windows.SplashScreen>类可以轻松加载你的应用程序时显示启动窗口。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-193">The <xref:System.Windows.SplashScreen> class makes it easy to display a startup window while your application is loading.</span></span> <span data-ttu-id="1bf2d-194"><xref:System.Windows.SplashScreen>窗口中将创建和显示之前<xref:System.Windows.Application.Run%2A>调用。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-194">The <xref:System.Windows.SplashScreen> window is created and shown before <xref:System.Windows.Application.Run%2A> is called.</span></span> <span data-ttu-id="1bf2d-195">有关详细信息，请参阅[应用程序启动时间](../advanced/application-startup-time.md)并[向 WPF 应用程序添加初始屏幕](how-to-add-a-splash-screen-to-a-wpf-application.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-195">For more information, see [Application Startup Time](../advanced/application-startup-time.md) and [Add a Splash Screen to a WPF Application](how-to-add-a-splash-screen-to-a-wpf-application.md).</span></span>  
  
<a name="Starting_an_Application"></a>   
### <a name="starting-an-application"></a><span data-ttu-id="1bf2d-196">启动应用程序</span><span class="sxs-lookup"><span data-stu-id="1bf2d-196">Starting an Application</span></span>  
 <span data-ttu-id="1bf2d-197">之后<xref:System.Windows.Application.Run%2A>称为和初始化应用程序，该应用程序已准备好运行。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-197">After <xref:System.Windows.Application.Run%2A> is called and the application is initialized, the application is ready to run.</span></span> <span data-ttu-id="1bf2d-198">当表示此时刻<xref:System.Windows.Application.Startup>引发事件：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-198">This moment is signified when the <xref:System.Windows.Application.Startup> event is raised:</span></span>  
  
[!code-csharp[Startup-event](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs?range=3-11,31-33)]
[!code-vb[Startup-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb?range=5-11,30-32)]
  
 <span data-ttu-id="1bf2d-199">此时在应用程序的生命周期的最常见的做法是显示 UI。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-199">At this point in an application's lifetime, the most common thing to do is to show a UI.</span></span>  
  
<a name="Showing_a_User_Interface"></a>
### <a name="showing-a-user-interface"></a><span data-ttu-id="1bf2d-200">显示用户界面</span><span class="sxs-lookup"><span data-stu-id="1bf2d-200">Showing a User Interface</span></span>  
 <span data-ttu-id="1bf2d-201">大多数的独立 Windows 应用程序打开<xref:System.Windows.Window>开始时间运行。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-201">Most standalone Windows applications open a <xref:System.Windows.Window> when they begin running.</span></span> <span data-ttu-id="1bf2d-202"><xref:System.Windows.Application.Startup>事件处理程序是一个位置可以从其执行此操作，如以下代码所示。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-202">The <xref:System.Windows.Application.Startup> event handler is one location from which you can do this, as demonstrated by the following code.</span></span>  
  
 [!code-xaml[AppShowWindowHardSnippets#StartupEventMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml#startupeventmarkup)]  
  
 [!code-csharp[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/AppShowWindowHardSnippets/CSharp/App.xaml.cs#startupeventcodebehind)]
 [!code-vb[AppShowWindowHardSnippets#StartupEventCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/AppShowWindowHardSnippets/VisualBasic/Application.xaml.vb#startupeventcodebehind)]  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-203">第一个<xref:System.Windows.Window>要实例化位于独立的应用程序将成为主应用程序窗口默认情况下。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-203">The first <xref:System.Windows.Window> to be instantiated in a standalone application becomes the main application window by default.</span></span> <span data-ttu-id="1bf2d-204">这<xref:System.Windows.Window>引用的对象<xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-204">This <xref:System.Windows.Window> object is referenced by the <xref:System.Windows.Application.MainWindow%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="1bf2d-205">值<xref:System.Windows.Application.MainWindow%2A>属性可以以编程方式更改，如果第一个不同的窗口实例化<xref:System.Windows.Window>应该是主窗口。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-205">The value of the <xref:System.Windows.Application.MainWindow%2A> property can be changed programmatically if a different window than the first instantiated <xref:System.Windows.Window> should be the main window.</span></span>  
  
 <span data-ttu-id="1bf2d-206">XBAP 首次启动时，它将很可能会导航到<xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-206">When an XBAP first starts, it will most likely navigate to a <xref:System.Windows.Controls.Page>.</span></span> <span data-ttu-id="1bf2d-207">以下代码对此进行了演示。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-207">This is shown in the following code.</span></span>  
  
 [!code-xaml[XBAPAppStartupSnippets#StartupXBAPMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml#startupxbapmarkup)]  
  
 [!code-csharp[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/XBAPAppStartupSnippets/CSharp/App.xaml.cs#startupxbapcodebehind)]
 [!code-vb[XBAPAppStartupSnippets#StartupXBAPCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/XBAPAppStartupSnippets/VisualBasic/Application.xaml.vb#startupxbapcodebehind)]  
  
 <span data-ttu-id="1bf2d-208">如果处理<xref:System.Windows.Application.Startup>仅打开<xref:System.Windows.Window>或导航到<xref:System.Windows.Controls.Page>，可以设置`StartupUri`特性标记中。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-208">If you handle <xref:System.Windows.Application.Startup> to only open a <xref:System.Windows.Window> or navigate to a <xref:System.Windows.Controls.Page>, you can set the `StartupUri` attribute in markup instead.</span></span>  
  
 <span data-ttu-id="1bf2d-209">下面的示例演示如何使用<xref:System.Windows.Application.StartupUri%2A>独立应用程序以打开<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-209">The following example shows how to use the <xref:System.Windows.Application.StartupUri%2A> from a standalone application to open a <xref:System.Windows.Window>.</span></span>  
  
 [!code-xaml[ApplicationManagementOverviewSnippets#OverviewStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationManagementOverviewSnippets/CSharp/App.xaml#overviewstartupurimarkup)]  
  
 <span data-ttu-id="1bf2d-210">下面的示例演示如何使用<xref:System.Windows.Application.StartupUri%2A>XBAP 以导航到从<xref:System.Windows.Controls.Page>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-210">The following example shows how to use <xref:System.Windows.Application.StartupUri%2A> from an XBAP to navigate to a <xref:System.Windows.Controls.Page>.</span></span>  
  
 [!code-xaml[PageSnippets#XBAPStartupUriMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/PageSnippets/CSharp/App.xaml#xbapstartupurimarkup)]  
  
 <span data-ttu-id="1bf2d-211">此标记的效果等同于用于打开窗口的上一段代码。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-211">This markup has the same effect as the previous code for opening a window.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-212">在导航栏的详细信息，请参阅[导航概述](navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-212">For more information on navigation, see [Navigation Overview](navigation-overview.md).</span></span>  
  
 <span data-ttu-id="1bf2d-213">您需要处理<xref:System.Windows.Application.Startup>事件以打开<xref:System.Windows.Window>如果需要实例化它使用非默认构造函数，或需要设置其属性或订阅其事件之前显示它，或需要处理任何命令行参数，启动应用程序时提供。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-213">You need to handle the <xref:System.Windows.Application.Startup> event to open a <xref:System.Windows.Window> if you need to instantiate it using a non-default constructor, or you need to set its properties or subscribe to its events before showing it, or you need to process any command-line arguments that were supplied when the application was launched.</span></span>  
  
<a name="Processing_Command_Line_Arguments"></a>   
### <a name="processing-command-line-arguments"></a><span data-ttu-id="1bf2d-214">处理命令行参数</span><span class="sxs-lookup"><span data-stu-id="1bf2d-214">Processing Command-Line Arguments</span></span>  
 <span data-ttu-id="1bf2d-215">在 Windows 中，可以从命令提示符或桌面启动独立应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-215">In Windows, standalone applications can be launched from either a command prompt or the desktop.</span></span> <span data-ttu-id="1bf2d-216">在这两种情况下，命令行参数都可以传递至应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-216">In both cases, command-line arguments can be passed to the application.</span></span> <span data-ttu-id="1bf2d-217">以下示例展示了一个通过单个命令行参数“/StartMinimized”来启动的应用程序：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-217">The following example shows an application that is launched with a single command-line argument, "/StartMinimized":</span></span>  
  
 `wpfapplication.exe /StartMinimized`  
  
 <span data-ttu-id="1bf2d-218">在应用程序初始化期间 WPF 从操作系统检索命令行参数，并将它们传递到<xref:System.Windows.Application.Startup>事件处理程序通过<xref:System.Windows.StartupEventArgs.Args%2A>属性的<xref:System.Windows.StartupEventArgs>参数。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-218">During application initialization, WPF retrieves the command-line arguments from the operating system and passes them to the <xref:System.Windows.Application.Startup> event handler via the <xref:System.Windows.StartupEventArgs.Args%2A> property of the <xref:System.Windows.StartupEventArgs> parameter.</span></span> <span data-ttu-id="1bf2d-219">可以使用如下代码来检索和存储命令行参数。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-219">You can retrieve and store the command-line arguments using code like the following.</span></span>  
  
 [!code-xaml[ApplicationStartupSnippets#HandleStartupXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml#handlestartupxaml)]  
  
 [!code-csharp[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationStartupSnippets/CSharp/App.xaml.cs#handlestartupcodebehind)]
 [!code-vb[ApplicationStartupSnippets#HandleStartupCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationStartupSnippets/visualbasic/application.xaml.vb#handlestartupcodebehind)]  
  
 <span data-ttu-id="1bf2d-220">这段代码处理<xref:System.Windows.Application.Startup>检查是否 **/StartMinimized**提供的命令行参数; 如果是这样，它将打开主窗口中的以<xref:System.Windows.WindowState>的<xref:System.Windows.WindowState.Minimized>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-220">The code handles <xref:System.Windows.Application.Startup> to check whether the **/StartMinimized** command-line argument was provided; if so, it opens the main window with a <xref:System.Windows.WindowState> of <xref:System.Windows.WindowState.Minimized>.</span></span> <span data-ttu-id="1bf2d-221">请注意，由于<xref:System.Windows.Window.WindowState%2A>必须以编程方式设置主属性<xref:System.Windows.Window>必须在代码中显式打开。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-221">Note that because the <xref:System.Windows.Window.WindowState%2A> property must be set programmatically, the main <xref:System.Windows.Window> must be opened explicitly in code.</span></span>  
  
 <span data-ttu-id="1bf2d-222">Xbap 不能检索和处理命令行参数，因为程序启动时使用 ClickOnce 部署 (请参阅[部署 WPF 应用程序](deploying-a-wpf-application-wpf.md))。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-222">XBAPs cannot retrieve and process command-line arguments because they are launched using ClickOnce deployment (see [Deploying a WPF Application](deploying-a-wpf-application-wpf.md)).</span></span> <span data-ttu-id="1bf2d-223">但是，它们可以检索和处理来自用于启动它们的 URL 的查询字符串参数。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-223">However, they can retrieve and process query string parameters from the URLs that are used to launch them.</span></span>  
  
<a name="Application_Activation_and_Deactivation"></a>   
### <a name="application-activation-and-deactivation"></a><span data-ttu-id="1bf2d-224">应用程序激活和停用</span><span class="sxs-lookup"><span data-stu-id="1bf2d-224">Application Activation and Deactivation</span></span>  
 <span data-ttu-id="1bf2d-225">Windows 允许用户应用程序之间切换。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-225">Windows allows users to switch between applications.</span></span> <span data-ttu-id="1bf2d-226">最常见的方法是使用 ALT + TAB 键组合。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-226">The most common way is to use the ALT+TAB key combination.</span></span> <span data-ttu-id="1bf2d-227">仅可应用程序切换为，如果具有可见<xref:System.Windows.Window>，用户可以选择。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-227">An application can only be switched to if it has a visible <xref:System.Windows.Window> that a user can select.</span></span> <span data-ttu-id="1bf2d-228">当前所选<xref:System.Windows.Window>是*活动窗口*(也称为*前台窗口*) 是<xref:System.Windows.Window>接收用户输入。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-228">The currently selected <xref:System.Windows.Window> is the *active window* (also known as the *foreground window*) and is the <xref:System.Windows.Window> that receives user input.</span></span> <span data-ttu-id="1bf2d-229">与活动窗口的应用程序是*活动的应用程序*(或*前台应用程序*)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-229">The application with the active window is the *active application* (or *foreground application*).</span></span> <span data-ttu-id="1bf2d-230">应用程序会在以下情况下变为活动应用程序：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-230">An application becomes the active application in the following circumstances:</span></span>  
  
-   <span data-ttu-id="1bf2d-231">它将启动并显示<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-231">It is launched and shows a <xref:System.Windows.Window>.</span></span>  
  
-   <span data-ttu-id="1bf2d-232">用户通过选择从另一个应用程序切换<xref:System.Windows.Window>应用程序中。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-232">A user switches from another application by selecting a <xref:System.Windows.Window> in the application.</span></span>  
  
 <span data-ttu-id="1bf2d-233">通过处理应用程序将变为活动状态时可以检测<xref:System.Windows.Application.Activated?displayProperty=nameWithType>事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-233">You can detect when an application becomes active by handling the <xref:System.Windows.Application.Activated?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="1bf2d-234">同样地，应用程序会在以下情况下变为非活动状态：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-234">Likewise, an application can become inactive in the following circumstances:</span></span>  
  
-   <span data-ttu-id="1bf2d-235">用户从当前应用程序切换到另一应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-235">A user switches to another application from the current one.</span></span>  
  
-   <span data-ttu-id="1bf2d-236">应用程序关闭后。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-236">When the application shuts down.</span></span>  
  
 <span data-ttu-id="1bf2d-237">当应用程序通过处理成为非活动状态时，可以检测到<xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-237">You can detect when an application becomes inactive by handling the <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> event.</span></span>  
  
 <span data-ttu-id="1bf2d-238">下面的代码演示如何处理<xref:System.Windows.Application.Activated>和<xref:System.Windows.Application.Deactivated>事件，以确定应用程序是否处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-238">The following code shows how to handle the <xref:System.Windows.Application.Activated> and <xref:System.Windows.Application.Deactivated> events to determine whether an application is active.</span></span>  
  
 [!code-xaml[ApplicationActivationSnippets#DetectActivationStateXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml#detectactivationstatexaml)]  
  
 [!code-csharp[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationActivationSnippets/CSharp/App.xaml.cs#detectactivationstatecodebehind)]
 [!code-vb[ApplicationActivationSnippets#DetectActivationStateCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationActivationSnippets/visualbasic/application.xaml.vb#detectactivationstatecodebehind)]  
  
 <span data-ttu-id="1bf2d-239">一个<xref:System.Windows.Window>还可以激活和停用。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-239">A <xref:System.Windows.Window> can also be activated and deactivated.</span></span> <span data-ttu-id="1bf2d-240">有关更多信息，请参见<xref:System.Windows.Window.Activated?displayProperty=nameWithType>和<xref:System.Windows.Window.Deactivated?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-240">See <xref:System.Windows.Window.Activated?displayProperty=nameWithType> and <xref:System.Windows.Window.Deactivated?displayProperty=nameWithType> for more information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-241">既不<xref:System.Windows.Application.Activated?displayProperty=nameWithType>也不<xref:System.Windows.Application.Deactivated?displayProperty=nameWithType>引发的 Xbap。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-241">Neither <xref:System.Windows.Application.Activated?displayProperty=nameWithType> nor <xref:System.Windows.Application.Deactivated?displayProperty=nameWithType> is raised for XBAPs.</span></span>  
  
<a name="Application_Shutdown"></a>   
### <a name="application-shutdown"></a><span data-ttu-id="1bf2d-242">应用程序关闭</span><span class="sxs-lookup"><span data-stu-id="1bf2d-242">Application Shutdown</span></span>  
 <span data-ttu-id="1bf2d-243">应用程序的生存期会在其关闭时结束，出现这一情况可能是因为：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-243">The life of an application ends when it is shut down, which can occur for the following reasons:</span></span>  
  
-   <span data-ttu-id="1bf2d-244">用户关闭每个<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-244">A user closes every <xref:System.Windows.Window>.</span></span>  
  
-   <span data-ttu-id="1bf2d-245">用户关闭了主<xref:System.Windows.Window>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-245">A user closes the main <xref:System.Windows.Window>.</span></span>  
  
-   <span data-ttu-id="1bf2d-246">用户通过注销或关闭来结束 Windows 会话。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-246">A user ends the Windows session by logging off or shutting down.</span></span>  
  
-   <span data-ttu-id="1bf2d-247">满足了特定于应用程序的条件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-247">An application-specific condition has been met.</span></span>  
  
 <span data-ttu-id="1bf2d-248">若要帮助你管理应用程序关闭<xref:System.Windows.Application>提供了<xref:System.Windows.Application.Shutdown%2A>方法，<xref:System.Windows.Application.ShutdownMode%2A>属性，和<xref:System.Windows.Application.SessionEnding>和<xref:System.Windows.Application.Exit>事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-248">To help you manage application shutdown, <xref:System.Windows.Application> provides the <xref:System.Windows.Application.Shutdown%2A> method, the <xref:System.Windows.Application.ShutdownMode%2A> property, and the <xref:System.Windows.Application.SessionEnding> and <xref:System.Windows.Application.Exit> events.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-249"><xref:System.Windows.Application.Shutdown%2A> 仅可以从具有的应用程序调用<xref:System.Security.Permissions.UIPermission>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-249"><xref:System.Windows.Application.Shutdown%2A> can only be called from applications that have <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="1bf2d-250">独立 WPF 应用程序始终具有此权限。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-250">Standalone WPF applications always have this permission.</span></span> <span data-ttu-id="1bf2d-251">但是，Internet 区域部分信任安全沙箱中运行的 Xbap 不这样做。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-251">However, XBAPs running in the Internet zone partial-trust security sandbox do not.</span></span>  
  
#### <a name="shutdown-mode"></a><span data-ttu-id="1bf2d-252">关闭模式</span><span class="sxs-lookup"><span data-stu-id="1bf2d-252">Shutdown Mode</span></span>  
 <span data-ttu-id="1bf2d-253">大多数应用程序会在所有窗口都关闭后或在主窗口关闭后关闭。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-253">Most applications shut down either when all the windows are closed or when the main window is closed.</span></span> <span data-ttu-id="1bf2d-254">但是，有时，应用程序会在何时关闭取决于特定于应用程序的其他条件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-254">Sometimes, however, other application-specific conditions may determine when an application shuts down.</span></span> <span data-ttu-id="1bf2d-255">你可以指定在其下你的应用程序会自动关机设置的条件<xref:System.Windows.Application.ShutdownMode%2A>具有以下项之一<xref:System.Windows.ShutdownMode>枚举值：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-255">You can specify the conditions under which your application will shut down by setting <xref:System.Windows.Application.ShutdownMode%2A> with one of the following <xref:System.Windows.ShutdownMode> enumeration values:</span></span>  
  
-   <xref:System.Windows.ShutdownMode.OnLastWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnMainWindowClose>  
  
-   <xref:System.Windows.ShutdownMode.OnExplicitShutdown>  
  
 <span data-ttu-id="1bf2d-256">默认值<xref:System.Windows.Application.ShutdownMode%2A>是<xref:System.Windows.ShutdownMode.OnLastWindowClose>，这意味着，应用程序会自动将关闭时用户关闭应用程序中的最后一个窗口。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-256">The default value of <xref:System.Windows.Application.ShutdownMode%2A> is <xref:System.Windows.ShutdownMode.OnLastWindowClose>, which means that an application automatically shuts down when the last window in the application is closed by the user.</span></span> <span data-ttu-id="1bf2d-257">但是，如果主窗口关闭时，应关闭你的应用程序，WPF 会自动执行，如果您设置<xref:System.Windows.Application.ShutdownMode%2A>到<xref:System.Windows.ShutdownMode.OnMainWindowClose>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-257">However, if your application should be shut down when the main window is closed, WPF automatically does that if you set <xref:System.Windows.Application.ShutdownMode%2A> to <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span> <span data-ttu-id="1bf2d-258">这在下面的示例中显示。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-258">This is shown in the following example.</span></span>  
  
 [!code-xaml[ApplicationShutdownModeSnippets#OnMainWindowCloseMARKUP](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationShutdownModeSnippets/CS/Page1.xaml#onmainwindowclosemarkup)]  
  
 <span data-ttu-id="1bf2d-259">特定于应用程序的关闭条件后，您设置<xref:System.Windows.Application.ShutdownMode%2A>到<xref:System.Windows.ShutdownMode.OnExplicitShutdown>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-259">When you have application-specific shutdown conditions, you set <xref:System.Windows.Application.ShutdownMode%2A> to <xref:System.Windows.ShutdownMode.OnExplicitShutdown>.</span></span> <span data-ttu-id="1bf2d-260">在这种情况下，则需要负责以关闭应用程序的情况下通过显式调用<xref:System.Windows.Application.Shutdown%2A>方法; 否则，你的应用程序将继续运行，即使所有窗口已都关闭。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-260">In this case, it is your responsibility to shut an application down by explicitly calling the <xref:System.Windows.Application.Shutdown%2A> method; otherwise, your application will continue running even if all the windows are closed.</span></span> <span data-ttu-id="1bf2d-261">请注意，<xref:System.Windows.Application.Shutdown%2A>时隐式调用<xref:System.Windows.Application.ShutdownMode%2A>可以是<xref:System.Windows.ShutdownMode.OnLastWindowClose>或<xref:System.Windows.ShutdownMode.OnMainWindowClose>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-261">Note that <xref:System.Windows.Application.Shutdown%2A> is called implicitly when the <xref:System.Windows.Application.ShutdownMode%2A> is either <xref:System.Windows.ShutdownMode.OnLastWindowClose> or <xref:System.Windows.ShutdownMode.OnMainWindowClose>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-262"><xref:System.Windows.Application.ShutdownMode%2A> 可以设置从 XBAP，但将被忽略;在浏览器中或已关闭承载 XBAP 的浏览器导航离开时，将始终关闭 XBAP。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-262"><xref:System.Windows.Application.ShutdownMode%2A> can be set from an XBAP, but it is ignored; an XBAP is always shut down when it is navigated away from in a browser or when the browser that hosts the XBAP is closed.</span></span> <span data-ttu-id="1bf2d-263">有关详细信息，请参阅[导航概述](navigation-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-263">For more information, see [Navigation Overview](navigation-overview.md).</span></span>  
  
#### <a name="session-ending"></a><span data-ttu-id="1bf2d-264">会话结束</span><span class="sxs-lookup"><span data-stu-id="1bf2d-264">Session Ending</span></span>  
 <span data-ttu-id="1bf2d-265">由描述的关闭条件<xref:System.Windows.Application.ShutdownMode%2A>属性是特定于应用程序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-265">The shutdown conditions that are described by the <xref:System.Windows.Application.ShutdownMode%2A> property are specific to an application.</span></span> <span data-ttu-id="1bf2d-266">不过，在某些情况下，应用程序可能会因外部条件而关闭。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-266">In some cases, though, an application may shut down as a result of an external condition.</span></span> <span data-ttu-id="1bf2d-267">用户通过以下操作来结束 Windows 会话时发生的最常见的外部条件：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-267">The most common external condition occurs when a user ends the Windows session by the following actions:</span></span>  
  
-   <span data-ttu-id="1bf2d-268">注销</span><span class="sxs-lookup"><span data-stu-id="1bf2d-268">Logging off</span></span>  
  
-   <span data-ttu-id="1bf2d-269">关闭</span><span class="sxs-lookup"><span data-stu-id="1bf2d-269">Shutting down</span></span>  
  
-   <span data-ttu-id="1bf2d-270">重新启动</span><span class="sxs-lookup"><span data-stu-id="1bf2d-270">Restarting</span></span>  
  
-   <span data-ttu-id="1bf2d-271">休眠</span><span class="sxs-lookup"><span data-stu-id="1bf2d-271">Hibernating</span></span>  
  
 <span data-ttu-id="1bf2d-272">若要检测 Windows 会话结束时，你可以处理<xref:System.Windows.Application.SessionEnding>事件，如下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-272">To detect when a Windows session ends, you can handle the <xref:System.Windows.Application.SessionEnding> event, as illustrated in the following example.</span></span>  
  
 [!code-xaml[ApplicationSessionEndingSnippets#HandlingSessionEndingXAML](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml#handlingsessionendingxaml)]  
  
 [!code-csharp[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/CSharp/App.xaml.cs#handlingsessionendingcodebehind)]
 [!code-vb[ApplicationSessionEndingSnippets#HandlingSessionEndingCODEBEHIND](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationSessionEndingSnippets/visualbasic/application.xaml.vb#handlingsessionendingcodebehind)]  
  
 <span data-ttu-id="1bf2d-273">在此示例中，代码会检查<xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A>属性来确定如何结束 Windows 会话。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-273">In this example, the code inspects the <xref:System.Windows.SessionEndingCancelEventArgs.ReasonSessionEnding%2A> property to determine how the Windows session is ending.</span></span> <span data-ttu-id="1bf2d-274">它会根据该值向用户显示确认消息。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-274">It uses this value to display a confirmation message to the user.</span></span> <span data-ttu-id="1bf2d-275">如果用户不希望会话结束，该代码将设置<xref:System.ComponentModel.CancelEventArgs.Cancel%2A>到`true`以阻止结束 Windows 会话。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-275">If the user does not want the session to end, the code sets <xref:System.ComponentModel.CancelEventArgs.Cancel%2A> to `true` to prevent the Windows session from ending.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-276"><xref:System.Windows.Application.SessionEnding> 不会引发为 Xbap。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-276"><xref:System.Windows.Application.SessionEnding> is not raised for XBAPs.</span></span>

#### <a name="exit"></a><span data-ttu-id="1bf2d-277">Exit</span><span class="sxs-lookup"><span data-stu-id="1bf2d-277">Exit</span></span>  
 <span data-ttu-id="1bf2d-278">应用程序在关闭时可能需要执行一些最终处理，如保持应用程序状态。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-278">When an application shuts down, it may need to perform some final processing, such as persisting application state.</span></span> <span data-ttu-id="1bf2d-279">对于这些情况下，您就可以处理<xref:System.Windows.Application.Exit>事件，作为`App_Exit`事件处理程序执行在下面的示例。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-279">For these situations, you can handle the <xref:System.Windows.Application.Exit> event, as the `App_Exit` event handler does in the following example.</span></span> <span data-ttu-id="1bf2d-280">它被定义为事件处理程序中*App.xaml*文件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-280">It is defined as an event handler in the *App.xaml* file.</span></span> <span data-ttu-id="1bf2d-281">其实现中突出显示*App.xaml.cs*并*Application.xaml.vb*文件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-281">Its implementation is highlighted in the *App.xaml.cs* and *Application.xaml.vb* files.</span></span>
  
[!code-xaml[Defining-the-Exit-event-handler](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]  
  
 [!code-csharp[Handling-the-Exit-event](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=42-55)]
 [!code-vb[Handling-the-Exit-event](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=34-45)]  
  
 <span data-ttu-id="1bf2d-282">有关完整示例，请参阅[保持和还原应用程序作用域属性跨应用程序会话](persist-and-restore-application-scope-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-282">For the complete example, see [Persist and Restore Application-Scope Properties Across Application Sessions](persist-and-restore-application-scope-properties.md).</span></span>  
  
 <span data-ttu-id="1bf2d-283"><xref:System.Windows.Application.Exit> 可以处理由独立应用程序和 Xbap。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-283"><xref:System.Windows.Application.Exit> can be handled by both standalone applications and XBAPs.</span></span> <span data-ttu-id="1bf2d-284">Xbap 的<xref:System.Windows.Application.Exit>时在以下情况下引发：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-284">For XBAPs, <xref:System.Windows.Application.Exit> is raised when in the following circumstances:</span></span>  
  
-   <span data-ttu-id="1bf2d-285">XBAP 导航离开。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-285">An XBAP is navigated away from.</span></span>  
  
-   <span data-ttu-id="1bf2d-286">在[!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)]，当关闭承载 XBAP 的选项卡。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-286">In [!INCLUDE[TLA2#tla_ie7](../../../../includes/tla2sharptla-ie7-md.md)], when the tab that is hosting the XBAP is closed.</span></span>  
  
-   <span data-ttu-id="1bf2d-287">关闭浏览器时。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-287">When the browser is closed.</span></span>  
  
#### <a name="exit-code"></a><span data-ttu-id="1bf2d-288">退出代码</span><span class="sxs-lookup"><span data-stu-id="1bf2d-288">Exit Code</span></span>  
 <span data-ttu-id="1bf2d-289">在大多数情况下，应用程序由操作系统根据用户的请求来启动。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-289">Applications are mostly launched by the operating system in response to a user request.</span></span> <span data-ttu-id="1bf2d-290">但是，应用程序也可由另一应用程序启动，以执行某项特定任务。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-290">However, an application can be launched by another application to perform some specific task.</span></span> <span data-ttu-id="1bf2d-291">当被启动的应用程序关闭时，执行启动操作的应用程序可能想要了解导致被启动应用程序关闭的条件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-291">When the launched application shuts down, the launching application may want to know the condition under which the launched application shut down.</span></span> <span data-ttu-id="1bf2d-292">在这些情况下，Windows 允许应用程序在关闭会返回应用程序退出代码。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-292">In these situations, Windows allows applications to return an application exit code on shutdown.</span></span> <span data-ttu-id="1bf2d-293">默认情况下，WPF 应用程序返回的退出代码值为 0。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-293">By default, WPF applications return an exit code value of 0.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-294">应用程序退出代码时从 Visual Studio 进行调试时，会显示在**输出**窗口应用程序关闭时，在一条消息，如以下所示：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-294">When you debug from Visual Studio, the application exit code is displayed in the **Output** window when the application shuts down, in a message that looks like the following:</span></span>  
>   
>  `The program '[5340] AWPFApp.vshost.exe: Managed' has exited with code 0 (0x0).`  
>   
>  <span data-ttu-id="1bf2d-295">打开**输出**通过单击窗口**输出**上**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-295">You open the **Output** window by clicking **Output** on the **View** menu.</span></span>  
  
 <span data-ttu-id="1bf2d-296">若要更改退出代码，可以调用<xref:System.Windows.Application.Shutdown%28System.Int32%29>重载，这样便可以接受整数参数作为退出代码：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-296">To change the exit code, you can call the <xref:System.Windows.Application.Shutdown%28System.Int32%29> overload, which accepts an integer argument to be the exit code:</span></span>  
  
 [!code-csharp[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationExitSnippets/CSharp/MainWindow.xaml.cs#appexitcode)]
 [!code-vb[ApplicationExitSnippets#AppExitCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationExitSnippets/visualbasic/mainwindow.xaml.vb#appexitcode)]  
  
 <span data-ttu-id="1bf2d-297">可以检测的退出代码值和其进行更改，通过处理<xref:System.Windows.Application.Exit>事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-297">You can detect the value of the exit code, and change it, by handling the <xref:System.Windows.Application.Exit> event.</span></span> <span data-ttu-id="1bf2d-298"><xref:System.Windows.Application.Exit>事件处理程序传递<xref:System.Windows.ExitEventArgs>以便进行访问的退出代码与<xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-298">The <xref:System.Windows.Application.Exit> event handler is passed an <xref:System.Windows.ExitEventArgs> which provides access to the exit code with the <xref:System.Windows.ExitEventArgs.ApplicationExitCode%2A> property.</span></span> <span data-ttu-id="1bf2d-299">有关详细信息，请参阅 <xref:System.Windows.Application.Exit>。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-299">For more information, see <xref:System.Windows.Application.Exit>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="1bf2d-300">可以在独立应用程序和 Xbap 设置退出代码。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-300">You can set the exit code in both standalone applications and XBAPs.</span></span> <span data-ttu-id="1bf2d-301">但是，退出代码值被忽略的 Xbap。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-301">However, the exit code value is ignored for XBAPs.</span></span>  
  
<a name="Unhandled_Exceptions"></a>   
### <a name="unhandled-exceptions"></a><span data-ttu-id="1bf2d-302">未经处理的异常</span><span class="sxs-lookup"><span data-stu-id="1bf2d-302">Unhandled Exceptions</span></span>  
 <span data-ttu-id="1bf2d-303">有时，应用程序可能会在异常条件下关闭，如引发意外异常时。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-303">Sometimes an application may shut down under abnormal conditions, such as when an unanticipated exception is thrown.</span></span> <span data-ttu-id="1bf2d-304">在这种情况下，应用程序可能没有可用于检测和处理异常的代码。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-304">In this case, the application may not have the code to detect and process the exception.</span></span> <span data-ttu-id="1bf2d-305">这类异常就是未经处理的异常；应用程序会在关闭之前显示一个与下图所示内容类似的通知。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-305">This type of exception is an unhandled exception; a notification similar to that shown in the following figure is displayed before the application is closed.</span></span>  
  
 ![显示未处理的异常通知的屏幕截图。](./media/application-management-overview/unhandled-exception-notification.png)  
  
 <span data-ttu-id="1bf2d-307">从用户体验的角度来看，应用程序最好通过执行以下部分或全部操作来避免这种默认行为：</span><span class="sxs-lookup"><span data-stu-id="1bf2d-307">From the user experience perspective, it is better for an application to avoid this default behavior by doing some or all of the following:</span></span>  
  
-   <span data-ttu-id="1bf2d-308">显示对用户友好的信息。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-308">Displaying user-friendly information.</span></span>  
  
-   <span data-ttu-id="1bf2d-309">尝试让应用程序保持运行。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-309">Attempting to keep an application running.</span></span>  
  
-   <span data-ttu-id="1bf2d-310">录制详细，Windows 事件日志中的开发人员友好的异常信息。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-310">Recording detailed, developer-friendly exception information in the Windows event log.</span></span>  
  
 <span data-ttu-id="1bf2d-311">实现此支持取决于能否检测到未经处理的异常，这是什么<xref:System.Windows.Application.DispatcherUnhandledException>为引发事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-311">Implementing this support depends on being able to detect unhandled exceptions, which is what the <xref:System.Windows.Application.DispatcherUnhandledException> event is raised for.</span></span>  
  
[!code-xaml[detecting-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml#handledispatcherunhandledexceptionxaml)]  
  
[!code-csharp[code-to-detect-unhandled-exceptions](~/samples/snippets/csharp/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/CSharp/App.xaml.cs)]
[!code-vb[code-to-detect-unhandled-exceptions](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ApplicationDispatcherUnhandledExceptionSnippets/visualbasic/application.xaml.vb)]  
  
 <span data-ttu-id="1bf2d-312"><xref:System.Windows.Application.DispatcherUnhandledException>事件处理程序传递<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs>参数，其中包含与未经处理的异常，包括异常本身相关的上下文信息 (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>)。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-312">The <xref:System.Windows.Application.DispatcherUnhandledException> event handler is passed a <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs> parameter that contains contextual information regarding the unhandled exception, including the exception itself (<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Exception%2A?displayProperty=nameWithType>).</span></span> <span data-ttu-id="1bf2d-313">这些信息可用来确定如何处理异常。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-313">You can use this information to determine how to handle the exception.</span></span>  
  
 <span data-ttu-id="1bf2d-314">当处理<xref:System.Windows.Application.DispatcherUnhandledException>，则应将设置<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType>属性设置为`true`; 否则为 WPF 仍会将异常视为未经处理，并将恢复为前面所述的默认行为。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-314">When you handle <xref:System.Windows.Application.DispatcherUnhandledException>, you should set the <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A?displayProperty=nameWithType> property to `true`; otherwise, WPF still considers the exception to be unhandled and reverts to the default behavior described earlier.</span></span> <span data-ttu-id="1bf2d-315">如果引发了未经处理的异常和任一<xref:System.Windows.Application.DispatcherUnhandledException>不处理事件，或处理的事件和<xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A>设置为`false`，在应用程序立即关闭。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-315">If an unhandled exception is raised and either the <xref:System.Windows.Application.DispatcherUnhandledException> event is not handled, or the event is handled and <xref:System.Windows.Threading.DispatcherUnhandledExceptionEventArgs.Handled%2A> is set to `false`, the application shuts down immediately.</span></span> <span data-ttu-id="1bf2d-316">此外，没有其他<xref:System.Windows.Application>引发事件。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-316">Furthermore, no other <xref:System.Windows.Application> events are raised.</span></span> <span data-ttu-id="1bf2d-317">因此，您需要处理<xref:System.Windows.Application.DispatcherUnhandledException>如果应用程序的应用程序关闭之前必须运行的代码。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-317">Consequently, you need to handle <xref:System.Windows.Application.DispatcherUnhandledException> if your application has code that must run before the application shuts down.</span></span>  
  
 <span data-ttu-id="1bf2d-318">正如下一节所述，虽然应用程序可能会因未经处理的异常而关闭，但通常都是应用户请求而关闭的。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-318">Although an application may shut down as a result of an unhandled exception, an application usually shuts down in response to a user request, as discussed in the next section.</span></span>  
  
<a name="Application_Lifetime_Events"></a>   
### <a name="application-lifetime-events"></a><span data-ttu-id="1bf2d-319">应用程序生存期事件</span><span class="sxs-lookup"><span data-stu-id="1bf2d-319">Application Lifetime Events</span></span>  
 <span data-ttu-id="1bf2d-320">独立应用程序和 Xbap 不具有完全相同的生存期。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-320">Standalone applications and XBAPs don't have exactly the same lifetimes.</span></span> <span data-ttu-id="1bf2d-321">下图展示了独立应用程序生存期内的各个关键事件及其引发顺序。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-321">The following figure illustrates the key events in the lifetime of a standalone application and shows the sequence in which they are raised.</span></span>  
  
 <span data-ttu-id="1bf2d-322">![独立应用程序 &#45; 应用程序对象事件](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")</span><span class="sxs-lookup"><span data-stu-id="1bf2d-322">![Standalone Application &#45; Application Object Events](./media/applicationmodeloverview-applicationobjectevents.png "ApplicationModelOverview_ApplicationObjectEvents")</span></span>  
  
 <span data-ttu-id="1bf2d-323">同样，以下图生存期内的 XBAP，说明了各个关键事件及其引发它们的序列。</span><span class="sxs-lookup"><span data-stu-id="1bf2d-323">Likewise, the following figure illustrates the key events in the lifetime of an XBAP, and shows the sequence in which they are raised.</span></span>  
  
 <span data-ttu-id="1bf2d-324">![XBAP &#45; 应用程序对象事件](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")</span><span class="sxs-lookup"><span data-stu-id="1bf2d-324">![XBAP &#45; Application Object Events](./media/applicationmodeloverview-applicationobjectevents-xbap.png "ApplicationModelOverview_ApplicationObjectEvents_xbap")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1bf2d-325">请参阅</span><span class="sxs-lookup"><span data-stu-id="1bf2d-325">See also</span></span>
- <xref:System.Windows.Application>
- [<span data-ttu-id="1bf2d-326">WPF 窗口概述</span><span class="sxs-lookup"><span data-stu-id="1bf2d-326">WPF Windows Overview</span></span>](wpf-windows-overview.md)
- [<span data-ttu-id="1bf2d-327">导航概述</span><span class="sxs-lookup"><span data-stu-id="1bf2d-327">Navigation Overview</span></span>](navigation-overview.md)
- [<span data-ttu-id="1bf2d-328">WPF 应用程序资源、内容和数据文件</span><span class="sxs-lookup"><span data-stu-id="1bf2d-328">WPF Application Resource, Content, and Data Files</span></span>](wpf-application-resource-content-and-data-files.md)
- [<span data-ttu-id="1bf2d-329">WPF 中的 Pack URI</span><span class="sxs-lookup"><span data-stu-id="1bf2d-329">Pack URIs in WPF</span></span>](pack-uris-in-wpf.md)
- <span data-ttu-id="1bf2d-330">[应用程序模型：操作指南主题](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="1bf2d-330">[Application Model: How-to Topics](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms749013(v=vs.100))</span></span>
- [<span data-ttu-id="1bf2d-331">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="1bf2d-331">Application Development</span></span>](index.md)
