---
title: .NET Core 上不支持的 API
description: 了解 .NET Framework 中始终在 .NET Core 上引发异常的 API。
ms.date: 12/23/2019
ms.openlocfilehash: 0cb533f10d53fd3d287265032e3de13c242a8ae0
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901342"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="2933e-103">始终在 .NET Core 上引发异常的 API</span><span class="sxs-lookup"><span data-stu-id="2933e-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="2933e-104">以下 API 在指定平台的 .NET Core 上运行时将始终通过 <xref:System.PlatformNotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="2933e-104">The following APIs will always through a <xref:System.PlatformNotSupportedException> when run on .NET Core on the specified platform.</span></span>

<span data-ttu-id="2933e-105">本文按命名空间组织受影响的 API 成员。</span><span class="sxs-lookup"><span data-stu-id="2933e-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="2933e-106">本文是当前正在进行的工作。</span><span class="sxs-lookup"><span data-stu-id="2933e-106">This article is a work-in-progress.</span></span> <span data-ttu-id="2933e-107">它不是在 .NET Core 上引发异常的 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="2933e-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="2933e-108">本文不包括在 .NET Core 上引发的二进制序列化的显式接口实现。</span><span class="sxs-lookup"><span data-stu-id="2933e-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="2933e-109">有关详细信息，请参阅 [.NET Core 中的二进制序列化](../../standard/serialization/binary-serialization.md#net-core)。</span><span class="sxs-lookup"><span data-stu-id="2933e-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="2933e-110">System</span><span class="sxs-lookup"><span data-stu-id="2933e-110">System</span></span>

| <span data-ttu-id="2933e-111">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-111">Member</span></span> | <span data-ttu-id="2933e-112">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-112">Platform</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-113">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="2933e-114">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="2933e-115">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="2933e-116">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-117">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="2933e-118">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="2933e-119">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="2933e-120">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-121">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="2933e-122">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="2933e-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="2933e-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="2933e-124">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-124">Member</span></span> | <span data-ttu-id="2933e-125">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-125">Platform</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-126">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-127">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-128">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="2933e-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="2933e-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="2933e-130">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-130">Member</span></span> | <span data-ttu-id="2933e-131">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-131">Platform</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-132">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-133">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="2933e-134">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="2933e-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="2933e-135">System.Configuration</span></span>

| <span data-ttu-id="2933e-136">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-136">Member</span></span> | <span data-ttu-id="2933e-137">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-137">Platform</span></span> |
| - | - |
| <span data-ttu-id="2933e-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>（所有成员）</span><span class="sxs-lookup"><span data-stu-id="2933e-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="2933e-139">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="2933e-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="2933e-140">System.Console</span></span>

| <span data-ttu-id="2933e-141">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-141">Member</span></span> | <span data-ttu-id="2933e-142">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-142">Platform</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="2933e-143">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-143">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-145">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-145">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-147">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-147">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-149">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-149">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>（仅获取）</span><span class="sxs-lookup"><span data-stu-id="2933e-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="2933e-151">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-152">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-153">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-154">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-154">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-155"><xref:System.Console.Title?displayProperty=nameWithType>（仅获取）</span><span class="sxs-lookup"><span data-stu-id="2933e-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="2933e-156">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-156">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-158">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-158">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-160">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-160">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-162">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-162">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-164">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="2933e-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="2933e-165">System.Data.Common</span></span>

