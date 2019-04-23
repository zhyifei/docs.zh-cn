---
title: 如何：调试 Windows 服务应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- debugging Windows Service applications
- debugging [Visual Studio], Windows services
- Windows NT services, debugging
- Windows Service applications, debugging
- services, debugging
ms.assetid: 63ab0800-0f05-4f1e-88e6-94c73fd920a2
author: ghogen
ms.openlocfilehash: 1abb64f7d76b772168ed97024f5f1381670c6882
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59321440"
---
# <a name="how-to-debug-windows-service-applications"></a><span data-ttu-id="ce360-102">如何：调试 Windows 服务应用程序</span><span class="sxs-lookup"><span data-stu-id="ce360-102">How to: Debug Windows Service Applications</span></span>
<span data-ttu-id="ce360-103">必须从服务控制管理器的上下文中而不是 Visual Studio 中运行服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-103">A service must be run from within the context of the Services Control Manager rather than from within Visual Studio.</span></span> <span data-ttu-id="ce360-104">因此，调试服务不像调试其他 Visual Studio 应用程序类型一样简单。</span><span class="sxs-lookup"><span data-stu-id="ce360-104">For this reason, debugging a service is not as straightforward as debugging other Visual Studio application types.</span></span> <span data-ttu-id="ce360-105">要调试服务，必须启动该服务，然后将调试器附加到该服务正在其中运行的进程中。</span><span class="sxs-lookup"><span data-stu-id="ce360-105">To debug a service, you must start the service and then attach a debugger to the process in which it is running.</span></span> <span data-ttu-id="ce360-106">然后你可以使用所有 Visual Studio 的标准调试功能来调试你的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ce360-106">You can then debug your application by using all of the standard debugging functionality of Visual Studio.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="ce360-107">除非你知道该进程是什么进程并了解进行附加和可能终止该进程的后果，否则你不应该附加到进程。</span><span class="sxs-lookup"><span data-stu-id="ce360-107">You should not attach to a process unless you know what the process is and understand the consequences of attaching to and possibly killing that process.</span></span> <span data-ttu-id="ce360-108">例如，如果你附加到 WinLogon 进程然后停止调试，系统将停止，因为系统没有 WinLogon 无法运行。</span><span class="sxs-lookup"><span data-stu-id="ce360-108">For example, if you attach to the WinLogon process and then stop debugging, the system will halt because it can’t operate without WinLogon.</span></span>  
  
 <span data-ttu-id="ce360-109">你仅可将调试器附加到正在运行的服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-109">You can attach the debugger only to a running service.</span></span> <span data-ttu-id="ce360-110">附加过程会中断服务的当前运行；它实际不会停止或暂停服务的处理。</span><span class="sxs-lookup"><span data-stu-id="ce360-110">The attachment process interrupts the current functioning of your service; it doesn’t actually stop or pause the service's processing.</span></span> <span data-ttu-id="ce360-111">也就是说，如果当你开始调试时你的服务正在运行，在你调试它时它在技术上仍处于启动状态，但是它的处理已经挂起。</span><span class="sxs-lookup"><span data-stu-id="ce360-111">That is, if your service is running when you begin debugging, it is still technically in the Started state as you debug it, but its processing has been suspended.</span></span>  
  
 <span data-ttu-id="ce360-112">附加到进程后，你可以设置断点并使用它们来调试你的代码。</span><span class="sxs-lookup"><span data-stu-id="ce360-112">After attaching to the process, you can set breakpoints and use these to debug your code.</span></span> <span data-ttu-id="ce360-113">退出你用于附加到进程的对话框后，你实际上处于调试模式。</span><span class="sxs-lookup"><span data-stu-id="ce360-113">Once you exit the dialog box you use to attach to the process, you are effectively in debug mode.</span></span> <span data-ttu-id="ce360-114">你可以使用服务控制管理器来启动、停止、暂停和继续你的服务，从而命中你设置的断点。</span><span class="sxs-lookup"><span data-stu-id="ce360-114">You can use the Services Control Manager to start, stop, pause and continue your service, thus hitting the breakpoints you've set.</span></span> <span data-ttu-id="ce360-115">调试成功后，你可稍后删除该虚拟服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-115">You can later remove this dummy service after debugging is successful.</span></span>  
  
 <span data-ttu-id="ce360-116">本文介绍了调试在本地计算机上运行的服务，但你也可以调试在远程计算机上运行的 Windows 服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-116">This article covers debugging a service that's running on the local computer, but you can also debug Windows Services that are running on a remote computer.</span></span> <span data-ttu-id="ce360-117">请参阅[远程调试](/visualstudio/debugger/debug-installed-app-package)。</span><span class="sxs-lookup"><span data-stu-id="ce360-117">See [Remote Debugging](/visualstudio/debugger/debug-installed-app-package).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ce360-118">调试 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法会比较困难，因为服务控制管理器对所有启动服务的尝试施加了 30 秒的限制。</span><span class="sxs-lookup"><span data-stu-id="ce360-118">Debugging the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method can be difficult because the Services Control Manager imposes a 30-second limit on all attempts to start a service.</span></span> <span data-ttu-id="ce360-119">有关详细信息，请参阅[疑难解答：调试 Windows 服务](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ce360-119">For more information, see [Troubleshooting: Debugging Windows Services](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="ce360-120">若要获取有意义的调试信息，Visual Studio 调试器需要找到正在调试的二进制文件的符号文件。</span><span class="sxs-lookup"><span data-stu-id="ce360-120">To get meaningful information for debugging, the Visual Studio debugger needs to find symbol files for the binaries that are being debugged.</span></span> <span data-ttu-id="ce360-121">如果你正在调试你在 Visual Studio 中生成的服务，符号文件（.pdb 文件）就在与可执行文件或库相同的文件夹中，调试器会自动加载它们。</span><span class="sxs-lookup"><span data-stu-id="ce360-121">If you are debugging a service that you built in Visual Studio, the symbol files (.pdb files) are in the same folder as the executable or library, and the debugger loads them automatically.</span></span> <span data-ttu-id="ce360-122">如果你正在调试你没有生成过的服务，你应该首先查找该服务的符号文件，确保调试器可找到它们。</span><span class="sxs-lookup"><span data-stu-id="ce360-122">If you are debugging a service that you didn't build, you should first find symbols for the service and make sure they can be found by the debugger.</span></span> <span data-ttu-id="ce360-123">请参阅[在 Visual Studio 调试器中指定符号 (.pdb) 和源文件](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger)。</span><span class="sxs-lookup"><span data-stu-id="ce360-123">See [Specify Symbol (.pdb) and Source Files in the Visual Studio Debugger](/visualstudio/debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger).</span></span> <span data-ttu-id="ce360-124">如果你正在调试系统进程，或想要你的服务中的系统调用符号，你应该添加 Microsoft 符号服务器。</span><span class="sxs-lookup"><span data-stu-id="ce360-124">If you're debugging a system process or want to have symbols for system calls in your services, you should add the Microsoft Symbol Servers.</span></span> <span data-ttu-id="ce360-125">请参阅[调试符号](/windows/desktop/DxTechArts/debugging-with-symbols)。</span><span class="sxs-lookup"><span data-stu-id="ce360-125">See [Debugging Symbols](/windows/desktop/DxTechArts/debugging-with-symbols).</span></span>  
  
### <a name="to-debug-a-service"></a><span data-ttu-id="ce360-126">调试服务</span><span class="sxs-lookup"><span data-stu-id="ce360-126">To debug a service</span></span>  
  
1. <span data-ttu-id="ce360-127">在调试配置中生成你的服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-127">Build your service in the Debug configuration.</span></span>  
  
2. <span data-ttu-id="ce360-128">安装你的服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-128">Install your service.</span></span> <span data-ttu-id="ce360-129">有关详细信息，请参阅[如何：安装和卸载服务](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ce360-129">For more information, see [How to: Install and Uninstall Services](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md).</span></span>  
  
3. <span data-ttu-id="ce360-130">从“服务控制管理器”、“服务器资源管理器”或代码启动服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-130">Start your service, either from **Services Control Manager**, **Server Explorer**, or from code.</span></span> <span data-ttu-id="ce360-131">有关详细信息，请参阅[如何：启动服务](../../../docs/framework/windows-services/how-to-start-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ce360-131">For more information, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span>  
  
4. <span data-ttu-id="ce360-132">使用管理凭据启动 Visual Studio,那么你就能附加到系统进程。</span><span class="sxs-lookup"><span data-stu-id="ce360-132">Start Visual Studio with administrative credentials so you can attach to system processes.</span></span>  
  
5. <span data-ttu-id="ce360-133">（可选）在 Visual Studio 菜单栏上，选择“工具”、“选项”。</span><span class="sxs-lookup"><span data-stu-id="ce360-133">(Optional) On the Visual Studio menu bar, choose **Tools**, **Options**.</span></span> <span data-ttu-id="ce360-134">在“选项”对话框中，选择“调试”、“符号”，选择“Microsoft 符号服务器”复选框，然后选择“确定”按钮。</span><span class="sxs-lookup"><span data-stu-id="ce360-134">In the **Options** dialog box, choose **Debugging**, **Symbols**, select the **Microsoft Symbol Servers** check box, and then choose the **OK** button.</span></span>  
  
6. <span data-ttu-id="ce360-135">在菜单栏上，从“调试”或“工具”菜单选择“附加到进程”。</span><span class="sxs-lookup"><span data-stu-id="ce360-135">On the menu bar, choose **Attach to Process** from the **Debug** or **Tools** menu.</span></span> <span data-ttu-id="ce360-136">（键盘：Ctrl+Alt+P）</span><span class="sxs-lookup"><span data-stu-id="ce360-136">(Keyboard: Ctrl+Alt+P)</span></span>  
  
     <span data-ttu-id="ce360-137">这将显示“进程”对话框。</span><span class="sxs-lookup"><span data-stu-id="ce360-137">The **Processes** dialog box appears.</span></span>  
  
7. <span data-ttu-id="ce360-138">选择“显示所有用户的进程”复选框。</span><span class="sxs-lookup"><span data-stu-id="ce360-138">Select the **Show processes from all users** check box.</span></span>  
  
8. <span data-ttu-id="ce360-139">在“可用进程”部分,为服务选择进程，然后选择“附加”。</span><span class="sxs-lookup"><span data-stu-id="ce360-139">In the **Available Processes** section, choose the process for your service, and then choose **Attach**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="ce360-140">该进程的名称将与你的服务的可执行文件相同。</span><span class="sxs-lookup"><span data-stu-id="ce360-140">The process will have the same name as the executable file for your service.</span></span>  
  
     <span data-ttu-id="ce360-141">出现 **“附加到进程”** 对话框。</span><span class="sxs-lookup"><span data-stu-id="ce360-141">The **Attach to Process** dialog box appears.</span></span>  
  
9. <span data-ttu-id="ce360-142">选择相应的选项，然后选择“确定”以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="ce360-142">Choose the appropriate options, and then choose **OK** to close the dialog box.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="ce360-143">你现在处于调试模式。</span><span class="sxs-lookup"><span data-stu-id="ce360-143">You are now in debug mode.</span></span>  
  
10. <span data-ttu-id="ce360-144">设置任意你想要在代码中使用的断点。</span><span class="sxs-lookup"><span data-stu-id="ce360-144">Set any breakpoints you want to use in your code.</span></span>  
  
11. <span data-ttu-id="ce360-145">访问服务控制管理器并操作你的服务，发送停止、暂停和继续命令以命中你的断点。</span><span class="sxs-lookup"><span data-stu-id="ce360-145">Access the Services Control Manager and manipulate your service, sending stop, pause, and continue commands to hit your breakpoints.</span></span> <span data-ttu-id="ce360-146">有关运行服务控制管理器的详细信息，请参阅[如何：启动服务](../../../docs/framework/windows-services/how-to-start-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ce360-146">For more information about running the Services Control Manager, see [How to: Start Services](../../../docs/framework/windows-services/how-to-start-services.md).</span></span> <span data-ttu-id="ce360-147">请参见[疑难解答：调试 Windows 服务](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md)。</span><span class="sxs-lookup"><span data-stu-id="ce360-147">Also, see [Troubleshooting: Debugging Windows Services](../../../docs/framework/windows-services/troubleshooting-debugging-windows-services.md).</span></span>  
  
## <a name="debugging-tips-for-windows-services"></a><span data-ttu-id="ce360-148">Windows 服务的调试提示</span><span class="sxs-lookup"><span data-stu-id="ce360-148">Debugging Tips for Windows Services</span></span>  
 <span data-ttu-id="ce360-149">附加到服务的进程使你可调试该服务的大多数代码，但不是全部。</span><span class="sxs-lookup"><span data-stu-id="ce360-149">Attaching to the service's process allows you to debug most, but not all, the code for that service.</span></span> <span data-ttu-id="ce360-150">例如，由于服务已经启动，你无法调试服务的 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法中的代码或 `Main` 方法中用于在此处加载服务的代码。</span><span class="sxs-lookup"><span data-stu-id="ce360-150">For example, because the service has already been started, you cannot debug the code in the service's <xref:System.ServiceProcess.ServiceBase.OnStart%2A> method or the code in the `Main` method that is used to load the service this way.</span></span> <span data-ttu-id="ce360-151">避免这种限制的一种方法是在你的仅用于辅助调试的服务应用程序中创建一个临时辅助服务。</span><span class="sxs-lookup"><span data-stu-id="ce360-151">One way to work around this limitation is to create a temporary second service in your service application that exists only to aid in debugging.</span></span> <span data-ttu-id="ce360-152">你可以安装两个服务，然后启动该虚拟服务来加载服务进程。</span><span class="sxs-lookup"><span data-stu-id="ce360-152">You can install both services, and then start this dummy service to load the service process.</span></span> <span data-ttu-id="ce360-153">临时服务启动进程后，可以使用 Visual Studio 中的“调试”菜单来附加到服务进程。</span><span class="sxs-lookup"><span data-stu-id="ce360-153">Once the temporary service has started the process, you can use the **Debug** menu in Visual Studio to attach to the service process.</span></span>  
  
 <span data-ttu-id="ce360-154">尝试添加对 <xref:System.Threading.Thread.Sleep%2A> 方法的调用延迟操作，直到你能够附加到该进程。</span><span class="sxs-lookup"><span data-stu-id="ce360-154">Try adding calls to the <xref:System.Threading.Thread.Sleep%2A> method to delay action until you’re able to attach to the process.</span></span>  
  
 <span data-ttu-id="ce360-155">尝试更改常规控制台应用程序的程序。</span><span class="sxs-lookup"><span data-stu-id="ce360-155">Try changing the program to a regular console application.</span></span> <span data-ttu-id="ce360-156">为此，请按如下所示重写 `Main` 方法，这样它可以作为 Windows 服务和控制台应用程序运行，具体取决于启动方式。</span><span class="sxs-lookup"><span data-stu-id="ce360-156">To do this, rewrite the `Main` method as follows so it can run both as a Windows Service and as a console application, depending on how it's started.</span></span>  
  
#### <a name="how-to-run-a-windows-service-as-a-console-application"></a><span data-ttu-id="ce360-157">如何：将 Windows 服务作为控制台应用运行</span><span class="sxs-lookup"><span data-stu-id="ce360-157">How to: Run a Windows Service as a console application</span></span>  
  
1. <span data-ttu-id="ce360-158">向你运行 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法的服务添加一个方法：</span><span class="sxs-lookup"><span data-stu-id="ce360-158">Add a method to your service that runs the <xref:System.ServiceProcess.ServiceBase.OnStart%2A> and <xref:System.ServiceProcess.ServiceBase.OnStop%2A> methods:</span></span>  
  
    ```csharp  
    internal void TestStartupAndStop(string[] args)  
    {  
        this.OnStart(args);  
        Console.ReadLine();  
        this.OnStop();  
    }  
    ```  
  
2. <span data-ttu-id="ce360-159">按如下所示重写 `Main` 方法：</span><span class="sxs-lookup"><span data-stu-id="ce360-159">Rewrite the `Main` method as follows:</span></span>  
  
    ```csharp  
    static void Main(string[] args)  
    {  
        if (Environment.UserInteractive)  
        {  
            MyNewService service1 = new MyNewService(args);  
            service1.TestStartupAndStop(args);  
        }  
        else  
        {  
            // Put the body of your old Main method here.  
        }  
    }
    ```  
  
3. <span data-ttu-id="ce360-160">在项目属性的“应用程序”选项卡中，将“输出类型”设置为“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="ce360-160">In the **Application** tab of the project's properties, set the **Output type** to **Console Application**.</span></span>  
  
4. <span data-ttu-id="ce360-161">选择“启动调试”(F5)。</span><span class="sxs-lookup"><span data-stu-id="ce360-161">Choose **Start Debugging** (F5).</span></span>  
  
5. <span data-ttu-id="ce360-162">若要将该程序再次作为 Windows 服务运行，请安装它并像通常启动 Windows 服务一样启动它。</span><span class="sxs-lookup"><span data-stu-id="ce360-162">To run the program as a Windows Service again, install it and start it as usual for a Windows Service.</span></span> <span data-ttu-id="ce360-163">不必恢复这些更改。</span><span class="sxs-lookup"><span data-stu-id="ce360-163">It's not necessary to reverse these changes.</span></span>  
  
 <span data-ttu-id="ce360-164">在某些情况下，你必须使用 Windows 调试器，比如当你想要调试仅在系统启动时发生的问题时。</span><span class="sxs-lookup"><span data-stu-id="ce360-164">In some cases, such as when you want to debug an issue that occurs only on system startup, you have to use the Windows debugger.</span></span> <span data-ttu-id="ce360-165">[下载 Windows 驱动程序工具包 (WDK)](/windows-hardware/drivers/download-the-wdk)，并查看[如何调试 Windows 服务](https://support.microsoft.com/kb/824344)。</span><span class="sxs-lookup"><span data-stu-id="ce360-165">[Download the Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk) and see [How to debug Windows Services](https://support.microsoft.com/kb/824344).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce360-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="ce360-166">See also</span></span>

- [<span data-ttu-id="ce360-167">Windows 服务应用程序介绍</span><span class="sxs-lookup"><span data-stu-id="ce360-167">Introduction to Windows Service Applications</span></span>](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [<span data-ttu-id="ce360-168">如何：安装和卸载服务</span><span class="sxs-lookup"><span data-stu-id="ce360-168">How to: Install and Uninstall Services</span></span>](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)
- [<span data-ttu-id="ce360-169">如何：启动服务</span><span class="sxs-lookup"><span data-stu-id="ce360-169">How to: Start Services</span></span>](../../../docs/framework/windows-services/how-to-start-services.md)
- [<span data-ttu-id="ce360-170">调试服务</span><span class="sxs-lookup"><span data-stu-id="ce360-170">Debugging a Service</span></span>](/windows/desktop/Services/debugging-a-service)
