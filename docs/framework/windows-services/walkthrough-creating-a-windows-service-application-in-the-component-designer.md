---
title: 教程：创建 Windows 服务应用
ms.date: 03/27/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: 35ef113acffbebdcd4cb585970e575f17959f75b
ms.sourcegitcommit: 680a741667cf6859de71586a0caf6be14f4f7793
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2019
ms.locfileid: "59518027"
---
# <a name="tutorial-create-a-windows-service-app"></a><span data-ttu-id="133c3-102">教程：创建 Windows 服务应用</span><span class="sxs-lookup"><span data-stu-id="133c3-102">Tutorial: Create a Windows service app</span></span>

<span data-ttu-id="133c3-103">本文演示了如何在 Visual Studio 中创建可向事件日志中写入消息的 Windows 服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="133c3-103">This article demonstrates how to create a Windows service app in Visual Studio that writes messages to an event log.</span></span>

## <a name="create-a-service"></a><span data-ttu-id="133c3-104">创建服务</span><span class="sxs-lookup"><span data-stu-id="133c3-104">Create a service</span></span>

<span data-ttu-id="133c3-105">首先，创建项目并设置服务正常运行所必需的值。</span><span class="sxs-lookup"><span data-stu-id="133c3-105">To begin, create the project and set the values that are required for the service to function correctly.</span></span>

1. <span data-ttu-id="133c3-106">从 Visual Studio“文件”菜单中，选择“新建” > “项目”（或按 Ctrl+Shift+N），打开“新建项目”窗口。</span><span class="sxs-lookup"><span data-stu-id="133c3-106">From the Visual Studio **File** menu, select **New** > **Project** (or press **Ctrl**+**Shift**+**N**) to open the **New Project** window.</span></span>

2. <span data-ttu-id="133c3-107">导航到并选择“Windows 服务 (.NET Framework)”项目模板。</span><span class="sxs-lookup"><span data-stu-id="133c3-107">Navigate to and select the **Windows Service (.NET Framework)** project template.</span></span> <span data-ttu-id="133c3-108">若要找到它，请展开“已安装”和 **“Visual C#”** 或 **“Visual Basic”**，然后选择“Windows 桌面”。</span><span class="sxs-lookup"><span data-stu-id="133c3-108">To find it, expand **Installed** and **Visual C#** or **Visual Basic**, then select **Windows Desktop**.</span></span> <span data-ttu-id="133c3-109">或者，在右上方的搜索框中输入 Windows 服务，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="133c3-109">Or, enter *Windows Service* in the search box on the upper right and press **Enter**.</span></span>

   ![Visual Studio“新建项目”对话框中的“Windows 服务”模板](media/new-project-dialog.png)

   > [!NOTE]
   > <span data-ttu-id="133c3-111">如果未看到“Windows 服务”模板，建议安装“.NET 桌面开发”工作负载：</span><span class="sxs-lookup"><span data-stu-id="133c3-111">If you don't see the **Windows Service** template, you may need to install the **.NET desktop development** workload:</span></span>
   >  
   > <span data-ttu-id="133c3-112">在“新建项目”对话框中，选择左下方的“打开 Visual Studio 安装程序”。</span><span class="sxs-lookup"><span data-stu-id="133c3-112">In the **New Project** dialog, select **Open Visual Studio Installer** on the lower left.</span></span> <span data-ttu-id="133c3-113">选择“.NET 桌面开发”工作负载，然后选择“修改”。</span><span class="sxs-lookup"><span data-stu-id="133c3-113">Select the **.NET desktop development** workload, and then select **Modify**.</span></span>

3. <span data-ttu-id="133c3-114">对于“名称”，请输入 MyNewService，然后选择“确定”。</span><span class="sxs-lookup"><span data-stu-id="133c3-114">For **Name**, enter *MyNewService*, and then select **OK**.</span></span>

   <span data-ttu-id="133c3-115">将出现“设计”选项卡（“Service1.cs [Design]”或“Service1.vb [Design]”）。</span><span class="sxs-lookup"><span data-stu-id="133c3-115">The **Design** tab appears (**Service1.cs [Design]** or **Service1.vb [Design]**).</span></span>
   
   <span data-ttu-id="133c3-116">项目模板包括从 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 继承的名为 `Service1` 的组件类。</span><span class="sxs-lookup"><span data-stu-id="133c3-116">The project template includes a component class named `Service1` that inherits from <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType>.</span></span> <span data-ttu-id="133c3-117">它包括许多基本服务代码，例如用于启动服务的代码。</span><span class="sxs-lookup"><span data-stu-id="133c3-117">It includes much of the basic service code, such as the code to start the service.</span></span>

## <a name="rename-the-service"></a><span data-ttu-id="133c3-118">对服务进行重命名</span><span class="sxs-lookup"><span data-stu-id="133c3-118">Rename the service</span></span>

<span data-ttu-id="133c3-119">将服务从 **Service1** 重命名为 **MyNewService**。</span><span class="sxs-lookup"><span data-stu-id="133c3-119">Rename the service from **Service1** to **MyNewService**.</span></span>

1. <span data-ttu-id="133c3-120">在“解决方案资源管理器”中，选择“Service1.cs”或“Service1.vb”，然后从快捷菜单中选择“重命名”。</span><span class="sxs-lookup"><span data-stu-id="133c3-120">In **Solution Explorer**, select **Service1.cs**, or **Service1.vb**, and choose **Rename** from the shortcut menu.</span></span> <span data-ttu-id="133c3-121">将文件重命名为“MyNewService.cs”或“MyNewService.vb”，然后按 Enter</span><span class="sxs-lookup"><span data-stu-id="133c3-121">Rename the file to **MyNewService.cs**, or **MyNewService.vb**, and then press **Enter**</span></span>

    <span data-ttu-id="133c3-122">随即将出现一个弹出窗口，询问是否要重命名对代码元素 Service1 的所有引用。</span><span class="sxs-lookup"><span data-stu-id="133c3-122">A pop-up window appears asking whether you would like to rename all references to the code element *Service1*.</span></span>

2. <span data-ttu-id="133c3-123">在弹出窗口中，选择“是”。</span><span class="sxs-lookup"><span data-stu-id="133c3-123">In the pop-up window, select **Yes**.</span></span>

    <span data-ttu-id="133c3-124">![重命名提示](media/windows-service-rename.png "Windows 服务重命名提示")</span><span class="sxs-lookup"><span data-stu-id="133c3-124">![Rename prompt](media/windows-service-rename.png "Windows service rename prompt")</span></span>

2. <span data-ttu-id="133c3-125">在“设计”选项卡中，从快捷菜单中选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="133c3-125">In the **Design** tab, select **Properties** from the shortcut menu.</span></span> <span data-ttu-id="133c3-126">在“属性”窗口中，将“ServiceName”值更改为 MyNewService。</span><span class="sxs-lookup"><span data-stu-id="133c3-126">From the **Properties** window, change the **ServiceName** value to *MyNewService*.</span></span>

    <span data-ttu-id="133c3-127">![服务属性](media/windows-service-properties.png "Windows 服务属性")</span><span class="sxs-lookup"><span data-stu-id="133c3-127">![Service properties](media/windows-service-properties.png "Windows service properties")</span></span>