| <span data-ttu-id="2933e-166">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-166">Member</span></span> | <span data-ttu-id="2933e-167">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-167">Platform</span></span> |
| - | - |
| <span data-ttu-id="2933e-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>（引发 <xref:System.NotSupportedException>）</span><span class="sxs-lookup"><span data-stu-id="2933e-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="2933e-169">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="2933e-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="2933e-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="2933e-171">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-171">Member</span></span> | <span data-ttu-id="2933e-172">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-172">Platform</span></span> |
| - | - |
| <span data-ttu-id="2933e-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-174">Linux</span><span class="sxs-lookup"><span data-stu-id="2933e-174">Linux</span></span> |
| <span data-ttu-id="2933e-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-176">Linux</span><span class="sxs-lookup"><span data-stu-id="2933e-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="2933e-177">macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="2933e-178">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-179">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="2933e-180">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="2933e-181">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="2933e-182">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="2933e-183">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-183">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-185">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-185">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>（仅获取）</span><span class="sxs-lookup"><span data-stu-id="2933e-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="2933e-187">macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-187">macOS</span></span> |
| <span data-ttu-id="2933e-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-189">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="2933e-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="2933e-190">System.IO</span></span>

| <span data-ttu-id="2933e-191">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-191">Member</span></span> | <span data-ttu-id="2933e-192">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-192">Platform</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-193">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-194">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="2933e-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="2933e-195">System.IO.Pipes</span></span>

| <span data-ttu-id="2933e-196">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-196">Member</span></span> | <span data-ttu-id="2933e-197">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-197">Platform</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="2933e-198">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="2933e-199">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="2933e-200">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="2933e-201">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-201">Linux and macOS</span></span> |
| <span data-ttu-id="2933e-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-203">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="2933e-204">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="2933e-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="2933e-205">System.Media</span></span>

| <span data-ttu-id="2933e-206">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-206">Member</span></span> | <span data-ttu-id="2933e-207">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-207">Platform</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-208">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="2933e-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="2933e-209">System.Net</span></span>

| <span data-ttu-id="2933e-210">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-210">Member</span></span> | <span data-ttu-id="2933e-211">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-211">Platform</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="2933e-212">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="2933e-213">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-214">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-215">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-216">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-217">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-218">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-219">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-220">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-221">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-222">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="2933e-223">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-224">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-225">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-226">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-227">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-228">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="2933e-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="2933e-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="2933e-230">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-230">Member</span></span> | <span data-ttu-id="2933e-231">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-231">Platform</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="2933e-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="2933e-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="2933e-233">System.Net.Sockets</span></span>

| <span data-ttu-id="2933e-234">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-234">Member</span></span> | <span data-ttu-id="2933e-235">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-235">Platform</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="2933e-236">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-236">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="2933e-237">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="2933e-237">System.Net.WebSockets</span></span>

| <span data-ttu-id="2933e-238">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-238">Member</span></span> | <span data-ttu-id="2933e-239">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-239">Platform</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="2933e-240">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-240">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="2933e-241">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="2933e-241">System.Reflection</span></span>

| <span data-ttu-id="2933e-242">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-242">Member</span></span> | <span data-ttu-id="2933e-243">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-243">Platform</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-244">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-244">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-245">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-245">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-246">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="2933e-247">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-247">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-248">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-249">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="2933e-250">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-250">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="2933e-251">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="2933e-251">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="2933e-252">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-252">Member</span></span> | <span data-ttu-id="2933e-253">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-253">Platform</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="2933e-254">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-254">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="2933e-255">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="2933e-255">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="2933e-256">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-256">Member</span></span> | <span data-ttu-id="2933e-257">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-257">Platform</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="2933e-258">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-258">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="2933e-259">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="2933e-260">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="2933e-261">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-261">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-262">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-262">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="2933e-263">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="2933e-264">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-264">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="2933e-265">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="2933e-265">System.Runtime.Serialization</span></span>

| <span data-ttu-id="2933e-266">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-266">Member</span></span> | <span data-ttu-id="2933e-267">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-267">Platform</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="2933e-268">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-268">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="2933e-269">System.Security</span><span class="sxs-lookup"><span data-stu-id="2933e-269">System.Security</span></span>

