---
title: .NET Core 上不支持的 API
titleSuffix: ''
description: 了解 .NET Framework 中始终在 .NET Core 上引发异常的 API。
ms.date: 12/23/2019
ms.openlocfilehash: bd3516d9480ef42b6ea89825ba64867a3ca104e3
ms.sourcegitcommit: 7980a91f90ae5eca859db7e6bfa03e23e76a1a50
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "81242941"
---
# <a name="apis-that-always-throw-exceptions-on-net-core"></a><span data-ttu-id="0e345-103">始终在 .NET Core 上引发异常的 API</span><span class="sxs-lookup"><span data-stu-id="0e345-103">APIs that always throw exceptions on .NET Core</span></span>

<span data-ttu-id="0e345-104">以下 API 将始终在所有或部分平台上的 .NET Core 中引发 <xref:System.PlatformNotSupportedException>。</span><span class="sxs-lookup"><span data-stu-id="0e345-104">The following APIs will always throw a <xref:System.PlatformNotSupportedException> on .NET Core on all or a subset of platforms.</span></span>

<span data-ttu-id="0e345-105">本文按命名空间组织受影响的 API 成员。</span><span class="sxs-lookup"><span data-stu-id="0e345-105">This article organizes the affected API members by namespace.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="0e345-106">本文是当前正在进行的工作。</span><span class="sxs-lookup"><span data-stu-id="0e345-106">This article is a work-in-progress.</span></span> <span data-ttu-id="0e345-107">它不是在 .NET Core 上引发异常的 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="0e345-107">It is not a complete list of APIs that throw exceptions on .NET Core.</span></span>
> - <span data-ttu-id="0e345-108">本文不包括在 .NET Core 上引发的二进制序列化的显式接口实现。</span><span class="sxs-lookup"><span data-stu-id="0e345-108">This article does not include the explicit interface implementations for binary serialization that throw on .NET Core.</span></span> <span data-ttu-id="0e345-109">有关详细信息，请参阅 [.NET Core 中的二进制序列化](../../standard/serialization/binary-serialization.md#net-core)。</span><span class="sxs-lookup"><span data-stu-id="0e345-109">For more information, see [Binary serialization in .NET Core](../../standard/serialization/binary-serialization.md#net-core).</span></span>

## <a name="system"></a><span data-ttu-id="0e345-110">系统</span><span class="sxs-lookup"><span data-stu-id="0e345-110">System</span></span>

| <span data-ttu-id="0e345-111">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-111">Member</span></span> | <span data-ttu-id="0e345-112">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-112">Platforms that throw</span></span> |
| - | - |
| <xref:System.AppDomain.CreateDomain%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-113">All</span><span class="sxs-lookup"><span data-stu-id="0e345-113">All</span></span> |
| <xref:System.AppDomain.ExecuteAssembly(System.String,System.String[],System.Byte[],System.Configuration.Assemblies.AssemblyHashAlgorithm)?displayProperty=nameWithType> | <span data-ttu-id="0e345-114">All</span><span class="sxs-lookup"><span data-stu-id="0e345-114">All</span></span> |
| <xref:System.Console.CapsLock?displayProperty=nameWithType> | <span data-ttu-id="0e345-115">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-115">Linux and macOS</span></span> |
| <xref:System.Console.NumberLock?displayProperty=nameWithType> | <span data-ttu-id="0e345-116">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-116">Linux and macOS</span></span> |
| <xref:System.Delegate.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-117">All</span><span class="sxs-lookup"><span data-stu-id="0e345-117">All</span></span> |
| <xref:System.Exception.SerializeObjectState?displayProperty=nameWithType> | <span data-ttu-id="0e345-118">All</span><span class="sxs-lookup"><span data-stu-id="0e345-118">All</span></span> |
| <xref:System.MarshalByRefObject.GetLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0e345-119">All</span><span class="sxs-lookup"><span data-stu-id="0e345-119">All</span></span> |
| <xref:System.MarshalByRefObject.InitializeLifetimeService?displayProperty=nameWithType> | <span data-ttu-id="0e345-120">All</span><span class="sxs-lookup"><span data-stu-id="0e345-120">All</span></span> |
| <xref:System.OperatingSystem.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-121">All</span><span class="sxs-lookup"><span data-stu-id="0e345-121">All</span></span> |
| <xref:System.Type.ReflectionOnlyGetType(System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0e345-122">All</span><span class="sxs-lookup"><span data-stu-id="0e345-122">All</span></span> |

## <a name="systemcodedomcompiler"></a><span data-ttu-id="0e345-123">System.CodeDom.Compiler</span><span class="sxs-lookup"><span data-stu-id="0e345-123">System.CodeDom.Compiler</span></span>

| <span data-ttu-id="0e345-124">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-124">Member</span></span> | <span data-ttu-id="0e345-125">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-125">Platforms that throw</span></span> |
| - | - |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromDom%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-126">All</span><span class="sxs-lookup"><span data-stu-id="0e345-126">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromFile%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-127">All</span><span class="sxs-lookup"><span data-stu-id="0e345-127">All</span></span> |
| <xref:System.CodeDom.Compiler.CodeDomProvider.CompileAssemblyFromSource%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-128">All</span><span class="sxs-lookup"><span data-stu-id="0e345-128">All</span></span> |

## <a name="systemcollectionsspecialized"></a><span data-ttu-id="0e345-129">System.Collections.Specialized</span><span class="sxs-lookup"><span data-stu-id="0e345-129">System.Collections.Specialized</span></span>

| <span data-ttu-id="0e345-130">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-130">Member</span></span> | <span data-ttu-id="0e345-131">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-131">Platforms that throw</span></span> |
| - | - |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-132">All</span><span class="sxs-lookup"><span data-stu-id="0e345-132">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-133">All</span><span class="sxs-lookup"><span data-stu-id="0e345-133">All</span></span> |
| <xref:System.Collections.Specialized.NameObjectCollectionBase.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0e345-134">All</span><span class="sxs-lookup"><span data-stu-id="0e345-134">All</span></span> |

## <a name="systemconfiguration"></a><span data-ttu-id="0e345-135">System.Configuration</span><span class="sxs-lookup"><span data-stu-id="0e345-135">System.Configuration</span></span>

| <span data-ttu-id="0e345-136">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-136">Member</span></span> | <span data-ttu-id="0e345-137">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-137">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0e345-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType>（所有成员）</span><span class="sxs-lookup"><span data-stu-id="0e345-138"><xref:System.Configuration.RsaProtectedConfigurationProvider?displayProperty=nameWithType> (all members)</span></span> | <span data-ttu-id="0e345-139">All</span><span class="sxs-lookup"><span data-stu-id="0e345-139">All</span></span> |

## <a name="systemconsole"></a><span data-ttu-id="0e345-140">System.Console</span><span class="sxs-lookup"><span data-stu-id="0e345-140">System.Console</span></span>

| <span data-ttu-id="0e345-141">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-141">Member</span></span> | <span data-ttu-id="0e345-142">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-142">Platforms that throw</span></span> |
| - | - |
| <xref:System.Console.Beep?displayProperty=nameWithType> | <span data-ttu-id="0e345-143">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-143">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-144"><xref:System.Console.BufferHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-145">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-145">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-146"><xref:System.Console.BufferWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-147">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-147">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-148"><xref:System.Console.CursorSize?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-148"><xref:System.Console.CursorSize?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-149">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-149">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType>（仅获取）</span><span class="sxs-lookup"><span data-stu-id="0e345-150"><xref:System.Console.CursorVisible?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0e345-151">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-151">Linux and macOS</span></span> |
| <xref:System.Console.MoveBufferArea%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-152">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-152">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowPosition%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-153">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-153">Linux and macOS</span></span> |
| <xref:System.Console.SetWindowSize%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-154">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-154">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-155"><xref:System.Console.Title?displayProperty=nameWithType>（仅获取）</span><span class="sxs-lookup"><span data-stu-id="0e345-155"><xref:System.Console.Title?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0e345-156">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-156">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-157"><xref:System.Console.WindowHeight?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-158">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-158">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-159"><xref:System.Console.WindowLeft?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-160">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-160">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-161"><xref:System.Console.WindowTop?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-161"><xref:System.Console.WindowTop?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-162">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-162">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-163"><xref:System.Console.WindowWidth?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-164">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-164">Linux and macOS</span></span> |

## <a name="systemdatacommon"></a><span data-ttu-id="0e345-165">System.Data.Common</span><span class="sxs-lookup"><span data-stu-id="0e345-165">System.Data.Common</span></span>

| <span data-ttu-id="0e345-166">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-166">Member</span></span> | <span data-ttu-id="0e345-167">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-167">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0e345-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType>（引发 <xref:System.NotSupportedException>）</span><span class="sxs-lookup"><span data-stu-id="0e345-168"><xref:System.Data.Common.DbDataReader.GetSchemaTable%2A?displayProperty=nameWithType> (throws <xref:System.NotSupportedException>)</span></span> | <span data-ttu-id="0e345-169">All</span><span class="sxs-lookup"><span data-stu-id="0e345-169">All</span></span> |

## <a name="systemdiagnosticsprocess"></a><span data-ttu-id="0e345-170">System.Diagnostics.Process</span><span class="sxs-lookup"><span data-stu-id="0e345-170">System.Diagnostics.Process</span></span>

| <span data-ttu-id="0e345-171">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-171">Member</span></span> | <span data-ttu-id="0e345-172">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-172">Platforms that throw</span></span> |
| - | - |
| <span data-ttu-id="0e345-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-173"><xref:System.Diagnostics.Process.MaxWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-174">Linux</span><span class="sxs-lookup"><span data-stu-id="0e345-174">Linux</span></span> |
| <span data-ttu-id="0e345-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-175"><xref:System.Diagnostics.Process.MinWorkingSet?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-176">Linux</span><span class="sxs-lookup"><span data-stu-id="0e345-176">Linux</span></span> |
| <xref:System.Diagnostics.Process.ProcessorAffinity?displayProperty=nameWithType> | <span data-ttu-id="0e345-177">macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-177">macOS</span></span> |
| <xref:System.Diagnostics.Process.MainWindowHandle?displayProperty=nameWithType> | <span data-ttu-id="0e345-178">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-178">Linux and macOS</span></span> |
| <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-179">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-179">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.UserName?displayProperty=nameWithType> | <span data-ttu-id="0e345-180">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-180">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.PasswordInClearText?displayProperty=nameWithType> | <span data-ttu-id="0e345-181">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-181">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.Domain?displayProperty=nameWithType> | <span data-ttu-id="0e345-182">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-182">Linux and macOS</span></span> |
| <xref:System.Diagnostics.ProcessStartInfo.LoadUserProfile?displayProperty=nameWithType> | <span data-ttu-id="0e345-183">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-183">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-184"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-185">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-185">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType>（仅获取）</span><span class="sxs-lookup"><span data-stu-id="0e345-186"><xref:System.Diagnostics.ProcessThread.BasePriority?displayProperty=nameWithType> (get only)</span></span> | <span data-ttu-id="0e345-187">macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-187">macOS</span></span> |
| <span data-ttu-id="0e345-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-188"><xref:System.Diagnostics.ProcessThread.ProcessorAffinity?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-189">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-189">Linux and macOS</span></span> |

## <a name="systemio"></a><span data-ttu-id="0e345-190">System.IO</span><span class="sxs-lookup"><span data-stu-id="0e345-190">System.IO</span></span>

| <span data-ttu-id="0e345-191">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-191">Member</span></span> | <span data-ttu-id="0e345-192">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-192">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.FileSystemInfo.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-193">All</span><span class="sxs-lookup"><span data-stu-id="0e345-193">All</span></span> |
| <xref:System.IO.FileSystemInfo.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-194">All</span><span class="sxs-lookup"><span data-stu-id="0e345-194">All</span></span> |

## <a name="systemiopipes"></a><span data-ttu-id="0e345-195">System.IO.Pipes</span><span class="sxs-lookup"><span data-stu-id="0e345-195">System.IO.Pipes</span></span>

| <span data-ttu-id="0e345-196">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-196">Member</span></span> | <span data-ttu-id="0e345-197">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-197">Platforms that throw</span></span> |
| - | - |
| <xref:System.IO.Pipes.NamedPipeClientStream.NumberOfServerInstances?displayProperty=nameWithType> | <span data-ttu-id="0e345-198">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-198">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.NamedPipeServerStream.GetImpersonationUserName?displayProperty=nameWithType> | <span data-ttu-id="0e345-199">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-199">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.InBufferSize?displayProperty=nameWithType> | <span data-ttu-id="0e345-200">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-200">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.OutBufferSize?displayProperty=nameWithType> | <span data-ttu-id="0e345-201">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-201">Linux and macOS</span></span> |
| <span data-ttu-id="0e345-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-202"><xref:System.IO.Pipes.PipeStream.ReadMode?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-203">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-203">Linux and macOS</span></span> |
| <xref:System.IO.Pipes.PipeStream.WaitForPipeDrain?displayProperty=nameWithType> | <span data-ttu-id="0e345-204">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-204">Linux and macOS</span></span> |

## <a name="systemmedia"></a><span data-ttu-id="0e345-205">System.Media</span><span class="sxs-lookup"><span data-stu-id="0e345-205">System.Media</span></span>

| <span data-ttu-id="0e345-206">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-206">Member</span></span> | <span data-ttu-id="0e345-207">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-207">Platforms that throw</span></span> |
| - | - |
| <xref:System.Media.SoundPlayer.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-208">All</span><span class="sxs-lookup"><span data-stu-id="0e345-208">All</span></span> |

## <a name="systemnet"></a><span data-ttu-id="0e345-209">System.Net</span><span class="sxs-lookup"><span data-stu-id="0e345-209">System.Net</span></span>

| <span data-ttu-id="0e345-210">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-210">Member</span></span> | <span data-ttu-id="0e345-211">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-211">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.AuthenticationManager.Authenticate(System.String,System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="0e345-212">All</span><span class="sxs-lookup"><span data-stu-id="0e345-212">All</span></span> |
| <xref:System.Net.AuthenticationManager.PreAuthenticate(System.Net.WebRequest,System.Net.ICredentials)?displayProperty=nameWithType> | <span data-ttu-id="0e345-213">All</span><span class="sxs-lookup"><span data-stu-id="0e345-213">All</span></span> |
| <xref:System.Net.FileWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-214">All</span><span class="sxs-lookup"><span data-stu-id="0e345-214">All</span></span> |
| <xref:System.Net.FileWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-215">All</span><span class="sxs-lookup"><span data-stu-id="0e345-215">All</span></span> |
| <xref:System.Net.FileWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-216">All</span><span class="sxs-lookup"><span data-stu-id="0e345-216">All</span></span> |
| <xref:System.Net.FileWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-217">All</span><span class="sxs-lookup"><span data-stu-id="0e345-217">All</span></span> |
| <xref:System.Net.HttpWebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-218">All</span><span class="sxs-lookup"><span data-stu-id="0e345-218">All</span></span> |
| <xref:System.Net.HttpWebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-219">All</span><span class="sxs-lookup"><span data-stu-id="0e345-219">All</span></span> |
| <xref:System.Net.HttpWebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-220">All</span><span class="sxs-lookup"><span data-stu-id="0e345-220">All</span></span> |
| <xref:System.Net.HttpWebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-221">All</span><span class="sxs-lookup"><span data-stu-id="0e345-221">All</span></span> |
| <xref:System.Net.WebProxy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-222">All</span><span class="sxs-lookup"><span data-stu-id="0e345-222">All</span></span> |
| <xref:System.Net.WebProxy.GetDefaultProxy?displayProperty=nameWithType> | <span data-ttu-id="0e345-223">All</span><span class="sxs-lookup"><span data-stu-id="0e345-223">All</span></span> |
| <xref:System.Net.WebProxy.GetObjectData%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-224">All</span><span class="sxs-lookup"><span data-stu-id="0e345-224">All</span></span> |
| <xref:System.Net.WebRequest.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-225">All</span><span class="sxs-lookup"><span data-stu-id="0e345-225">All</span></span> |
| <xref:System.Net.WebRequest.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-226">All</span><span class="sxs-lookup"><span data-stu-id="0e345-226">All</span></span> |
| <xref:System.Net.WebResponse.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-227">All</span><span class="sxs-lookup"><span data-stu-id="0e345-227">All</span></span> |
| <xref:System.Net.WebResponse.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-228">All</span><span class="sxs-lookup"><span data-stu-id="0e345-228">All</span></span> |

## <a name="systemnetnetworkinformation"></a><span data-ttu-id="0e345-229">System.Net.NetworkInformation</span><span class="sxs-lookup"><span data-stu-id="0e345-229">System.Net.NetworkInformation</span></span>

| <span data-ttu-id="0e345-230">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-230">Member</span></span> | <span data-ttu-id="0e345-231">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-231">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.NetworkInformation.Ping.Send%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-232">Windows (UWP)</span><span class="sxs-lookup"><span data-stu-id="0e345-232">Windows (UWP)</span></span> |

## <a name="systemnetsockets"></a><span data-ttu-id="0e345-233">System.Net.Sockets</span><span class="sxs-lookup"><span data-stu-id="0e345-233">System.Net.Sockets</span></span>

| <span data-ttu-id="0e345-234">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-234">Member</span></span> | <span data-ttu-id="0e345-235">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-235">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.Sockets.Socket.%23ctor(System.Net.Sockets.SocketInformation)> | <span data-ttu-id="0e345-236">All</span><span class="sxs-lookup"><span data-stu-id="0e345-236">All</span></span> |
| <xref:System.Net.Sockets.Socket.DuplicateAndClose(System.Int32)?displayProperty=nameWithType> | <span data-ttu-id="0e345-237">All</span><span class="sxs-lookup"><span data-stu-id="0e345-237">All</span></span> |

## <a name="systemnetwebsockets"></a><span data-ttu-id="0e345-238">System.Net.WebSockets</span><span class="sxs-lookup"><span data-stu-id="0e345-238">System.Net.WebSockets</span></span>

| <span data-ttu-id="0e345-239">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-239">Member</span></span> | <span data-ttu-id="0e345-240">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-240">Platforms that throw</span></span> |
| - | - |
| <xref:System.Net.WebSockets.WebSocket.RegisterPrefixes?displayProperty=nameWithType> | <span data-ttu-id="0e345-241">All</span><span class="sxs-lookup"><span data-stu-id="0e345-241">All</span></span> |

## <a name="systemreflection"></a><span data-ttu-id="0e345-242">System.Reflection</span><span class="sxs-lookup"><span data-stu-id="0e345-242">System.Reflection</span></span>

| <span data-ttu-id="0e345-243">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-243">Member</span></span> | <span data-ttu-id="0e345-244">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-244">Platforms that throw</span></span> |
| - | - |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoad%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-245">All</span><span class="sxs-lookup"><span data-stu-id="0e345-245">All</span></span> |
| <xref:System.Reflection.Assembly.ReflectionOnlyLoadFrom(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0e345-246">All</span><span class="sxs-lookup"><span data-stu-id="0e345-246">All</span></span> |
| <xref:System.Reflection.AssemblyName.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-247">All</span><span class="sxs-lookup"><span data-stu-id="0e345-247">All</span></span> |
| <xref:System.Reflection.AssemblyName.OnDeserialization(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0e345-248">All</span><span class="sxs-lookup"><span data-stu-id="0e345-248">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.String)> | <span data-ttu-id="0e345-249">All</span><span class="sxs-lookup"><span data-stu-id="0e345-249">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-250">All</span><span class="sxs-lookup"><span data-stu-id="0e345-250">All</span></span> |
| <xref:System.Reflection.StrongNameKeyPair.PublicKey?displayProperty=nameWithType> | <span data-ttu-id="0e345-251">All</span><span class="sxs-lookup"><span data-stu-id="0e345-251">All</span></span> |

## <a name="systemruntimecompilerservices"></a><span data-ttu-id="0e345-252">System.Runtime.CompilerServices</span><span class="sxs-lookup"><span data-stu-id="0e345-252">System.Runtime.CompilerServices</span></span>

| <span data-ttu-id="0e345-253">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-253">Member</span></span> | <span data-ttu-id="0e345-254">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-254">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> | <span data-ttu-id="0e345-255">All</span><span class="sxs-lookup"><span data-stu-id="0e345-255">All</span></span> |

## <a name="systemruntimeinteropservices"></a><span data-ttu-id="0e345-256">System.Runtime.InteropServices</span><span class="sxs-lookup"><span data-stu-id="0e345-256">System.Runtime.InteropServices</span></span>

| <span data-ttu-id="0e345-257">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-257">Member</span></span> | <span data-ttu-id="0e345-258">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-258">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.InteropServices.Marshal.GetIDispatchForObject(System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0e345-259">All</span><span class="sxs-lookup"><span data-stu-id="0e345-259">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.SystemConfigurationFile?displayProperty=nameWithType> | <span data-ttu-id="0e345-260">All</span><span class="sxs-lookup"><span data-stu-id="0e345-260">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsIntPtr(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="0e345-261">All</span><span class="sxs-lookup"><span data-stu-id="0e345-261">All</span></span> |
| <xref:System.Runtime.InteropServices.RuntimeEnvironment.GetRuntimeInterfaceAsObject(System.Guid,System.Guid)?displayProperty=nameWithType> | <span data-ttu-id="0e345-262">All</span><span class="sxs-lookup"><span data-stu-id="0e345-262">All</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.StringToHString(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0e345-263">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-263">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.PtrToStringHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="0e345-264">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-264">Linux and macOS</span></span> |
| <xref:System.Runtime.InteropServices.WindowsRuntime.WindowsRuntimeMarshal.FreeHString(System.IntPtr)?displayProperty=nameWithType> | <span data-ttu-id="0e345-265">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-265">Linux and macOS</span></span> |

## <a name="systemruntimeserialization"></a><span data-ttu-id="0e345-266">System.Runtime.Serialization</span><span class="sxs-lookup"><span data-stu-id="0e345-266">System.Runtime.Serialization</span></span>

| <span data-ttu-id="0e345-267">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-267">Member</span></span> | <span data-ttu-id="0e345-268">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-268">Platforms that throw</span></span> |
| - | - |
| <xref:System.Runtime.Serialization.XsdDataContractExporter.Schemas?displayProperty=nameWithType> | <span data-ttu-id="0e345-269">All</span><span class="sxs-lookup"><span data-stu-id="0e345-269">All</span></span> |

## <a name="systemsecurity"></a><span data-ttu-id="0e345-270">System.Security</span><span class="sxs-lookup"><span data-stu-id="0e345-270">System.Security</span></span>

| <span data-ttu-id="0e345-271">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-271">Member</span></span> | <span data-ttu-id="0e345-272">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-272">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.CodeAccessPermission.Deny?displayProperty=nameWithType> | <span data-ttu-id="0e345-273">All</span><span class="sxs-lookup"><span data-stu-id="0e345-273">All</span></span> |
| <xref:System.Security.CodeAccessPermission.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="0e345-274">All</span><span class="sxs-lookup"><span data-stu-id="0e345-274">All</span></span> |
| <xref:System.Security.PermissionSet.ConvertPermissionSet(System.String,System.Byte[],System.String)?displayProperty=nameWithType> | <span data-ttu-id="0e345-275">All</span><span class="sxs-lookup"><span data-stu-id="0e345-275">All</span></span> |
| <xref:System.Security.PermissionSet.Deny?displayProperty=nameWithType> | <span data-ttu-id="0e345-276">All</span><span class="sxs-lookup"><span data-stu-id="0e345-276">All</span></span> |
| <xref:System.Security.PermissionSet.PermitOnly?displayProperty=nameWithType> | <span data-ttu-id="0e345-277">All</span><span class="sxs-lookup"><span data-stu-id="0e345-277">All</span></span> |
| <xref:System.Security.SecurityContext.Capture?displayProperty=nameWithType> | <span data-ttu-id="0e345-278">All</span><span class="sxs-lookup"><span data-stu-id="0e345-278">All</span></span> |
| <xref:System.Security.SecurityContext.CreateCopy?displayProperty=nameWithType> | <span data-ttu-id="0e345-279">All</span><span class="sxs-lookup"><span data-stu-id="0e345-279">All</span></span> |
| <xref:System.Security.SecurityContext.Dispose?displayProperty=nameWithType> | <span data-ttu-id="0e345-280">All</span><span class="sxs-lookup"><span data-stu-id="0e345-280">All</span></span> |
| <xref:System.Security.SecurityContext.IsFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="0e345-281">All</span><span class="sxs-lookup"><span data-stu-id="0e345-281">All</span></span> |
| <xref:System.Security.SecurityContext.IsWindowsIdentityFlowSuppressed?displayProperty=nameWithType> | <span data-ttu-id="0e345-282">All</span><span class="sxs-lookup"><span data-stu-id="0e345-282">All</span></span> |
| <xref:System.Security.SecurityContext.RestoreFlow?displayProperty=nameWithType> | <span data-ttu-id="0e345-283">All</span><span class="sxs-lookup"><span data-stu-id="0e345-283">All</span></span> |
| <xref:System.Security.SecurityContext.Run(System.Security.SecurityContext,System.Threading.ContextCallback,System.Object)?displayProperty=nameWithType> | <span data-ttu-id="0e345-284">All</span><span class="sxs-lookup"><span data-stu-id="0e345-284">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlow?displayProperty=nameWithType> | <span data-ttu-id="0e345-285">All</span><span class="sxs-lookup"><span data-stu-id="0e345-285">All</span></span> |
| <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity?displayProperty=nameWithType> | <span data-ttu-id="0e345-286">All</span><span class="sxs-lookup"><span data-stu-id="0e345-286">All</span></span> |

## <a name="systemsecurityclaims"></a><span data-ttu-id="0e345-287">System.Security.Claims</span><span class="sxs-lookup"><span data-stu-id="0e345-287">System.Security.Claims</span></span>

| <span data-ttu-id="0e345-288">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-288">Member</span></span> | <span data-ttu-id="0e345-289">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-289">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Claims.ClaimsPrincipal.%23ctor> | <span data-ttu-id="0e345-290">All</span><span class="sxs-lookup"><span data-stu-id="0e345-290">All</span></span> |
| <xref:System.Security.Claims.ClaimsPrincipal.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-291">All</span><span class="sxs-lookup"><span data-stu-id="0e345-291">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo)> | <span data-ttu-id="0e345-292">All</span><span class="sxs-lookup"><span data-stu-id="0e345-292">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-293">All</span><span class="sxs-lookup"><span data-stu-id="0e345-293">All</span></span> |
| <xref:System.Security.Claims.ClaimsIdentity.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-294">All</span><span class="sxs-lookup"><span data-stu-id="0e345-294">All</span></span> |

## <a name="systemsecuritycryptography"></a><span data-ttu-id="0e345-295">System.Security.Cryptography</span><span class="sxs-lookup"><span data-stu-id="0e345-295">System.Security.Cryptography</span></span>

| <span data-ttu-id="0e345-296">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-296">Member</span></span> | <span data-ttu-id="0e345-297">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-297">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.AsymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0e345-298">All</span><span class="sxs-lookup"><span data-stu-id="0e345-298">All</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.%23ctor%2A> | <span data-ttu-id="0e345-299">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-299">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Accessible?displayProperty=nameWithType> | <span data-ttu-id="0e345-300">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-300">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Exportable?displayProperty=nameWithType> | <span data-ttu-id="0e345-301">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-301">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.HardwareDevice?displayProperty=nameWithType> | <span data-ttu-id="0e345-302">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-302">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="0e345-303">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-303">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.KeyNumber?displayProperty=nameWithType> | <span data-ttu-id="0e345-304">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-304">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.MachineKeyStore?displayProperty=nameWithType> | <span data-ttu-id="0e345-305">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-305">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Protected?displayProperty=nameWithType> | <span data-ttu-id="0e345-306">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-306">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderName?displayProperty=nameWithType> | <span data-ttu-id="0e345-307">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-307">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.ProviderType?displayProperty=nameWithType> | <span data-ttu-id="0e345-308">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-308">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.RandomlyGenerated?displayProperty=nameWithType> | <span data-ttu-id="0e345-309">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-309">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.Removable?displayProperty=nameWithType> | <span data-ttu-id="0e345-310">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-310">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.CspKeyContainerInfo.UniqueKeyContainerName?displayProperty=nameWithType> | <span data-ttu-id="0e345-311">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-311">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.HashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0e345-312">All</span><span class="sxs-lookup"><span data-stu-id="0e345-312">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create?displayProperty=nameWithType> | <span data-ttu-id="0e345-313">All</span><span class="sxs-lookup"><span data-stu-id="0e345-313">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0e345-314">All</span><span class="sxs-lookup"><span data-stu-id="0e345-314">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashCore%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-315">All</span><span class="sxs-lookup"><span data-stu-id="0e345-315">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.HashFinal%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-316">All</span><span class="sxs-lookup"><span data-stu-id="0e345-316">All</span></span> |
| <xref:System.Security.Cryptography.HMAC.Initialize%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-317">All</span><span class="sxs-lookup"><span data-stu-id="0e345-317">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0e345-318">All</span><span class="sxs-lookup"><span data-stu-id="0e345-318">All</span></span> |
| <xref:System.Security.Cryptography.KeyedHashAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0e345-319">All</span><span class="sxs-lookup"><span data-stu-id="0e345-319">All</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Protect%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-320">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-320">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.ProtectedData.Unprotect%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-321">Linux 和 macOS</span><span class="sxs-lookup"><span data-stu-id="0e345-321">Linux and macOS</span></span> |
| <xref:System.Security.Cryptography.RSA.FromXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-322">All</span><span class="sxs-lookup"><span data-stu-id="0e345-322">All</span></span> |
| <xref:System.Security.Cryptography.RSA.ToXmlString%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-323">All</span><span class="sxs-lookup"><span data-stu-id="0e345-323">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create?displayProperty=nameWithType> | <span data-ttu-id="0e345-324">All</span><span class="sxs-lookup"><span data-stu-id="0e345-324">All</span></span> |
| <xref:System.Security.Cryptography.SymmetricAlgorithm.Create(System.String)?displayProperty=nameWithType> | <span data-ttu-id="0e345-325">All</span><span class="sxs-lookup"><span data-stu-id="0e345-325">All</span></span> |

## <a name="systemsecuritycryptographypkcs"></a><span data-ttu-id="0e345-326">System.Security.Cryptography.Pkcs</span><span class="sxs-lookup"><span data-stu-id="0e345-326">System.Security.Cryptography.Pkcs</span></span>

| <span data-ttu-id="0e345-327">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-327">Member</span></span> | <span data-ttu-id="0e345-328">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-328">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.Pkcs.CmsSigner.%23ctor(System.Security.Cryptography.CspParameters)> | <span data-ttu-id="0e345-329">All</span><span class="sxs-lookup"><span data-stu-id="0e345-329">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignedCms.ComputeSignature(System.Security.Cryptography.Pkcs.CmsSigner,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0e345-330">All</span><span class="sxs-lookup"><span data-stu-id="0e345-330">All</span></span> |
| <xref:System.Security.Cryptography.Pkcs.SignerInfo.ComputeCounterSignature?displayProperty=nameWithType> | <span data-ttu-id="0e345-331">All</span><span class="sxs-lookup"><span data-stu-id="0e345-331">All</span></span> |

## <a name="systemsecuritycryptographyx509certificates"></a><span data-ttu-id="0e345-332">System.Security.Cryptography.X509Certificates</span><span class="sxs-lookup"><span data-stu-id="0e345-332">System.Security.Cryptography.X509Certificates</span></span>

| <span data-ttu-id="0e345-333">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-333">Member</span></span> | <span data-ttu-id="0e345-334">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-334">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-335">All</span><span class="sxs-lookup"><span data-stu-id="0e345-335">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate.Import%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-336">All</span><span class="sxs-lookup"><span data-stu-id="0e345-336">All</span></span> |
| <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-337">All</span><span class="sxs-lookup"><span data-stu-id="0e345-337">All</span></span> |
| <span data-ttu-id="0e345-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType>（仅设置）</span><span class="sxs-lookup"><span data-stu-id="0e345-338"><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.PrivateKey?displayProperty=nameWithType> (set only)</span></span> | <span data-ttu-id="0e345-339">All</span><span class="sxs-lookup"><span data-stu-id="0e345-339">All</span></span> |

## <a name="systemsecurityauthenticationextendedprotection"></a><span data-ttu-id="0e345-340">System.Security.Authentication.ExtendedProtection</span><span class="sxs-lookup"><span data-stu-id="0e345-340">System.Security.Authentication.ExtendedProtection</span></span>

| <span data-ttu-id="0e345-341">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-341">Member</span></span> | <span data-ttu-id="0e345-342">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-342">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-343">All</span><span class="sxs-lookup"><span data-stu-id="0e345-343">All</span></span> |

## <a name="systemsecuritypolicy"></a><span data-ttu-id="0e345-344">System.Security.Policy</span><span class="sxs-lookup"><span data-stu-id="0e345-344">System.Security.Policy</span></span>

| <span data-ttu-id="0e345-345">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-345">Member</span></span> | <span data-ttu-id="0e345-346">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-346">Platforms that throw</span></span> |
| - | - |
| <xref:System.Security.Policy.Hash.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-347">All</span><span class="sxs-lookup"><span data-stu-id="0e345-347">All</span></span> |

## <a name="systemserviceprocessservicecontroller"></a><span data-ttu-id="0e345-348">System.ServiceProcess.ServiceController</span><span class="sxs-lookup"><span data-stu-id="0e345-348">System.ServiceProcess.ServiceController</span></span>

| <span data-ttu-id="0e345-349">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-349">Member</span></span> | <span data-ttu-id="0e345-350">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-350">Platforms that throw</span></span> |
| - | - |
| <xref:System.ServiceProcess.TimeoutException.%23ctor(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)> | <span data-ttu-id="0e345-351">All</span><span class="sxs-lookup"><span data-stu-id="0e345-351">All</span></span> |

## <a name="systemtextregularexpressions"></a><span data-ttu-id="0e345-352">System.Text.RegularExpressions</span><span class="sxs-lookup"><span data-stu-id="0e345-352">System.Text.RegularExpressions</span></span>

| <span data-ttu-id="0e345-353">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-353">Member</span></span> | <span data-ttu-id="0e345-354">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-354">Platforms that throw</span></span> |
| - | - |
| <xref:System.Text.RegularExpressions.Regex.CompileToAssembly%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-355">All</span><span class="sxs-lookup"><span data-stu-id="0e345-355">All</span></span> |

## <a name="systemthreading"></a><span data-ttu-id="0e345-356">System.Threading</span><span class="sxs-lookup"><span data-stu-id="0e345-356">System.Threading</span></span>

| <span data-ttu-id="0e345-357">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-357">Member</span></span> | <span data-ttu-id="0e345-358">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-358">Platforms that throw</span></span> |
| - | - |
| <xref:System.Threading.CompressedStack.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-359">All</span><span class="sxs-lookup"><span data-stu-id="0e345-359">All</span></span> |
| <xref:System.Threading.ExecutionContext.GetObjectData(System.Runtime.Serialization.SerializationInfo,System.Runtime.Serialization.StreamingContext)?displayProperty=nameWithType> | <span data-ttu-id="0e345-360">All</span><span class="sxs-lookup"><span data-stu-id="0e345-360">All</span></span> |
| <xref:System.Threading.Thread.Abort%2A?displayProperty=nameWithType> | <span data-ttu-id="0e345-361">All</span><span class="sxs-lookup"><span data-stu-id="0e345-361">All</span></span> |
| <xref:System.Threading.Thread.ResetAbort?displayProperty=nameWithType> | <span data-ttu-id="0e345-362">All</span><span class="sxs-lookup"><span data-stu-id="0e345-362">All</span></span> |
| <xref:System.Threading.Thread.Resume?displayProperty=nameWithType> | <span data-ttu-id="0e345-363">All</span><span class="sxs-lookup"><span data-stu-id="0e345-363">All</span></span> |
| <xref:System.Threading.Thread.Suspend?displayProperty=nameWithType> | <span data-ttu-id="0e345-364">All</span><span class="sxs-lookup"><span data-stu-id="0e345-364">All</span></span> |

## <a name="systemxml"></a><span data-ttu-id="0e345-365">System.Xml</span><span class="sxs-lookup"><span data-stu-id="0e345-365">System.Xml</span></span>

| <span data-ttu-id="0e345-366">成员</span><span class="sxs-lookup"><span data-stu-id="0e345-366">Member</span></span> | <span data-ttu-id="0e345-367">引发异常的平台</span><span class="sxs-lookup"><span data-stu-id="0e345-367">Platforms that throw</span></span> |
| - | - |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.Byte[],System.Int32,System.Int32,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="0e345-368">All</span><span class="sxs-lookup"><span data-stu-id="0e345-368">All</span></span> |
| <xref:System.Xml.XmlDictionaryReader.CreateMtomReader(System.IO.Stream,System.Text.Encoding[],System.String,System.Xml.XmlDictionaryReaderQuotas,System.Int32,System.Xml.OnXmlDictionaryReaderClose)?displayProperty=nameWithType> | <span data-ttu-id="0e345-369">All</span><span class="sxs-lookup"><span data-stu-id="0e345-369">All</span></span> |
| <xref:System.Xml.XmlDictionaryWriter.CreateMtomWriter(System.IO.Stream,System.Text.Encoding,System.Int32,System.String,System.String,System.String,System.Boolean,System.Boolean)?displayProperty=nameWithType> | <span data-ttu-id="0e345-370">All</span><span class="sxs-lookup"><span data-stu-id="0e345-370">All</span></span> |

## <a name="see-also"></a><span data-ttu-id="0e345-371">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e345-371">See also</span></span>

- [<span data-ttu-id="0e345-372">从 .NET Framework 迁移到 .NET Core 的中断性变更</span><span class="sxs-lookup"><span data-stu-id="0e345-372">Breaking changes for migration from .NET Framework to .NET Core</span></span>](../compatibility/fx-core.md)
- [<span data-ttu-id="0e345-373">.NET Core 中的二进制序列化</span><span class="sxs-lookup"><span data-stu-id="0e345-373">Binary serialization in .NET Core</span></span>](../../standard/serialization/binary-serialization.md#net-core)
- [<span data-ttu-id="0e345-374">.NET 可移植性分析器</span><span class="sxs-lookup"><span data-stu-id="0e345-374">.NET portability analyzer</span></span>](../../standard/analyzers/portability-analyzer.md)