3. <span data-ttu-id="133c3-128">从“文件”菜单中选择“全部保存”。</span><span class="sxs-lookup"><span data-stu-id="133c3-128">Select **Save All** from the **File** menu.</span></span>

## <a name="add-features-to-the-service"></a><span data-ttu-id="133c3-129">向服务添加功能</span><span class="sxs-lookup"><span data-stu-id="133c3-129">Add features to the service</span></span>

<span data-ttu-id="133c3-130">在本节中，你会添加自定义事件日志到 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="133c3-130">In this section, you add a custom event log to the Windows service.</span></span> <span data-ttu-id="133c3-131"><xref:System.Diagnostics.EventLog> 组件是可以添加到 Windows 服务的组件类型的示例。</span><span class="sxs-lookup"><span data-stu-id="133c3-131">The <xref:System.Diagnostics.EventLog> component is an example of the type of component you can add to a Windows service.</span></span>

### <a name="add-custom-event-log-functionality"></a><span data-ttu-id="133c3-132">添加自定义事件日志功能</span><span class="sxs-lookup"><span data-stu-id="133c3-132">Add custom event log functionality</span></span>

1. <span data-ttu-id="133c3-133">在“解决方案资源管理器”中，从“MyNewService.cs”或“MyNewService.vb”的快捷菜单中，选择“查看设计器”。</span><span class="sxs-lookup"><span data-stu-id="133c3-133">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="133c3-134">在“工具箱”中，展开“组件”，然后将“EventLog”组件拖到“Service1.cs [Design]”或“Service1.vb [Design]”标签。</span><span class="sxs-lookup"><span data-stu-id="133c3-134">In **Toolbox**, expand **Components**, and then drag the **EventLog** component to the **Service1.cs [Design]**, or **Service1.vb [Design]** tab.</span></span>

3. <span data-ttu-id="133c3-135">在“解决方案资源管理器”中，从“MyNewService.cs”或“MyNewService.vb”的快捷菜单中，选择“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="133c3-135">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Code**.</span></span>