| <span data-ttu-id="2933e-270">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-270">Member</span></span> | <span data-ttu-id="2933e-271">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-271">Platform</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="2933e-272">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-272">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="2933e-273">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-273">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-274">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-274">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="2933e-275">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-275">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="2933e-276">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-276">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="2933e-277">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-277">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="2933e-278">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-278">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="2933e-279">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-279">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="2933e-280">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="2933e-281">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-281">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="2933e-282">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-282">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="2933e-283">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-283">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="2933e-284">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="2933e-285">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-285">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="2933e-286">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="2933e-286">System.Security.Claims</span></span>

| <span data-ttu-id="2933e-287">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-287">Member</span></span> | <span data-ttu-id="2933e-288">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-288">Platform</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor?displayProperty=nameWithType> | <span data-ttu-id="2933e-289">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-289">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-290">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)?displayProperty=nameWithType> | <span data-ttu-id="2933e-291">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-292">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-293">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-293">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="2933e-294">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="2933e-294">System.Security.Cryptography</span></span>

| <span data-ttu-id="2933e-295">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-295">Member</span></span> | <span data-ttu-id="2933e-296">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-296">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-297">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-297">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-298">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-298">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="2933e-299">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="2933e-300">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="2933e-301">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="2933e-302">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="2933e-303">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="2933e-304">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="2933e-305">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="2933e-306">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="2933e-307">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="2933e-308">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="2933e-309">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="2933e-310">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="2933e-311">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-311">All</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-312">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="2933e-313">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-314">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-315">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-316">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-317">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="2933e-318">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-319">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-320">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-321">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="2933e-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-322">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-323">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="2933e-324">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="2933e-325">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="2933e-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="2933e-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="2933e-327">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-327">Member</span></span> | <span data-ttu-id="2933e-328">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-328">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)?displayProperty=nameWithType> | <span data-ttu-id="2933e-329">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="2933e-330">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="2933e-331">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="2933e-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="2933e-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="2933e-333">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-333">Member</span></span> | <span data-ttu-id="2933e-334">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-334">Platform</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-335">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-336">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-337">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-337">All</span></span> |
| <span data-ttu-id="2933e-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="2933e-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="2933e-339">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="2933e-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="2933e-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="2933e-341">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-341">Member</span></span> | <span data-ttu-id="2933e-342">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-342">Platform</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-343">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="2933e-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="2933e-344">System.Security.Policy</span></span>

| <span data-ttu-id="2933e-345">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-345">Member</span></span> | <span data-ttu-id="2933e-346">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-346">Platform</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-347">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="2933e-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="2933e-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="2933e-349">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-349">Member</span></span> | <span data-ttu-id="2933e-350">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-350">Platform</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-351">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="2933e-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="2933e-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="2933e-353">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-353">Member</span></span> | <span data-ttu-id="2933e-354">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-354">Platform</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-355">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="2933e-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="2933e-356">System.Threading</span></span>

| <span data-ttu-id="2933e-357">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-357">Member</span></span> | <span data-ttu-id="2933e-358">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-358">Platform</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-359">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="2933e-360">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="2933e-361">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="2933e-362">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="2933e-363">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="2933e-364">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="2933e-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="2933e-365">System.Xml</span></span>

| <span data-ttu-id="2933e-366">成员</span><span class="sxs-lookup"><span data-stu-id="2933e-366">Member</span></span> | <span data-ttu-id="2933e-367">Platform</span><span class="sxs-lookup"><span data-stu-id="2933e-367">Platform</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="2933e-368">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="2933e-369">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="2933e-370">全部</span><span class="sxs-lookup"><span data-stu-id="2933e-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="2933e-371">请参阅</span><span class="sxs-lookup"><span data-stu-id="2933e-371">See also</span></span>

- [<span data-ttu-id="2933e-372">从 .NET Framework 迁移到 .NET Core 的中断性变更</span><span class="sxs-lookup"><span data-stu-id="2933e-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="2933e-373">.NET Core 中的二进制序列化</span><span class="sxs-lookup"><span data-stu-id="2933e-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="2933e-374">.NET 可移植性分析器</span><span class="sxs-lookup"><span data-stu-id="2933e-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
