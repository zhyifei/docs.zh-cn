---
title: CLR 探查器和 Windows 应用商店应用程序
ms.date: 03/30/2017
dev_langs:
- csharp
applies_to:
- Windows 10
- Windows 8
helpviewer_keywords:
- profiling API
- profiling API [.NET Framework]
- profiling managed code
- profiling managed code [Windows Store Apps]
ms.assetid: 1c8eb2e7-f20a-42f9-a795-71503486a0f5
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 27e1433415bdc6303555ab9ae04a20e097248535
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/21/2018
ms.locfileid: "46538003"
---
# <a name="clr-profilers-and-windows-store-apps"></a><span data-ttu-id="7d9ff-102">CLR 探查器和 Windows 应用商店应用程序</span><span class="sxs-lookup"><span data-stu-id="7d9ff-102">CLR Profilers and Windows Store Apps</span></span>

<span data-ttu-id="7d9ff-103">本主题讨论你需要想办法编写诊断工具分析的管理 Windows 应用商店应用程序内运行的代码时。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-103">This topic discusses what you need to think about when writing diagnostic tools that analyze managed code running inside a Windows Store app.</span></span> <span data-ttu-id="7d9ff-104">它还提供了指导原则来修改现有的开发工具，以使它们继续工作时对 Windows 应用商店应用程序运行它们。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-104">It also provides guidelines to modify your existing development tools so they continue to work when you run them against Windows Store apps.</span></span> <span data-ttu-id="7d9ff-105">若要了解此信息，最好是如果您熟悉使用公共语言运行时分析 API，已针对 Windows 桌面应用程序，并且您正确运行现在感兴趣修改该工具的诊断工具中使用此 API若要针对 Windows 应用商店应用程序正确运行。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-105">To understand this information, it’s best if you're  familiar with the Common Language Runtime Profiling API, you’ve already used this API in a diagnostic tool that runs correctly against Windows desktop applications, and you’re now interested in modifying the tool to run correctly against Windows Store apps.</span></span>

## <a name="introduction"></a><span data-ttu-id="7d9ff-106">介绍</span><span class="sxs-lookup"><span data-stu-id="7d9ff-106">Introduction</span></span>

<span data-ttu-id="7d9ff-107">如果过去的介绍性段落中做它，然后您熟悉 CLR 分析 API。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-107">If you made it past the introductory paragraph, then you’re familiar with the CLR Profiling API.</span></span> <span data-ttu-id="7d9ff-108">编写了一个诊断工具，还针对托管桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-108">You’ve already written a diagnostic tool that works well against managed desktop applications.</span></span> <span data-ttu-id="7d9ff-109">现在，您想要执行的操作，以便所需的工具适用于托管的 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-109">Now you’re curious what to do so that your tool works with a managed Windows Store app.</span></span> <span data-ttu-id="7d9ff-110">可能已尝试进行这项工作，并发现它不是简单的任务。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-110">Perhaps you’ve already tried to make this work, and have discovered that it’s not a straightforward task.</span></span> <span data-ttu-id="7d9ff-111">实际上，有一些可能不太明显的所有工具开发人员的注意事项。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-111">Indeed, there are a number of considerations that might not be obvious to all tools developers.</span></span> <span data-ttu-id="7d9ff-112">例如：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-112">For example:</span></span>

- <span data-ttu-id="7d9ff-113">具有严重降低的权限的上下文中运行 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-113">Windows Store apps run in a context with severely reduced permissions.</span></span>

- <span data-ttu-id="7d9ff-114">Windows 元数据文件具有唯一特征相比传统的托管模块时。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-114">Windows Metadata files have unique characteristics when compared to traditional managed modules.</span></span>

- <span data-ttu-id="7d9ff-115">Windows 应用商店应用程序具有交互性出现故障时挂起自己的习惯。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-115">Windows Store apps have a habit of suspending themselves when interactivity goes down.</span></span>

- <span data-ttu-id="7d9ff-116">进程间通信机制可能由于各种原因而无法继续工作。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-116">Your inter-process communication mechanisms may no longer work for various reasons.</span></span>

<span data-ttu-id="7d9ff-117">本主题列出了需要注意的事项，以及如何正确处理它们。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-117">This topic lists the things you need to be aware of and how to deal with them properly.</span></span>

<span data-ttu-id="7d9ff-118">如果您熟悉 CLR 分析 API，请跳到本主题末尾处的资源，可找到更好地介绍性信息。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-118">If you’re new to the CLR Profiling API, skip down to the Resources at the end of this topic to find better introductory information.</span></span>

<span data-ttu-id="7d9ff-119">提供有关特定 Windows Api 使用方式的详细信息也是本主题的讨论范围内。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-119">Providing detail about specific Windows APIs and how they should be used is also outside the scope of this topic.</span></span> <span data-ttu-id="7d9ff-120">请考虑本主题的起点，并参考 MSDN，了解有关此处引用的任何 Windows Api 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-120">Consider this topic a starting point, and refer to MSDN to learn more about any Windows APIs referenced here.</span></span>

## <a name="architecture-and-terminology"></a><span data-ttu-id="7d9ff-121">体系结构和术语</span><span class="sxs-lookup"><span data-stu-id="7d9ff-121">Architecture and terminology</span></span>

<span data-ttu-id="7d9ff-122">通常，一种诊断工具的体系结构，如下面的插图中所示。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-122">Typically, a diagnostic tool has an architecture like the one shown in the following illustration.</span></span> <span data-ttu-id="7d9ff-123">它使用术语"探查器，"但许多此类工具远不止于典型性能或内存分析为领域，如代码覆盖率，模拟对象框架、 时程调试应用程序监视，依此类推。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-123">It uses the term "profiler," but many such tools go well beyond typical performance or memory profiling into areas such as code coverage, mock object frameworks, time-travel debugging, application monitoring, and so on.</span></span> <span data-ttu-id="7d9ff-124">为简单起见，本主题将继续引用所有这些工具为探查器。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-124">For simplicity, this topic will continue to refer to all these tools as profilers.</span></span>

<span data-ttu-id="7d9ff-125">在本主题中使用了以下术语：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-125">The following terminology is used throughout this topic:</span></span>

<span data-ttu-id="7d9ff-126">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-126">**Application**</span></span>

<span data-ttu-id="7d9ff-127">这是探查器分析的应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-127">This is the application that the profiler is analyzing.</span></span> <span data-ttu-id="7d9ff-128">通常情况下，此应用程序的开发人员现在使用探查器可帮助您诊断与应用程序的问题。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-128">Typically, the developer of this application is now using the profiler to help diagnose issues with the application.</span></span> <span data-ttu-id="7d9ff-129">传统上，此应用程序是 Windows 桌面应用程序，但在本主题中，我们正在寻找 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-129">Traditionally, this application would be a Windows desktop application, but in this topic, we’re looking at Windows Store apps.</span></span>

<span data-ttu-id="7d9ff-130">**Profiler DLL**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-130">**Profiler DLL**</span></span>

<span data-ttu-id="7d9ff-131">这是将加载到应用程序所分析的进程空间的组件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-131">This is the component that loads into the process space of the application being analyzed.</span></span> <span data-ttu-id="7d9ff-132">此组件，也称为探查器"代理，"将实现[ICorProfilerCallback](icorprofilercallback-interface.md)[ICorProfilerCallback 接口](icorprofilercallback-interface.md)(2，3，等等) 接口，并在使用[ICorProfilerInfo](icorprofilerinfo-interface.md)(2，3，等等) 接口，以便收集有关已分析的应用程序和可能的数据修改应用程序的行为的各个方面。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-132">This component, also known as the profiler "agent," implements the [ICorProfilerCallback](icorprofilercallback-interface.md)[ICorProfilerCallback Interface](icorprofilercallback-interface.md)(2,3,etc.) interfaces and consumes the [ICorProfilerInfo](icorprofilerinfo-interface.md)(2,3,etc.) interfaces to collect data about the analyzed application and potentially modify aspects of the application’s behavior.</span></span>

<span data-ttu-id="7d9ff-133">**Profiler UI**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-133">**Profiler UI**</span></span>

