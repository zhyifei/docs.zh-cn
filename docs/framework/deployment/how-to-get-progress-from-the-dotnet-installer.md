---
title: 如何：获取 .NET Framework 4.5 安装程序的进度
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- progress information, .NET Framework installer
- .NET Framework, installing
ms.assetid: 0a1a3ba3-7e46-4df2-afd3-f3a8237e1c4f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bdb74259d7b034511722b1d2992b4ec16adb551e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64750436"
---
# <a name="how-to-get-progress-from-the-net-framework-45-installer"></a><span data-ttu-id="8875e-102">如何：获取 .NET Framework 4.5 安装程序的进度</span><span class="sxs-lookup"><span data-stu-id="8875e-102">How to: Get Progress from the .NET Framework 4.5 Installer</span></span>

<span data-ttu-id="8875e-103">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 是可再发行运行时。</span><span class="sxs-lookup"><span data-stu-id="8875e-103">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is a redistributable runtime.</span></span> <span data-ttu-id="8875e-104">如果开发基于此 .NET framework 版本的应用程序，则可以将（链）[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装程序作为必备组件包括在应用的安装程序中。</span><span class="sxs-lookup"><span data-stu-id="8875e-104">If you develop apps for this version of the .NET Framework, you can include (chain) [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup as a prerequisite part of your app's setup.</span></span> <span data-ttu-id="8875e-105">若要提供自定义或统一的安装体验，可能需要以无提示方式启动 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装程序并跟踪其进度，同时显示应用的安装进度。</span><span class="sxs-lookup"><span data-stu-id="8875e-105">To present a customized or unified setup experience, you may want to silently launch [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup and track its progress while showing your app's setup progress.</span></span> <span data-ttu-id="8875e-106">若要启用无提示跟踪，[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装程序（可观察）通过使用内存映射 I/O (MMIO) 段来定义协议，以便与安装程序（观察程序或链接器）进行通信。</span><span class="sxs-lookup"><span data-stu-id="8875e-106">To enable silent tracking, [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup (which can be watched) defines a protocol by using a memory-mapped I/O (MMIO) segment to communicate with your setup (the watcher or chainer).</span></span> <span data-ttu-id="8875e-107">此协议定义链接器获取进度信息、详细结果，响应消息和取消 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装的方式。</span><span class="sxs-lookup"><span data-stu-id="8875e-107">This protocol defines a way for a chainer to obtain progress information, get detailed results, respond to messages, and cancel the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup.</span></span>

- <span data-ttu-id="8875e-108">**调用**。</span><span class="sxs-lookup"><span data-stu-id="8875e-108">**Invocation**.</span></span> <span data-ttu-id="8875e-109">若要调用 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装程序并接收来自 MMIO 节的进度信息，安装程序必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8875e-109">To call [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup and receive progress information from the MMIO section, your setup program must do the following:</span></span>

    1. <span data-ttu-id="8875e-110">调用 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 可再发行程序：</span><span class="sxs-lookup"><span data-stu-id="8875e-110">Call the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]redistributable program:</span></span>

        ```
        dotNetFx45_Full_x86_x64.exe /q /norestart /pipe section-name
        ```

        <span data-ttu-id="8875e-111">其中“section name”是要用来标识应用的任意名称。</span><span class="sxs-lookup"><span data-stu-id="8875e-111">Where *section name* is any name you want to use to identify your app.</span></span> <span data-ttu-id="8875e-112">.NET Framework 安装程序以异步方式在 MMIO 节进行读写，因此可能会发现在此期间使用事件和消息很方便。</span><span class="sxs-lookup"><span data-stu-id="8875e-112">.NET Framework setup reads and writes to the MMIO section asynchronously, so you might find it convenient to use events and messages during that time.</span></span> <span data-ttu-id="8875e-113">在示例中，.NET Framework 安装进程由分配 MMIO 节 (`TheSectionName`) 和定义事件 (`TheEventName`) 的构造函数创建：</span><span class="sxs-lookup"><span data-stu-id="8875e-113">In the example, the .NET Framework setup process is created by a constructor that both allocates the MMIO section (`TheSectionName`) and defines an event (`TheEventName`):</span></span>

        ```
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName")
        ```

        <span data-ttu-id="8875e-114">请使用对于安装程序唯一的名称替换这些名称。</span><span class="sxs-lookup"><span data-stu-id="8875e-114">Please replace those names with names that are unique to your setup program.</span></span>

    2. <span data-ttu-id="8875e-115">从 MMIO 节读取。</span><span class="sxs-lookup"><span data-stu-id="8875e-115">Read from the MMIO section.</span></span> <span data-ttu-id="8875e-116">在 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 中，下载和安装操作是同时进行的：下载 .NET Framework 一部分的同时，可能正在安装另一部分。</span><span class="sxs-lookup"><span data-stu-id="8875e-116">In the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)], the download and installation operations are simultaneous: One part of the .NET Framework might be installing while another part is downloading.</span></span> <span data-ttu-id="8875e-117">因此，进度会以从 0 到 255 递增的两个数字（`m_downloadSoFar` 和 `m_installSoFar`）形式发送回（即写入）MMIO 节。</span><span class="sxs-lookup"><span data-stu-id="8875e-117">As a result, progress is sent back (that is, written) to the MMIO section as two numbers (`m_downloadSoFar` and `m_installSoFar`) that increase from 0 to 255.</span></span> <span data-ttu-id="8875e-118">如果写入 255 且 .NET Framework 存在，则表示安装完成。</span><span class="sxs-lookup"><span data-stu-id="8875e-118">When 255 is written and the .NET Framework exits, the installation is complete.</span></span>

- <span data-ttu-id="8875e-119">退出代码。</span><span class="sxs-lookup"><span data-stu-id="8875e-119">**Exit codes**.</span></span> <span data-ttu-id="8875e-120">以下命令中的退出代码用于调用 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 可再发行程序，指示安装是成功还是失败：</span><span class="sxs-lookup"><span data-stu-id="8875e-120">The following exit codes from the command to call the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable program indicate whether setup has succeeded or failed:</span></span>

  - <span data-ttu-id="8875e-121">0 - 安装已成功完成。</span><span class="sxs-lookup"><span data-stu-id="8875e-121">0 - Setup completed successfully.</span></span>

  - <span data-ttu-id="8875e-122">3010 - 安装已成功完成；需要重启系统。</span><span class="sxs-lookup"><span data-stu-id="8875e-122">3010 – Setup completed successfully; a system restart is required.</span></span>

  - <span data-ttu-id="8875e-123">1602 - 安装已取消。</span><span class="sxs-lookup"><span data-stu-id="8875e-123">1602 – Setup has been canceled.</span></span>

  - <span data-ttu-id="8875e-124">所有其他代码 - 安装过程中出现错误；请检查 %temp% 中创建的日志文件，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="8875e-124">All other codes - Setup encountered errors; examine the log files created in %temp% for details.</span></span>

- <span data-ttu-id="8875e-125">取消安装。</span><span class="sxs-lookup"><span data-stu-id="8875e-125">**Canceling setup**.</span></span> <span data-ttu-id="8875e-126">可随时通过使用 `Abort` 方法在 MMIO 节中设置 `m_downloadAbort` 和 `m_ installAbort` 标志来取消安装。</span><span class="sxs-lookup"><span data-stu-id="8875e-126">You can cancel setup at any time by using the `Abort` method to set the `m_downloadAbort` and `m_ installAbort` flags in the MMIO section.</span></span>

## <a name="chainer-sample"></a><span data-ttu-id="8875e-127">链接器示例</span><span class="sxs-lookup"><span data-stu-id="8875e-127">Chainer Sample</span></span>

<span data-ttu-id="8875e-128">链接器示例以无提示方式启动并跟踪 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装程序，同时显示进度。</span><span class="sxs-lookup"><span data-stu-id="8875e-128">The Chainer sample silently launches and tracks [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] setup while showing progress.</span></span> <span data-ttu-id="8875e-129">此示例类似于为 .NET Framework 4 提供的链接器示例。</span><span class="sxs-lookup"><span data-stu-id="8875e-129">This sample is similar to the Chainer sample provided for the .NET Framework 4.</span></span> <span data-ttu-id="8875e-130">但是，它还可以通过处理用于关闭 .NET framework 4 应用的消息框来避免系统重启。</span><span class="sxs-lookup"><span data-stu-id="8875e-130">However, in addition, it can avoid system restarts by processing the message box for closing .NET Framework 4 apps.</span></span> <span data-ttu-id="8875e-131">有关此消息框的信息，请参阅[在 .NET Framework 4.5 安装期间减少系统重启](../../../docs/framework/deployment/reducing-system-restarts.md)。</span><span class="sxs-lookup"><span data-stu-id="8875e-131">For information about this message box, see [Reducing System Restarts During .NET Framework 4.5 Installations](../../../docs/framework/deployment/reducing-system-restarts.md).</span></span> <span data-ttu-id="8875e-132">可以将此示例与 .NET Framework 4 安装程序结合使用；在这种情况下，不会发送消息。</span><span class="sxs-lookup"><span data-stu-id="8875e-132">You can use this sample with the .NET Framework 4 installer; in that scenario, the message is simply not sent.</span></span>

> [!WARNING]
> <span data-ttu-id="8875e-133">必须以管理员身份运行此示例。</span><span class="sxs-lookup"><span data-stu-id="8875e-133">You must run the example as an administrator.</span></span>

<span data-ttu-id="8875e-134">可从 MSDN 示例库下载针对 [.NET Framework 4.5 链接器示例](https://go.microsoft.com/fwlink/?LinkId=231345)的完整 Visual Studio 解决方案。</span><span class="sxs-lookup"><span data-stu-id="8875e-134">You can download the complete Visual Studio solution for the [.NET Framework 4.5 Chainer Sample](https://go.microsoft.com/fwlink/?LinkId=231345) from the MSDN Samples Gallery.</span></span>

<span data-ttu-id="8875e-135">以下章节对此示例中的重要文件进行了介绍：MMIOChainer.h、ChainingdotNet4.cpp 和 IProgressObserver.h。</span><span class="sxs-lookup"><span data-stu-id="8875e-135">The following sections describe the significant files in this sample: MMIOChainer.h, ChainingdotNet4.cpp, and IProgressObserver.h.</span></span>

#### <a name="mmiochainerh"></a><span data-ttu-id="8875e-136">MMIOChainer.h</span><span class="sxs-lookup"><span data-stu-id="8875e-136">MMIOChainer.h</span></span>

- <span data-ttu-id="8875e-137">MMIOChainer.h 文件（请参阅[完整代码](https://go.microsoft.com/fwlink/?LinkId=231369)）包含数据结构定义和链接器类应派生自的基类。</span><span class="sxs-lookup"><span data-stu-id="8875e-137">The MMIOChainer.h file (see [complete code](https://go.microsoft.com/fwlink/?LinkId=231369)) contains the data structure definition and the base class from which the chainer class should be derived.</span></span> <span data-ttu-id="8875e-138">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 扩展 MMIO 数据结构，处理 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 安装程序需要的数据。</span><span class="sxs-lookup"><span data-stu-id="8875e-138">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] extends the MMIO data structure to handle data that the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] installer needs.</span></span> <span data-ttu-id="8875e-139">对 MMIO 结构的更改为后向兼容，因此 .NET Framework 4 链接器可在无需重新编译的情况下与 .NET Framework 4.5 安装程序结合使用。</span><span class="sxs-lookup"><span data-stu-id="8875e-139">The changes to the MMIO structure are backward-compatible, so a .NET Framework 4 chainer can work with .NET Framework 4.5 setup without requiring recompilation.</span></span> <span data-ttu-id="8875e-140">但是，此方案不支持用于减少系统重启的功能。</span><span class="sxs-lookup"><span data-stu-id="8875e-140">However, this scenario does not support the feature for reducing system restarts.</span></span>

    <span data-ttu-id="8875e-141">版本字段提供标识结构和消息格式的修订的方法。</span><span class="sxs-lookup"><span data-stu-id="8875e-141">A version field provides a means of identifying revisions to the structure and message format.</span></span> <span data-ttu-id="8875e-142">.NET Framework 安装程序通过调用 `VirtualQuery` 函数来确定文件映射的大小，从而确定链接器接口的版本。</span><span class="sxs-lookup"><span data-stu-id="8875e-142">The .NET Framework setup determines the version of the chainer interface by calling the `VirtualQuery` function to determine the size of the file mapping.</span></span> <span data-ttu-id="8875e-143">如果大小足以容纳版本字段，则 .NET framework 安装程序将使用该指定值。</span><span class="sxs-lookup"><span data-stu-id="8875e-143">If the size is large enough to accommodate the version field, .NET Framework setup uses the specified value.</span></span> <span data-ttu-id="8875e-144">如果文件映射因过小而无法包含版本字段（.NET framework 4 即是这种情况），则安装过程假定为版本 0 (4)。</span><span class="sxs-lookup"><span data-stu-id="8875e-144">If the file mapping is too small to contain a version field, which is the case with the .NET Framework 4, the setup process assumes version 0 (4).</span></span> <span data-ttu-id="8875e-145">如果链接器不支持 .NET framework 安装程序希望发送的消息版本，则 .NET framework 安装程序会假定一个忽略响应。</span><span class="sxs-lookup"><span data-stu-id="8875e-145">If the chainer does not support the version of the message that .NET Framework setup wants to send, .NET Framework setup assumes an ignore response.</span></span>

    <span data-ttu-id="8875e-146">按以下方式定义 MMIO 数据结构：</span><span class="sxs-lookup"><span data-stu-id="8875e-146">The MMIO data structure is defined as follows:</span></span>

    ```cpp
    // MMIO data structure for interprocess communication
        struct MmioDataStructure
        {
            bool m_downloadFinished;               // Is download complete?
            bool m_installFinished;                // Is installation complete?
            bool m_downloadAbort;                  // Set to cause downloader to abort.
            bool m_installAbort;                   // Set to cause installer to abort.
            HRESULT m_hrDownloadFinished;          // Resulting HRESULT for download.
            HRESULT m_hrInstallFinished;           // Resulting HRESULT for installation.
            HRESULT m_hrInternalError;
            WCHAR m_szCurrentItemStep[MAX_PATH];
            unsigned char m_downloadSoFar;         // Download progress 0-255 (0-100% done).
            unsigned char m_installSoFar;          // Installation progress 0-255 (0-100% done).
            WCHAR m_szEventName[MAX_PATH];         // Event that chainer creates and chainee opens to sync communications.

            BYTE m_version;                        // Version of the data structure, set by chainer:
                                                   // 0x0: .NET Framework 4
                                                   // 0x1: .NET Framework 4.5

            DWORD m_messageCode;                   // Current message sent by the chainee; 0 if no message is active.
            DWORD m_messageResponse;               // Chainer's response to current message; 0 if not yet handled.
            DWORD m_messageDataLength;             // Length of the m_messageData field, in bytes.
            BYTE m_messageData[1];                 // Variable-length buffer; content depends on m_messageCode.
        };
    ```

- <span data-ttu-id="8875e-147">不应直接使用 `MmioDataStructure` 数据结构；而应改用 `MmioChainer` 类以实现链接器。</span><span class="sxs-lookup"><span data-stu-id="8875e-147">The `MmioDataStructure` data structure should not be used directly; use the `MmioChainer` class instead to implement your chainer.</span></span> <span data-ttu-id="8875e-148">派生自 `MmioChainer` 类，链接 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 可再发行组件。</span><span class="sxs-lookup"><span data-stu-id="8875e-148">Derive from the `MmioChainer` class to chain the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable.</span></span>

#### <a name="iprogressobserverh"></a><span data-ttu-id="8875e-149">IProgressObserver.h</span><span class="sxs-lookup"><span data-stu-id="8875e-149">IProgressObserver.h</span></span>

- <span data-ttu-id="8875e-150">IProgressObserver.h 文件实现进度观察器（[请参阅完整代码](https://go.microsoft.com/fwlink/?LinkId=231370)）。</span><span class="sxs-lookup"><span data-stu-id="8875e-150">The IProgressObserver.h file implements a progress observer ([see complete code](https://go.microsoft.com/fwlink/?LinkId=231370)).</span></span> <span data-ttu-id="8875e-151">此观察程序会获得下载和安装进度通知（指定为无符号 `char`，0-255，指示 1%-100% 完成进度）。</span><span class="sxs-lookup"><span data-stu-id="8875e-151">This observer gets notified of download and installation progress (specified as an unsigned `char`, 0-255, indicating 1%-100% complete).</span></span> <span data-ttu-id="8875e-152">链接发送消息时，观察程序也会得到通知，并且观察程序应该发送一个答复。</span><span class="sxs-lookup"><span data-stu-id="8875e-152">The observer is also notified when the chainee sends a message, and the observer should send a response.</span></span>

    ```cpp
        class IProgressObserver
        {
        public:
            virtual void OnProgress(unsigned char) = 0; // 0 - 255:  255 == 100%
            virtual void Finished(HRESULT) = 0;         // Called when operation is complete
            virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength) = 0; // Called when a message is sent
        };
    ```

#### <a name="chainingdotnet45cpp"></a><span data-ttu-id="8875e-153">ChainingdotNet4.5.cpp</span><span class="sxs-lookup"><span data-stu-id="8875e-153">ChainingdotNet4.5.cpp</span></span>

- <span data-ttu-id="8875e-154">[ChainingdotNet4.5.cpp](https://go.microsoft.com/fwlink/?LinkId=231368) 文件实现从 `MmioChainer` 派生的 `Server` 类，并重写了相应方法以显示进度信息。</span><span class="sxs-lookup"><span data-stu-id="8875e-154">The [ChainingdotNet4.5.cpp](https://go.microsoft.com/fwlink/?LinkId=231368) file implements the `Server` class, which derives from the `MmioChainer` class and overrides the appropriate methods to display progress information.</span></span> <span data-ttu-id="8875e-155">MmioChainer 使用指定的节名称创建一节并使用指定的事件名称初始化链接器。</span><span class="sxs-lookup"><span data-stu-id="8875e-155">The MmioChainer creates a section with the specified section name and initializes the chainer with the specified event name.</span></span> <span data-ttu-id="8875e-156">事件名称会保存在映射数据结构中。</span><span class="sxs-lookup"><span data-stu-id="8875e-156">The event name is saved in the mapped data structure.</span></span> <span data-ttu-id="8875e-157">应确保节和事件名称的唯一性。</span><span class="sxs-lookup"><span data-stu-id="8875e-157">You should make the section and event names unique.</span></span> <span data-ttu-id="8875e-158">以下代码中的 `Server` 类会启动指定的安装程序，监视其进度并返回退出代码。</span><span class="sxs-lookup"><span data-stu-id="8875e-158">The `Server` class in the following code launches the specified setup program, monitors its progress, and returns an exit code.</span></span>

    ```cpp
    class Server : public ChainerSample::MmioChainer, public ChainerSample::IProgressObserver
    {
    public:
        …………….
        Server():ChainerSample::MmioChainer(L"TheSectionName", L"TheEventName") //customize for your event names
        {}
    ```

    <span data-ttu-id="8875e-159">在 Main 方法中开始安装。</span><span class="sxs-lookup"><span data-stu-id="8875e-159">The installation is started in the Main method.</span></span>

    ```cpp
    // Main entry point for program
    int __cdecl main(int argc, _In_count_(argc) char **_argv)
    {
        int result = 0;
        CString args;
        if (argc > 1)
        {
            args = CString(_argv[1]);
        }

        if (IsNetFx4Present(NETFX45_RC_REVISION))
        {
            printf(".NET Framework 4.5 is already installed");
        }
        else
        {
            result = Server().Launch(args);
        }

        return result;
    }
    ```

- <span data-ttu-id="8875e-160">启动安装之前，链接器会先进行检查，查看是否已通过调用 `IsNetFx4Present` 安装 [!INCLUDE[net_v45](../../../includes/net-v45-md.md)]：</span><span class="sxs-lookup"><span data-stu-id="8875e-160">Before launching the installation, the chainer checks to see if the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] is already installed by calling `IsNetFx4Present`:</span></span>

    ```cpp
    ///  Checks for presence of the .NET Framework 4.
    ///    A value of 0 for dwMinimumRelease indicates a check for the .NET Framework 4 full
    ///    Any other value indicates a check for a specific compatible release of the .NET Framework 4.
    #define NETFX40_FULL_REVISION 0
    // TODO: Replace with released revision number
    #define NETFX45_RC_REVISION MAKELONG(50309, 5)   // .NET Framework 4.5
    bool IsNetFx4Present(DWORD dwMinimumRelease)
    {
        DWORD dwError = ERROR_SUCCESS;
        HKEY hKey = NULL;
        DWORD dwData = 0;
        DWORD dwType = 0;
        DWORD dwSize = sizeof(dwData);

        dwError = ::RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4\\Full", 0, KEY_READ, &hKey);
        if (ERROR_SUCCESS == dwError)
        {
            dwError = ::RegQueryValueExW(hKey, L"Release", 0, &dwType, (LPBYTE)&dwData, &dwSize);

            if ((ERROR_SUCCESS == dwError) && (REG_DWORD != dwType))
            {
                dwError = ERROR_INVALID_DATA;
            }
            else if (ERROR_FILE_NOT_FOUND == dwError)
            {
                // Release value was not found, let's check for 4.0.
                dwError = ::RegQueryValueExW(hKey, L"Install", 0, &dwType, (LPBYTE)&dwData, &dwSize);

                // Install = (REG_DWORD)1;
                if ((ERROR_SUCCESS == dwError) && (REG_DWORD == dwType) && (dwData == 1))
                {
                    // treat 4.0 as Release = 0
                    dwData = 0;
                }
                else
                {
                    dwError = ERROR_INVALID_DATA;
                }
            }
        }

        if (hKey != NULL)
        {
            ::RegCloseKey(hKey);
        }

        return ((ERROR_SUCCESS == dwError) && (dwData >= dwMinimumRelease));
    }
    ```

- <span data-ttu-id="8875e-161">可以更改 `Launch` 方法中可执行组件（在此示例中为 Setup.exe）的路径以指向其正确位置，或者自定义代码以确定位置。</span><span class="sxs-lookup"><span data-stu-id="8875e-161">You can change the path of the executable (Setup.exe in the example) in the `Launch` method to point to its correct location, or customize the code to determine the location.</span></span> <span data-ttu-id="8875e-162">`MmioChainer` 基类提供派生类调用的阻止 `Run()` 方法。</span><span class="sxs-lookup"><span data-stu-id="8875e-162">The `MmioChainer` base class provides a blocking `Run()` method that the derived class calls.</span></span>

    ```cpp
    bool Launch(const CString& args)
    {
    CString cmdline = L"dotNetFx45_Full_x86_x64.exe -pipe TheSectionName " + args; // Customize with name and location of setup .exe that you want to run
    STARTUPINFO si = {0};
    si.cb = sizeof(si);
    PROCESS_INFORMATION pi = {0};

    // Launch the Setup.exe that installs the .NET Framework 4.5
    BOOL bLaunchedSetup = ::CreateProcess(NULL,
     cmdline.GetBuffer(),
     NULL, NULL, FALSE, 0, NULL, NULL,
     &si,
     &pi);

    // If successful
    if (bLaunchedSetup != 0)
    {
    IProgressObserver& observer = dynamic_cast<IProgressObserver&>(*this);
    Run(pi.hProcess, observer);

    ……………………..
    return (bLaunchedSetup != 0);
    }
    ```

- <span data-ttu-id="8875e-163">`Send` 方法截获并处理消息。</span><span class="sxs-lookup"><span data-stu-id="8875e-163">The `Send` method intercepts and processes the messages.</span></span> <span data-ttu-id="8875e-164">在此版本的 .NET Framework 中，唯一支持的消息是关闭应用程序消息。</span><span class="sxs-lookup"><span data-stu-id="8875e-164">In this version of the .NET Framework, the only supported message is the close application message.</span></span>

    ```cpp
            // SendMessage
            //
            // Send a message and wait for the response.
            // dwMessage: Message to send
            // pData: The buffer to copy the data to
            // dwDataLength: Initially a pointer to the size of pBuffer. Upon successful call, the number of bytes copied to pBuffer.
            //--------------------------------------------------------------
        virtual DWORD Send(DWORD dwMessage, LPVOID pData, DWORD dwDataLength)
        {
            DWORD dwResult = 0;
            printf("received message: %d\n", dwMessage);
            // Handle message
            switch (dwMessage)
            {
            case MMIO_CLOSE_APPS:
                {
                    printf("    applications are holding files in use:\n");
                    IronMan::MmioCloseApplications* applications = reinterpret_cast<IronMan::MmioCloseApplications*>(pData);
                    for(DWORD i = 0; i < applications->m_dwApplicationsSize; i++)
                    {
                        printf("      %ls (%d)\n", applications->m_applications[i].m_szName, applications->m_applications[i].m_dwPid);
                    }

                    printf("    should appliations be closed? (Y)es, (N)o, (R)efresh : ");
                    while (dwResult == 0)
                    {
                        switch (toupper(getwchar()))
                        {
                        case 'Y':
                            dwResult = IDYES;  // Close apps
                            break;
                        case 'N':
                            dwResult = IDNO;
                            break;
                        case 'R':
                            dwResult = IDRETRY;
                            break;
                        }
                    }
                    printf("\n");
                    break;
                }
            default:
                break;
            }
            printf("  response: %d\n  ", dwResult);
            return dwResult;
        }
    };
    ```

- <span data-ttu-id="8875e-165">进度数据是 0 (0%) 到 255 (100%) 之间的无符号 `char`。</span><span class="sxs-lookup"><span data-stu-id="8875e-165">Progress data is an unsigned `char` between 0 (0%) and 255 (100%).</span></span>

    ```cpp
    private: // IProgressObserver
        virtual void OnProgress(unsigned char ubProgressSoFar)
        {…………
       }
    ```

- <span data-ttu-id="8875e-166">将 HRESULT 传递给 `Finished` 方法。</span><span class="sxs-lookup"><span data-stu-id="8875e-166">The HRESULT is passed to the `Finished` method.</span></span>

    ```cpp
    virtual void Finished(HRESULT hr)
    {
    // This HRESULT is communicated over MMIO and may be different than process
    // Exit code of the Chainee Setup.exe itself
    printf("\r\nFinished HRESULT: 0x%08X\r\n", hr);
    }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="8875e-167">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)] 可再发行组件通常会写入多条进度消息和一条指示完成的消息（在链接器端）。</span><span class="sxs-lookup"><span data-stu-id="8875e-167">The [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] redistributable typically writes many progress messages and a single message that indicates completion (on the chainer side).</span></span> <span data-ttu-id="8875e-168">它还会以异步方式进行读取，查找 `Abort` 记录。</span><span class="sxs-lookup"><span data-stu-id="8875e-168">It also reads asynchronously, looking for `Abort` records.</span></span> <span data-ttu-id="8875e-169">如果接收到 `Abort` 记录，则会取消安装，并在安装中止和安装操作回退后，使用 E ABORT 作为其数据编写已完成记录。</span><span class="sxs-lookup"><span data-stu-id="8875e-169">If it receives an `Abort` record, it cancels the installation, and writes a finished record with E_ABORT as its data after the installation has been aborted and setup operations have been rolled back.</span></span>

<span data-ttu-id="8875e-170">典型的服务器会创建随机 MMIO 文件名、创建文件（如上一个代码示例 `Server::CreateSection` 中所示），并通过使用 `CreateProcess` 和借助 `-pipe someFileSectionName` 选项传递管道名称来启动可再发行组件。</span><span class="sxs-lookup"><span data-stu-id="8875e-170">A typical server creates a random MMIO file name, creates the file (as shown in the previous code example, in `Server::CreateSection`), and launches the redistributable by using the `CreateProcess` method and passing the pipe name with the `-pipe someFileSectionName` option.</span></span> <span data-ttu-id="8875e-171">服务器应使用特定于应用程序 UI 的代码来实现 `OnProgress`、`Send` 和 `Finished` 方法。</span><span class="sxs-lookup"><span data-stu-id="8875e-171">The server should implement `OnProgress`, `Send`, and `Finished` methods with application UI-specific code.</span></span>

## <a name="see-also"></a><span data-ttu-id="8875e-172">请参阅</span><span class="sxs-lookup"><span data-stu-id="8875e-172">See also</span></span>

- [<span data-ttu-id="8875e-173">面向开发人员的部署指南</span><span class="sxs-lookup"><span data-stu-id="8875e-173">Deployment Guide for Developers</span></span>](../../../docs/framework/deployment/deployment-guide-for-developers.md)
- [<span data-ttu-id="8875e-174">部署</span><span class="sxs-lookup"><span data-stu-id="8875e-174">Deployment</span></span>](../../../docs/framework/deployment/index.md)