4. <span data-ttu-id="133c3-136">定义自定义事件日志。</span><span class="sxs-lookup"><span data-stu-id="133c3-136">Define a custom event log.</span></span> <span data-ttu-id="133c3-137">对于 C#，编辑现有的 `MyNewService()` 构造函数；对于 Visual Basic，添加 `New()` 构造函数：</span><span class="sxs-lookup"><span data-stu-id="133c3-137">For C#, edit the existing `MyNewService()` constructor; for Visual Basic, add the `New()` constructor:</span></span>

   [!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#2)]
   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

5. <span data-ttu-id="133c3-138">将 `using` 语句添加到“MyNewService.cs”（如果它尚不存在）或者，对于 <xref:System.Diagnostics?displayProperty=nameWithType> 命名空间，将 `Imports` 语句添加到“MyNewService.vb”：</span><span class="sxs-lookup"><span data-stu-id="133c3-138">Add a `using` statement to **MyNewService.cs** (if it doesn't already exist), or an `Imports` statement **MyNewService.vb**, for the <xref:System.Diagnostics?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Diagnostics;
    ```

    ```vb
    Imports System.Diagnostics
    ```

6. <span data-ttu-id="133c3-139">从“文件”菜单中选择“全部保存”。</span><span class="sxs-lookup"><span data-stu-id="133c3-139">Select **Save All** from the **File** menu.</span></span>

### <a name="define-what-occurs-when-the-service-starts"></a><span data-ttu-id="133c3-140">定义服务启动时发生的情况</span><span class="sxs-lookup"><span data-stu-id="133c3-140">Define what occurs when the service starts</span></span>

<span data-ttu-id="133c3-141">在“MyNewService.cs”或“MyNewService.vb”的代码编辑器中，找到 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法；创建项目时，Visual Studio 会自动创建一个空方法定义。</span><span class="sxs-lookup"><span data-stu-id="133c3-141">In the code editor for **MyNewService.cs** or **MyNewService.vb**, locate the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method; Visual Studio automatically created an empty method definition when you created the project.</span></span> <span data-ttu-id="133c3-142">添加代码，以在服务启动时向事件日志写入一个条目：</span><span class="sxs-lookup"><span data-stu-id="133c3-142">Add code that writes an entry to the event log when the service starts:</span></span>

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

#### <a name="polling"></a><span data-ttu-id="133c3-143">轮询</span><span class="sxs-lookup"><span data-stu-id="133c3-143">Polling</span></span>

<span data-ttu-id="133c3-144">由于服务应用程序设计为长时间运行，因此它通常会轮询或监视你在 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法中设置的系统。</span><span class="sxs-lookup"><span data-stu-id="133c3-144">Because a service application is designed to be long-running, it usually polls or monitors the system, which you set up in the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method.</span></span> <span data-ttu-id="133c3-145">在服务操作开始后，`OnStart` 方法必须返回操作系统，以便不阻止系统。</span><span class="sxs-lookup"><span data-stu-id="133c3-145">The `OnStart` method must return to the operating system after the service's operation has begun so that the system isn't blocked.</span></span> 

<span data-ttu-id="133c3-146">若要设置简单的轮询机制，请使用 <xref:System.Timers.Timer?displayProperty=nameWithType> 组件。</span><span class="sxs-lookup"><span data-stu-id="133c3-146">To set up a simple polling mechanism, use the <xref:System.Timers.Timer?displayProperty=nameWithType> component.</span></span> <span data-ttu-id="133c3-147">计时器定期引发 <xref:System.Timers.Timer.Elapsed> 事件，此时你的服务可以进行监视。</span><span class="sxs-lookup"><span data-stu-id="133c3-147">The timer raises an <xref:System.Timers.Timer.Elapsed> event at regular intervals, at which time your service can do its monitoring.</span></span> <span data-ttu-id="133c3-148">可按如下方式使用 <xref:System.Timers.Timer> 组件：</span><span class="sxs-lookup"><span data-stu-id="133c3-148">You use the <xref:System.Timers.Timer> component as follows:</span></span>

- <span data-ttu-id="133c3-149">在 `MyNewService.OnStart` 方法中设置 <xref:System.Timers.Timer> 组件的属性。</span><span class="sxs-lookup"><span data-stu-id="133c3-149">Set the properties of the <xref:System.Timers.Timer> component in the `MyNewService.OnStart` method.</span></span>
- <span data-ttu-id="133c3-150">通过调用 <xref:System.Timers.Timer.Start%2A> 方法启动计时器。</span><span class="sxs-lookup"><span data-stu-id="133c3-150">Start the timer by calling the <xref:System.Timers.Timer.Start%2A> method.</span></span>

##### <a name="set-up-the-polling-mechanism"></a><span data-ttu-id="133c3-151">设置轮询机制。</span><span class="sxs-lookup"><span data-stu-id="133c3-151">Set up the polling mechanism.</span></span>

1. <span data-ttu-id="133c3-152">在 `MyNewService.OnStart` 事件中添加以下代码以设置轮询机制：</span><span class="sxs-lookup"><span data-stu-id="133c3-152">Add the following code in the `MyNewService.OnStart` event to set up the polling mechanism:</span></span>

   ```csharp
   // Set up a timer that triggers every minute.
   Timer timer = new Timer();
   timer.Interval = 60000; // 60 seconds
   timer.Elapsed += new ElapsedEventHandler(this.OnTimer);
   timer.Start();
   ```

   ```vb
   ' Set up a timer that triggers every minute.
   Dim timer As Timer = New Timer()
   timer.Interval = 60000 ' 60 seconds
   AddHandler timer.Elapsed, AddressOf Me.OnTimer
   timer.Start()
   ```

2. <span data-ttu-id="133c3-153">将 `using` 语句添加到“MyNewService.cs”，或者，对于 <xref:System.Timers?displayProperty=nameWithType> 命名空间，将 `Imports` 语句添加到“MyNewService.vb”：</span><span class="sxs-lookup"><span data-stu-id="133c3-153">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Timers?displayProperty=nameWithType> namespace:</span></span>

   ```csharp
   using System.Timers;
   ```

   ```vb
   Imports System.Timers
   ```

3. <span data-ttu-id="133c3-154">在 `MyNewService` 类中，添加 `OnTimer` 方法来处理 <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> 事件：</span><span class="sxs-lookup"><span data-stu-id="133c3-154">In the `MyNewService` class, add the `OnTimer` method to handle the <xref:System.Timers.Timer.Elapsed?displayProperty=nameWithType> event:</span></span>

   ```csharp
   public void OnTimer(object sender, ElapsedEventArgs args)
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

4. <span data-ttu-id="133c3-155">在 `MyNewService` 类中，添加成员变量。</span><span class="sxs-lookup"><span data-stu-id="133c3-155">In the `MyNewService` class, add a member variable.</span></span> <span data-ttu-id="133c3-156">它包含下一个要写入事件日志的事件的标识符：</span><span class="sxs-lookup"><span data-stu-id="133c3-156">It contains the identifier of the next event to write into the event log:</span></span>

   ```csharp
   private int eventId = 1;
   ```

   ```vb
   Private eventId As Integer = 1
   ```

<span data-ttu-id="133c3-157">可以使用后台工作线程来运行任务，而不是在主线程上运行所有工作。</span><span class="sxs-lookup"><span data-stu-id="133c3-157">Instead of running all your work on the main thread, you can run tasks by using background worker threads.</span></span> <span data-ttu-id="133c3-158">有关更多信息，请参见<xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="133c3-158">For more information, see <xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>.</span></span>

### <a name="define-what-occurs-when-the-service-is-stopped"></a><span data-ttu-id="133c3-159">定义服务停止时发生的情况</span><span class="sxs-lookup"><span data-stu-id="133c3-159">Define what occurs when the service is stopped</span></span>

<span data-ttu-id="133c3-160">向 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法插入代码行，以在服务停止时向事件日志添加一个条目：</span><span class="sxs-lookup"><span data-stu-id="133c3-160">Insert a line of code in the <xref:System.ServiceProcess.ServiceBase.OnStop%2A> method that adds an entry to the event log when the service is stopped:</span></span>

[!code-csharp[VbRadconService#2](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#4)]
[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a><span data-ttu-id="133c3-161">定义服务的其他操作</span><span class="sxs-lookup"><span data-stu-id="133c3-161">Define other actions for the service</span></span>

<span data-ttu-id="133c3-162">可以重写 <xref:System.ServiceProcess.ServiceBase.OnPause%2A>、<xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> 方法来定义对组件的其他处理。</span><span class="sxs-lookup"><span data-stu-id="133c3-162">You can override the <xref:System.ServiceProcess.ServiceBase.OnPause%2A>, <xref:System.ServiceProcess.ServiceBase.OnContinue%2A>, and <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> methods to define additional processing for your component.</span></span> 

<span data-ttu-id="133c3-163">以下代码显示了如何替代 `MyNewService` 类中的 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 方法：</span><span class="sxs-lookup"><span data-stu-id="133c3-163">The following code shows how you to override the <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> method in the `MyNewService` class:</span></span>

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

## <a name="set-service-status"></a><span data-ttu-id="133c3-164">设置服务状态</span><span class="sxs-lookup"><span data-stu-id="133c3-164">Set service status</span></span>

<span data-ttu-id="133c3-165">服务向[服务控制管理器](/windows/desktop/Services/service-control-manager)报告其状态，以便用户可以判断服务是否运行正常。</span><span class="sxs-lookup"><span data-stu-id="133c3-165">Services report their status to the [Service Control Manager](/windows/desktop/Services/service-control-manager) so that a user can tell whether a service is functioning correctly.</span></span> <span data-ttu-id="133c3-166">默认情况下，从 <xref:System.ServiceProcess.ServiceBase> 继承的服务会报告一组有限的状态设置，包括 SERVICE_STOPPED、SERVICE_PAUSED 和 SERVICE_RUNNING。</span><span class="sxs-lookup"><span data-stu-id="133c3-166">By default, a service that inherits from <xref:System.ServiceProcess.ServiceBase> reports a limited set of status settings, which include SERVICE_STOPPED, SERVICE_PAUSED, and SERVICE_RUNNING.</span></span> <span data-ttu-id="133c3-167">如果服务需要一段时间才能启动，则报告 SERVICE_START_PENDING 状态非常有用。</span><span class="sxs-lookup"><span data-stu-id="133c3-167">If a service takes a while to start up, it's useful to report a SERVICE_START_PENDING status.</span></span> 

<span data-ttu-id="133c3-168">可以通过添加调用 Windows [ SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) 函数的代码来实现 SERVICE_START_PENDING 和 SERVICE_STOP_PENDING 状态设置。</span><span class="sxs-lookup"><span data-stu-id="133c3-168">You can implement the SERVICE_START_PENDING and SERVICE_STOP_PENDING status settings by adding code that calls the Windows [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function.</span></span>

### <a name="implement-service-pending-status"></a><span data-ttu-id="133c3-169">实现服务挂起状态</span><span class="sxs-lookup"><span data-stu-id="133c3-169">Implement service pending status</span></span>

1. <span data-ttu-id="133c3-170">将 `using` 语句添加到“MyNewService.cs”，或者，对于 <xref:System.Runtime.InteropServices?displayProperty=nameWithType> 命名空间，将 `Imports` 语句添加到“MyNewService.vb”：</span><span class="sxs-lookup"><span data-stu-id="133c3-170">Add a `using` statement to **MyNewService.cs**, or an `Imports` statement to **MyNewService.vb**, for the <xref:System.Runtime.InteropServices?displayProperty=nameWithType> namespace:</span></span>

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. <span data-ttu-id="133c3-171">将以下代码添加到 MyNewService.cs 或 MyNewService.vb，声明 `ServiceState` 值和添加你将在平台调用中使用的状态结构：</span><span class="sxs-lookup"><span data-stu-id="133c3-171">Add the following code to **MyNewService.cs**, or **MyNewService.vb**, to declare the `ServiceState` values and to add a structure for the status, which you'll use in a platform invoke call:</span></span>

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

    > [!NOTE]
    > <span data-ttu-id="133c3-172">服务控制管理器使用 [SERVICE_STATUS 结构](/windows/desktop/api/winsvc/ns-winsvc-_service_status)的 `dwWaitHint` 和 `dwCheckpoint` 成员来确定等待 Windows 服务启动或关闭所需的时间。</span><span class="sxs-lookup"><span data-stu-id="133c3-172">The Service Control Manager uses the `dwWaitHint` and `dwCheckpoint` members of the [SERVICE_STATUS structure](/windows/desktop/api/winsvc/ns-winsvc-_service_status) to determine how much time to wait for a Windows service to start or shut down.</span></span> <span data-ttu-id="133c3-173">如果 `OnStart` 和 `OnStop` 方法运行时间较长，服务可以使用递增的 `dwCheckPoint` 值再次调用 `SetServiceStatus` 来请求更多时间。</span><span class="sxs-lookup"><span data-stu-id="133c3-173">If your `OnStart` and `OnStop` methods run long, your service can request more time by calling `SetServiceStatus` again with an incremented `dwCheckPoint` value.</span></span>

3. <span data-ttu-id="133c3-174">在 `MyNewService` 类中，使用[平台调用](../interop/consuming-unmanaged-dll-functions.md)声明 [SetServiceStatus 函数](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus)：</span><span class="sxs-lookup"><span data-stu-id="133c3-174">In the `MyNewService` class, declare the [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) function by using [platform invoke](../interop/consuming-unmanaged-dll-functions.md):</span></span>

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. <span data-ttu-id="133c3-175">若要实现“SERVICE_START_PENDING”状态，请将以下代码添加到 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法的开头：</span><span class="sxs-lookup"><span data-stu-id="133c3-175">To implement the SERVICE_START_PENDING status, add the following code to the beginning of the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method:</span></span>

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

5. <span data-ttu-id="133c3-176">将代码添加到 `OnStart` 方法的末尾，可将状态设置为 SERVICE_RUNNING：</span><span class="sxs-lookup"><span data-stu-id="133c3-176">Add code to the end of the `OnStart` method to set the status to SERVICE_RUNNING:</span></span>

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

6. <span data-ttu-id="133c3-177">（可选）如果 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 是长时间运行的方法，请在 `OnStop` 方法中重复此过程。</span><span class="sxs-lookup"><span data-stu-id="133c3-177">(Optional) If <xref:System.ServiceProcess.ServiceBase.OnStop%2A> is a long-running method, repeat this procedure in the `OnStop` method.</span></span> <span data-ttu-id="133c3-178">实现 SERVICE_STOP_PENDING 状态并在 `OnStop` 方法退出之前返回 SERVICE_STOPPED 状态。</span><span class="sxs-lookup"><span data-stu-id="133c3-178">Implement the SERVICE_STOP_PENDING status and return the SERVICE_STOPPED status before the `OnStop` method exits.</span></span>

   <span data-ttu-id="133c3-179">例如:</span><span class="sxs-lookup"><span data-stu-id="133c3-179">For example:</span></span>

    ```csharp
    // Update the service state to Stop Pending.
    ServiceStatus serviceStatus = new ServiceStatus();
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING;
    serviceStatus.dwWaitHint = 100000;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);

    // Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED;
    SetServiceStatus(this.ServiceHandle, ref serviceStatus);
    ```

    ```vb
    ' Update the service state to Stop Pending.
    Dim serviceStatus As ServiceStatus = New ServiceStatus()
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOP_PENDING
    serviceStatus.dwWaitHint = 100000
    SetServiceStatus(Me.ServiceHandle, serviceStatus)

    ' Update the service state to Stopped.
    serviceStatus.dwCurrentState = ServiceState.SERVICE_STOPPED
    SetServiceStatus(Me.ServiceHandle, serviceStatus)    
    ```

## <a name="add-installers-to-the-service"></a><span data-ttu-id="133c3-180">向服务添加安装程序</span><span class="sxs-lookup"><span data-stu-id="133c3-180">Add installers to the service</span></span>

<span data-ttu-id="133c3-181">需要先安装 Windows 服务然后才能运行，这会将其注册到服务控制管理器。</span><span class="sxs-lookup"><span data-stu-id="133c3-181">Before you run a Windows service, you need to install it, which registers it with the Service Control Manager.</span></span> <span data-ttu-id="133c3-182">将安装程序添加到项目以处理注册详细信息。</span><span class="sxs-lookup"><span data-stu-id="133c3-182">Add installers to your project to handle the registration details.</span></span>

1. <span data-ttu-id="133c3-183">在“解决方案资源管理器”中，从“MyNewService.cs”或“MyNewService.vb”的快捷菜单中，选择“查看设计器”。</span><span class="sxs-lookup"><span data-stu-id="133c3-183">In **Solution Explorer**, from the shortcut menu for **MyNewService.cs**, or **MyNewService.vb**, choose **View Designer**.</span></span>

2. <span data-ttu-id="133c3-184">在“设计”视图中，选择背景区域，然后从快捷菜单中选择“添加安装程序”。</span><span class="sxs-lookup"><span data-stu-id="133c3-184">In the **Design** view, select the background area, then choose **Add Installer** from the shortcut menu.</span></span>

     <span data-ttu-id="133c3-185">默认情况下，Visual Studio 会向项目中添加一个名为 `ProjectInstaller` 的组件类，其中包含两个安装程序。</span><span class="sxs-lookup"><span data-stu-id="133c3-185">By default, Visual Studio adds a component class named `ProjectInstaller`, which contains two installers, to your project.</span></span> <span data-ttu-id="133c3-186">这些安装程序是为你的服务以及服务的相关过程准备的。</span><span class="sxs-lookup"><span data-stu-id="133c3-186">These installers are for your service and for the service's associated process.</span></span>

4. <span data-ttu-id="133c3-187">在“ProjectInstaller”的“设计”视图中，为 Visual C# 项目选择“serviceInstaller1”，或为 Visual Basic 项目选择“ServiceInstaller1”，然后选择快捷菜单中的“属性”。</span><span class="sxs-lookup"><span data-stu-id="133c3-187">In the **Design** view for **ProjectInstaller**, select **serviceInstaller1** for a Visual C# project, or **ServiceInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span>

5. <span data-ttu-id="133c3-188">在“属性”窗口中，验证 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 属性是否已设置为“MyNewService”。</span><span class="sxs-lookup"><span data-stu-id="133c3-188">In the **Properties** window, verify the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property is set to **MyNewService**.</span></span>

6. <span data-ttu-id="133c3-189">将文本添加到 <xref:System.ServiceProcess.ServiceInstaller.Description%2A> 属性，例如“一个示例服务”。</span><span class="sxs-lookup"><span data-stu-id="133c3-189">Add text to the <xref:System.ServiceProcess.ServiceInstaller.Description%2A> property, such as *A sample service*.</span></span> 

     <span data-ttu-id="133c3-190">此文本显示在“服务”窗口的“说明”列中，并向用户说明了该服务。</span><span class="sxs-lookup"><span data-stu-id="133c3-190">This text appears in the **Description** column of the **Services** window and describes the service to the user.</span></span>

    <span data-ttu-id="133c3-191">![“服务”窗口中的服务说明。](media/windows-service-description.png "服务说明")</span><span class="sxs-lookup"><span data-stu-id="133c3-191">![Service description in the Services window.](media/windows-service-description.png "Service description")</span></span>

7. <span data-ttu-id="133c3-192">将文本添加到 <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="133c3-192">Add text to the <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> property.</span></span> <span data-ttu-id="133c3-193">例如，“MyNewService 显示名称”。</span><span class="sxs-lookup"><span data-stu-id="133c3-193">For example, *MyNewService Display Name*.</span></span> 

     <span data-ttu-id="133c3-194">此文本显示在“服务”窗口的“显示名称”列中。</span><span class="sxs-lookup"><span data-stu-id="133c3-194">This text appears in the **Display Name** column of the **Services** window.</span></span> <span data-ttu-id="133c3-195">此名称可以不同于 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 属性，它是系统使用的名称（例如，用于启动服务的 `net start` 命令的名称）。</span><span class="sxs-lookup"><span data-stu-id="133c3-195">This name can be different from the <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> property, which is the name the system uses (for example, the name you use for the `net start` command to start your service).</span></span>

8. <span data-ttu-id="133c3-196">从下拉列表中将 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 属性设置为 <xref:System.ServiceProcess.ServiceStartMode.Automatic>。</span><span class="sxs-lookup"><span data-stu-id="133c3-196">Set the <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> property to <xref:System.ServiceProcess.ServiceStartMode.Automatic> from the drop-down list.</span></span>

9. <span data-ttu-id="133c3-197">完成后，“属性”窗口应如下图所示：</span><span class="sxs-lookup"><span data-stu-id="133c3-197">When you're finished, the **Properties** windows should look like the following figure:</span></span>

     <span data-ttu-id="133c3-198">![Windows 服务的安装程序属性](media/windows-service-installer-properties.png "Windows 服务安装程序属性")</span><span class="sxs-lookup"><span data-stu-id="133c3-198">![Installer Properties for a Windows service](media/windows-service-installer-properties.png "Windows service installer properties")</span></span>

9. <span data-ttu-id="133c3-199">在“ProjectInstaller”的“设计”视图中，为 Visual C# 项目选择“serviceProcessInstaller1”，或为 Visual Basic 项目选择“serviceProcessInstaller1”，然后选择快捷菜单中的“属性”。</span><span class="sxs-lookup"><span data-stu-id="133c3-199">In the **Design** view for **ProjectInstaller**, choose **serviceProcessInstaller1** for a Visual C# project, or **ServiceProcessInstaller1** for a Visual Basic project, then choose **Properties** from the shortcut menu.</span></span> <span data-ttu-id="133c3-200">从下拉列表中将 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 属性设置为 <xref:System.ServiceProcess.ServiceAccount.LocalSystem>。</span><span class="sxs-lookup"><span data-stu-id="133c3-200">Set the <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> property to <xref:System.ServiceProcess.ServiceAccount.LocalSystem> from the drop-down list.</span></span> 

     <span data-ttu-id="133c3-201">此设置将安装服务并使用本地系统帐户运行它。</span><span class="sxs-lookup"><span data-stu-id="133c3-201">This setting installs the service and runs it by using the local system account.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="133c3-202"><xref:System.ServiceProcess.ServiceAccount.LocalSystem> 帐户具有广泛的权限，包括能够写入事件日志。</span><span class="sxs-lookup"><span data-stu-id="133c3-202">The <xref:System.ServiceProcess.ServiceAccount.LocalSystem> account has broad permissions, including the ability to write to the event log.</span></span> <span data-ttu-id="133c3-203">使用此帐户时要特别小心，因为它会增加你受到恶意软件攻击的风险。</span><span class="sxs-lookup"><span data-stu-id="133c3-203">Use this account with caution, because it might increase your risk of attacks from malicious software.</span></span> <span data-ttu-id="133c3-204">对于其他任务，请考虑使用 <xref:System.ServiceProcess.ServiceAccount.LocalService> 帐户，该帐户用作本地计算机上的非特权用户，并向任意远程服务器提供匿名凭据。</span><span class="sxs-lookup"><span data-stu-id="133c3-204">For other tasks, consider using the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, which acts as a non-privileged user on the local computer and presents anonymous credentials to any remote server.</span></span> <span data-ttu-id="133c3-205">如果你尝试使用 <xref:System.ServiceProcess.ServiceAccount.LocalService> 账户，此例子将失败，因为它需要写入事件日志的权限。</span><span class="sxs-lookup"><span data-stu-id="133c3-205">This example fails if you try to use the <xref:System.ServiceProcess.ServiceAccount.LocalService> account, because it needs permission to write to the event log.</span></span>

<span data-ttu-id="133c3-206">有关安装程序的详细信息，请参阅[如何：将安装程序添加到服务应用程序](how-to-add-installers-to-your-service-application.md)。</span><span class="sxs-lookup"><span data-stu-id="133c3-206">For more information about installers, see [How to: Add installers to your service application](how-to-add-installers-to-your-service-application.md).</span></span>

## <a name="optional-set-startup-parameters"></a><span data-ttu-id="133c3-207">（可选）设置启动参数</span><span class="sxs-lookup"><span data-stu-id="133c3-207">(Optional) Set startup parameters</span></span>

> [!NOTE]
> <span data-ttu-id="133c3-208">在决定添加启动参数前，请考虑这是否是向你的服务传递信息的最好办法。</span><span class="sxs-lookup"><span data-stu-id="133c3-208">Before you decide to add startup parameters, consider whether it's the best way to pass information to your service.</span></span> <span data-ttu-id="133c3-209">虽然它们易于使用和分析，而且用户可以轻松地替代它们，但是如果没有相关的文档说明，用户可能较难发现和使用它们。</span><span class="sxs-lookup"><span data-stu-id="133c3-209">Although they're easy to use and parse, and a user can easily override them, they might be harder for a user to discover and use without documentation.</span></span> <span data-ttu-id="133c3-210">通常情况下，如果服务需要不止几个启动参数，则应改用注册表或配置文件。</span><span class="sxs-lookup"><span data-stu-id="133c3-210">Generally, if your service requires more than just a few startup parameters, you should use the registry or a configuration file instead.</span></span> 

<span data-ttu-id="133c3-211">Windows 服务可以接受命令行参数或启动参数。</span><span class="sxs-lookup"><span data-stu-id="133c3-211">A Windows service can accept command-line arguments, or startup parameters.</span></span> <span data-ttu-id="133c3-212">将代码添加到进程启动参数后，用户可以在服务属性窗口中使用自己的自定义启动参数启动服务。</span><span class="sxs-lookup"><span data-stu-id="133c3-212">When you add code to process startup parameters, a user can start your service with their own custom startup parameters in the service properties window.</span></span> <span data-ttu-id="133c3-213">但是，这些启动参数不会保留到下一次服务启动。</span><span class="sxs-lookup"><span data-stu-id="133c3-213">However, these startup parameters aren't persisted the next time the service starts.</span></span> <span data-ttu-id="133c3-214">若要永久设置启动参数，请在注册表中设置它们。</span><span class="sxs-lookup"><span data-stu-id="133c3-214">To set startup parameters permanently, set them in the registry.</span></span>

<span data-ttu-id="133c3-215">每个 Windows 服务在“HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services”子项下都有一个注册表项。</span><span class="sxs-lookup"><span data-stu-id="133c3-215">Each Windows service has a registry entry under the **HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services** subkey.</span></span> <span data-ttu-id="133c3-216">在每个服务的子项下，使用“参数”子项存储服务可以访问的信息。</span><span class="sxs-lookup"><span data-stu-id="133c3-216">Under each service's subkey, use the **Parameters** subkey to store information that your service can access.</span></span> <span data-ttu-id="133c3-217">你可以使用 Windows 服务的应用程序配置文件，与使用其他类型的程序一样。</span><span class="sxs-lookup"><span data-stu-id="133c3-217">You can use application configuration files for a Windows service the same way you do for other types of programs.</span></span> <span data-ttu-id="133c3-218">有关示例代码，请参阅 <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="133c3-218">For sample code, see <xref:System.Configuration.ConfigurationManager.AppSettings?displayProperty=nameWithType>.</span></span>

### <a name="to-add-startup-parameters"></a><span data-ttu-id="133c3-219">添加启动参数</span><span class="sxs-lookup"><span data-stu-id="133c3-219">To add startup parameters</span></span>

1. <span data-ttu-id="133c3-220">选择“Program.cs”或“MyNewService.Designer.vb”，然后从快捷菜单中选择“查看代码”。</span><span class="sxs-lookup"><span data-stu-id="133c3-220">Select **Program.cs**, or **MyNewService.Designer.vb**, then choose **View Code** from the shortcut menu.</span></span> <span data-ttu-id="133c3-221">在 `Main` 方法中，更改代码以添加输入参数并将其传递给服务构造函数：</span><span class="sxs-lookup"><span data-stu-id="133c3-221">In the `Main` method, change the code to add an input parameter and pass it to the service constructor:</span></span>

   [!code-csharp[VbRadconService](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/Program-add-parameter.cs?highlight=1,6)]
   [!code-vb[VbRadconService](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.Designer-add-parameter.vb?highlight=1-2)]

2. <span data-ttu-id="133c3-222">在“MyNewService.cs”或“MyNewService.vb”中，更改 `MyNewService` 构造函数以处理输入参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="133c3-222">In **MyNewService.cs**, or **MyNewService.vb**, change the `MyNewService` constructor to process the input parameter as follows:</span></span>

   ```csharp
   using System.Diagnostics;

   public MyNewService(string[] args)
   {
       InitializeComponent();

       string eventSourceName = "MySource";
       string logName = "MyNewLog";

       if (args.Length > 0)
       {
          eventSourceName = args[0];
       }

       if (args.Length > 1)
       {
           logName = args[1];
       }

       eventLog1 = new EventLog();

       if (!EventLog.SourceExists(eventSourceName))
       {
           EventLog.CreateEventSource(eventSourceName, logName);
       }

       eventLog1.Source = eventSourceName;
       eventLog1.Log = logName;
   }
   ```

   ```vb
   Imports System.Diagnostics

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
       eventLog1 = New EventLog()
       If (Not EventLog.SourceExists(eventSourceName)) Then
           EventLog.CreateEventSource(eventSourceName, logName)
       End If
       eventLog1.Source = eventSourceName
       eventLog1.Log = logName
   End Sub
   ```

   <span data-ttu-id="133c3-223">此代码根据用户提供的启动参数设置事件源和日志名称。</span><span class="sxs-lookup"><span data-stu-id="133c3-223">This code sets the event source and log name according to the startup parameters that the user supplies.</span></span> <span data-ttu-id="133c3-224">如果未提供参数，则使用默认值。</span><span class="sxs-lookup"><span data-stu-id="133c3-224">If no arguments are supplied, it uses default values.</span></span>

3. <span data-ttu-id="133c3-225">若要指定命令行参数，请将以下代码添加到“ProjectInstaller.cs”或“ProjectInstaller.vb”中的 `ProjectInstaller` 类：</span><span class="sxs-lookup"><span data-stu-id="133c3-225">To specify the command-line arguments, add the following code to the `ProjectInstaller` class in **ProjectInstaller.cs**, or **ProjectInstaller.vb**:</span></span>

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

   <span data-ttu-id="133c3-226">通常，此值包含 Windows 服务的可执行文件的完整路径。</span><span class="sxs-lookup"><span data-stu-id="133c3-226">Typically, this value contains the full path to the executable for the Windows service.</span></span> <span data-ttu-id="133c3-227">要使服务正确启动，用户必须为路径和每个参数提供引号。</span><span class="sxs-lookup"><span data-stu-id="133c3-227">For the service to start up correctly, the user must supply quotation marks for the path and each individual parameter.</span></span> <span data-ttu-id="133c3-228">用户可以更改“ImagePath”注册表项中的参数，以更改 Windows 服务的启动参数。</span><span class="sxs-lookup"><span data-stu-id="133c3-228">A user can change the parameters in the **ImagePath** registry entry to change the startup parameters for the Windows service.</span></span> <span data-ttu-id="133c3-229">但是，更好的方法是以编程方式更改值，并以用户友好的方式公开功能，例如使用管理或配置实用程序。</span><span class="sxs-lookup"><span data-stu-id="133c3-229">However, a better way is to change the value programmatically and expose the functionality in a user-friendly way, such as by using a management or configuration utility.</span></span>

## <a name="build-the-service"></a><span data-ttu-id="133c3-230">生成服务</span><span class="sxs-lookup"><span data-stu-id="133c3-230">Build the service</span></span>

1. <span data-ttu-id="133c3-231">在“解决方案资源管理器”中，从“MyNewService”项目的快捷菜单中选择“属性”。</span><span class="sxs-lookup"><span data-stu-id="133c3-231">In **Solution Explorer**, choose **Properties** from the shortcut menu for the **MyNewService** project.</span></span>

   <span data-ttu-id="133c3-232">项目的属性页面会显示出来。</span><span class="sxs-lookup"><span data-stu-id="133c3-232">The property pages for your project appear.</span></span>

2. <span data-ttu-id="133c3-233">在“应用程序”选项卡上，在“启动对象”列表中，为 Visual Basic 项目选择 **“MyNewService.Program”** 或 **“Sub Main”**。</span><span class="sxs-lookup"><span data-stu-id="133c3-233">On the **Application** tab, in the **Startup object** list, choose **MyNewService.Program**, or **Sub Main** for Visual Basic projects.</span></span>

3. <span data-ttu-id="133c3-234">要在“解决方案资源管理器”中生成项目，请从项目的快捷菜单中选择“生成”（或按 Ctrl+Shift+B）。</span><span class="sxs-lookup"><span data-stu-id="133c3-234">To build the project, in **Solution Explorer**, choose **Build** from the shortcut menu for your project (or press **Ctrl**+**Shift**+**B**).</span></span>

## <a name="install-the-service"></a><span data-ttu-id="133c3-235">安装服务</span><span class="sxs-lookup"><span data-stu-id="133c3-235">Install the service</span></span>

<span data-ttu-id="133c3-236">由于已经生成了 Windows 服务，你现在可以安装它。</span><span class="sxs-lookup"><span data-stu-id="133c3-236">Now that you've built the Windows service, you can install it.</span></span> <span data-ttu-id="133c3-237">要安装 Windows 服务，必须在安装它的计算机上拥有管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="133c3-237">To install a Windows service, you must have administrator credentials on the computer where it's installed.</span></span>

1. <span data-ttu-id="133c3-238">使用管理凭据打开[“Visual Studio 开发人员命令提示”](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs)。</span><span class="sxs-lookup"><span data-stu-id="133c3-238">Open [Developer Command Prompt for Visual Studio](https://docs.microsoft.com/dotnet/framework/tools/developer-command-prompt-for-vs) with administrative credentials.</span></span> <span data-ttu-id="133c3-239">从 Windows“开始”菜单中，在 Visual Studio 文件夹中选择“VS 2017 的开发人员命令提示”，然后从快捷菜单中选择“更多” > “以管理员身份运行”。</span><span class="sxs-lookup"><span data-stu-id="133c3-239">From the Windows **Start** menu, select **Developer Command Prompt for VS 2017** in the Visual Studio folder, then select **More** > **Run as Administrator** from the shortcut menu.</span></span>

2. <span data-ttu-id="133c3-240">在“Visual Studio 的开发人员命令提示”窗口中，导航到包含项目输出的文件夹（默认情况下，它是项目的 \bin\Debug 子目录）。</span><span class="sxs-lookup"><span data-stu-id="133c3-240">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output (by default, the *\bin\Debug* subdirectory of your project).</span></span>

3. <span data-ttu-id="133c3-241">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="133c3-241">Enter the following command:</span></span>

    ```shell
    installutil MyNewService.exe
    ```

    <span data-ttu-id="133c3-242">如果服务成功安装，该命令将报告成功。</span><span class="sxs-lookup"><span data-stu-id="133c3-242">If the service installs successfully, the command reports success.</span></span> 

    <span data-ttu-id="133c3-243">如果系统找不到 installutil.exe，请确保你的计算机上存在该安装程序。</span><span class="sxs-lookup"><span data-stu-id="133c3-243">If the system can't find *installutil.exe*, make sure that it exists on your computer.</span></span> <span data-ttu-id="133c3-244">此工具随 .NET Framework 安装在 %windir%\Microsoft.NET\Framework[64]\\&lt;framework version&gt; 文件夹下。</span><span class="sxs-lookup"><span data-stu-id="133c3-244">This tool is installed with the .NET Framework to the folder *%windir%\Microsoft.NET\Framework[64]\\&lt;framework version&gt;*.</span></span> <span data-ttu-id="133c3-245">例如，64 位版本的默认路径是 %windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe。</span><span class="sxs-lookup"><span data-stu-id="133c3-245">For example, the default path for the 64-bit version is *%windir%\Microsoft.NET\Framework64\v4.0.30319\InstallUtil.exe*.</span></span>

    <span data-ttu-id="133c3-246">如果“installutil.exe”进程失败，请查看安装日志以找出原因。</span><span class="sxs-lookup"><span data-stu-id="133c3-246">If the **installutil.exe** process fails, check the install log to find out why.</span></span> <span data-ttu-id="133c3-247">默认情况下，该日志与服务可执行文件位于同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="133c3-247">By default, the log is in the same folder as the service executable.</span></span> <span data-ttu-id="133c3-248">在以下情况下安装可能会失败：</span><span class="sxs-lookup"><span data-stu-id="133c3-248">The installation can fail if:</span></span> 
    - <span data-ttu-id="133c3-249">`ProjectInstaller` 类中不存在 <xref:System.ComponentModel.RunInstallerAttribute> 类。</span><span class="sxs-lookup"><span data-stu-id="133c3-249">The <xref:System.ComponentModel.RunInstallerAttribute> class isn't present on the `ProjectInstaller` class.</span></span>
    -  <span data-ttu-id="133c3-250">该属性未设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="133c3-250">The attribute isn't set to `true`.</span></span> 
    - <span data-ttu-id="133c3-251">`ProjectInstaller` 类未定义为 `public`。</span><span class="sxs-lookup"><span data-stu-id="133c3-251">The `ProjectInstaller` class isn't defined as `public`.</span></span>

<span data-ttu-id="133c3-252">有关详细信息，请参阅[如何：安装和卸载服务](how-to-install-and-uninstall-services.md)。</span><span class="sxs-lookup"><span data-stu-id="133c3-252">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="start-and-run-the-service"></a><span data-ttu-id="133c3-253">启动并运行服务</span><span class="sxs-lookup"><span data-stu-id="133c3-253">Start and run the service</span></span>

1. <span data-ttu-id="133c3-254">在 Windows 中，打开“服务”桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="133c3-254">In Windows, open the **Services** desktop app.</span></span> <span data-ttu-id="133c3-255">按“Windows 徽标键+R”以打开“运行”框，然后输入 services.msc 并按 Enter 或单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="133c3-255">Press **Windows**+**R** to open the **Run** box, enter *services.msc*, and then press **Enter** or select **OK**.</span></span>

     <span data-ttu-id="133c3-256">你会看到“服务”中列出的服务按其设置的显示名称的字母顺序显示。</span><span class="sxs-lookup"><span data-stu-id="133c3-256">You should see your service listed in **Services**, displayed alphabetically by the display name that you set for it.</span></span>

     ![服务窗口中的 MyNewService](media/windowsservices-serviceswindow.PNG)

2. <span data-ttu-id="133c3-258">若要启动该服务，请从服务的快捷菜单中选择“启动”。</span><span class="sxs-lookup"><span data-stu-id="133c3-258">To start the service, choose **Start** from the service's shortcut menu.</span></span>

3. <span data-ttu-id="133c3-259">若要停止该服务，请从服务的快捷菜单中选择“停止”。</span><span class="sxs-lookup"><span data-stu-id="133c3-259">To stop the service, choose **Stop** from the service's shortcut menu.</span></span>

4. <span data-ttu-id="133c3-260">（可选）可在命令行使用“net start&lt;服务名称&gt;”和“net stop&lt;服务名称&gt;”来启动和停止服务。</span><span class="sxs-lookup"><span data-stu-id="133c3-260">(Optional) From the command line, use the commands **net start &lt;service name&gt;** and **net stop &lt;service name&gt;** to start and stop your service.</span></span>

### <a name="verify-the-event-log-output-of-your-service"></a><span data-ttu-id="133c3-261">验证服务的事件日志输出</span><span class="sxs-lookup"><span data-stu-id="133c3-261">Verify the event log output of your service</span></span>

1. <span data-ttu-id="133c3-262">在 Windows 中，打开“事件查看器”桌面应用。</span><span class="sxs-lookup"><span data-stu-id="133c3-262">In Windows, open the **Event Viewer** desktop app.</span></span> <span data-ttu-id="133c3-263">在 Windows 搜索栏中输入事件查看器，然后从搜索结果中选择“事件查看器”。</span><span class="sxs-lookup"><span data-stu-id="133c3-263">Enter *Event Viewer* in the Windows search bar, and then select **Event Viewer** from the search results.</span></span>

   > [!TIP]
   > <span data-ttu-id="133c3-264">在 Visual Studio 中，可通过从“查看”菜单（或按 Ctrl+Alt+S）打开“服务器资源管理器”并展开本地计算机的“事件日志”节点来访问事件日志。</span><span class="sxs-lookup"><span data-stu-id="133c3-264">In Visual Studio, you can access event logs by opening **Server Explorer** from the **View** menu (or press **Ctrl**+**Alt**+**S**) and expanding the **Event Logs** node for the local computer.</span></span>

2. <span data-ttu-id="133c3-265">在“事件查看器”中，展开“应用程序和服务日志”。</span><span class="sxs-lookup"><span data-stu-id="133c3-265">In **Event Viewer**, expand **Applications and Services Logs**.</span></span>

3. <span data-ttu-id="133c3-266">找到“MyNewLog”（如果按照过程来添加命令行参数，则找到“MyLogFile1”）列表并将其展开。</span><span class="sxs-lookup"><span data-stu-id="133c3-266">Locate the listing for **MyNewLog** (or **MyLogFile1** if you followed the procedure to add command-line arguments) and expand it.</span></span> <span data-ttu-id="133c3-267">你会看到你的服务所执行的两个操作（启动和停止）的条目。</span><span class="sxs-lookup"><span data-stu-id="133c3-267">You should see the entries for the two actions (start and stop) that your service performed.</span></span>

     ![使用事件查看器查看事件日志条目](media/windows-service-event-viewer.png)

## <a name="clean-up-resources"></a><span data-ttu-id="133c3-269">清理资源</span><span class="sxs-lookup"><span data-stu-id="133c3-269">Clean up resources</span></span>

<span data-ttu-id="133c3-270">如果不再需要 Windows 服务应用，则可以将其删除。</span><span class="sxs-lookup"><span data-stu-id="133c3-270">If you no longer need the Windows service app, you can remove it.</span></span> 

1. <span data-ttu-id="133c3-271">使用管理凭据打开 **“Visual Studio 开发人员命令提示”**。</span><span class="sxs-lookup"><span data-stu-id="133c3-271">Open **Developer Command Prompt for Visual Studio** with administrative credentials.</span></span>

2. <span data-ttu-id="133c3-272">在“Visual Studio 的开发人员命令提示”窗口中，导航到包含项目输出的文件夹。</span><span class="sxs-lookup"><span data-stu-id="133c3-272">In the **Developer Command Prompt for Visual Studio** window, navigate to the folder that contains your project's output.</span></span>

3. <span data-ttu-id="133c3-273">输入以下命令：</span><span class="sxs-lookup"><span data-stu-id="133c3-273">Enter the following command:</span></span>

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   <span data-ttu-id="133c3-274">如果服务成功卸载，该命令将报告已成功删除服务。</span><span class="sxs-lookup"><span data-stu-id="133c3-274">If the service uninstalls successfully, the command reports that your service was successfully removed.</span></span> <span data-ttu-id="133c3-275">有关详细信息，请参阅[如何：安装和卸载服务](how-to-install-and-uninstall-services.md)。</span><span class="sxs-lookup"><span data-stu-id="133c3-275">For more information, see [How to: Install and uninstall services](how-to-install-and-uninstall-services.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="133c3-276">后续步骤</span><span class="sxs-lookup"><span data-stu-id="133c3-276">Next steps</span></span>

<span data-ttu-id="133c3-277">创建服务后，现在可以：</span><span class="sxs-lookup"><span data-stu-id="133c3-277">Now that you've created the service, you can:</span></span>

- <span data-ttu-id="133c3-278">为其他人创建一个独立的安装程序，用于安装 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="133c3-278">Create a standalone setup program for others to use to install your Windows service.</span></span> <span data-ttu-id="133c3-279">使用 [WiX 工具集](http://wixtoolset.org/)为 Windows 服务创建安装程序。</span><span class="sxs-lookup"><span data-stu-id="133c3-279">Use the [WiX Toolset](http://wixtoolset.org/) to create an installer for a Windows service.</span></span> <span data-ttu-id="133c3-280">有关其他提示，请参阅[创建安装程序包](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)。</span><span class="sxs-lookup"><span data-stu-id="133c3-280">For other ideas, see [Create an installer package](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop).</span></span>

- <span data-ttu-id="133c3-281">探索 <xref:System.ServiceProcess.ServiceController> 组件，以便将命令发送到已安装的服务。</span><span class="sxs-lookup"><span data-stu-id="133c3-281">Explore the <xref:System.ServiceProcess.ServiceController> component, which enables you to send commands to the service you've installed.</span></span>

- <span data-ttu-id="133c3-282">不是在应用程序运行时创建事件日志，而是在安装应用程序时使用安装程序创建事件日志。</span><span class="sxs-lookup"><span data-stu-id="133c3-282">Instead of creating the event log when the application runs, use an installer to create an event log when you install the application.</span></span> <span data-ttu-id="133c3-283">卸载应用程序时，安装程序将删除事件日志。</span><span class="sxs-lookup"><span data-stu-id="133c3-283">The event log is deleted by the installer when you uninstall the application.</span></span> <span data-ttu-id="133c3-284">有关更多信息，请参见<xref:System.Diagnostics.EventLogInstaller>。</span><span class="sxs-lookup"><span data-stu-id="133c3-284">For more information, see <xref:System.Diagnostics.EventLogInstaller>.</span></span>

## <a name="see-also"></a><span data-ttu-id="133c3-285">请参阅</span><span class="sxs-lookup"><span data-stu-id="133c3-285">See also</span></span>

- [<span data-ttu-id="133c3-286">Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="133c3-286">Windows service applications</span></span>](index.md)
- [<span data-ttu-id="133c3-287">Windows 服务应用程序简介</span><span class="sxs-lookup"><span data-stu-id="133c3-287">Introduction to Windows service applications</span></span>](introduction-to-windows-service-applications.md)
- [<span data-ttu-id="133c3-288">如何：调试 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="133c3-288">How to: Debug Windows service applications</span></span>](how-to-debug-windows-service-applications.md)
- [<span data-ttu-id="133c3-289">服务 (Windows)</span><span class="sxs-lookup"><span data-stu-id="133c3-289">Services (Windows)</span></span>](/windows/desktop/Services/services)
