---
title: 演练：在组件设计器中创建 Windows 服务应用程序
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Service applications, walkthroughs
- Windows Service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
manager: douge
ms.openlocfilehash: c33b8badcacd4e228d70f8e770d4bf27144c29eb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520508"
---
# <a name="walkthrough-creating-a-windows-service-application-in-the-component-designer"></a><span data-ttu-id="859c0-102">演练：在组件设计器中创建 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="859c0-102">Walkthrough: Creating a Windows Service Application in the Component Designer</span></span>
<span data-ttu-id="859c0-103">本文演示了如何在 Visual Studio 中创建向事件日志中写入消息的简单 Windows 服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="859c0-103">This article demonstrates how to create a simple Windows Service application in Visual Studio that writes messages to an event log.</span></span> <span data-ttu-id="859c0-104">下面是创建和使用你的服务所执行的基本步骤：</span><span class="sxs-lookup"><span data-stu-id="859c0-104">Here are the basic steps that you perform to create and use your service:</span></span>  
  
1.  <span data-ttu-id="859c0-105">[创建服务](#BK_CreateProject) 使用 **Windows 服务** 项目模板，并对其进行配置。</span><span class="sxs-lookup"><span data-stu-id="859c0-105">[Creating a Service](#BK_CreateProject) by using the **Windows Service** project template, and configure it.</span></span> <span data-ttu-id="859c0-106">此模板为你创建一个从 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 继承的类，并编写大量基本服务代码，例如启动服务的代码。</span><span class="sxs-lookup"><span data-stu-id="859c0-106">This template creates a class for you that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> and writes much of the basic service code, such as the code to start the service.</span></span>  
  
2.  <span data-ttu-id="859c0-107">[向服务添加功能](#BK_WriteCode) 针对 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 过程，重写任意你想要重新定义的其他方法。</span><span class="sxs-lookup"><span data-stu-id="859c0-107">[Adding Features to the Service](#BK_WriteCode) for the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> procedures, and override any other methods that you want to redefine.</span></span>  
  
3.  <span data-ttu-id="859c0-108">[设置服务状态](#BK_SetStatus)。</span><span class="sxs-lookup"><span data-stu-id="859c0-108">[Setting Service Status](#BK_SetStatus).</span></span> <span data-ttu-id="859c0-109">默认情况下，用 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 创建的服务仅会实现可用状态标志的子集。</span><span class="sxs-lookup"><span data-stu-id="859c0-109">By default, services created with <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> implement only a subset of the available status flags.</span></span> <span data-ttu-id="859c0-110">如果你的服务启动、暂停或停止所需的时间较长，你可以实施“启动挂起”或“停止挂起”等状态值，表示它正在运行。</span><span class="sxs-lookup"><span data-stu-id="859c0-110">If your service takes a long time to start up, pause, or stop, you can implement status values such as Start Pending or Stop Pending to indicate that it's working on an operation.</span></span>  
  
4.  <span data-ttu-id="859c0-111">[向服务添加安装程序](#BK_AddInstallers) 针对你的服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="859c0-111">[Adding Installers to the Service](#BK_AddInstallers) for your service application.</span></span>  
  
5.  <span data-ttu-id="859c0-112">（可选） [设置启动参数](#BK_StartupParameters)，指定默认启动参数，并使用户在手动启动你的服务时能重写默认设置。</span><span class="sxs-lookup"><span data-stu-id="859c0-112">(Optional) [Set Startup Parameters](#BK_StartupParameters), specify default startup arguments, and enable users to override default settings when they start your service manually.</span></span>  
  
6.  <span data-ttu-id="859c0-113">[生成服务](#BK_Build)。</span><span class="sxs-lookup"><span data-stu-id="859c0-113">[Building the Service](#BK_Build).</span></span>  
  
7.  <span data-ttu-id="859c0-114">[安装服务](#BK_Install) 在本地计算机上。</span><span class="sxs-lookup"><span data-stu-id="859c0-114">[Installing the Service](#BK_Install) on the local machine.</span></span>  
  
8.  <span data-ttu-id="859c0-115">访问 Windows 服务控制管理器并 [启动和运行服务](#BK_StartService)。</span><span class="sxs-lookup"><span data-stu-id="859c0-115">Access the Windows Service Control Manager and [Starting and Running the Service](#BK_StartService).</span></span>  
  
9. <span data-ttu-id="859c0-116">[卸载 Windwos 服务](#BK_Uninstall)。</span><span class="sxs-lookup"><span data-stu-id="859c0-116">[Uninstalling a Windows Service](#BK_Uninstall).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="859c0-117">Visual Studio 速成版中未提供本演练所需的 Windows 服务项目模板。</span><span class="sxs-lookup"><span data-stu-id="859c0-117">The Windows Services project template that is required for this walkthrough is not available in the Express edition of Visual Studio.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]  
  
<a name="BK_CreateProject"></a>   
## <a name="creating-a-service"></a><span data-ttu-id="859c0-118">创建服务</span><span class="sxs-lookup"><span data-stu-id="859c0-118">Creating a Service</span></span>  
 <span data-ttu-id="859c0-119">首先，创建项目并设置服务正常运行所必需的值。</span><span class="sxs-lookup"><span data-stu-id="859c0-119">To begin, you create the project and set values that are required for the service to function correctly.</span></span>  
  
#### <a name="to-create-and-configure-your-service"></a><span data-ttu-id="859c0-120">创建并配置服务</span><span class="sxs-lookup"><span data-stu-id="859c0-120">To create and configure your service</span></span>  
  
1.  <span data-ttu-id="859c0-121">在 Visual Studio 中，在菜单栏上，选择 **“文件”**、 **“新建”**、 **“项目”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-121">In Visual Studio, on the menu bar, choose **File**, **New**, **Project**.</span></span>  
  
     <span data-ttu-id="859c0-122">**“新建项目”** 对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="859c0-122">The **New Project** dialog box opens.</span></span>  
  
2.  <span data-ttu-id="859c0-123">在 Visual Basic 或 Visual C# 项目模板列表中，选择“Windows 服务” ，然后对项目 **MyNewService**命名。</span><span class="sxs-lookup"><span data-stu-id="859c0-123">In the list of Visual Basic or Visual C# project templates, choose **Windows Service**, and name the project **MyNewService**.</span></span> <span data-ttu-id="859c0-124">选择 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-124">Choose **OK**.</span></span>  
  
     <span data-ttu-id="859c0-125">项目模板自动添加从 `Service1` 继承的名为 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 的组件类。</span><span class="sxs-lookup"><span data-stu-id="859c0-125">The project template automatically adds a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span>  
  
3.  <span data-ttu-id="859c0-126">在“编辑”  菜单上，依次选择“查找和替换” 、“在文件中查找”  （键盘：Ctrl+Shift+F）。</span><span class="sxs-lookup"><span data-stu-id="859c0-126">On the **Edit** menu, choose **Find and Replace**, **Find in Files** (Keyboard: Ctrl+Shift+F).</span></span> <span data-ttu-id="859c0-127">更改 `Service1` 到 `MyNewService`的所有匹配项。</span><span class="sxs-lookup"><span data-stu-id="859c0-127">Change all occurrences of `Service1` to `MyNewService`.</span></span> <span data-ttu-id="859c0-128">你将在 Service1.cs、Program.cs 和 Service1.Designer.cs（或它们的 .vb 等效项）中找到实例。</span><span class="sxs-lookup"><span data-stu-id="859c0-128">You’ll find instances in Service1.cs, Program.cs, and Service1.Designer.cs (or their .vb equivalents).</span></span>  
  
4.  <span data-ttu-id="859c0-129">在“Service1.cs [Design]”  或“Service1.vb [Design]”  的“属性” 窗口中，将 <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> 和 **的“(Name)”**`Service1` 属性设置为 **MyNewService**（如果尚未设置）。</span><span class="sxs-lookup"><span data-stu-id="859c0-129">In the **Properties** window for **Service1.cs [Design]** or **Service1.vb [Design]**, set the <xref:System.ServiceProcess.ServiceBase.ServiceName%2A> and the **(Name)** property for `Service1` to **MyNewService**, if it's not already set.</span></span>  
  
5.  <span data-ttu-id="859c0-130">在解决方案资源管理器中，将 **Service1.cs** 重命名为 **MyNewService.cs**，或将 **Service1.vb** 重命名为 **MyNewService.vb**。</span><span class="sxs-lookup"><span data-stu-id="859c0-130">In Solution Explorer, rename **Service1.cs** to **MyNewService.cs**, or **Service1.vb** to **MyNewService.vb**.</span></span>  
  
<a name="BK_WriteCode"></a>   
## <a name="adding-features-to-the-service"></a><span data-ttu-id="859c0-131">向服务添加功能</span><span class="sxs-lookup"><span data-stu-id="859c0-131">Adding Features to the Service</span></span>  
 <span data-ttu-id="859c0-132">在本节中，你会添加自定义事件日志到 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="859c0-132">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="859c0-133">事件日志与 Windows 服务没有任何形式的关联。</span><span class="sxs-lookup"><span data-stu-id="859c0-133">Event logs are not associated in any way with Windows services.</span></span> <span data-ttu-id="859c0-134">此处， <xref:System.Diagnostics.EventLog> 组件用作可以添加到 Windows 服务的组件类型的示例。</span><span class="sxs-lookup"><span data-stu-id="859c0-134">Here the <xref:System.Diagnostics.EventLog> component is used as an example of the type of component you could add to a Windows service.</span></span>  
  
#### <a name="to-add-custom-event-log-functionality-to-your-service"></a><span data-ttu-id="859c0-135">将自定义事件日志功能添加到服务中</span><span class="sxs-lookup"><span data-stu-id="859c0-135">To add custom event log functionality to your service</span></span>  
  
1.  <span data-ttu-id="859c0-136">在 **“解决方案资源管理器”** 中，打开 **MyNewService.cs** 或 **MyNewService.vb**的上下文菜单，然后选择 **“查看设计器”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-136">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>  
  
2.  <span data-ttu-id="859c0-137">从 **工具箱** 的 **“组件”** 部分，将 <xref:System.Diagnostics.EventLog> 组件拖动到设计器中。</span><span class="sxs-lookup"><span data-stu-id="859c0-137">From the **Components** section of the **Toolbox**, drag an <xref:System.Diagnostics.EventLog> component to the designer.</span></span>  
  
3.  <span data-ttu-id="859c0-138">在 **“解决方案资源管理器”** 中，打开 **MyNewService.cs** 或 **MyNewService.vb**的上下文菜单，然后选择 **“查看代码”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-138">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Code**.</span></span>  
  
4.  <span data-ttu-id="859c0-139">在`MyNewService`类中添加 **“eventLog”** 对象的声明，位置紧随声明 `components` 变量的行后：</span><span class="sxs-lookup"><span data-stu-id="859c0-139">Add a declaration for the **eventLog** object in the `MyNewService` class, right after the line that declares the `components` variable:</span></span>  
  
     [!code-csharp[VbRadconService#16](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#16)]
     [!code-vb[VbRadconService#16](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#16)]  
  
5.  <span data-ttu-id="859c0-140">添加或编辑构造函数定义自定义事件日志：</span><span class="sxs-lookup"><span data-stu-id="859c0-140">Add or edit the constructor to define a custom event log:</span></span>  
  
     [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
     [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]  
  
#### <a name="to-define-what-occurs-when-the-service-starts"></a><span data-ttu-id="859c0-141">定义服务启动时发生的情况</span><span class="sxs-lookup"><span data-stu-id="859c0-141">To define what occurs when the service starts</span></span>  
  
-   <span data-ttu-id="859c0-142">在代码编辑器中，找到你创建项目时自动改写的 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法，然后用以下代码替换该代码。</span><span class="sxs-lookup"><span data-stu-id="859c0-142">In the Code Editor, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method that was automatically overridden when you created the project, and replace the code with the following.</span></span> <span data-ttu-id="859c0-143">这会在服务开始运行时向事件日志添加条目：</span><span class="sxs-lookup"><span data-stu-id="859c0-143">This adds an entry to the event log when the service starts running:</span></span>  
  
     [!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
     [!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]  
  
     <span data-ttu-id="859c0-144">服务应用程序设计为长时间运行的，所以它通常轮询或监视系统中的情况。</span><span class="sxs-lookup"><span data-stu-id="859c0-144">A service application is designed to be long-running, so it usually polls or monitors something in the system.</span></span> <span data-ttu-id="859c0-145">监视是在 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法中设置的。</span><span class="sxs-lookup"><span data-stu-id="859c0-145">The monitoring is set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="859c0-146">但是， <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 实际上不进行监视。</span><span class="sxs-lookup"><span data-stu-id="859c0-146">However, <xref:System.ServiceProcess.ServiceBase.OnStart%2A> doesn’t actually do the monitoring.</span></span> <span data-ttu-id="859c0-147">服务的操作开始之后， <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法必须返回到操作系统。</span><span class="sxs-lookup"><span data-stu-id="859c0-147">The <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method must return to the operating system after the service's operation has begun.</span></span> <span data-ttu-id="859c0-148">它不能始终循环或阻止。</span><span class="sxs-lookup"><span data-stu-id="859c0-148">It must not loop forever or block.</span></span> <span data-ttu-id="859c0-149">若要设置简单的轮询机制，可以使用 <xref:System.Timers.Timer?displayProperty=nameWithType> 组件，如下所示：在 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法中，在组件上设置参数，然后将 <xref:System.Timers.Timer.Enabled%2A> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="859c0-149">To set up a simple polling mechanism, you can use the <xref:System.Timers.Timer?displayProperty=nameWithType> component as follows: In the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method, set parameters on the component, and then set the <xref:System.Timers.Timer.Enabled%2A> property to `true`.</span></span> <span data-ttu-id="859c0-150">计时器定期在你的代码中引发事件，此时你的服务可以进行监视。</span><span class="sxs-lookup"><span data-stu-id="859c0-150">The timer raises events in your code periodically, at which time your service could do its monitoring.</span></span> <span data-ttu-id="859c0-151">你可以使用以下代码来执行该操作：</span><span class="sxs-lookup"><span data-stu-id="859c0-151">You can use the following code to do this:</span></span>  
  
    ```csharp  
    // Set up a timer to trigger every minute.  
    System.Timers.Timer timer = new System.Timers.Timer();  
    timer.Interval = 60000; // 60 seconds  
    timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);  
    timer.Start();  
    ```  
  
    ```vb  
    ' Set up a timer to trigger every minute.  
    Dim timer As System.Timers.Timer = New System.Timers.Timer()  
    timer.Interval = 60000 ' 60 seconds  
    AddHandler timer.Elapsed, AddressOf Me.OnTimer  
    timer.Start()  
    ```  
     <span data-ttu-id="859c0-152">向类添加一个成员变量。</span><span class="sxs-lookup"><span data-stu-id="859c0-152">Add a member variable to the class.</span></span> <span data-ttu-id="859c0-153">它将包含要写入事件日志的下一个事件的标识符。</span><span class="sxs-lookup"><span data-stu-id="859c0-153">It will contain the identifier of the next event to write into the event log.</span></span>

    ```csharp
    private int eventId = 1;
    ```

    ```vb
    Private eventId As Integer = 1
    ```

     <span data-ttu-id="859c0-154">添加代码来处理计时器事件：</span><span class="sxs-lookup"><span data-stu-id="859c0-154">Add code to handle the timer event:</span></span>  
  
    ```csharp  
    public void OnTimer(object sender, System.Timers.ElapsedEventArgs args)  
    {  
        // TODO: Insert monitoring activities here.  
        eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId++);  
    }  
    ```  
  
    ```vb  
    Private Sub OnTimer(sender As Object, e As Timers.ElapsedEventArgs)  
        ' TODO: Insert monitoring activities here.  
        eventLog1.WriteEntry("Monitoring the System", EventLogEntryType.Information, eventId)  
        eventId = eventId + 1  
    End Sub  
    ```  
  
     <span data-ttu-id="859c0-155">你可能需要使用后台辅助线程来执行任务，而不是在主线程上运行所有工作。</span><span class="sxs-lookup"><span data-stu-id="859c0-155">You might want to perform tasks by using background worker threads instead of running all your work on the main thread.</span></span> <span data-ttu-id="859c0-156">有于此的示例，请参阅 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 引用页。</span><span class="sxs-lookup"><span data-stu-id="859c0-156">For an example of this, see the <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> reference page.</span></span>  
  
#### <a name="to-define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="859c0-157">定义服务停止时发生的情况</span><span class="sxs-lookup"><span data-stu-id="859c0-157">To define what occurs when the service is stopped</span></span>  
  
-   <span data-ttu-id="859c0-158">将 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="859c0-158">Replace the code for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method with the following.</span></span> <span data-ttu-id="859c0-159">这会在服务停止时向事件日志添加条目：</span><span class="sxs-lookup"><span data-stu-id="859c0-159">This adds an entry to the event log when the service is stopped:</span></span>  
  
     [!code-csharp[VbRadconService#4](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
     [!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]  
  
 <span data-ttu-id="859c0-160">在下一节中，你可以重写 <xref:System.ServiceProcess.ServiceBase.OnPause%2A>、 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>和 <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> 方法来为你的组件定义其他处理。</span><span class="sxs-lookup"><span data-stu-id="859c0-160">In the next section, you can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span>  
  
#### <a name="to-define-other-actions-for-the-service"></a><span data-ttu-id="859c0-161">定义服务的其他操作</span><span class="sxs-lookup"><span data-stu-id="859c0-161">To define other actions for the service</span></span>  
  
-   <span data-ttu-id="859c0-162">找到你想要处理的方法，然后改写它来定义你想要发生的操作。</span><span class="sxs-lookup"><span data-stu-id="859c0-162">Locate the method that you want to handle, and override it to define what you want to occur.</span></span>  
  
     <span data-ttu-id="859c0-163">下列代码显示你可如何改写 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="859c0-163">The following code shows how you can override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method:</span></span>  
  
     [!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
     [!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]  
  
 <span data-ttu-id="859c0-164"><xref:System.Configuration.Install.Installer> 类安装 Windows 服务后，需要发生一些自定义操作。</span><span class="sxs-lookup"><span data-stu-id="859c0-164">Some custom actions have to occur when a Windows service is installed by the <xref:System.Configuration.Install.Installer> class.</span></span> <span data-ttu-id="859c0-165">Visual Studio 可以专门为 Windows 服务创建这些安装程序并将它们添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="859c0-165">Visual Studio can create these installers specifically for a Windows service and add them to your project.</span></span>  
  
<a name="BK_SetStatus"></a>   
## <a name="setting-service-status"></a><span data-ttu-id="859c0-166">设置服务状态</span><span class="sxs-lookup"><span data-stu-id="859c0-166">Setting Service Status</span></span>  
 <span data-ttu-id="859c0-167">服务向服务控制管理器报告其状态，以便用户可以判断服务是否运行正常。</span><span class="sxs-lookup"><span data-stu-id="859c0-167">Services report their status to the Service Control Manager, so that users can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="859c0-168">默认情况下，从 <xref:System.ServiceProcess.ServiceBase> 继承的服务会报告有限的状态设置，包括已停止、已暂停和正在运行。</span><span class="sxs-lookup"><span data-stu-id="859c0-168">By default, services that inherit from <xref:System.ServiceProcess.ServiceBase> report a limited set of status settings, including Stopped, Paused, and Running.</span></span> <span data-ttu-id="859c0-169">如果服务启动所需的时间很短，则可能对报告“启动挂起”状态有帮助。</span><span class="sxs-lookup"><span data-stu-id="859c0-169">If a service takes a little while to start up, it might be helpful to report a Start Pending status.</span></span> <span data-ttu-id="859c0-170">你也可以通过添加调入 Windows [SetServiceStatus 函数](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx)的代码来实现“启动挂起”和“停止挂起”状态设置。</span><span class="sxs-lookup"><span data-stu-id="859c0-170">You can also implement the Start Pending and Stop Pending status settings by adding code that calls into the Windows [SetServiceStatus function](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx).</span></span>  
  
#### <a name="to-implement-service-pending-status"></a><span data-ttu-id="859c0-171">若要实现服务挂起状态</span><span class="sxs-lookup"><span data-stu-id="859c0-171">To implement service pending status</span></span>  
  
1.  <span data-ttu-id="859c0-172">添加 `using` 语句或 `Imports` 声明到 MyNewService.cs 或 MyNewService.vb 文件中的 <xref:System.Runtime.InteropServices?displayProperty=nameWithType> 命名空间：</span><span class="sxs-lookup"><span data-stu-id="859c0-172">Add a `using` statement or `Imports` declaration to the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace in the MyNewService.cs or MyNewService.vb file:</span></span>  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    ```  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    ```  
  
2.  <span data-ttu-id="859c0-173">添加以下代码到 MyNewService.cs 以声明 `ServiceState` 值和添加你将在平台调用中使用的状态结构：</span><span class="sxs-lookup"><span data-stu-id="859c0-173">Add the following code to MyNewService.cs to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>  
  
    ```csharp  
    public enum ServiceState  
      {  
          SERVICE_STOPPED = 0x00000001,  
          SERVICE_START_PENDING = 0x00000002,  
          SERVICE_STOP_PENDING = 0x00000003,  
          SERVICE_RUNNING = 0x00000004,  
          SERVICE_CONTINUE_PENDING = 0x00000005,  
          SERVICE_PAUSE_PENDING = 0x00000006,  
          SERVICE_PAUSED = 0x00000007,  
      }  
  
      [StructLayout(LayoutKind.Sequential)]  
      public struct ServiceStatus  
      {  
          public int dwServiceType;  
          public ServiceState dwCurrentState;  
          public int dwControlsAccepted;  
          public int dwWin32ExitCode;  
          public int dwServiceSpecificExitCode;  
          public int dwCheckPoint;  
          public int dwWaitHint;  
      };  
    ```  
  
    ```vb  
    Public Enum ServiceState  
        SERVICE_STOPPED = 1  
        SERVICE_START_PENDING = 2  
        SERVICE_STOP_PENDING = 3  
        SERVICE_RUNNING = 4  
        SERVICE_CONTINUE_PENDING = 5  
        SERVICE_PAUSE_PENDING = 6  
        SERVICE_PAUSED = 7  
    End Enum  
  
    <StructLayout(LayoutKind.Sequential)>  
    Public Structure ServiceStatus  
        Public dwServiceType As Long  
        Public dwCurrentState As ServiceState  
        Public dwControlsAccepted As Long  
        Public dwWin32ExitCode As Long  
        Public dwServiceSpecificExitCode As Long  
        Public dwCheckPoint As Long  
        Public dwWaitHint As Long  
    End Structure  
    ```  
  
3.  <span data-ttu-id="859c0-174">现在，在 `MyNewService` 类中，使用平台调用声明 [SetServiceStatus 函数](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) ：</span><span class="sxs-lookup"><span data-stu-id="859c0-174">Now, in the `MyNewService` class, declare the [SetServiceStatus function](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) by using platform invoke:</span></span>  
  
    ```csharp  
    [DllImport("advapi32.dll", SetLastError=true)]  
            private static extern bool SetServiceStatus(IntPtr handle, ref ServiceStatus serviceStatus);  
    ```  
  
    ```vb  
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean  
    ```  
  
4.  <span data-ttu-id="859c0-175">若要实现“启动挂起”状态，请添加下列代码到 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法的开头：</span><span class="sxs-lookup"><span data-stu-id="859c0-175">To implement the Start Pending status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>  
  
    ```csharp  
    // Update the service state to Start Pending.  
    ServiceStatus serviceStatus = new ServiceStatus();  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING;  
    serviceStatus.dwWaitHint = 100000;  
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);  
    ```  
  
    ```vb  
    ' Update the service state to Start Pending.  
    Dim serviceStatus As ServiceStatus = New ServiceStatus()  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_START_PENDING  
    serviceStatus.dwWaitHint = 100000  
    SetServiceStatus(Me.ServiceHandle, serviceStatus)  
    ```  
  
5.  <span data-ttu-id="859c0-176">在 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法的末尾添加代码以将状态设置为“正在运行”。</span><span class="sxs-lookup"><span data-stu-id="859c0-176">Add code to set the status to Running at the end of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span>  
  
    ```csharp
    // Update the service state to Running.  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING;  
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);  
    ```  
  
    ```vb  
    ' Update the service state to Running.  
    serviceStatus.dwCurrentState = ServiceState.SERVICE_RUNNING  
    SetServiceStatus(Me.ServiceHandle, serviceStatus)  
    ```  
  
6.  <span data-ttu-id="859c0-177">（可选）针对 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法重复此过程。</span><span class="sxs-lookup"><span data-stu-id="859c0-177">(Optional) Repeat this procedure for the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="859c0-178">服务的操作开始之后， [服务控制管理器](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) 使用 `dwWaitHint` 和 `dwCheckpoint` 和 [dwCheckpoint](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) 成员确定等待 Windows 服务启动或关闭需要多长时间。</span><span class="sxs-lookup"><span data-stu-id="859c0-178">The [Service Control Manager](http://msdn.microsoft.com/library/windows/desktop/ms685150.aspx) uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](http://msdn.microsoft.com/library/windows/desktop/ms685996.aspx) to determine how much time to wait for a Windows Service to start or shut down.</span></span> <span data-ttu-id="859c0-179">如果你的 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法运行时间较长，你的服务可以使用递增的 [dwCheckPoint](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) 值再次调用 `dwCheckPoint` 来请求更多时间。</span><span class="sxs-lookup"><span data-stu-id="859c0-179">If your <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods run long, your service can request more time by calling [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241.aspx) again with an incremented `dwCheckPoint` value.</span></span>  
  
<a name="BK_AddInstallers"></a>   
## <a name="adding-installers-to-the-service"></a><span data-ttu-id="859c0-180">向服务添加安装程序</span><span class="sxs-lookup"><span data-stu-id="859c0-180">Adding Installers to the Service</span></span>  
 <span data-ttu-id="859c0-181">在你能运行 Windows 服务之前，你需要先安装它，这会将其注册到服务控制管理器。</span><span class="sxs-lookup"><span data-stu-id="859c0-181">Before you can run a Windows Service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="859c0-182">你可以将安装程序添加到处理注册详细信息的项目。</span><span class="sxs-lookup"><span data-stu-id="859c0-182">You can add installers to your project that handle the registration details.</span></span>  
  
#### <a name="to-create-the-installers-for-your-service"></a><span data-ttu-id="859c0-183">为服务创建安装程序</span><span class="sxs-lookup"><span data-stu-id="859c0-183">To create the installers for your service</span></span>  
  
1.  <span data-ttu-id="859c0-184">在 **“解决方案资源管理器”** 中，打开 **MyNewService.cs** 或 **MyNewService.vb**的上下文菜单，然后选择 **“查看设计器”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-184">In **Solution Explorer**, open the context menu for **MyNewService.cs** or **MyNewService.vb**, and then choose **View Designer**.</span></span>  
  
2.  <span data-ttu-id="859c0-185">单击设计器的背景以选择服务本身，而不是它的任何内容。</span><span class="sxs-lookup"><span data-stu-id="859c0-185">Click the background of the designer to select the service itself, instead of any of its contents.</span></span>  
  
3.  <span data-ttu-id="859c0-186">打开设计器窗口的上下文菜单（如果使用指针设备，在窗口中右键单击），然后选择 **“添加安装程序”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-186">Open the context menu for the designer window (if you’re using a pointing device, right-click inside the window), and then choose **Add Installer**.</span></span>  
  
     <span data-ttu-id="859c0-187">默认情况下，向你的项目添加一个包含两个安装程序的组件类。</span><span class="sxs-lookup"><span data-stu-id="859c0-187">By default, a component class that contains two installers is added to your project.</span></span> <span data-ttu-id="859c0-188">将该组件命名为 **ProjectInstaller**，它包含的安装程序分别是服务的安装程序和服务关联进程的安装程序。</span><span class="sxs-lookup"><span data-stu-id="859c0-188">The component is named **ProjectInstaller**, and the installers it contains are the installer for your service and the installer for the service's associated process.</span></span>  
  
4.  <span data-ttu-id="859c0-189">在 **ProjectInstaller** 的 **“设计”** 视图中，选择 **serviceInstaller1** （对于 Visual C# 项目）或 **ServiceInstaller1** （对于 Visual Basic 项目）。</span><span class="sxs-lookup"><span data-stu-id="859c0-189">In **Design** view for **ProjectInstaller**, choose **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project.</span></span>  
  
5.  <span data-ttu-id="859c0-190">在“属性”  窗口中，确保 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 属性已设置为 **MyNewService**。</span><span class="sxs-lookup"><span data-stu-id="859c0-190">In the **Properties** window, make sure the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>  
  
6.  <span data-ttu-id="859c0-191">将 **“描述”** 属性设置为一些文本，比如“示例服务”。</span><span class="sxs-lookup"><span data-stu-id="859c0-191">Set the **Description** property to some text, such as "A sample service".</span></span> <span data-ttu-id="859c0-192">该文本会显示在“服务”窗口中，帮助用户标识服务并理解其用处。</span><span class="sxs-lookup"><span data-stu-id="859c0-192">This text appears in the Services window and helps the user identify the service and understand what it’s used for.</span></span>  
  
7.  <span data-ttu-id="859c0-193">在 <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> “名称” **列中将** 属性设置为你想要显示在“服务”窗口中的文本。</span><span class="sxs-lookup"><span data-stu-id="859c0-193">Set the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property to the text that you want to appear in the Services window in the **Name** column.</span></span> <span data-ttu-id="859c0-194">例如，你可以输入“MyNewService 显示名称”。</span><span class="sxs-lookup"><span data-stu-id="859c0-194">For example, you can enter "MyNewService Display Name".</span></span> <span data-ttu-id="859c0-195">该名称可以不同于 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 属性，它是系统使用的名称（例如，当你使用 `net start` 命令启动服务时）。</span><span class="sxs-lookup"><span data-stu-id="859c0-195">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name used by the system (for example, when you use the `net start` command to start your service).</span></span>  
  
8.  <span data-ttu-id="859c0-196">将 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 属性设置为 <xref:System.ServiceProcess.ServiceStartMode.Automatic>。</span><span class="sxs-lookup"><span data-stu-id="859c0-196">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic>.</span></span>  
  
     <span data-ttu-id="859c0-197">![Windows 服务的安装程序属性](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span><span class="sxs-lookup"><span data-stu-id="859c0-197">![Installer Properties for a Windows Service](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")</span></span>  
  
9. <span data-ttu-id="859c0-198">在设计器中，选择 **serviceProcessInstaller1** （对于 Visual C# 项目）或 **ServiceProcessInstaller1** （对于 Visual Basic 项目）。</span><span class="sxs-lookup"><span data-stu-id="859c0-198">In the designer, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project.</span></span> <span data-ttu-id="859c0-199">将 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 属性设置为 <xref:System.ServiceProcess.ServiceAccount.LocalSystem>。</span><span class="sxs-lookup"><span data-stu-id="859c0-199">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem>.</span></span> <span data-ttu-id="859c0-200">这将使得在本地服务帐户上安装和运行该服务。</span><span class="sxs-lookup"><span data-stu-id="859c0-200">This will cause the service to be installed and to run on a local service account.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="859c0-201"><xref:System.ServiceProcess.ServiceAccount.LocalSystem> 帐户具有广泛的权限，包括能够写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="859c0-201">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="859c0-202">使用此帐户时要特别小心，因为它会增加你受到恶意软件攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="859c0-202">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="859c0-203">对于其他任务，请考虑使用 <xref:System.ServiceProcess.ServiceAccount.LocalService> 帐户，该帐户用作本地计算机上的非特权用户，并向任意远程服务器提供匿名凭据。</span><span class="sxs-lookup"><span data-stu-id="859c0-203">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="859c0-204">如果你尝试使用 <xref:System.ServiceProcess.ServiceAccount.LocalService> 账户，此例子将失败，因为它需要写入事件日志的权限。</span><span class="sxs-lookup"><span data-stu-id="859c0-204">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>  
  
     <span data-ttu-id="859c0-205">有关安装程序的详细信息，请参阅 [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="859c0-205">For more information about installers, see [How to: Add Installers to Your Service Application](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md).</span></span>  
  
<a name="BK_StartupParameters"></a>   
## <a name="set-startup-parameters"></a><span data-ttu-id="859c0-206">设置启动参数</span><span class="sxs-lookup"><span data-stu-id="859c0-206">Set Startup Parameters</span></span>  
 <span data-ttu-id="859c0-207">Windows 服务像任何其他可执行文件一样，可以接受命令行参数或启动参数。</span><span class="sxs-lookup"><span data-stu-id="859c0-207">A Windows Service, like any other executable, can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="859c0-208">添加代码到进程启动参数后，用户可以使用 Windows 控制面板中的“服务”窗口，用他们自己的自定义启动参数启动你的服务。</span><span class="sxs-lookup"><span data-stu-id="859c0-208">When you add code to process startup parameters, users can start your service with their own custom startup parameters by using the Services window in the Windows Control Panel.</span></span> <span data-ttu-id="859c0-209">但是，这些启动参数不会保留到下一次服务启动。</span><span class="sxs-lookup"><span data-stu-id="859c0-209">However, these startup parameters are not persisted the next time the service starts.</span></span> <span data-ttu-id="859c0-210">若要永久性设置启动参数，你可以按此步骤所示，在注册表中对它们进行设置。</span><span class="sxs-lookup"><span data-stu-id="859c0-210">To set startup parameters permanently, you can set them in the registry, as shown in this procedure.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="859c0-211">在你决定添加启动参数前，考虑这是否是向你的服务传递信息的最好办法。</span><span class="sxs-lookup"><span data-stu-id="859c0-211">Before you decide to add startup parameters, consider whether that is the best way to pass information to your service.</span></span> <span data-ttu-id="859c0-212">虽然启动参数易于使用和分析，而且用户可以轻松地改写它们，但是如果没有相关的文档说明，用户可能较难发现和使用它们。</span><span class="sxs-lookup"><span data-stu-id="859c0-212">Although startup parameters are easy to use and to parse, and users can easily override them, they might be harder for users to discover and use without documentation.</span></span> <span data-ttu-id="859c0-213">通常情况下，如果你的服务需要不止几个启动参数，你应该考虑改为使用注册表或配置文件。</span><span class="sxs-lookup"><span data-stu-id="859c0-213">Generally, if your service requires more than just a few startup parameters, you should consider using the registry or a configuration file instead.</span></span> <span data-ttu-id="859c0-214">每个 Windows 服务都在 HKLM\System\CurrentControlSet\services 下有注册表项。</span><span class="sxs-lookup"><span data-stu-id="859c0-214">Every Windows Service has an entry in the registry under HKLM\System\CurrentControlSet\services.</span></span> <span data-ttu-id="859c0-215">在服务的项下，你可以使用 **“参数”** 子项存储你的服务能访问的信息。</span><span class="sxs-lookup"><span data-stu-id="859c0-215">Under the service's key, you can use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="859c0-216">你可以使用 Windows 服务的应用程序配置文件,与使用其他类型的程序一样。</span><span class="sxs-lookup"><span data-stu-id="859c0-216">You can use application configuration files for a Windows Service the same way you do for other types of programs.</span></span> <span data-ttu-id="859c0-217">有关示例代码，请参阅 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>。</span><span class="sxs-lookup"><span data-stu-id="859c0-217">For example code, see <xref:System.Configuration.ConfigurationManager.AppSettings%2A>.</span></span>  
  
#### <a name="adding-startup-parameters"></a><span data-ttu-id="859c0-218">添加启动参数</span><span class="sxs-lookup"><span data-stu-id="859c0-218">Adding startup parameters</span></span>  
  
1.  <span data-ttu-id="859c0-219">在 Program.cs 或 MyNewService.Designer.vb 中的 `Main` 方法中，添加命令行参数：</span><span class="sxs-lookup"><span data-stu-id="859c0-219">In the `Main` method in Program.cs or in MyNewService.Designer.vb, add an argument for the command line:</span></span>  
  
```csharp  
static void Main(string[] args)
{
    ServiceBase[] ServicesToRun = new ServiceBase[] { new MyNewService(args) };
    ServiceBase.Run(ServicesToRun);
}
```  
  
```vb
Shared Sub Main(ByVal cmdArgs() As String)
    Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
    System.ServiceProcess.ServiceBase.Run(ServicesToRun)
End Sub
```  
  
2.  <span data-ttu-id="859c0-220">按如下所示更改 `MyNewService` 构造函数：</span><span class="sxs-lookup"><span data-stu-id="859c0-220">Change the `MyNewService` constructor as follows:</span></span>  
  
```csharp  
public MyNewService(string[] args)
{
    InitializeComponent();
    string eventSourceName = "MySource";
    string logName = "MyNewLog";
    if (args.Count() > 0) 
    {
        eventSourceName = args[0];
    }
    if (args.Count() > 1)
    {
        logName = args[1];
    }
    eventLog1 = new System.Diagnostics.EventLog();
    if (!System.Diagnostics.EventLog.SourceExists(eventSourceName))
    {
        System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName);
    }
    eventLog1.Source = eventSourceName;
    eventLog1.Log = logName;        
}
```  
  
```vb  
Public Sub New(ByVal cmdArgs() As String)
    InitializeComponent()
    Dim eventSourceName As String = "MySource"
    Dim logName As String = "MyNewLog"
    If (cmdArgs.Count() > 0) Then
        eventSourceName = cmdArgs(0)
    End If
    If (cmdArgs.Count() > 1) Then
        logName = cmdArgs(1)
    End If
    eventLog1 = New System.Diagnostics.EventLog()
    If (Not System.Diagnostics.EventLog.SourceExists(eventSourceName)) Then
        System.Diagnostics.EventLog.CreateEventSource(eventSourceName, logName)
    End If
    eventLog1.Source = eventSourceName
    eventLog1.Log = logName
End Sub  
```  
  
<span data-ttu-id="859c0-221">此代码根据提供的启动参数设置事件源和日志名称，或者如果没有提供参数就使用默认值。</span><span class="sxs-lookup"><span data-stu-id="859c0-221">This code sets the event source and log name according to the supplied startup parameters, or uses default values if no arguments are supplied.</span></span>  
  
3. <span data-ttu-id="859c0-222">若要指定命令行参数，请将下列代码添加到 ProjectInstaller.cs 或 ProjectInstaller.vb 的 `ProjectInstaller` 类中：</span><span class="sxs-lookup"><span data-stu-id="859c0-222">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in ProjectInstaller.cs or ProjectInstaller.vb:</span></span>  
  
```csharp  
protected override void OnBeforeInstall(IDictionary savedState)
{
    string parameter = "MySource1\" \"MyLogFile1";
    Context.Parameters["assemblypath"] = "\"" + Context.Parameters["assemblypath"] + "\" \"" + parameter + "\"";
    base.OnBeforeInstall(savedState);
}
```

```vb  
Protected Overrides Sub OnBeforeInstall(ByVal savedState As IDictionary)
    Dim parameter As String = "MySource1"" ""MyLogFile1"
    Context.Parameters("assemblypath") = """" + Context.Parameters("assemblypath") + """ """ + parameter + """"
    MyBase.OnBeforeInstall(savedState)
End Sub  
```  
  
<span data-ttu-id="859c0-223">此代码会通过添加默认参数值修改 **“ImagePath”** 注册表项，该注册表项通常包含 Windows 服务可执行文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="859c0-223">This code modifies the **ImagePath** registry key, which typically contains the full path to the executable for the Windows Service, by adding the default parameter values.</span></span> <span data-ttu-id="859c0-224">要正常启动服务需要使用引号将路径括起来（包围括住每个参数）。</span><span class="sxs-lookup"><span data-stu-id="859c0-224">The quotation marks around the path (and around each individual parameter) are required for the service to start up correctly.</span></span> <span data-ttu-id="859c0-225">若要更改该 Windows 服务的启动参数，用户可以更改 **ImagePath** 注册表项中给定的参数，然而更好的方式是以编程的方式对其进行更改，并以友好的方式（例如，在管理或配置实用工具中）向用户公开功能。</span><span class="sxs-lookup"><span data-stu-id="859c0-225">To change the startup parameters for this Windows Service, users can change the parameters given in the **ImagePath** registry key, although the better way is to change it programmatically and expose the functionality to users in a friendly way (for example, in a management or configuration utility).</span></span>  
  
<a name="BK_Build"></a>   
## <a name="building-the-service"></a><span data-ttu-id="859c0-226">生成服务</span><span class="sxs-lookup"><span data-stu-id="859c0-226">Building the Service</span></span>  
  
#### <a name="to-build-your-service-project"></a><span data-ttu-id="859c0-227">生成服务项目</span><span class="sxs-lookup"><span data-stu-id="859c0-227">To build your service project</span></span>  
  
1.  <span data-ttu-id="859c0-228">在 **“解决方案资源管理器”** 中，打开项目的上下文菜单，然后选择 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-228">In **Solution Explorer**, open the context menu for your project, and then choose **Properties**.</span></span> <span data-ttu-id="859c0-229">出现项目的属性页面。</span><span class="sxs-lookup"><span data-stu-id="859c0-229">The property pages for your project  appear.</span></span>  
  
2.  <span data-ttu-id="859c0-230">在应用程序选项卡上，在 **“启动对象”** 列表中，选择 **MyNewService.Program**。</span><span class="sxs-lookup"><span data-stu-id="859c0-230">On the Application tab, in the **Startup object** list, choose **MyNewService.Program**.</span></span>  
  
3.  <span data-ttu-id="859c0-231">在“解决方案资源管理器” 中，打开项目的上下文菜单，然后选择“生成”  以生成项目（键盘：Ctrl+Shift+B）。</span><span class="sxs-lookup"><span data-stu-id="859c0-231">In **Solution Explorer**, open the context menu for your project, and then choose **Build** to build the project (Keyboard: Ctrl+Shift+B).</span></span>  
  
<a name="BK_Install"></a>   
## <a name="installing-the-service"></a><span data-ttu-id="859c0-232">安装服务</span><span class="sxs-lookup"><span data-stu-id="859c0-232">Installing the Service</span></span>  
 <span data-ttu-id="859c0-233">由于已经生成了 Windows 服务，你现在可以安装它。</span><span class="sxs-lookup"><span data-stu-id="859c0-233">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="859c0-234">若要安装 Windows 服务，你必须拥有你将要安装服务的计算机的管理凭据。</span><span class="sxs-lookup"><span data-stu-id="859c0-234">To install a Windows service, you must have administrative credentials on the computer on which you're installing it.</span></span>  
  
#### <a name="to-install-a-windows-service"></a><span data-ttu-id="859c0-235">若要安装 Windows 服务</span><span class="sxs-lookup"><span data-stu-id="859c0-235">To install a Windows Service</span></span>  
  
1.  <span data-ttu-id="859c0-236">在 Windows 7 和 Windows Server 中，打开 **“开始”** 菜单中 **“Visual Studio 工具”** 下的 **“开发人员命令提示”** 。</span><span class="sxs-lookup"><span data-stu-id="859c0-236">In Windows 7 and Windows Server, open the **Developer Command Prompt** under **Visual Studio Tools** in the **Start** menu.</span></span> <span data-ttu-id="859c0-237">在 Windows 8 或 Windows 8.1 中，选择 **“开始”** 屏幕上的 **“Visual Studio 工具”** 图块，然后使用管理凭据运行开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="859c0-237">In Windows 8 or Windows 8.1, choose the **Visual Studio Tools** tile on the **Start** screen, and then run Developer Command Prompt with administrative credentials.</span></span> <span data-ttu-id="859c0-238">（如果使用鼠标，右键单击 **“开发人员命令提示”**，然后选择 **“以管理员身份运行”**。）</span><span class="sxs-lookup"><span data-stu-id="859c0-238">(If you’re using a mouse, right-click on **Developer Command Prompt**, and then choose **Run as Administrator**.)</span></span>  
  
2.  <span data-ttu-id="859c0-239">在命令提示窗口中，导航到包含项目输出的文件夹。</span><span class="sxs-lookup"><span data-stu-id="859c0-239">In the Command Prompt window, navigate to the folder that contains your project's output.</span></span> <span data-ttu-id="859c0-240">例如，在“我的文档”文件夹下，导航到 Visual Studio 2013\Projects\MyNewService\bin\Debug。</span><span class="sxs-lookup"><span data-stu-id="859c0-240">For example, under your My Documents folder, navigate to Visual Studio 2013\Projects\MyNewService\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="859c0-241">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="859c0-241">Enter the following command:</span></span>  
  
    ```  
    installutil.exe MyNewService.exe  
    ```  
  
     <span data-ttu-id="859c0-242">如果服务成功安装，installutil.exe 将报告成功。</span><span class="sxs-lookup"><span data-stu-id="859c0-242">If the service installs successfully, installutil.exe will report success.</span></span> <span data-ttu-id="859c0-243">如果系统找不到 InstallUtil.exe,请确保它存在于你的计算机上。</span><span class="sxs-lookup"><span data-stu-id="859c0-243">If the system could not find InstallUtil.exe, make sure that it exists on your computer.</span></span> <span data-ttu-id="859c0-244">此工具随 .NET Framework 安装到了 `%WINDIR%\Microsoft.NET\Framework[64]\`*framework_version*文件夹。</span><span class="sxs-lookup"><span data-stu-id="859c0-244">This tool is installed with the .NET Framework to the folder `%WINDIR%\Microsoft.NET\Framework[64]\`*framework_version*.</span></span> <span data-ttu-id="859c0-245">例如，32 位版本的 .NET Framework 4、4.5、4.5.1 和 4.5.2 的默认路径为 `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`。</span><span class="sxs-lookup"><span data-stu-id="859c0-245">For example, the default path for the 32-bit version of the .NET Framework 4, 4.5, 4.5.1, and 4.5.2 is `C:\Windows\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe`.</span></span>  
  
     <span data-ttu-id="859c0-246">如果 installutil.exe 进程报告失败，请查看安装日志以找出原因。</span><span class="sxs-lookup"><span data-stu-id="859c0-246">If the installutil.exe process reports failure, check the install log to find out why.</span></span> <span data-ttu-id="859c0-247">默认情况下，该日志与服务可执行文件位于同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="859c0-247">By default the log is in the same folder as the service executable.</span></span> <span data-ttu-id="859c0-248">如果 `ProjectInstaller` 类上不存在 <xref:System.ComponentModel.RunInstallerAttribute> 类，或者该属性未设置为 `true`，或者 `ProjectInstaller` 类不是 `public`，则安装可能失败。</span><span class="sxs-lookup"><span data-stu-id="859c0-248">The installation can fail if  the <xref:System.ComponentModel.RunInstallerAttribute> Class is not present on the `ProjectInstaller` class, or else the attribute is not set to `true`, or else the `ProjectInstaller` class is not `public`.</span></span>  
  
     <span data-ttu-id="859c0-249">有关更多信息，请参见 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。</span><span class="sxs-lookup"><span data-stu-id="859c0-249">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
<a name="BK_StartService"></a>   
## <a name="starting-and-running-the-service"></a><span data-ttu-id="859c0-250">启动和运行服务</span><span class="sxs-lookup"><span data-stu-id="859c0-250">Starting and Running the Service</span></span>  
  
#### <a name="to-start-and-stop-your-service"></a><span data-ttu-id="859c0-251">启动和停止服务</span><span class="sxs-lookup"><span data-stu-id="859c0-251">To start and stop your service</span></span>  
  
1.  <span data-ttu-id="859c0-252">在 Windows 中，打开“开始”  屏幕或“开始”  菜单，然后键入 `services.msc`。</span><span class="sxs-lookup"><span data-stu-id="859c0-252">In Windows, open the **Start** screen or **Start** menu, and type `services.msc`.</span></span>  
  
     <span data-ttu-id="859c0-253">你应该会看见 **MyNewService** 列于 **“服务”** 窗口中。</span><span class="sxs-lookup"><span data-stu-id="859c0-253">You should now see **MyNewService** listed in the **Services** window.</span></span>  
  
     <span data-ttu-id="859c0-254">![“服务”窗口中的 MyNewService。](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "WindowsServices_ServicesWindow")</span><span class="sxs-lookup"><span data-stu-id="859c0-254">![MyNewService in the Services window.](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG "WindowsServices_ServicesWindow")</span></span>  
  
2.  <span data-ttu-id="859c0-255">在 **“服务”** 窗口中，打开你的服务的快捷菜，然后选择 **“启动”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-255">In the **Services** window, open the shortcut menu for your service, and then choose **Start**.</span></span>  
  
3.  <span data-ttu-id="859c0-256">打开该服务的快捷菜单，然后选择 **“停止”**。</span><span class="sxs-lookup"><span data-stu-id="859c0-256">Open the shortcut menu for the service, and then choose **Stop**.</span></span>  
  
4.  <span data-ttu-id="859c0-257">（可选）你可以在命令行中使用 `net start``ServiceName` 和 `net stop``ServiceName` 命令来启动和停止你的服务。</span><span class="sxs-lookup"><span data-stu-id="859c0-257">(Optional) From the command line, you can use the commands `net start``ServiceName` and `net stop``ServiceName` to start and stop your service.</span></span>  
  
#### <a name="to-verify-the-event-log-output-of-your-service"></a><span data-ttu-id="859c0-258">验证服务的事件日志输出</span><span class="sxs-lookup"><span data-stu-id="859c0-258">To verify the event log output of your service</span></span>  
  
1.  <span data-ttu-id="859c0-259">在 Visual Studio 中，打开“服务器资源管理器”  （键盘：Ctrl+Alt+S），并访问本地计算机的“事件日志”  节点。</span><span class="sxs-lookup"><span data-stu-id="859c0-259">In Visual Studio, open **Server Explorer** (Keyboard: Ctrl+Alt+S), and access the **Event Logs** node for the local computer.</span></span>  
  
2.  <span data-ttu-id="859c0-260">找到 **MyNewLog** （或 **MyLogFile1**，如果你使用了可选步骤来添加命令行参数）列表并将它展开。</span><span class="sxs-lookup"><span data-stu-id="859c0-260">Locate the listing for **MyNewLog** (or **MyLogFile1**, if you used the optional procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="859c0-261">你会看到你的服务执行的两个操作（启动和停止）的条目。</span><span class="sxs-lookup"><span data-stu-id="859c0-261">You should see entries for the two actions (start and stop) your service has performed.</span></span>  
  
     <span data-ttu-id="859c0-262">![使用事件查看器查看事件日志条目。](../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "WindowsServices_EventViewer")</span><span class="sxs-lookup"><span data-stu-id="859c0-262">![Use the Event Viewer to see the event log entries.](../../../docs/framework/windows-services/media/windowsservices-eventviewer.PNG "WindowsServices_EventViewer")</span></span>  
  
<a name="BK_Uninstall"></a>   
## <a name="uninstalling-a-windows-service"></a><span data-ttu-id="859c0-263">卸载 Windwos 服务</span><span class="sxs-lookup"><span data-stu-id="859c0-263">Uninstalling a Windows Service</span></span>  
  
#### <a name="to-uninstall-your-service"></a><span data-ttu-id="859c0-264">卸载服务</span><span class="sxs-lookup"><span data-stu-id="859c0-264">To uninstall your service</span></span>  
  
1.  <span data-ttu-id="859c0-265">使用管理凭据打开开发人员命令提示。</span><span class="sxs-lookup"><span data-stu-id="859c0-265">Open a developer command prompt with administrative credentials.</span></span>  
  
2.  <span data-ttu-id="859c0-266">在命令提示窗口中，导航到包含项目输出的文件夹。</span><span class="sxs-lookup"><span data-stu-id="859c0-266">In the Command Prompt window, navigate to the folder that contains your project's output.</span></span> <span data-ttu-id="859c0-267">例如，在“我的文档”文件夹下，导航到 Visual Studio 2013\Projects\MyNewService\bin\Debug。</span><span class="sxs-lookup"><span data-stu-id="859c0-267">For example, under your My Documents folder, navigate to Visual Studio 2013\Projects\MyNewService\bin\Debug.</span></span>  
  
3.  <span data-ttu-id="859c0-268">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="859c0-268">Enter the following command:</span></span>  
  
    ```  
    installutil.exe /u MyNewService.exe  
    ```  
  
     <span data-ttu-id="859c0-269">如果服务成功卸载，installutil.exe 将报告已成功移除服务。</span><span class="sxs-lookup"><span data-stu-id="859c0-269">If the service uninstalls successfully, installutil.exe will report that your service was successfully removed.</span></span> <span data-ttu-id="859c0-270">有关更多信息，请参见 [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。</span><span class="sxs-lookup"><span data-stu-id="859c0-270">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="859c0-271">后续步骤</span><span class="sxs-lookup"><span data-stu-id="859c0-271">Next Steps</span></span>  
 <span data-ttu-id="859c0-272">你可以创建其他人可以用来安装你的 Windows 服务的独立安装程序，但需要额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="859c0-272">You can create a standalone setup program that others can use to install your Windows service, but it requires additional steps.</span></span> <span data-ttu-id="859c0-273">ClickOnce 不支持 Windows 服务，因此你无法使用发布向导。</span><span class="sxs-lookup"><span data-stu-id="859c0-273">ClickOnce doesn't support Windows services, so you can't use the Publish Wizard.</span></span> <span data-ttu-id="859c0-274">可使用 InstallShield 的完整版（Microsoft 不提供）。</span><span class="sxs-lookup"><span data-stu-id="859c0-274">You can use a full edition of InstallShield, which Microsoft doesn't provide.</span></span> <span data-ttu-id="859c0-275">有关 InstallShield 的详细信息，请参阅 [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition)。</span><span class="sxs-lookup"><span data-stu-id="859c0-275">For more information about InstallShield, see [InstallShield Limited Edition](/visualstudio/deployment/installshield-limited-edition).</span></span> <span data-ttu-id="859c0-276">你也可以使用 [Windows Installer XML 工具集](http://go.microsoft.com/fwlink/?LinkId=249067) 来为 Windows 服务创建安装程序。</span><span class="sxs-lookup"><span data-stu-id="859c0-276">You can also use the [Windows Installer XML Toolset](http://go.microsoft.com/fwlink/?LinkId=249067) to create an installer for a Windows service.</span></span>  
  
 <span data-ttu-id="859c0-277">你可以浏览 <xref:System.ServiceProcess.ServiceController> 组件的用途，这将使你能发送命令到你已经安装的服务。</span><span class="sxs-lookup"><span data-stu-id="859c0-277">You might explore the use of a <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you have installed.</span></span>  
  
 <span data-ttu-id="859c0-278">可以在安装应用程序时使用安装程序创建事件日志，而不是在运行应用程序时创建事件日志。</span><span class="sxs-lookup"><span data-stu-id="859c0-278">You can use an installer to create an event log when the application is installed instead of creating the event log when the application runs.</span></span> <span data-ttu-id="859c0-279">此外，在卸载应用程序时，事件日志将被安装程序删除。</span><span class="sxs-lookup"><span data-stu-id="859c0-279">Additionally, the event log will be deleted by the installer when the application is uninstalled.</span></span> <span data-ttu-id="859c0-280">有关详细信息，请参阅 <xref:System.Diagnostics.EventLogInstaller> 引用页。</span><span class="sxs-lookup"><span data-stu-id="859c0-280">For more information, see the <xref:System.Diagnostics.EventLogInstaller> reference page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859c0-281">请参阅</span><span class="sxs-lookup"><span data-stu-id="859c0-281">See Also</span></span>  
 [<span data-ttu-id="859c0-282">Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="859c0-282">Windows Service Applications</span></span>](../../../docs/framework/windows-services/index.md)  
 [<span data-ttu-id="859c0-283">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="859c0-283">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)  
 [<span data-ttu-id="859c0-284">如何：调试 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="859c0-284">How to: Debug Windows Service Applications</span></span>](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)  
 [<span data-ttu-id="859c0-285">服务 (Windows)</span><span class="sxs-lookup"><span data-stu-id="859c0-285">Services (Windows)</span></span>](http://msdn.microsoft.com/library/windows/desktop/ms685141.aspx)