<span data-ttu-id="7d9ff-134">这是探查器用户与之交互的桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-134">This is a desktop application that the profiler user interacts with.</span></span> <span data-ttu-id="7d9ff-135">它负责向用户显示应用程序状态以及可让用户控制的已分析的应用程序的行为的方法。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-135">It’s responsible for displaying application status to the user and giving the user the means to control the behavior of the analyzed application.</span></span> <span data-ttu-id="7d9ff-136">此组件始终在其自身进程空间，独立于应用程序所分析的进程空间中运行。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-136">This component always runs in its own process space, separate from the process space of the application being profiled.</span></span> <span data-ttu-id="7d9ff-137">Profiler UI 也可用作"附加触发器，"该调用进程[iclrprofiling:: Attachprofiler](iclrprofiling-attachprofiler-method.md)方法，使分析应用程序中，若要加载在这些情况下，探查器 DLL 没有 Profiler DLL在启动时加载。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-137">The Profiler UI can also act as the "attach trigger," which is the process that calls the [ICLRProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method, to cause the analyzed application to load the Profiler DLL in those cases where the profiler DLL did not load on startup.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d9ff-138">Profiler UI 应保持 Windows 桌面应用程序，即使它所应用到控件和 Windows 应用商店应用程序的报表。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-138">Your Profiler UI should remain a Windows desktop application, even when it is used to control and report on a Windows Store app.</span></span> <span data-ttu-id="7d9ff-139">不希望能够打包和交付您在 Windows 应用商店中的诊断工具。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-139">Don’t expect to be able to package and ship your diagnostics tool in the Windows Store.</span></span> <span data-ttu-id="7d9ff-140">需要执行操作的 Windows 应用商店应用程序不能这样做，并提供其中的许多驻留在 Profiler UI 所需的工具。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-140">Your tool needs to do things that Windows Store apps cannot do, and many of those things reside inside your Profiler UI.</span></span>

<span data-ttu-id="7d9ff-141">在本文档的示例代码假定：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-141">Throughout this document, the sample code assumes that:</span></span>

- <span data-ttu-id="7d9ff-142">Profiler DLL 是用 c + +，因为它必须是本机 DLL，根据 CLR 分析 API 的要求。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-142">Your Profiler DLL is written in C++, because it must be a native DLL, as per the requirements of the CLR Profiling API.</span></span>

- <span data-ttu-id="7d9ff-143">Profiler UI 是用 C# 编写的。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-143">Your Profiler UI is written in C#.</span></span> <span data-ttu-id="7d9ff-144">这不是有必要，但因为没有任何要求 Profiler UI 的过程语言，为什么不选择一种语言的简洁和简单？</span><span class="sxs-lookup"><span data-stu-id="7d9ff-144">This isn’t necessary, but because there are no requirements on the language for your Profiler UI’s process, why not pick a language that’s concise and simple?</span></span>

### <a name="windows-rt-devices"></a><span data-ttu-id="7d9ff-145">Windows RT 设备</span><span class="sxs-lookup"><span data-stu-id="7d9ff-145">Windows RT devices</span></span>

<span data-ttu-id="7d9ff-146">Windows RT 设备相当已锁定。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-146">Windows RT devices are quite locked down.</span></span> <span data-ttu-id="7d9ff-147">只需第三方探查器无法加载此类设备上。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-147">Third-party profilers simply cannot be loaded on such devices.</span></span> <span data-ttu-id="7d9ff-148">本文档重点介绍 Windows 8 Pc。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-148">This document focuses on Windows 8 PCs.</span></span>

## <a name="consuming-windows-runtime-apis"></a><span data-ttu-id="7d9ff-149">使用 Windows 运行时 Api</span><span class="sxs-lookup"><span data-stu-id="7d9ff-149">Consuming Windows Runtime APIs</span></span>

<span data-ttu-id="7d9ff-150">在以下各节所述的方案很多，Profiler UI 桌面应用程序需要使用一些新的 Windows 运行时 Api。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-150">In a number of scenarios discussed in the following sections, your Profiler UI desktop application needs to consume some new Windows Runtime APIs.</span></span> <span data-ttu-id="7d9ff-151">您需要请查阅文档以了解可以从桌面应用程序使用的 Windows 运行时 Api 和它们的行为不同时是否调用从桌面应用程序和 Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-151">You’ll want to consult the documentation to understand which Windows Runtime APIs can be used from desktop applications, and whether their behavior is different when called from desktop applications and Windows Store apps.</span></span>

<span data-ttu-id="7d9ff-152">如果 Profiler UI 用托管代码编写的将有几个步骤都需要执行的操作进行使用这些简单的 Windows 运行时 Api。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-152">If your Profiler UI is written in managed code, there will be a few steps you’ll need to do to make consuming those Windows Runtime APIs easy.</span></span> <span data-ttu-id="7d9ff-153">请参阅[托管桌面应用程序和 Windows 运行时](https://go.microsoft.com/fwlink/?LinkID=271858)文章了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-153">See the [Managed desktop apps and Windows Runtime](https://go.microsoft.com/fwlink/?LinkID=271858) article for more information.</span></span>

## <a name="loading-the-profiler-dll"></a><span data-ttu-id="7d9ff-154">正在加载 Profiler DLL</span><span class="sxs-lookup"><span data-stu-id="7d9ff-154">Loading the Profiler DLL</span></span>

<span data-ttu-id="7d9ff-155">本部分介绍如何 Profiler UI 将导致 Windows 应用商店应用程序加载 Profiler DLL。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-155">This section describes how your Profiler UI causes the Windows Store app to load your Profiler DLL.</span></span> <span data-ttu-id="7d9ff-156">在本部分中所讨论的代码位于 Profiler UI 桌面应用程序，并因此涉及到使用安全的桌面应用程序，但不一定是安全的 Windows 应用商店应用程序的 Windows Api。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-156">The code discussed in this section belongs in your Profiler UI desktop app, and therefore involves using Windows APIs that are safe for desktop apps but not necessarily safe for Windows Store apps.</span></span>

<span data-ttu-id="7d9ff-157">Profiler UI 可能会导致你 Profiler DLL 被加载到应用程序的进程空间中通过两种方式：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-157">Your Profiler UI can cause your Profiler DLL to be loaded into the application’s process space in two ways:</span></span>

- <span data-ttu-id="7d9ff-158">在应用程序启动时，如控制的环境变量。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-158">At application startup, as controlled by environment variables.</span></span>

- <span data-ttu-id="7d9ff-159">通过将附加到应用程序启动完成后通过调用[iclrprofiling:: Attachprofiler](iclrprofiling-attachprofiler-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-159">By attaching to the application after startup is complete by calling the [ICLRProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md) method.</span></span>

<span data-ttu-id="7d9ff-160">第一个障碍之一将获取启动负载和附加负载的 Profiler DLL 与 Windows 应用商店应用程序一起正常工作。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-160">One of your first roadblocks will be getting startup-load and attach-load of your Profiler DLL to work properly with Windows Store apps.</span></span> <span data-ttu-id="7d9ff-161">加载这两种形式共享公用的特殊注意事项，因此，让我们开始使用它们。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-161">Both forms of loading share some special considerations in common, so let’s start with them.</span></span>

### <a name="common-considerations-for-startup-and-attach-loads"></a><span data-ttu-id="7d9ff-162">常见注意事项启动和附加的负载</span><span class="sxs-lookup"><span data-stu-id="7d9ff-162">Common considerations for startup and attach loads</span></span>

<span data-ttu-id="7d9ff-163">**签名在 Profiler DLL**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-163">**Signing your Profiler DLL**</span></span>

<span data-ttu-id="7d9ff-164">当 Windows 尝试加载 Profiler DLL 时，它验证 Profiler DLL 已正确签名。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-164">When Windows attempts to load your Profiler DLL, it verifies that your Profiler DLL is properly signed.</span></span> <span data-ttu-id="7d9ff-165">如果没有，则加载默认情况下会失败。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-165">If not, the load fails by default.</span></span> <span data-ttu-id="7d9ff-166">有两种方法可以实现此目的：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-166">There are two ways to do this:</span></span>

- <span data-ttu-id="7d9ff-167">请确保您 Profiler 的 DLL 进行签名。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-167">Ensure that your Profiler DLL is signed.</span></span>

- <span data-ttu-id="7d9ff-168">告诉您的用户，他们必须安装开发人员许可证在其 Windows 8 计算机上使用所需的工具之前。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-168">Tell your user that they must install a developer license on their Windows 8 machine before using your tool.</span></span> <span data-ttu-id="7d9ff-169">这可以从 Visual Studio 或手动从命令提示符处自动完成。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-169">This can be done automatically from Visual Studio or manually from a command prompt.</span></span> <span data-ttu-id="7d9ff-170">有关详细信息，请参阅[获取开发人员许可证](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-170">For more information, see [Get a developer license](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx).</span></span>

<span data-ttu-id="7d9ff-171">**文件系统权限**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-171">**File system permissions**</span></span>

<span data-ttu-id="7d9ff-172">Windows 应用商店应用程序必须有权加载并从它的文件系统上的位置执行 Profiler DLL residesBy 默认情况下，Windows 应用商店应用程序不具备在大多数目录和任何失败的尝试加载 Profiler DLL 上的此类权限将生成如下所示的 Windows 应用程序事件日志中的条目：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-172">The Windows Store app must have permission to load and execute your Profiler DLL from the location on the file system in which it residesBy default, the Windows Store app doesn’t have such permission on most directories, and any failed attempt to load your Profiler DLL will produce an entry in the Windows Application event log that looks something like this:</span></span>

```Output
NET Runtime version 4.0.30319.17929 - Loading profiler failed during CoCreateInstance.  Profiler CLSID: '{xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx}'.  HRESULT: 0x80070005.  Process ID (decimal): 4688.  Message ID: [0x2504].
```

<span data-ttu-id="7d9ff-173">通常情况下，Windows 应用商店应用程序只允许访问一组有限的磁盘上的位置。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-173">Generally, Windows Store apps are only allowed to access a limited set of locations on the disk.</span></span> <span data-ttu-id="7d9ff-174">每个 Windows 应用商店应用程序可以为其所有 Windows 应用商店应用程序被都授予访问权限的文件系统中访问其自己的应用程序数据文件夹，以及其他几个方面。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-174">Each Windows Store app can access its own application data folders, as well as a few other areas in the file system for which all Windows Store apps are granted access.</span></span> <span data-ttu-id="7d9ff-175">最好是安装 Profiler DLL Program Files 或 Program Files (x86) 下的某个位置及其依赖项，因为所有 Windows 应用商店应用程序具有读取和执行权限默认情况下。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-175">It's best to install your Profiler DLL and its dependencies somewhere under Program Files or Program Files (x86), because all Windows Store apps have read and execute permissions there by default.</span></span>

### <a name="startup-load"></a><span data-ttu-id="7d9ff-176">启动负载</span><span class="sxs-lookup"><span data-stu-id="7d9ff-176">Startup load</span></span>

<span data-ttu-id="7d9ff-177">通常情况下，在桌面应用中，Profiler UI 会提示你 Profiler DLL 启动负载通过初始化包含所需的 CLR 分析 API 的环境变量的环境块 (即`COR_PROFILER`， `COR_ENABLE_PROFILING`，和`COR_PROFILER_PATH`)，并然后使用该环境块创建一个新的进程。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-177">Typically, in a desktop app, your Profiler UI prompts a startup load of your Profiler DLL by initializing an environment block that contains the required CLR Profiling API environment variables (i.e., `COR_PROFILER`, `COR_ENABLE_PROFILING`, and `COR_PROFILER_PATH`), and then creating a new process with that environment block.</span></span> <span data-ttu-id="7d9ff-178">同样适用于 Windows 应用商店应用程序，但机制不同。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-178">The same holds true for Windows Store apps, but the mechanisms are different.</span></span>

<span data-ttu-id="7d9ff-179">**不会运行提升的权限**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-179">**Don’t run elevated**</span></span>

<span data-ttu-id="7d9ff-180">如果进程尝试生成 Windows 应用商店应用程序进程 B 进程 A 应运行在中等完整性级别，不能在高完整性级别 （即，未提升的权限）。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-180">If Process A attempts to spawn Windows Store app Process B, Process A should be run at medium integrity level, not at high integrity level (that is, not elevated).</span></span> <span data-ttu-id="7d9ff-181">这意味着应在中等完整性级别运行 Profiler UI，或它必须生成在中等完整性级别启动 Windows 应用商店应用程序，需要注意的另一个桌面进程。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-181">This means that either your Profiler UI should be running at medium integrity level, or it must spawn another desktop process at medium integrity level to take care of launching the Windows Store app.</span></span>

<span data-ttu-id="7d9ff-182">**选择 Windows 应用商店应用到配置文件**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-182">**Choosing a Windows Store App to profile**</span></span>

<span data-ttu-id="7d9ff-183">首先，你将想要让探查器用户启动的 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-183">First, you’ll want to ask your profiler user which Windows Store app to launch.</span></span> <span data-ttu-id="7d9ff-184">对于桌面应用，可能会显示文件浏览对话框中，然后用户会查找并选择.exe 文件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-184">For desktop apps, perhaps you’d show a file Browse dialog, and the user would find and select an .exe file.</span></span> <span data-ttu-id="7d9ff-185">但 Windows 应用商店应用程序是不同的并使用一个浏览对话框没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-185">But Windows Store apps are different, and using a Browse dialog doesn’t make sense.</span></span> <span data-ttu-id="7d9ff-186">相反，它是更好地向用户显示的 Windows 应用商店应用程序已安装了该用户就可以从选择列表。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-186">Instead, it’s better to show the user a list of Windows Store apps installed for that user to select from.</span></span>

<span data-ttu-id="7d9ff-187">可以使用[PackageManager 类](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx)生成此列表。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-187">You can use the [PackageManager class](https://msdn.microsoft.com/library/windows/apps/windows.management.deployment.packagemanager.aspx) to generate this list.</span></span> <span data-ttu-id="7d9ff-188">`PackageManager` 适用于桌面应用的 Windows 运行时类，实际上它是*仅*适用于桌面应用。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-188">`PackageManager` is a Windows Runtime class that is available to desktop apps, and in fact it is *only* available to desktop apps.</span></span>

<span data-ttu-id="7d9ff-189">下面的代码示例从编写为桌面应用程序在 C# yses 假设 Profiler UI`PackageManager`生成 Windows 应用的列表：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-189">The following code example from a hypothetical Profiler UI written as a desktop app in C# yses the `PackageManager` to generate a list of Windows apps:</span></span>

```csharp
string currentUserSID = WindowsIdentity.GetCurrent().User.ToString();
IAppxFactory appxFactory = (IAppxFactory) new AppxFactory();
PackageManager packageManager = new PackageManager();
IEnumerable<Package> packages = packageManager.FindPackagesForUser(currentUserSID);
```

<span data-ttu-id="7d9ff-190">**指定的自定义的环境块**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-190">**Specifying the custom environment block**</span></span>

<span data-ttu-id="7d9ff-191">新的 COM 接口， [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)，可用于自定义为了简化某些形式的诊断的 Windows 应用商店应用的执行行为。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-191">A new COM interface, [IPackageDebugSettings](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx), allows you to customize the execution behavior of a Windows Store app to make some forms of diagnostics easier.</span></span> <span data-ttu-id="7d9ff-192">其方法之一[EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx)，可以将环境块传递给 Windows 应用商店应用程序时它已启动，以及其他有用的效果，例如禁用自动进程挂起。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-192">One of its methods, [EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=vs.85\).aspx), lets you pass an environment block to the Windows Store app when it’s launched, along with other useful effects like disabling automatic process suspension.</span></span> <span data-ttu-id="7d9ff-193">环境块很重要，因为这是您需要指定环境变量 (`COR_PROFILER`， `COR_ENABLE_PROFILING`，和`COR_PROFILER_PATH)`) 使用 CLR 加载 Profiler DLL。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-193">The environment block is important because that’s where you need to specify the environment variables (`COR_PROFILER`, `COR_ENABLE_PROFILING`, and `COR_PROFILER_PATH)`) used by the CLR to load your Profiler DLL .</span></span>

<span data-ttu-id="7d9ff-194">请思考以下代码片段：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-194">Consider the following code snippet:</span></span>

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packgeFullName, debuggerCommandLine, 
                                                                 (IntPtr)fixedEnvironmentPzz);
```

<span data-ttu-id="7d9ff-195">有几个项都需要得到正确结果：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-195">There are a couple of items you'll need to get right:</span></span>

- <span data-ttu-id="7d9ff-196">`packageFullName` 可循环访问包，然后抓取时确定`package.Id.FullName`。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-196">`packageFullName` can be determined while iterating over the packages and grabbing `package.Id.FullName`.</span></span>

- <span data-ttu-id="7d9ff-197">`debuggerCommandLine` 更有趣的是。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-197">`debuggerCommandLine` is a bit more interesting.</span></span> <span data-ttu-id="7d9ff-198">若要将自定义的环境块传递给 Windows 应用商店应用程序，需要编写您自己，简单的虚拟调试器。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-198">In order to pass the custom environment block to the Windows Store app, you need to write your own, simplistic dummy debugger.</span></span> <span data-ttu-id="7d9ff-199">Windows 会生成 Windows 应用商店应用程序挂起，然后将调试器附加通过启动您的调试器在此示例中类似的命令行：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-199">Windows spawns the Windows Store app suspended and then attaches your debugger by launching your debugger with a command line like in this example:</span></span>

    ```Output
    MyDummyDebugger.exe -p 1336 -tid 1424
    ```

     <span data-ttu-id="7d9ff-200">其中`-p 1336`意味着 Windows 应用商店应用程序具有进程 ID 1336 和`-tid 1424`表示线程 ID 1424 是线程处于挂起状态。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-200">where `-p 1336` means the Windows Store app has Process ID 1336, and `-tid 1424` means Thread ID 1424 is the thread that is suspended.</span></span> <span data-ttu-id="7d9ff-201">虚拟调试器会分析从命令行 ThreadID，恢复该线程，然后退出。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-201">Your dummy debugger would parse the ThreadID from the command-line, resume that thread, and then exit.</span></span>

     <span data-ttu-id="7d9ff-202">下面是一些示例来执行此操作的 c + + 代码 （请确保添加错误检查 ！）：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-202">Here’s some example C++ code to do this (be sure to add error checking!):</span></span>

    ```cpp
    int wmain(int argc, wchar_t* argv[])
    {
        // …
        // Parse command line here
        // …

        HANDLE hThread = OpenThread(THREAD_SUSPEND_RESUME, 
                                                                  FALSE /* bInheritHandle */, nThreadID);
        ResumeThread(hThread);
        CloseHandle(hThread);
        return 0;
    }
    ```

     <span data-ttu-id="7d9ff-203">将需要安装的一部分在诊断工具，为部署此虚拟调试器，然后指定的路径中此调试器`debuggerCommandLine`参数。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-203">You’ll need to deploy this dummy debugger as part of your diagnostics tool installation, and then specify the path to this debugger in the `debuggerCommandLine` parameter.</span></span>

<span data-ttu-id="7d9ff-204">**启动 Windows 应用商店应用程序**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-204">**Launching the Windows Store app**</span></span>

<span data-ttu-id="7d9ff-205">启动 Windows 应用商店应用的时刻终于到来了。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-205">The moment to launch the Windows Store app has finally arrived.</span></span> <span data-ttu-id="7d9ff-206">如果您已尝试过做自己，您可能已经注意到， [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa)是不创建 Windows 应用商店应用程序进程。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-206">If you’ve already already tried doing this yourself, you may have noticed that [CreateProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createprocessa) is not how you create a Windows Store app process.</span></span> <span data-ttu-id="7d9ff-207">相反，你将需要使用[IApplicationActivationManager::ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication)方法。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-207">Instead, you’ll need to use the [IApplicationActivationManager::ActivateApplication](/windows/desktop/api/shobjidl_core/nf-shobjidl_core-iapplicationactivationmanager-activateapplication) method.</span></span> <span data-ttu-id="7d9ff-208">为此，你将需要获取要启动的 Windows 应用商店应用的应用程序用户模型 ID。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-208">To do that, you’ll need to get the App User Model ID of the Windows Store app that you’re launching.</span></span> <span data-ttu-id="7d9ff-209">这意味着您将需要执行一个小获知清单。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-209">And that means you’ll need to do a little digging through the manifest.</span></span>

<span data-ttu-id="7d9ff-210">时循环访问你的程序包 (请参阅中的"选择 Windows 应用商店应用到配置文件"[启动负载](#startup-load)前面部分)，可能想要获取当前包清单中包含的应用程序的一：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-210">While iterating over your packages (see "Choosing a Windows Store App to Profile" in the [Startup load](#startup-load) section earlier), you’ll want to grab the set of applications contained in the current package’s manifest:</span></span>

```csharp
string manifestPath = package.InstalledLocation.Path + "\\AppxManifest.xml";

AppxPackaging.IStream manifestStream;
SHCreateStreamOnFileEx(
                    manifestPath,
                    0x00000040,     // STGM_READ | STGM_SHARE_DENY_NONE
                    0,              // file creation attributes
                    false,          // fCreate
                    null,           // reserved
                    out manifestStream);

IAppxManifestReader manifestReader = appxFactory.CreateManifestReader(manifestStream);

IAppxManifestApplicationsEnumerator appsEnum = manifestReader.GetApplications();
```

<span data-ttu-id="7d9ff-211">是的一个包可以有多个应用程序，并且每个应用程序具有其自己的应用程序用户模型 id。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-211">Yes, one package can have multiple applications, and each application has its own Application User Model ID.</span></span> <span data-ttu-id="7d9ff-212">因此你将想要提出你的用户的应用程序到配置文件，并获取该特定应用程序中的应用程序用户模型 ID:</span><span class="sxs-lookup"><span data-stu-id="7d9ff-212">So you’ll want to ask your user which application to profile, and grab the Application User Model ID from that particular application:</span></span>

```csharp
while (appsEnum.GetHasCurrent() != 0)
{
    IAppxManifestApplication app = appsEnum.GetCurrent();
    string appUserModelId = app.GetAppUserModelId();
    //...
}
```

<span data-ttu-id="7d9ff-213">最后，您现在有您需要启动 Windows 应用商店应用程序：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-213">Finally, you now have what you need to launch the Windows Store app:</span></span>

```csharp
IApplicationActivationManager appActivationMgr = new ApplicationActivationManager();
appActivationMgr.ActivateApplication(appUserModelId, appArgs, ACTIVATEOPTIONS.AO_NONE, out pid);
```

<span data-ttu-id="7d9ff-214">**请记住要调用 DisableDebugging**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-214">**Remember to call DisableDebugging**</span></span>

<span data-ttu-id="7d9ff-215">当调用[IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx)，所做的承诺，您将清理后自行通过调用[IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx)方法，因此请确保执行操作分析会话时通过。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-215">When you called [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx), you made a promise that you would clean up after yourself by calling the [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) method, so be sure to do that when the profiling session is over.</span></span>

### <a name="attach-load"></a><span data-ttu-id="7d9ff-216">附加负载</span><span class="sxs-lookup"><span data-stu-id="7d9ff-216">Attach load</span></span>

<span data-ttu-id="7d9ff-217">当 Profiler UI 想要将其 Profiler DLL 附加到已开始运行的应用程序时，它使用[iclrprofiling:: Attachprofiler](iclrprofiling-attachprofiler-method.md)。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-217">When your Profiler UI wants to attach its Profiler DLL to an application that has already started running, it uses [ICLRProfiling::AttachProfiler](iclrprofiling-attachprofiler-method.md).</span></span> <span data-ttu-id="7d9ff-218">同样适用于 Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-218">The same holds true with Windows Store apps.</span></span> <span data-ttu-id="7d9ff-219">但除了前面列出的常见注意事项，请确保目标 Windows 应用商店应用程序不会挂起。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-219">But in addition to the common considerations listed earlier, make sure the that the target Windows Store app is not suspended.</span></span>

<span data-ttu-id="7d9ff-220">**EnableDebugging**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-220">**EnableDebugging**</span></span>

<span data-ttu-id="7d9ff-221">通过启动负载，如调用[IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-221">As with startup load, call the [IPackageDebugSettings::EnableDebugging](https://msdn.microsoft.com/library/hh438395\(v=VS.85\).aspx) method.</span></span> <span data-ttu-id="7d9ff-222">您不需要它传递的环境块，但您需要其他功能之一： 禁用自动进程挂起。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-222">You don’t need it for passing an environment block, but you need one of its other features: disabling automatic process suspension.</span></span> <span data-ttu-id="7d9ff-223">否则为当 Profiler UI 调用[AttachProfiler](iclrprofiling-attachprofiler-method.md)，目标 Windows 应用商店应用程序可能会挂起。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-223">Otherwise, when your Profiler UI calls [AttachProfiler](iclrprofiling-attachprofiler-method.md), the target Windows Store app may be suspended.</span></span> <span data-ttu-id="7d9ff-224">实际上，这可能是如果用户现在使用 Profiler UI，进行交互，并且 Windows 应用商店应用程序未在任何用户的屏幕上处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-224">In fact, this is likely if the user is now interacting with your Profiler UI, and the Windows Store app is not active on any of the user’s screens.</span></span> <span data-ttu-id="7d9ff-225">如果应用已挂起 Windows 应用商店，它也不能以响应任何发出信号，CLR 会向它发送附加 Profiler DLL。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-225">And if the Windows Store app is suspended, it won’t be able to respond to any signal that the CLR sends to it to attach your Profiler DLL.</span></span>

<span data-ttu-id="7d9ff-226">因此您会希望执行如下操作：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-226">So you’ll want to do something like this:</span></span>

```csharp
IPackageDebugSettings pkgDebugSettings = new PackageDebugSettings();
pkgDebugSettings.EnableDebugging(packgeFullName, null /* debuggerCommandLine */, 
                                                                 IntPtr.Zero /* environment */);
```

<span data-ttu-id="7d9ff-227">这是在相同的调用，但未指定调试器命令行或环境块为启动加载的情况下，可能会使。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-227">This is the same call you’d make for the startup load case, except you don’t specify a debugger command line or an environment block.</span></span>

<span data-ttu-id="7d9ff-228">**DisableDebugging**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-228">**DisableDebugging**</span></span>

<span data-ttu-id="7d9ff-229">与往常一样，不要忘记调用[IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx)完成分析会话的。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-229">As always, don’t forget to call [IPackageDebugSettings::DisableDebugging](https://msdn.microsoft.com/library/hh438394\(v=vs.85\).aspx) when your profiling session is completed.</span></span>

## <a name="running-inside-the-windows-store-app"></a><span data-ttu-id="7d9ff-230">在 Windows 应用商店应用程序内部运行</span><span class="sxs-lookup"><span data-stu-id="7d9ff-230">Running inside the Windows Store app</span></span>

<span data-ttu-id="7d9ff-231">因此 Windows 应用商店应用程序已最后加载 Profiler DLL。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-231">So the Windows Store app has finally loaded your Profiler DLL.</span></span> <span data-ttu-id="7d9ff-232">现在必须如何通过不同的规则所需的 Windows 应用商店应用程序播放让 Profiler DLL，包括允许哪些 Api 以及如何使用运行较少的权限。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-232">Now your Profiler DLL must be taught how to play by the different rules required by Windows Store apps, including which APIs are allowable and how to run with reduced permissions.</span></span>

### <a name="stick-to-the-windows-store-app-apis"></a><span data-ttu-id="7d9ff-233">坚持使用 Windows 应用商店应用 Api</span><span class="sxs-lookup"><span data-stu-id="7d9ff-233">Stick to the Windows Store app APIs</span></span>

<span data-ttu-id="7d9ff-234">当您浏览 Windows API 时，您会注意到不会成为适用于桌面应用程序、 Windows 应用商店应用程序，或同时记录了每个 API。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-234">As you browse the Windows API, you’ll notice that every API is documented as being applicable to desktop apps, Windows Store apps, or both.</span></span> <span data-ttu-id="7d9ff-235">例如，**要求**的文档部分[InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount)函数指示该函数，适用于桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-235">For example, the **Requirements** section of the documentation for the [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) function indicates that the function applies to desktop apps only.</span></span> <span data-ttu-id="7d9ff-236">与此相反， [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)函数是可用于桌面应用程序和 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-236">In contrast, the [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex) function is available for both desktop apps and Windows Store apps.</span></span>

<span data-ttu-id="7d9ff-237">在开发 Profiler DLL 时，将它视为如同它是 Windows 应用商店应用程序，并只使用记录到 Windows 应用商店应用程序为可用的 Api。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-237">When developing your Profiler DLL, treat it as if it’s a Windows Store app and only use APIs that are documented as available to Windows Store apps.</span></span> <span data-ttu-id="7d9ff-238">分析依赖项 (例如，可以运行`link /dump /imports`针对 Profiler DLL 审核)，然后搜索文档，请参阅哪些依赖项是确定，这不是。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-238">Analyze your dependencies (for example, you can run `link /dump /imports` against your Profiler DLL to audit), and then search the docs to see which of your dependencies are ok and which aren’t.</span></span> <span data-ttu-id="7d9ff-239">在大多数情况下，可以通过只需将它们替换为用于记录为安全的 API 的较新窗体修复您的违规 (例如，替换[InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount)与[InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex))。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-239">In most cases, your violations can be fixed by simply replacing them with a newer form of the API that is documented as safe (for example, replacing [InitializeCriticalSectionAndSpinCount](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionandspincount) with [InitializeCriticalSectionEx](/windows/desktop/api/synchapi/nf-synchapi-initializecriticalsectionex)).</span></span>

<span data-ttu-id="7d9ff-240">您可能注意到 Profiler DLL 调用适用于桌面应用程序，某些 Api 和它们看上去尚未处理甚至 Profiler DLL 加载 Windows 应用商店应用程序内。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-240">You might notice that your Profiler DLL calls some APIs that apply to desktop apps only, and yet they seem to work even when your Profiler DLL is loaded inside a Windows Store app.</span></span> <span data-ttu-id="7d9ff-241">请注意，它是有风险，若要使用 Profiler DLL 时加载到 Windows 应用商店应用程序进程中的 Windows 应用商店应用程序与使用未记录任何 API:</span><span class="sxs-lookup"><span data-stu-id="7d9ff-241">Be aware that it’s risky to use any API not documented for use with Windows Store apps in your Profiler DLL when loaded into a Windows Store app process:</span></span>

- <span data-ttu-id="7d9ff-242">此类 Api 不保证能够在 Windows 应用商店应用程序中运行的唯一上下文中调用时。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-242">Such APIs are not guaranteed to work when called in the unique context that Windows Store apps run in.</span></span>

- <span data-ttu-id="7d9ff-243">从不同的 Windows 应用商店应用程序进程中调用时，此类 Api 可能不一致地工作。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-243">Such APIs might not work consistently when called from within different Windows Store app processes.</span></span>

- <span data-ttu-id="7d9ff-244">此类 Api 可能看起来可以从当前版本的 Windows 中的 Windows 应用商店应用程序正常工作，但可能会中断或在 Windows 的未来版本中禁用。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-244">Such APIs might seem to work fine from Windows Store apps in the current version of Windows, but may break or be disabled in future releases of Windows.</span></span>

<span data-ttu-id="7d9ff-245">最佳建议是解决所有冲突，并避免风险。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-245">The best advice is to fix all your violations and avoid the risk.</span></span>

<span data-ttu-id="7d9ff-246">你可能会发现您绝对不能缺少特定的 API 和找不到替代适用于 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-246">You might find that you absolutely cannot do without a particular API and cannot find a replacement suitable for Windows Store apps.</span></span> <span data-ttu-id="7d9ff-247">这种情况下，最小值：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-247">In such a case, at a minimum:</span></span>

- <span data-ttu-id="7d9ff-248">测试、 测试、 测试生活 daylights 超出该 API 的使用情况。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-248">Test, test, test the living daylights out of your usage of that API.</span></span>

- <span data-ttu-id="7d9ff-249">了解 API 可能会突然中断或消失如果调用从在 Windows 应用商店应用在将来的版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-249">Understand that the API might suddenly break or disappear if called from inside Windows Store apps in future releases of Windows.</span></span> <span data-ttu-id="7d9ff-250">这不会由 Microsoft、 被视为一个兼容性问题和支持它的使用情况不会具有优先级。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-250">This won’t be considered a compatibility concern by Microsoft, and supporting your usage of it will not be a priority.</span></span>

### <a name="reduced-permissions"></a><span data-ttu-id="7d9ff-251">降低的权限</span><span class="sxs-lookup"><span data-stu-id="7d9ff-251">Reduced permissions</span></span>

<span data-ttu-id="7d9ff-252">它位于本主题列出 Windows 应用商店应用程序权限不同于桌面应用程序的所有方式的范围之外。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-252">It’s outside the scope of this topic to list all the ways that Windows Store app permissions differ from desktop apps.</span></span> <span data-ttu-id="7d9ff-253">但当然行为将每次尝试访问的任何资源 Profiler DLL （时加载到与桌面应用程序相比的 Windows 应用商店应用） 时不同。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-253">But certainly the behavior will be different every time your Profiler DLL (when loaded into a Windows Store app as compared to a desktop app) tries to access any resources.</span></span> <span data-ttu-id="7d9ff-254">文件系统是最常见的例子。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-254">The file system is the most common example.</span></span> <span data-ttu-id="7d9ff-255">存在但在给定的 Windows 应用商店应用程序有权访问的磁盘上放置几个 (请参阅[文件的访问和权限 (Windows 运行时应用](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx))，并且您 Profiler 的 DLL 将相同的限制。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-255">There are but a few places on disk that a given Windows Store app is allowed to access (see [File access and permissions (Windows Runtime apps](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)), and your Profiler DLL will be under the same restrictions.</span></span> <span data-ttu-id="7d9ff-256">进行全面测试您的代码。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-256">Test your code thoroughly.</span></span>

### <a name="inter-process-communication"></a><span data-ttu-id="7d9ff-257">进程间通信</span><span class="sxs-lookup"><span data-stu-id="7d9ff-257">Inter-process communication</span></span>

<span data-ttu-id="7d9ff-258">在本白皮书开头图中所示，Profiler DLL （加载到 Windows 应用商店应用程序进程空间） 可能需要与你 Profiler 的 UI （在单独的桌面应用程序进程空间中运行） 通过你自己自定义进程间通信通信 (IPC) 通道。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-258">As shown in the diagram at the beginning of this paper, your Profiler DLL (loaded into the Windows Store app process space) will likely need to communicate with your Profiler UI (running in a separate desktop app process space) through your own custom inter-process communication (IPC) channel.</span></span> <span data-ttu-id="7d9ff-259">Profiler UI 将信号发送到要修改其行为的 Profiler DLL 和 Profiler DLL 将数据从已分析 Windows 应用商店应用发送回用于后续处理和向探查器用户显示的 Profiler UI。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-259">The Profiler UI sends signals to the Profiler DLL to modify its behavior, and the Profiler DLL sends data from the analyzed Windows Store app back to the Profiler UI for post-processing and displaying to the profiler user.</span></span>

<span data-ttu-id="7d9ff-260">大多数探查器需要处理这种方式，但您的 IPC 机制为选择限制更多 Profiler DLL 加载到 Windows 应用商店应用程序时。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-260">Most profilers need to work this way, but your choices for IPC mechanisms are more limited when your Profiler DLL is loaded into a Windows Store app.</span></span> <span data-ttu-id="7d9ff-261">例如，命名的管道不属于 Windows 应用商店应用程序 SDK，因此不能使用它们。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-261">For example, named pipes are not part of the Windows Store app SDK, so you cannot use them.</span></span>

<span data-ttu-id="7d9ff-262">但毫无疑问，文件仍在中，但以限制更多的方式。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-262">But of course, files are still in, albeit in a more limited fashion.</span></span> <span data-ttu-id="7d9ff-263">此外，还提供事件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-263">Events are also available.</span></span>

<span data-ttu-id="7d9ff-264">**通过文件进行通信**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-264">**Communicating via files**</span></span>

<span data-ttu-id="7d9ff-265">大部分数据将通过文件可能传递 Profiler DLL 和 Profiler UI 之间。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-265">Most of your data will likely pass between the Profiler DLL and Profiler UI via files.</span></span> <span data-ttu-id="7d9ff-266">关键是要选取你 Profiler DLL （在 Windows 应用商店应用的上下文中） 和 Profiler UI 具有读取的文件位置和写入访问权限。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-266">The key is to pick a file location that both your Profiler DLL (in the context of a Windows Store app) and Profiler UI have read and write access to.</span></span> <span data-ttu-id="7d9ff-267">例如，临时文件夹的路径是一个位置，可以访问您的 Profiler DLL 和 Profiler UI，但没有其他 Windows 应用商店应用程序包可以访问 （从而避免登录其他 Windows 应用商店应用包中的任何信息）。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-267">For example, the Temporary Folder path is a location that both your Profiler DLL and Profiler UI can access, but no other Windows Store app package can access (thus shielding any information you log from other Windows Store app packages).</span></span>

<span data-ttu-id="7d9ff-268">在 Profiler UI 和 Profiler DLL 可以独立地确定此路径。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-268">Both your Profiler UI and Profiler DLL can determine this path independently.</span></span> <span data-ttu-id="7d9ff-269">在 Profiler 用户界面，它循环访问所有为当前用户安装的包 （请参阅前面的示例代码），获取的访问权限`PackageId`类，类似于此代码段中的代码与派生的临时文件夹路径。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-269">Your Profiler UI, when it iterates through all packages installed for the current user (see the sample code earlier), gets access to the `PackageId` class, from which the Temporary Folder path can be derived with code similar to this snippet.</span></span> <span data-ttu-id="7d9ff-270">（与往常一样，错误检查省略了为简洁起见。）</span><span class="sxs-lookup"><span data-stu-id="7d9ff-270">(As always, error checking is omitted for brevity.)</span></span>

```csharp
// C# code for the Profiler UI.
ApplicationData appData =
    ApplicationDataManager.CreateForPackageFamily(
        packageId.FamilyName);

tempDir = appData.TemporaryFolder.Path;
```

<span data-ttu-id="7d9ff-271">同时，Profiler DLL 可以执行基本上是相同的操作，但它可以更多轻松地访问[ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx)通过使用类[ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx)属性。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-271">Meanwhile, your Profiler DLL can do basically the same thing, though it can more easily get to the [ApplicationData](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.aspx) class by using the [ApplicationData.Current](https://msdn.microsoft.com/library/windows/apps/windows.storage.applicationdata.current.aspx) property.</span></span>

<span data-ttu-id="7d9ff-272">**通过事件进行通信**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-272">**Communicating via events**</span></span>

<span data-ttu-id="7d9ff-273">如果你想在 Profiler UI 和 Profiler DLL 之间的简单信号语义，可以使用 Windows 应用商店应用程序，以及桌面应用程序内的事件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-273">If you want simple signaling semantics between your Profiler UI and Profiler DLL, you can use events inside Windows Store apps as well as desktop apps.</span></span>

<span data-ttu-id="7d9ff-274">从 Profiler DLL，只需调用[CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa)函数以使用任何喜欢的名称创建命名的事件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-274">From your Profiler DLL, you can simply call the [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa) function to create a named event with any name you like.</span></span> <span data-ttu-id="7d9ff-275">例如：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-275">For example:</span></span>

```cpp
// Profiler DLL in Windows Store app (C++).
CreateEventEx(
    NULL,  // Not inherited
    "MyNamedEvent"
    CREATE_EVENT_MANUAL_RESET, /* explicit ResetEvent() required; leave initial state unsignaled */
    EVENT_ALL_ACCESS);
```

<span data-ttu-id="7d9ff-276">Profiler UI 然后需要查找 Windows 应用商店应用程序的命名空间下该命名的事件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-276">Your Profiler UI then needs to find that named event under the Windows Store app’s namespace.</span></span> <span data-ttu-id="7d9ff-277">例如，可以调用 Profiler UI [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa)，指定为事件名称</span><span class="sxs-lookup"><span data-stu-id="7d9ff-277">For example, your Profiler UI could call [CreateEventEx](/windows/desktop/api/synchapi/nf-synchapi-createeventexa), specifying the event name as</span></span>

`AppContainerNamedObjects\<acSid>\MyNamedEvent`

<span data-ttu-id="7d9ff-278">`<acSid>` 为 Windows 应用商店应用程序的 AppContainer SID。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-278">`<acSid>` is the Windows Store app’s AppContainer SID.</span></span> <span data-ttu-id="7d9ff-279">本主题前面部分介绍了如何循环访问当前用户安装的包。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-279">An earlier section of this topic showed how to iterate over the packages installed for the current user.</span></span> <span data-ttu-id="7d9ff-280">从该示例代码中，你可以获取包 Id。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-280">From that sample code, you can obtain the packageId.</span></span> <span data-ttu-id="7d9ff-281">你可以从包 Id，获取和`<acSid>`，类似于以下代码：</span><span class="sxs-lookup"><span data-stu-id="7d9ff-281">And from the packageId, you can obtain the `<acSid>` with code similar to the following:</span></span>

```csharp
IntPtr acPSID;
DeriveAppContainerSidFromAppContainerName(packageId.FamilyName, out acPSID);

string acSid;
ConvertSidToStringSid(acPSID, out acSid);

string acDir;
GetAppContainerFolderPath(acSid, out acDir);
```

### <a name="no-shutdown-notifications"></a><span data-ttu-id="7d9ff-282">没有关闭通知</span><span class="sxs-lookup"><span data-stu-id="7d9ff-282">No shutdown notifications</span></span>

<span data-ttu-id="7d9ff-283">运行时在 Windows 应用商店应用程序内，Profiler DLL 不应依赖于任一[icorprofilercallback:: Shutdown](icorprofilercallback-shutdown-method.md)甚至[DllMain](/windows/desktop/Dlls/dllmain) (使用`DLL_PROCESS_DETACH`) 正在调用以通知 Profiler DLL正在退出 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-283">When running inside a Windows Store app, your Profiler DLL should not rely on either [ICorProfilerCallback::Shutdown](icorprofilercallback-shutdown-method.md) or even [DllMain](/windows/desktop/Dlls/dllmain) (with `DLL_PROCESS_DETACH`) being called to notify your Profiler DLL that the Windows Store app is exiting.</span></span> <span data-ttu-id="7d9ff-284">事实上，应该会永远不会调用。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-284">In fact, you should expect they will never be called.</span></span> <span data-ttu-id="7d9ff-285">从历史上看，许多 Profiler Dll 使用这些通知作为方便的位置以刷新缓存磁盘、 关闭文件，将通知发送回的 Profiler UI，等等。但现在需要稍有不同组织 Profiler DLL。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-285">Historically, many Profiler DLLs have used those notifications as convenient places to flush caches to disk, close files, send notifications back to the Profiler UI, etc. But now your Profiler DLL needs to be organized a little differently.</span></span>

<span data-ttu-id="7d9ff-286">Profiler DLL 时对其应为日志记录信息。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-286">Your Profiler DLL should be logging information as it goes.</span></span> <span data-ttu-id="7d9ff-287">出于性能原因，你可能想要批处理在内存中的信息，然后刷新到磁盘大小超过某个阈值批处理随着。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-287">For performance reasons, you may want to batch information in memory and flush it to disk as the batch grows in size past some threshold.</span></span> <span data-ttu-id="7d9ff-288">但假设尚未刷新到磁盘的任何信息可能会丢失。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-288">But assume that any information not yet flushed to disk can be lost.</span></span> <span data-ttu-id="7d9ff-289">这意味着您需要明智地，选取你的阈值，Profiler UI 需要强制应对编写的 Profiler DLL 的信息不完整。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-289">This means you’ll want to pick your threshold wisely, and that your Profiler UI needs to be hardened to deal with incomplete information written by the Profiler DLL.</span></span>

## <a name="windows-runtime-metadata-files"></a><span data-ttu-id="7d9ff-290">Windows 运行时元数据文件</span><span class="sxs-lookup"><span data-stu-id="7d9ff-290">Windows Runtime metadata files</span></span>

<span data-ttu-id="7d9ff-291">它是深入介绍本文档的讨论范围内哪些 Windows 运行时元数据 (WinMD) 文件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-291">It is outside the scope of this document to go into detail on what Windows Runtime metadata (WinMD) files are.</span></span> <span data-ttu-id="7d9ff-292">本部分仅限于 CLR 分析 API 在 WinMD 文件加载的 Profiler DLL 分析 Windows 应用商店应用程序时的反应。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-292">This section is limited to how the CLR Profiling API reacts when WinMD files are loaded by the Windows Store app your Profiler DLL is analyzing.</span></span>

### <a name="managed-and-non-managed-winmds"></a><span data-ttu-id="7d9ff-293">托管和非托管 Winmd</span><span class="sxs-lookup"><span data-stu-id="7d9ff-293">Managed and non-managed WinMDs</span></span>

<span data-ttu-id="7d9ff-294">如果开发人员使用 Visual Studio 创建新的 Windows 运行时组件项目，该项目的生成过程生成 WinMD 文件，描述由开发人员编写的元数据 （类、 接口等的类型说明）。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-294">If a developer uses Visual Studio to create a new Windows Runtime Component project, a build of that project produces a WinMD file that describes the metadata (the type descriptions of classes, interfaces, etc.) authored by the developer.</span></span> <span data-ttu-id="7d9ff-295">如果此项目是用 C# 或 VB 编写的托管的语言项目，该相同的 WinMD 文件还包含这些类型 （它包含所有从开发人员的源代码编译的 IL 的含义） 的实现。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-295">If this project is a managed language project written in C# or VB, that same WinMD file also contains the implementation of those types (meaning that it contains all the IL compiled from the developer’s source code).</span></span> <span data-ttu-id="7d9ff-296">此类文件称为托管 WinMD 文件。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-296">Such files are known as managed WinMD files.</span></span> <span data-ttu-id="7d9ff-297">它们是有趣，因为它们包含 Windows 运行时元数据和基础实现。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-297">They're interesting in that they contain both Windows Runtime metadata and the underlying implementation.</span></span>

<span data-ttu-id="7d9ff-298">与此相反，如果开发人员的 c + + 创建 Windows 运行时组件项目，生成该项目生成包含仅元数据的 WinMD 文件，并实现编译为单独的本机 DLL。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-298">In contrast, if a developer creates a Windows Runtime Component project for C++, a build of that project produces a WinMD file that contains only metadata, and the implementation is compiled into a separate native DLL.</span></span> <span data-ttu-id="7d9ff-299">同样，在 Windows SDK 中提供的 WinMD 文件包含仅元数据编译到单独的本机 Dll 作为 Windows 的一部分提供的实现。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-299">Similarly, the WinMD files that ship in the Windows SDK contain only metadata, with the implementation compiled into separate native DLLs that ship as part of Windows.</span></span>

<span data-ttu-id="7d9ff-300">下面的信息适用于包含元数据和实现，这两个托管 Winmd 和非托管 Winmd，其中包含仅元数据。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-300">The information below applies to both managed WinMDs, which contain metadata and implementation, and to non-managed WinMDs, which contain only metadata.</span></span>

### <a name="winmd-files-look-like-clr-modules"></a><span data-ttu-id="7d9ff-301">WinMD 文件看起来像 CLR 模块</span><span class="sxs-lookup"><span data-stu-id="7d9ff-301">WinMD files look like CLR modules</span></span>

<span data-ttu-id="7d9ff-302">CLR 是而言，所有 WinMD 文件都是模块。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-302">As far as the CLR is concerned, all WinMD files are modules.</span></span> <span data-ttu-id="7d9ff-303">在 Profiler DLL 时加载 WinMD 文件和其 Moduleid 中有哪些，其他托管模块时一样，因此能够告知 CLR 分析 API。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-303">The CLR Profiling API therefore tells your Profiler DLL when WinMD files load and what their ModuleIDs are, in the same way as for other managed modules.</span></span>

<span data-ttu-id="7d9ff-304">Profiler DLL 可以通过调用从其他模块区分 WinMD 文件[ICorProfilerInfo3::GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md)方法，并检查`pdwModuleFlags`输出参数[COR_PRF_MODULE_WINDOWS_运行时](cor-prf-module-flags-enumeration.md)标志。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-304">Your Profiler DLL can distinguish WinMD files from other modules by calling the [ICorProfilerInfo3::GetModuleInfo2](icorprofilerinfo3-getmoduleinfo2-method.md) method and inspecting the `pdwModuleFlags` output parameter for the [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) flag.</span></span> <span data-ttu-id="7d9ff-305">（是设置当且仅当 ModuleID 表示 WinMD。）</span><span class="sxs-lookup"><span data-stu-id="7d9ff-305">(It’s set if and only if the ModuleID represents a WinMD.)</span></span>

### <a name="reading-metadata-from-winmds"></a><span data-ttu-id="7d9ff-306">从 Winmd 读取元数据</span><span class="sxs-lookup"><span data-stu-id="7d9ff-306">Reading metadata from WinMDs</span></span>

<span data-ttu-id="7d9ff-307">WinMD 文件，类似于常规模块包含可通过读取的元数据[元数据 Api](../../../../docs/framework/unmanaged-api/metadata/index.md)。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-307">WinMD files, like regular modules, contain metadata that can be read via the [Metadata APIs](../../../../docs/framework/unmanaged-api/metadata/index.md).</span></span> <span data-ttu-id="7d9ff-308">但是，CLR 将 Windows 运行时类型到.NET Framework 类型时它会读取 WinMD 文件，以便开发人员可以在托管代码中进行编程和使用 WinMD 文件可以更自然的编程体验。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-308">However, the CLR maps Windows Runtime types to .NET Framework types when it reads WinMD files so that developers who program in managed code and consume the WinMD file can have a more natural programming experience.</span></span> <span data-ttu-id="7d9ff-309">有关这些映射的一些示例，请参阅[.NET Framework 支持的 Windows 应用商店应用程序和 Windows 运行时](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-309">For some examples of these mappings, see [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md).</span></span>

<span data-ttu-id="7d9ff-310">因此哪种视图在探查器时，将看到它使用元数据 Api： 原始的 Windows 运行时视图或映射的.NET Framework 视图？</span><span class="sxs-lookup"><span data-stu-id="7d9ff-310">So which view will your profiler get when it uses the metadata APIs: the raw Windows Runtime view, or the mapped .NET Framework view?</span></span>  <span data-ttu-id="7d9ff-311">答案： 完全取决于您。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-311">The answer: it’s up to you.</span></span>

<span data-ttu-id="7d9ff-312">当您调用[icorprofilerinfo:: Getmodulemetadata](icorprofilerinfo-getmodulemetadata-method.md)方法获取元数据接口，例如 WinMD [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)，你可以选择设置[ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)中`dwOpenFlags`参数来关闭此映射。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-312">When you call the [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) method on a WinMD to obtain a metadata interface, such as [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md),  you can choose to set [ofNoTransform](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) in the `dwOpenFlags` parameter to turn off this mapping.</span></span> <span data-ttu-id="7d9ff-313">否则，默认情况下将启用此映射。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-313">Otherwise, by default, the mapping will be enabled.</span></span> <span data-ttu-id="7d9ff-314">通常情况下，探查器将保持启用，该映射，以便从 WinMD 元数据 （例如，类型的名称） 获取 Profiler DLL 的字符串看起来熟悉和自然向探查器用户。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-314">Typically, a profiler will keep the mapping enabled, so that the strings that the Profiler DLL obtains from the WinMD metadata (for example, names of types) will look familiar and natural to the profiler user.</span></span>

### <a name="modifying-metadata-from-winmds"></a><span data-ttu-id="7d9ff-315">修改从 Winmd 元数据</span><span class="sxs-lookup"><span data-stu-id="7d9ff-315">Modifying metadata from WinMDs</span></span>

<span data-ttu-id="7d9ff-316">不支持修改中 Winmd 元数据。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-316">Modifying metadata in WinMDs is not supported.</span></span> <span data-ttu-id="7d9ff-317">如果您调用[icorprofilerinfo:: Getmodulemetadata](icorprofilerinfo-getmodulemetadata-method.md)方法的 WinMD 文件，并指定[ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md)中`dwOpenFlags`参数或可写元数据接口提出，例如[IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)， [GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md)将失败。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-317">If you call the [ICorProfilerInfo::GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) method for a WinMD file and specify [ofWrite](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) in the `dwOpenFlags` parameter or ask for a writeable metadata interface such as [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md), [GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md) will fail.</span></span> <span data-ttu-id="7d9ff-318">这是于 IL 重写的探查器需要修改元数据以支持其检测 （例如，若要添加 AssemblyRefs 或新的方法） 尤其重要。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-318">This is of particular importance to IL-rewriting profilers, which need to modify metadata to support their instrumentation (for example, to add AssemblyRefs or new methods).</span></span> <span data-ttu-id="7d9ff-319">因此，应检查[COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md)首先 （如在上一节中讨论） 并避免在要求可写元数据接口提供对此类模块。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-319">So you should check for [COR_PRF_MODULE_WINDOWS_RUNTIME](cor-prf-module-flags-enumeration.md) first (as discussed in the previous section) and refrain from asking for writeable metadata interfaces on such modules.</span></span>

### <a name="resolving-assembly-references-with-winmds"></a><span data-ttu-id="7d9ff-320">解析与 Winmd 的程序集引用</span><span class="sxs-lookup"><span data-stu-id="7d9ff-320">Resolving assembly references with WinMDs</span></span>

<span data-ttu-id="7d9ff-321">对于许多探查器需要解析元数据引用手动以帮助检测或类型检查。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-321">Many profilers need to resolve metadata references manually to aid with instrumentation or type inspection.</span></span> <span data-ttu-id="7d9ff-322">此类探查器需要了解的 CLR 如何解析指向 Winmd，程序集引用，因为在标准的程序集引用完全不同的方式解析这些引用。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-322">Such profilers need to be aware of how the CLR resolves assembly references that point to WinMDs, because those references are resolved in a completely different way than standard assembly references.</span></span>

## <a name="memory-profilers"></a><span data-ttu-id="7d9ff-323">内存探查器</span><span class="sxs-lookup"><span data-stu-id="7d9ff-323">Memory profilers</span></span>

<span data-ttu-id="7d9ff-324">垃圾回收器和托管的堆不完全不同的 Windows 应用商店应用和桌面应用程序中。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-324">The garbage collector and managed heap are not fundamentally different in a Windows Store app and a desktop app.</span></span> <span data-ttu-id="7d9ff-325">但是，有一些细微的差异，探查器作者需要注意。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-325">However, there are some subtle differences that profiler authors need to be aware of.</span></span>

### <a name="forcegc-creates-a-managed-thread"></a><span data-ttu-id="7d9ff-326">ForceGC 创建托管的线程</span><span class="sxs-lookup"><span data-stu-id="7d9ff-326">ForceGC creates a managed thread</span></span>

<span data-ttu-id="7d9ff-327">Profiler DLL 时执行操作的内存分析，通常创建一个单独的线程从其调用[ForceGC 方法](icorprofilerinfo-forcegc-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-327">When doing memory profiling, your Profiler DLL typically creates a separate thread from which to call the [ForceGC Method](icorprofilerinfo-forcegc-method.md) method.</span></span> <span data-ttu-id="7d9ff-328">这是什么新鲜事物。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-328">This is nothing new.</span></span> <span data-ttu-id="7d9ff-329">但什么可能会感到惊讶是执行垃圾回收中的 Windows 应用商店应用的行为可能会将你的线程转换为托管线程 （例如，分析 API ThreadID 将为该线程创建）。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-329">But what might be surprising is that the act of doing a garbage collection inside a Windows Store app may transform your thread into a managed thread (for example, a Profiling API ThreadID will be created for that thread).</span></span>

<span data-ttu-id="7d9ff-330">若要了解这一后果，务必了解同步和异步调用之间的差异，由 CLR 分析 API 定义。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-330">To understand the consequences of this, it’s important to understand the differences between synchronous and asynchronous calls as defined by the CLR Profiling API.</span></span> <span data-ttu-id="7d9ff-331">请注意，这是从 Windows 应用商店应用中的异步调用的概念非常不同。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-331">Note that this is very different from the concept of asynchronous calls in Windows Store apps.</span></span> <span data-ttu-id="7d9ff-332">请参阅博客文章[我们使用了 CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/)有关详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-332">See the blog post [Why we have CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://blogs.msdn.microsoft.com/davbr/2008/12/23/why-we-have-corprof_e_unsupported_call_sequence/) for more information.</span></span>

<span data-ttu-id="7d9ff-333">相关的问题是，由探查器创建的线程上进行的调用，总是会考虑同步的即使这些调用都是从外部的 Profiler DLL 的一个实现[ICorProfilerCallback](icorprofilercallback-interface.md)方法。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-333">The relevant point is that calls made on threads created by your profiler are always considered synchronous, even if those calls are made from outside an implementation of one of your Profiler DLL’s [ICorProfilerCallback](icorprofilercallback-interface.md) methods.</span></span> <span data-ttu-id="7d9ff-334">至少，它用于出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-334">At least, that used to be the case.</span></span> <span data-ttu-id="7d9ff-335">现在，CLR 已启用探查器的线程到托管线程对的调用由于[ForceGC 方法](icorprofilerinfo-forcegc-method.md)，线程将不再被视为探查器的线程。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-335">Now that the CLR has turned your profiler’s thread into a managed thread because of your call to [ForceGC Method](icorprofilerinfo-forcegc-method.md), that thread is no longer considered your profiler’s thread.</span></span> <span data-ttu-id="7d9ff-336">在这种情况下，CLR 强制实施更严格的什么限定为该线程同步定义 — 即的调用必须源自的 Profiler DLL 的一个[ICorProfilerCallback](icorprofilercallback-interface.md)限定为同步的方法。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-336">As such, the CLR enforces a more stringent definition of what qualifies as synchronous for that thread—namely that a call must originate from inside one of your Profiler DLL’s [ICorProfilerCallback](icorprofilercallback-interface.md) methods to qualify as synchronous.</span></span>

<span data-ttu-id="7d9ff-337">在实践中，这意味着什么？</span><span class="sxs-lookup"><span data-stu-id="7d9ff-337">What does this mean in practice?</span></span> <span data-ttu-id="7d9ff-338">大多数[ICorProfilerInfo](icorprofilerinfo-interface.md)仅安全地同步，调用方法，否则将立即失败。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-338">Most [ICorProfilerInfo](icorprofilerinfo-interface.md) methods are only safe to be called synchronously, and will immediately fail otherwise.</span></span> <span data-ttu-id="7d9ff-339">因此，如果 Profiler DLL 重用您[ForceGC 方法](icorprofilerinfo-forcegc-method.md)探查器创建的线程通常由其他调用的线程 (例如，若[RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)， [RequestReJIT](icorprofilerinfo4-requestrejit-method.md)，或[RequestRevert](icorprofilerinfo4-requestrevert-method.md))，您会遇到问题。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-339">So if your Profiler DLL reuses your [ForceGC Method](icorprofilerinfo-forcegc-method.md) thread for other calls typically made on profiler-created threads (for example, to [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md), [RequestReJIT](icorprofilerinfo4-requestrejit-method.md), or [RequestRevert](icorprofilerinfo4-requestrevert-method.md)), you’re going to have trouble.</span></span> <span data-ttu-id="7d9ff-340">甚至如异步安全函数[DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)已从托管线程中调用时的特殊规则。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-340">Even an asynchronous-safe function such as [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md) has special rules when called from managed threads.</span></span> <span data-ttu-id="7d9ff-341">(请参阅博客文章[Profiler 堆栈遍历： 基础知识及更高版本](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/)有关详细信息。)</span><span class="sxs-lookup"><span data-stu-id="7d9ff-341">(See the blog post [Profiler stack walking: Basics and beyond](https://blogs.msdn.microsoft.com/davbr/2005/10/06/profiler-stack-walking-basics-and-beyond/) for more information.)</span></span>

<span data-ttu-id="7d9ff-342">因此，我们建议您 Profiler 的 DLL 创建，以便在调用任何线程[ForceGC 方法](icorprofilerinfo-forcegc-method.md)应使用*仅*为了触发 Gc，然后响应 GC 回调。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-342">Therefore, we recommend that any thread your Profiler DLL creates to call [ForceGC Method](icorprofilerinfo-forcegc-method.md) should be used *only* for the purpose of triggering GCs and then responding to the GC callbacks.</span></span> <span data-ttu-id="7d9ff-343">它不应调用到分析 API 来执行其他任务，例如采样或分离的堆栈。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-343">It should not call into the Profiling API to perform other tasks like stack sampling or detaching.</span></span>

### <a name="conditionalweaktablereferences"></a><span data-ttu-id="7d9ff-344">ConditionalWeakTableReferences</span><span class="sxs-lookup"><span data-stu-id="7d9ff-344">ConditionalWeakTableReferences</span></span>

<span data-ttu-id="7d9ff-345">从.NET Framework 4.5 开始，还有一个新的 GC 回调[ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md)，其中给出了探查器有关的更完整信息*依赖句柄*。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-345">Starting with the .NET Framework 4.5, there is a new GC callback, [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md), which gives the profiler more complete information about *dependent handles*.</span></span> <span data-ttu-id="7d9ff-346">这些句柄有效地将引用从源对象添加到以进行 GC 生存期管理的目标对象。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-346">These handles effectively add a reference from a source object to a target object for the purpose of GC lifetime management.</span></span> <span data-ttu-id="7d9ff-347">依赖句柄是什么新鲜事物，并在托管代码中进行编程的开发人员就能够通过创建其自己的依赖句柄<xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType>甚至在 Windows 8 和.NET Framework 4.5 之前的类。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-347">Dependent handles are nothing new, and developers who program in managed code have been able to create their own dependent handles by using the <xref:System.Runtime.CompilerServices.ConditionalWeakTable%602?displayProperty=nameWithType> class even before Windows 8 and the .NET Framework 4.5.</span></span>

<span data-ttu-id="7d9ff-348">但是，托管的 XAML Windows 应用商店应用程序现在进行大量使用依赖句柄。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-348">However, managed XAML Windows Store apps now make heavy use of dependent handles.</span></span> <span data-ttu-id="7d9ff-349">具体而言，CLR 使用它们来帮助管理托管的对象和非托管的 Windows 运行时对象之间的引用循环。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-349">In particular, the CLR uses them to aid with managing reference cycles between managed objects and unmanaged Windows Runtime objects.</span></span> <span data-ttu-id="7d9ff-350">这意味着它是比更重要现在前所未有的内存探查器，以了解这些依赖句柄，以便它们可以可视化，其余部分的堆关系图中的边缘。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-350">This means that it’s more important now than ever for memory profilers to be informed of these dependent handles so that they can be visualized along with the rest of the edges in the heap graph.</span></span> <span data-ttu-id="7d9ff-351">应使用 Profiler DLL [RootReferences2](icorprofilercallback2-rootreferences2-method.md)， [ObjectReferences](icorprofilercallback-objectreferences-method.md)，并[ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md)一起以形成一个完整的堆关系图视图.</span><span class="sxs-lookup"><span data-stu-id="7d9ff-351">Your Profiler DLL should use [RootReferences2](icorprofilercallback2-rootreferences2-method.md), [ObjectReferences](icorprofilercallback-objectreferences-method.md), and [ConditionalWeakTableElementReferences](icorprofilercallback5-conditionalweaktableelementreferences-method.md) together to form a complete view of the heap graph.</span></span>

## <a name="conclusion"></a><span data-ttu-id="7d9ff-352">结束语</span><span class="sxs-lookup"><span data-stu-id="7d9ff-352">Conclusion</span></span>

<span data-ttu-id="7d9ff-353">就可以使用 CLR 分析 API 来分析 Windows 应用商店应用程序内运行的托管的代码。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-353">It is possible to use the CLR Profiling API to analyze managed code running inside Windows Store apps.</span></span> <span data-ttu-id="7d9ff-354">事实上，可以执行你正在开发的现有探查器并进行一些特定的更改，以便它可以针对 Windows 应用商店应用程序。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-354">In fact, you can take an existing profiler that you’re developing and make some specific changes so that it can target Windows Store apps.</span></span> <span data-ttu-id="7d9ff-355">Profiler UI 应使用新的 Api 来激活 Windows 应用商店应用程序在调试模式下。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-355">Your Profiler UI should use the new APIs for activating the Windows Store app in debugging mode.</span></span> <span data-ttu-id="7d9ff-356">请确保你 Profiler DLL 使用适用于 Windows 应用商店应用程序的这些 Api。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-356">Make sure that your Profiler DLL consumes only those APIs applicable for Windows Store apps.</span></span> <span data-ttu-id="7d9ff-357">与 Windows 应用商店应用 API 限制记住和意识的现有 Windows 应用商店应用程序的受限权限，则应编写 Profiler DLL 和 Profiler UI 之间的通信机制。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-357">The communication mechanism between your Profiler DLL and Profiler UI should be written with the Windows Store app API restrictions in mind and with awareness of the restricted permissions in place for Windows Store apps.</span></span> <span data-ttu-id="7d9ff-358">Profiler DLL 必须了解 CLR 如何处理 Winmd，以及垃圾回收器的行为与托管线程不同。</span><span class="sxs-lookup"><span data-stu-id="7d9ff-358">Your Profiler DLL should be aware of how the CLR treats WinMDs, and how the Garbage Collector’s behavior is different with respect to managed threads.</span></span>

## <a name="resources"></a><span data-ttu-id="7d9ff-359">资源</span><span class="sxs-lookup"><span data-stu-id="7d9ff-359">Resources</span></span>

<span data-ttu-id="7d9ff-360">**公共语言运行时**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-360">**The Common Language Runtime**</span></span>

- [<span data-ttu-id="7d9ff-361">分析 （非托管的 API 参考）</span><span class="sxs-lookup"><span data-stu-id="7d9ff-361">Profiling (Unmanaged API Reference)</span></span>](index.md)

- [<span data-ttu-id="7d9ff-362">元数据 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="7d9ff-362">Metadata (Unmanaged API Reference)</span></span>](../metadata/index.md)

<span data-ttu-id="7d9ff-363">**与 Windows 运行时的 CLR 的交互**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-363">**The CLR's interaction with the Windows Runtime**</span></span>

- [<span data-ttu-id="7d9ff-364">.NET Framework 对 Windows 应用商店应用和 Windows 运行时的支持情况</span><span class="sxs-lookup"><span data-stu-id="7d9ff-364">.NET Framework Support for Windows Store Apps and Windows Runtime</span></span>](../../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md)

<span data-ttu-id="7d9ff-365">**Windows 应用商店应用**</span><span class="sxs-lookup"><span data-stu-id="7d9ff-365">**Windows Store apps**</span></span>

- [<span data-ttu-id="7d9ff-366">文件访问和权限 （Windows 运行时应用</span><span class="sxs-lookup"><span data-stu-id="7d9ff-366">File access and permissions (Windows Runtime apps</span></span>](https://msdn.microsoft.com/library/windows/apps/hh967755.aspx)

- [<span data-ttu-id="7d9ff-367">获取开发人员许可证</span><span class="sxs-lookup"><span data-stu-id="7d9ff-367">Get a developer license</span></span>](https://msdn.microsoft.com/library/windows/apps/Hh974578.aspx)

- <span data-ttu-id="7d9ff-368">[IPackageDebugSettings 接口](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7d9ff-368">[IPackageDebugSettings Interface](https://msdn.microsoft.com/library/hh438393\(v=vs.85\).aspx)</span></span>
