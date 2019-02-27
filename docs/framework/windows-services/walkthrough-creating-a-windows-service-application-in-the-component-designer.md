---
title: 在 Visual Studio 中创建 Windows 服务应用程序
ms.date: 09/10/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows service applications, walkthroughs
- Windows service applications, creating
ms.assetid: e24d8a3d-edc6-485c-b6e0-5672d91fb607
author: ghogen
ms.openlocfilehash: 52c2f64bbb71e07dcab1fd7cd42662f9ed2c8445
ms.sourcegitcommit: 2b986afe4ce9e13bbeec929c9737757eb61de60e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "56665025"
---
# <a name="walkthrough-create-a-windows-service-app"></a>演练：创建 Windows 服务应用

本文演示了如何在 Visual Studio 中创建可向事件日志中写入消息的简单 Windows 服务应用程序。

## <a name="create-a-service"></a>创建服务

首先，创建项目并设置服务正常运行所必需的值。

1. 在 Visual Studio 中，在菜单栏上选择“文件” > “新建” > “项目”（或按 **Ctrl**+**Shift**+**N**）以打开“新建项目”对话框。

2. 导航到并选择“Windows 服务”项目模板。 展开“已安装”> [Visual C# 或 Visual Basic] >“Windows 桌面”，或在右上角的搜索框中键入“Windows 服务”。

   ![Visual Studio“新建项目”对话框中的“Windows 服务”模板](media/new-project-dialog.png)

   > [!NOTE]
   > 如果未看到“Windows 服务”模板，则可能需要安装“.NET 桌面开发”工作负荷。 在“新建项目”对话框中，单击左下角指示“打开 Visual Studio 安装程序”的链接。 在“Visual Studio 安装程序”中，选择“.NET 桌面开发”工作负荷，然后选择“修改”。

3. 将项目命名为 **MyNewService**，然后选择“确定”。

   项目模板包括从 <xref:System.ServiceProcess.ServiceBase?displayProperty=nameWithType> 继承的名为 `Service1` 的组件类。 它包括许多基本服务代码，例如用于启动服务的代码。

## <a name="rename-the-service"></a>对服务进行重命名

将服务从 **Service1** 重命名为 **MyNewService**。

1. 在 Service1.cs（或 Service1.vb）的“设计”视图中，单击要切换到代码视图的链接。 右键单击 **Service1**，然后从上下文菜单中选择“重命名”。 输入 **MyNewService**，然后按 **Enter** 或单击“应用”。

2. 在 **Service1.cs [Design]** 或 **Service1.vb [Design]** 的“属性”窗口中，将 **ServiceName** 值更改为 **MyNewService**。

3. 在“解决方案资源管理器”中，将 **Service1.cs** 重命名为 **MyNewService.cs**，或将 **Service1.vb** 重命名为 **MyNewService.vb**。

## <a name="add-features-to-the-service"></a>向服务添加功能

在本节中，你会添加自定义事件日志到 Windows 服务。 事件日志与 Windows 服务没有任何形式的关联。 此处，<xref:System.Diagnostics.EventLog> 组件用作可以添加到 Windows 服务的组件类型的示例。

### <a name="add-custom-event-log-functionality"></a>添加自定义事件日志功能

1. 在 **“解决方案资源管理器”** 中，打开 **MyNewService.cs** 或 **MyNewService.vb**的上下文菜单，然后选择 **“查看设计器”**。

2. 从 **工具箱** 的 **“组件”** 部分，将 <xref:System.Diagnostics.EventLog> 组件拖动到设计器中。

3. 在 **“解决方案资源管理器”** 中，打开 **MyNewService.cs** 或 **MyNewService.vb**的上下文菜单，然后选择 **“查看代码”**。

4. 编辑构造函数以定义自定义事件日志：

   ```csharp
   public MyNewService()
   {
        InitializeComponent();

        eventLog1 = new System.Diagnostics.EventLog();
        if (!System.Diagnostics.EventLog.SourceExists("MySource"))
        {
            System.Diagnostics.EventLog.CreateEventSource(
                "MySource", "MyNewLog");
        }
        eventLog1.Source = "MySource";
        eventLog1.Log = "MyNewLog";
    }
   ```

   [!code-vb[VbRadconService#2](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#2)]

### <a name="define-what-occurs-when-the-service-starts"></a>定义服务启动时发生的情况

在代码编辑器中，找到你创建项目时自动改写的 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法。 添加一行代码，以在服务启动时向事件日志写入一个条目：

[!code-csharp[VbRadconService#3](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#3)]
[!code-vb[VbRadconService#3](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#3)]

服务应用程序设计为长时间运行的，所以它通常轮询或监视系统中的情况。 监视是在 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法中设置的。 但是， <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 实际上不进行监视。 服务的操作开始之后， <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法必须返回到操作系统。 它不能始终循环或阻止。 若要设置简单的轮询机制，你可以使用 <xref:System.Timers.Timer?displayProperty=nameWithType> 组件，如下所示：在 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法中，在组件上设置参数，然后将 <xref:System.Timers.Timer.Enabled%2A> 属性设置为 `true`。 计时器定期在你的代码中引发事件，此时你的服务可以进行监视。 你可以使用以下代码来执行该操作：

```csharp
// Set up a timer that triggers every minute.
System.Timers.Timer timer = new System.Timers.Timer();
timer.Interval = 60000; // 60 seconds
timer.Elapsed += new System.Timers.ElapsedEventHandler(this.OnTimer);
timer.Start();
```

```vb
' Set up a timer that triggers every minute.
Dim timer As System.Timers.Timer = New System.Timers.Timer()
timer.Interval = 60000 ' 60 seconds
AddHandler timer.Elapsed, AddressOf Me.OnTimer
timer.Start()
```

向类添加一个成员变量。 它包含下一个要写入事件日志的事件的标识符。

```csharp
private int eventId = 1;
```

```vb
Private eventId As Integer = 1
```

添加新方法来处理计时器事件：

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

你可能需要使用后台辅助线程来执行任务，而不是在主线程上运行所有工作。 有关更多信息，请参见<xref:System.ComponentModel.BackgroundWorker?displayProperty=fullName>。

### <a name="define-what-occurs-when-the-service-is-stopped"></a>定义服务停止时发生的情况

向 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法添加一行代码，以在服务停止时向事件日志添加一个条目：

```csharp
eventLog1.WriteEntry("In OnStop.");
```

[!code-vb[VbRadconService#4](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#4)]

### <a name="define-other-actions-for-the-service"></a>定义服务的其他操作

可以重写 <xref:System.ServiceProcess.ServiceBase.OnPause%2A>、<xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnShutdown%2A> 方法来定义对组件的其他处理。 下列代码显示你可如何改写 <xref:System.ServiceProcess.ServiceBase.OnContinue%2A> 方法：

[!code-csharp[VbRadconService#5](../../../samples/snippets/csharp/VS_Snippets_VBCSharp/VbRadconService/CS/MyNewService.cs#5)]
[!code-vb[VbRadconService#5](../../../samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbRadconService/VB/MyNewService.vb#5)]

<xref:System.Configuration.Install.Installer> 类安装 Windows 服务后，需要发生一些自定义操作。 Visual Studio 可以专门为 Windows 服务创建这些安装程序并将它们添加到项目中。

## <a name="set-service-status"></a>设置服务状态

服务向服务控制管理器报告其状态，以便用户可以判断服务是否运行正常。 默认情况下，从 <xref:System.ServiceProcess.ServiceBase> 继承的服务会报告有限的状态设置，包括已停止、已暂停和正在运行。 如果服务启动所需的时间很短，则可能对报告“启动挂起”状态有帮助。 也可通过添加调入 Windows [SetServiceStatus 函数](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus)的代码来实现“启动挂起”和“停止挂起”状态设置。

实现服务挂起状态：

1. 将 `using` 语句或 `Imports` 声明添加到 MyNewService.cs 或 MyNewService.vb 文件中的 <xref:System.Runtime.InteropServices?displayProperty=nameWithType> 命名空间：

    ```csharp
    using System.Runtime.InteropServices;
    ```

    ```vb
    Imports System.Runtime.InteropServices
    ```

2. 添加以下代码到 MyNewService.cs 以声明 `ServiceState` 值和添加你将在平台调用中使用的状态结构：

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

3. 现在，在 `MyNewService` 类中，使用[平台调用](../interop/consuming-unmanaged-dll-functions.md)声明 [SetServiceStatus 函数](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus)：

    ```csharp
    [DllImport("advapi32.dll", SetLastError = true)]
    private static extern bool SetServiceStatus(System.IntPtr handle, ref ServiceStatus serviceStatus);
    ```

    ```vb
    Declare Auto Function SetServiceStatus Lib "advapi32.dll" (ByVal handle As IntPtr, ByRef serviceStatus As ServiceStatus) As Boolean
    ```

4. 若要实现“启动挂起”状态，请添加下列代码到 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法的开头：

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

5. 在 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 方法的末尾添加代码以将状态设置为“正在运行”。

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

6. （可选）针对 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法重复此过程。

> [!NOTE]
> [服务控制管理器](/windows/desktop/Services/service-control-manager)使用 [SERVICE_STATUS 结构](/windows/desktop/api/winsvc/ns-winsvc-_service_status)的 `dwWaitHint` 和 `dwCheckpoint` 成员来确定等待 Windows 服务启动或关闭所需的时间。 如果你的 <xref:System.ServiceProcess.ServiceBase.OnStart%2A> 和 <xref:System.ServiceProcess.ServiceBase.OnStop%2A> 方法运行时间较长，服务可以使用递增的 `dwCheckPoint` 值再次调用 [SetServiceStatus](/windows/desktop/api/winsvc/nf-winsvc-setservicestatus) 来请求更多时间。

## <a name="add-installers-to-the-service"></a>向服务添加安装程序

你需要先安装 Windows 服务然后才能运行，这会将其注册到服务控制管理器。 你可以将安装程序添加到处理注册详细信息的项目。

1. 在 **“解决方案资源管理器”** 中，打开 **MyNewService.cs** 或 **MyNewService.vb**的上下文菜单，然后选择 **“查看设计器”**。

2. 单击设计器的背景以选择服务本身，而不是它的任何内容。

3. 打开设计器窗口的上下文菜单（如果使用指针设备，在窗口中右键单击），然后选择 **“添加安装程序”**。

   默认情况下，向你的项目添加一个包含两个安装程序的组件类。 将该组件命名为 **ProjectInstaller**，它包含的安装程序分别是服务的安装程序和服务关联进程的安装程序。

4. 在 **ProjectInstaller** 的 **“设计”** 视图中，选择 **serviceInstaller1** （对于 Visual C# 项目）或 **ServiceInstaller1** （对于 Visual Basic 项目）。

5. 在“属性”  窗口中，确保 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 属性已设置为 **MyNewService**。

6. 将 **“描述”** 属性设置为一些文本，比如“示例服务”。 该文本会显示在“服务”窗口中，帮助用户标识服务并理解其用处。

7. 在 <xref:System.ServiceProcess.ServiceInstaller.DisplayName%2A> “名称” **列中将** 属性设置为你想要显示在“服务”窗口中的文本。 例如，你可以输入“MyNewService 显示名称”。 该名称可以不同于 <xref:System.ServiceProcess.ServiceInstaller.ServiceName%2A> 属性，它是系统使用的名称（例如，当你使用 `net start` 命令启动服务时）。

8. 将 <xref:System.ServiceProcess.ServiceInstaller.StartType%2A> 属性设置为 <xref:System.ServiceProcess.ServiceStartMode.Automatic>。

     ![Windows 服务的安装程序属性](../../../docs/framework/windows-services/media/windowsservice-installerproperties.PNG "WindowsService_InstallerProperties")

9. 在设计器中，选择 **serviceProcessInstaller1** （对于 Visual C# 项目）或 **ServiceProcessInstaller1** （对于 Visual Basic 项目）。 将 <xref:System.ServiceProcess.ServiceProcessInstaller.Account%2A> 属性设置为 <xref:System.ServiceProcess.ServiceAccount.LocalSystem>。 这会导致安装该服务并使用本地系统帐户运行服务。

    > [!IMPORTANT]
    > <xref:System.ServiceProcess.ServiceAccount.LocalSystem> 帐户具有广泛的权限，包括能够写入事件日志。 使用此帐户时要特别小心，因为它会增加你受到恶意软件攻击的风险。 对于其他任务，请考虑使用 <xref:System.ServiceProcess.ServiceAccount.LocalService> 帐户，该帐户用作本地计算机上的非特权用户，并向任意远程服务器提供匿名凭据。 如果你尝试使用 <xref:System.ServiceProcess.ServiceAccount.LocalService> 账户，此例子将失败，因为它需要写入事件日志的权限。

有关安装程序的详细信息，请参阅[如何：将安装程序添加到服务应用程序](../../../docs/framework/windows-services/how-to-add-installers-to-your-service-application.md)。

## <a name="optional-set-startup-parameters"></a>（可选）设置启动参数

Windows 服务像任何其他可执行文件一样，可以接受命令行参数或启动参数。 添加代码到进程启动参数后，用户可以使用 Windows 控制面板中的“服务”窗口，用他们自己的自定义启动参数启动你的服务。 但是，这些启动参数不会保留到下一次服务启动。 若要永久性设置启动参数，你可以按此步骤所示，在注册表中对它们进行设置。

> [!NOTE]
> 在你决定添加启动参数前，考虑这是否是向你的服务传递信息的最好办法。 虽然启动参数易于使用和分析，而且用户可以轻松地改写它们，但是如果没有相关的文档说明，用户可能较难发现和使用它们。 通常情况下，如果你的服务需要不止几个启动参数，你应该考虑改为使用注册表或配置文件。 每个 Windows 服务都在 **HKLM\System\CurrentControlSet\services** 下有注册表项。 在服务的项下，你可以使用 **“参数”** 子项存储你的服务能访问的信息。 你可以使用 Windows 服务的应用程序配置文件，与使用其他类型的程序一样。 有关示例代码，请参阅 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>。

添加启动参数：

1. 在 Program.cs 或 MyNewService.Designer.vb 的 `Main` 方法中，添加要传递到服务构造函数的输入参数：

   ```csharp
   static void Main(string[] args)
   {
       ServiceBase[] ServicesToRun;
       ServicesToRun = new ServiceBase[]
       {
           new MyNewService(args)
       };
       ServiceBase.Run(ServicesToRun);
   }
   ```

   ```vb
   Shared Sub Main(ByVal cmdArgs() As String)
       Dim ServicesToRun() As System.ServiceProcess.ServiceBase = New System.ServiceProcess.ServiceBase() {New MyNewServiceVB(cmdArgs)}
       System.ServiceProcess.ServiceBase.Run(ServicesToRun)
   End Sub
   ```

2. 按如下所示更改 `MyNewService` 构造函数：

   ```csharp
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

   此代码根据提供的启动参数设置事件源和日志名称，或者如果没有提供参数就使用默认值。

3. 若要指定命令行参数，请将下列代码添加到 ProjectInstaller.cs 或 ProjectInstaller.vb 的 `ProjectInstaller` 类中：

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

   此代码会通过添加默认参数值修改 **ImagePath** 注册表项，该注册表项通常包含 Windows 服务可执行文件的完整路径。 要正常启动服务需要使用引号将路径括起来（包围括住每个参数）。 若要更改该 Windows 服务的启动参数，用户可以更改 **ImagePath** 注册表项中给定的参数，然而更好的方式是以编程方式对其进行更改，并以友好的方式（例如，在管理或配置实用工具中）向用户公开功能。

## <a name="build-the-service"></a>生成服务

1. 在 **“解决方案资源管理器”** 中，打开项目的上下文菜单，然后选择 **“属性”**。

   项目的属性页面会显示出来。

2. 在“应用程序”选项卡上，在“启动对象”列表中，选择 **MyNewService.Program**。

3. 在“解决方案资源管理器”中，打开项目的上下文菜单，然后选择“生成”以生成项目（或按 **Ctrl**+**Shift**+**B**）。

## <a name="install-the-service"></a>安装服务

由于已经生成了 Windows 服务，你现在可以安装它。 若要安装 Windows 服务，你必须在要安装此服务的计算机上拥有管理员凭据。

1. 使用管理凭据打开“Visual Studio 开发人员命令提示”。 如果使用鼠标，在 Windows“开始”菜单中右键单击“VS 2017 开发人员命令提示”，然后选择“更多” > “以管理员身份运行”。

2. 在“开发人员命令提示”窗口中，导航到包含项目输出的文件夹（默认情况下，它是项目的 *\bin\Debug* 子目录）。

3. 输入以下命令：

    ```shell
    installutil.exe MyNewService.exe
    ```

    如果服务成功安装，**installutil.exe** 将报告成功。 如果系统找不到 **InstallUtil.exe**，请确保它存在于你的计算机上。 此工具随 .NET Framework 安装在 *%windir%\Microsoft.NET\Framework[64]\\[framework version]* 文件夹下。 例如，32 位版本的默认路径是 *%windir%\Microsoft.NET\Framework\v4.0.30319\InstallUtil.exe*。

    如果 **installutil.exe** 进程报告失败，请查看安装日志以找出原因。 默认情况下，该日志与服务可执行文件位于同一文件夹中。 如果 `ProjectInstaller` 类上不存在 <xref:System.ComponentModel.RunInstallerAttribute> 类、该属性未设置为 **true**，或者 `ProjectInstaller` 类不标记为 **public**，则安装可能失败。

有关详细信息，请参阅[如何：安装和卸载服务](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。

## <a name="start-and-run-the-service"></a>启动并运行服务

1. 在 Windows 中，打开“服务”桌面应用程序。 按 **Windows**+**R** 以打开“运行”框，然后输入 **services.msc** 并按 **Enter** 或单击“确定”。

     你会看到“服务”中列出的服务按其设置的显示名称的字母顺序显示。

     ![服务窗口中的 MyNewService](../../../docs/framework/windows-services/media/windowsservices-serviceswindow.PNG)

2. 在“服务”中，打开服务快捷菜单，然后选择“启动”。

3. 要停止服务，打开服务快捷菜单，然后选择“停止”。

4. （可选）你可以在命令行中使用 `net start ServiceName` 和 `net stop ServiceName` 命令来启动和停止服务。

### <a name="verify-the-event-log-output-of-your-service"></a>验证服务的事件日志输出

1. 通过开始在 Windows 任务栏上的搜索框中键入“事件查看器”并从搜索结果中选择“事件查看器”来打开“事件查看器”。

   > [!TIP]
   > 在 Visual Studio 中，若要访问事件日志，可以打开“服务器资源管理器”（键盘：Ctrl+Alt+S），然后展开本地计算机的“事件日志”节点。

2. 在“事件查看器”中，展开“应用程序和服务日志”。

3. 找到 **MyNewLog**（或 **MyLogFile1**，如果你使用了可选步骤来添加命令行参数）列表并将它展开。 你会看到你的服务所执行的两个操作（启动和停止）的条目。

     ![使用事件查看器查看事件日志条目](../../../docs/framework/windows-services/media/windows-service-event-viewer.png)

## <a name="uninstall-the-service"></a>卸载服务

1. 使用管理凭据打开“Visual Studio 开发人员命令提示”。

2. 在命令提示窗口中，导航到包含项目输出的文件夹。

3. 输入以下命令：

    ```shell
    installutil.exe /u MyNewService.exe
    ```

   如果服务成功卸载，**installutil.exe** 将报告已成功移除服务。 有关详细信息，请参阅[如何：安装和卸载服务](../../../docs/framework/windows-services/how-to-install-and-uninstall-services.md)。

## <a name="next-steps"></a>后续步骤

创建服务后，你可能希望创建一个独立安装程序，以供其他人安装你的 Windows 服务。 ClickOnce 不支持 Windows 服务，但你可以使用 [WiX 工具集](http://wixtoolset.org/)为 Windows 服务创建安装程序。 有关其他提示，请参阅[创建安装程序包](/visualstudio/deployment/deploying-applications-services-and-components#create-an-installer-package-windows-desktop)。

你可能会探索 <xref:System.ServiceProcess.ServiceController> 组件的用法，以便将命令发送到已安装的服务。

可以在安装应用程序时使用安装程序创建事件日志，而不是在运行应用程序时创建事件日志。 此外，在卸载应用程序时，事件日志将被安装程序删除。 有关详细信息，请参阅 <xref:System.Diagnostics.EventLogInstaller> 引用页。

## <a name="see-also"></a>请参阅

- [Windows 服务应用程序](../../../docs/framework/windows-services/index.md)
- [Windows 服务应用程序简介](../../../docs/framework/windows-services/introduction-to-windows-service-applications.md)
- [如何：调试 Windows 服务应用程序](../../../docs/framework/windows-services/how-to-debug-windows-service-applications.md)
- [服务 (Windows)](/windows/desktop/Services/services)
