---
title: 控制 .NET Framework 日志记录
ms.date: 03/30/2017
helpviewer_keywords:
- CLR ETW events, logging
ms.assetid: ce13088e-3095-4f0e-9f6b-fad30bbd3d41
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bee42db7b9a92723b0640d0b3747a7921b8617c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43418980"
---
# <a name="controlling-net-framework-logging"></a><span data-ttu-id="c5c52-102">控制 .NET Framework 日志记录</span><span class="sxs-lookup"><span data-stu-id="c5c52-102">Controlling .NET Framework Logging</span></span>
<span data-ttu-id="c5c52-103">可以使用 Windows 事件跟踪 (ETW) 来记录公共语言运行时 (CLR) 事件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-103">You can use event tracing for Windows (ETW) to record common language runtime (CLR) events.</span></span> <span data-ttu-id="c5c52-104">可以使用以下工具来创建和查看跟踪：</span><span class="sxs-lookup"><span data-stu-id="c5c52-104">You can create and view traces by using the following tools:</span></span>  
  
-   <span data-ttu-id="c5c52-105">Windows 操作系统附带的 [Logman](https://go.microsoft.com/fwlink/?LinkId=150916) 和 [Tracerpt](https://go.microsoft.com/fwlink/?LinkId=150919) 命令行工具。</span><span class="sxs-lookup"><span data-stu-id="c5c52-105">The [Logman](https://go.microsoft.com/fwlink/?LinkId=150916) and [Tracerpt](https://go.microsoft.com/fwlink/?LinkId=150919) command-line tools, which are included with the Windows operating system.</span></span>  
  
-   <span data-ttu-id="c5c52-106">[Windows 性能工具包](https://msdn.microsoft.com/library/windows/hardware/hh162945.aspx)中的 [Xperf](https://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) 工具。</span><span class="sxs-lookup"><span data-stu-id="c5c52-106">The [Xperf](https://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) tools in the [Windows Performance Toolkit](https://msdn.microsoft.com/library/windows/hardware/hh162945.aspx).</span></span> <span data-ttu-id="c5c52-107">有关 Xperf 的详细信息，请参阅 [Windows 性能博客](https://go.microsoft.com/fwlink/?LinkId=179509)。</span><span class="sxs-lookup"><span data-stu-id="c5c52-107">For more information about Xperf, see the [Windows Performance blog](https://go.microsoft.com/fwlink/?LinkId=179509).</span></span>  
  
 <span data-ttu-id="c5c52-108">若要捕获 CLR 事件信息，必须在计算机上安装 CLR 提供程序。</span><span class="sxs-lookup"><span data-stu-id="c5c52-108">To capture CLR event information, the CLR provider must be installed on your computer.</span></span> <span data-ttu-id="c5c52-109">若要确认该提供程序已安装，请在命令提示符处键入 `logman query providers`。</span><span class="sxs-lookup"><span data-stu-id="c5c52-109">To confirm that the provider is installed, type `logman query providers` at the command prompt.</span></span> <span data-ttu-id="c5c52-110">将显示提供程序的列表。</span><span class="sxs-lookup"><span data-stu-id="c5c52-110">A list of providers is displayed.</span></span> <span data-ttu-id="c5c52-111">此列表应包含与 CLR 提供程序对应的项，如下所示。</span><span class="sxs-lookup"><span data-stu-id="c5c52-111">This list should contain an entry for the CLR provider, as follows.</span></span>  
  
```  
Provider                                 GUID  
-------------------------------------------------------------------------------  
.NET Common Language Runtime    {E13C0D23-CCBC-4E12-931B-D9CC2EEE27E4}.  
```  
  
 <span data-ttu-id="c5c52-112">如果未列出 CLR 提供程序，则可以通过使用 Windows [Wevtutil](https://go.microsoft.com/fwlink/?LinkID=150915) 命令行工具在 Windows Vista 和更高版本的操作系统上安装该提供程序。</span><span class="sxs-lookup"><span data-stu-id="c5c52-112">If the CLR provider is not listed, you can install it on Windows Vista and later operating systems by using the Windows [Wevtutil](https://go.microsoft.com/fwlink/?LinkID=150915) command-line tool.</span></span> <span data-ttu-id="c5c52-113">以管理员身份打开命令提示符窗口。</span><span class="sxs-lookup"><span data-stu-id="c5c52-113">Open the Command Prompt window as an administrator.</span></span> <span data-ttu-id="c5c52-114">将提示目录更改为 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 文件夹（%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET 版本>\）。</span><span class="sxs-lookup"><span data-stu-id="c5c52-114">Change the prompt directory to the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] folder (%WINDIR%\Microsoft.NET\Framework[64]\v4.\<.NET version>\ ).</span></span> <span data-ttu-id="c5c52-115">此文件夹包含 CLR-ETW.man 文件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-115">This folder contains the CLR-ETW.man file.</span></span> <span data-ttu-id="c5c52-116">在命令提示符处，键入以下命令来安装 CLR 提供程序：</span><span class="sxs-lookup"><span data-stu-id="c5c52-116">At the command prompt, type the following command to install the CLR provider:</span></span>  
  
 `wevtutil im CLR-ETW.man`  
  
## <a name="capturing-clr-etw-events"></a><span data-ttu-id="c5c52-117">捕获 CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c5c52-117">Capturing CLR ETW Events</span></span>  
 <span data-ttu-id="c5c52-118">可使用 [Logman](https://go.microsoft.com/fwlink/?LinkId=150916) 和 [Xperf](https://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) 命令行工具来捕获 ETW 事件，并使用 [Tracerpt](https://go.microsoft.com/fwlink/?LinkId=150919) 和 [Xperf](https://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) 工具来解码跟踪事件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-118">You can use the [Logman](https://go.microsoft.com/fwlink/?LinkId=150916) and [Xperf](https://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) command-line tools to capture ETW events, and the [Tracerpt](https://go.microsoft.com/fwlink/?LinkId=150919) and [Xperf](https://msdn.microsoft.com/library/windows/hardware/hh162920.aspx) tools to decode the trace events.</span></span>  
  
 <span data-ttu-id="c5c52-119">若要启用日志记录，用户必须指定以下三项：</span><span class="sxs-lookup"><span data-stu-id="c5c52-119">To turn on logging, a user must specify three things:</span></span>  
  
-   <span data-ttu-id="c5c52-120">进行通信的提供程序。</span><span class="sxs-lookup"><span data-stu-id="c5c52-120">The provider to communicate to.</span></span>  
  
-   <span data-ttu-id="c5c52-121">一个表示一组关键字的 64 位数。</span><span class="sxs-lookup"><span data-stu-id="c5c52-121">A 64-bit number that represents a set of keywords.</span></span> <span data-ttu-id="c5c52-122">每个关键字都表示提供程序可启用的一组事件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-122">Each keyword represents a set of events that the provider can turn on.</span></span> <span data-ttu-id="c5c52-123">此数字表示要启用的关键字的组合集。</span><span class="sxs-lookup"><span data-stu-id="c5c52-123">The number represents a combined set of keywords to turn on.</span></span>  
  
-   <span data-ttu-id="c5c52-124">一个表示进行记录的级别（详细信息）的较小数。</span><span class="sxs-lookup"><span data-stu-id="c5c52-124">A small number representing the level (verbosity) to log at.</span></span> <span data-ttu-id="c5c52-125">级别 1 表示最简明，级别 5 表示最详细。</span><span class="sxs-lookup"><span data-stu-id="c5c52-125">Level 1 is the least verbose, and level 5 is the most verbose.</span></span> <span data-ttu-id="c5c52-126">级别 0 是默认值，其含义将因提供程序而异。</span><span class="sxs-lookup"><span data-stu-id="c5c52-126">Level 0 is a default whose meaning is provider-specific.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-logman"></a><span data-ttu-id="c5c52-127">使用 Logman 捕获 CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c5c52-127">To capture CLR ETW events using Logman</span></span>  
  
1.  <span data-ttu-id="c5c52-128">在命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="c5c52-128">At the command prompt, type:</span></span>  
  
     `logman start clrevents -p {e13c0d23-ccbc-4e12-931b-d9cc2eee27e4} 0x1CCBD 0x5 -ets -ct perf`  
  
     <span data-ttu-id="c5c52-129">其中：</span><span class="sxs-lookup"><span data-stu-id="c5c52-129">where:</span></span>  
  
    -   <span data-ttu-id="c5c52-130">`-p` 参数标识提供程序 GUID。</span><span class="sxs-lookup"><span data-stu-id="c5c52-130">The `-p` parameter identifies the provider GUID.</span></span>  
  
    -   <span data-ttu-id="c5c52-131">`0x1CCBD` 指定将引发的事件的类别。</span><span class="sxs-lookup"><span data-stu-id="c5c52-131">`0x1CCBD` specifies the categories of events that will be raised.</span></span>  
  
    -   <span data-ttu-id="c5c52-132">`0x5` 设置记录的级别（在本例中为详细级别 (5)）。</span><span class="sxs-lookup"><span data-stu-id="c5c52-132">`0x5` sets the level of logging (in this case, verbose (5)).</span></span>  
  
    -   <span data-ttu-id="c5c52-133">`-ets` 参数指示 Logman 将命令发送给事件跟踪会话。</span><span class="sxs-lookup"><span data-stu-id="c5c52-133">The `-ets` parameter instructs Logman to send commands to event tracing sessions.</span></span>  
  
    -   <span data-ttu-id="c5c52-134">`-ct perf` 参数指定 `QueryPerformanceCounter` 函数将用于记录每个事件的时间戳。</span><span class="sxs-lookup"><span data-stu-id="c5c52-134">The `-ct perf` parameter specifies that the `QueryPerformanceCounter` function will be used to log the time stamp for each event.</span></span>  
  
2.  <span data-ttu-id="c5c52-135">若要停止记录事件，请键入：</span><span class="sxs-lookup"><span data-stu-id="c5c52-135">To stop logging the events, type:</span></span>  
  
     `logman stop clrevents -ets`  
  
     <span data-ttu-id="c5c52-136">此命令创建一个名为 clrevents.etl 的二进制跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-136">This command creates a binary trace file named clrevents.etl.</span></span>  
  
#### <a name="to-capture-clr-etw-events-using-xperf"></a><span data-ttu-id="c5c52-137">使用 Xperf 捕获 CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c5c52-137">To capture CLR ETW events using Xperf</span></span>  
  
1.  <span data-ttu-id="c5c52-138">在命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="c5c52-138">At the command prompt, type:</span></span>  
  
     `xperf -start clr -on e13c0d23-ccbc-4e12-931b-d9cc2eee27e4:0x1CCBD:5 -f clrevents.etl`  
  
     <span data-ttu-id="c5c52-139">其中 GUID 是 CLR ETW 提供程序 GUID，`0x1CCBD:5` 指跟踪级别 5（详细）及以下级别的所有事件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-139">where the GUID is the CLR ETW provider GUID, and `0x1CCBD:5` traces everything at and below level 5 (verbose).</span></span>  
  
2.  <span data-ttu-id="c5c52-140">若要停止跟踪，请键入：</span><span class="sxs-lookup"><span data-stu-id="c5c52-140">To stop tracing, type:</span></span>  
  
     `Xperf -stop clr`  
  
     <span data-ttu-id="c5c52-141">此命令创建一个名为 clrevents.etl 的跟踪文件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-141">This command creates a trace file named clrevents.etl.</span></span>  
  
## <a name="viewing-clr-etw-events"></a><span data-ttu-id="c5c52-142">查看 CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c5c52-142">Viewing CLR ETW Events</span></span>  
 <span data-ttu-id="c5c52-143">使用下面列出的命令来查看 CLR ETW 事件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-143">Use the commands listed below to view the CLR ETW events.</span></span> <span data-ttu-id="c5c52-144">有关事件的说明，请参见 [CLR ETW 事件](../../../docs/framework/performance/clr-etw-events.md)。</span><span class="sxs-lookup"><span data-stu-id="c5c52-144">For a description of the events, see [CLR ETW Events](../../../docs/framework/performance/clr-etw-events.md).</span></span>  
  
#### <a name="to-view-clr-etw-events-using-tracerpt"></a><span data-ttu-id="c5c52-145">使用 Tracerpt 查看 CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c5c52-145">To view CLR ETW events using Tracerpt</span></span>  
  
-   <span data-ttu-id="c5c52-146">在命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="c5c52-146">At the command prompt, type:</span></span>  
  
     `tracerpt clrevents.etl`  
  
     <span data-ttu-id="c5c52-147">此命令创建两个文件：dumpfile.xml 和 summary.txt。</span><span class="sxs-lookup"><span data-stu-id="c5c52-147">This command creates two files: dumpfile.xml and summary.txt.</span></span> <span data-ttu-id="c5c52-148">dumpfile.xml 文件列出所有事件，summary.txt 提供事件的摘要。</span><span class="sxs-lookup"><span data-stu-id="c5c52-148">The dumpfile.xml file lists all the events, and summary.txt provides a summary of the events.</span></span>  
  
#### <a name="to-view-clr-etw-events-using-xperf"></a><span data-ttu-id="c5c52-149">使用 Xperf 查看 CLR ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c5c52-149">To view CLR ETW events using Xperf</span></span>  
  
-   <span data-ttu-id="c5c52-150">在命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="c5c52-150">At the command prompt, type:</span></span>  
  
     `xperf clrevents.etl`  
  
     <span data-ttu-id="c5c52-151">此命令打开 Xperf ETL 文件查看器。</span><span class="sxs-lookup"><span data-stu-id="c5c52-151">This command opens the Xperf ETL file viewer.</span></span> <span data-ttu-id="c5c52-152">在此查看器中，CLR 事件将显示在“一般事件”视图中。</span><span class="sxs-lookup"><span data-stu-id="c5c52-152">In this viewer, the CLR events show up in the **Generic Events** view.</span></span> <span data-ttu-id="c5c52-153">要显示按类型分类的事件的数据网格，请选择此视图中的时间区域，然后右键单击并选择“摘要”。</span><span class="sxs-lookup"><span data-stu-id="c5c52-153">To display a data grid of events categorized by type, select a region of time in this view, and then right-click and select **Summary**.</span></span>  
  
#### <a name="to-convert-the-etl-file-to-a-comma-separated-value-file"></a><span data-ttu-id="c5c52-154">将 .etl 文件转换为逗号分隔值文件</span><span class="sxs-lookup"><span data-stu-id="c5c52-154">To convert the .etl file to a comma-separated value file</span></span>  
  
-   <span data-ttu-id="c5c52-155">在命令提示符处，键入：</span><span class="sxs-lookup"><span data-stu-id="c5c52-155">At the command prompt, type:</span></span>  
  
     `xperf -i clrevents.etl -f clrevents.csv`  
  
     <span data-ttu-id="c5c52-156">此命令可使 XPerf 将事件转储为可以查看的逗号分隔值 (CSV) 文件。</span><span class="sxs-lookup"><span data-stu-id="c5c52-156">This command causes XPerf to dump the events as a comma separated value (CSV) file that you can view.</span></span> <span data-ttu-id="c5c52-157">由于各个事件具有不同的字段，因此该 CSV 文件中的数据之前有多个标题行。</span><span class="sxs-lookup"><span data-stu-id="c5c52-157">Because different events have different fields, this CSV file is contains more than one header line before the data.</span></span> <span data-ttu-id="c5c52-158">每行的第一个字段为事件类型，它指示应使用哪一个标题来确定字段的其余部分。</span><span class="sxs-lookup"><span data-stu-id="c5c52-158">The first field of every line is the event type, which indicates which header should be used to determine the rest of the fields.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5c52-159">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5c52-159">See Also</span></span>  
 [<span data-ttu-id="c5c52-160">Windows 性能工具包</span><span class="sxs-lookup"><span data-stu-id="c5c52-160">Windows Performance Toolkit</span></span>](https://go.microsoft.com/fwlink/?LinkID=161141)  
 [<span data-ttu-id="c5c52-161">公共语言运行时中的 ETW 事件</span><span class="sxs-lookup"><span data-stu-id="c5c52-161">ETW Events in the Common Language Runtime</span></span>](../../../docs/framework/performance/etw-events-in-the-common-language-runtime.md)
