---
title: .NET Standard 中的新增功能
description: 本文总结了所有新版 .NET Standard 中的新功能和增强功能。
ms.custom: updateeachrelease
ms.date: 04/12/2018
ms.technology: dotnet-standard
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 19353bd068e3b04bc3d852c1e22db9c97ebef628
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583160"
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="e07d9-103">.NET Standard 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="e07d9-103">What's new in the .NET Standard</span></span>

<span data-ttu-id="e07d9-104">.NET Standard 是一种正式规范，它定义了一组版本化 API。这些 API 必须可用于符合相应 Standard 版本要求的 .NET 实现。</span><span class="sxs-lookup"><span data-stu-id="e07d9-104">The .NET Standard is a formal specification that defines a versioned set of APIs that must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="e07d9-105">.NET Standard 面向库开发者。</span><span class="sxs-lookup"><span data-stu-id="e07d9-105">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="e07d9-106">定目标到 .NET Standard 版本的库可用于任意 .NET Framework、.NET Core 或支持 Standard 版本的 Xamarin 实现。</span><span class="sxs-lookup"><span data-stu-id="e07d9-106">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="e07d9-107">.NET Standard 的最新版本是 2.0。</span><span class="sxs-lookup"><span data-stu-id="e07d9-107">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="e07d9-108">.NET Core 2.0 SDK 及已安装 .NET Core 工作负载的 Visual Studio 2017 版本 15.3 包含它。</span><span class="sxs-lookup"><span data-stu-id="e07d9-108">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="e07d9-109">支持的 .NET 实现</span><span class="sxs-lookup"><span data-stu-id="e07d9-109">Supported .NET implementations</span></span>

<span data-ttu-id="e07d9-110">以下 .NET 实现支持 .NET Standard 2.0：</span><span class="sxs-lookup"><span data-stu-id="e07d9-110">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="e07d9-111">.NET Core 2.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e07d9-111">.NET Core 2.0 or later</span></span>
- <span data-ttu-id="e07d9-112">.NET Framework 4.6.1 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e07d9-112">.NET Framework 4.6.1 or later</span></span>
- <span data-ttu-id="e07d9-113">Mono 5.4 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e07d9-113">Mono 5.4 or later</span></span>
- <span data-ttu-id="e07d9-114">Xamarin.iOS 10.14 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e07d9-114">Xamarin.iOS 10.14 or later</span></span>
- <span data-ttu-id="e07d9-115">Xamarin.Mac 3.8 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e07d9-115">Xamarin.Mac 3.8 or later</span></span>
- <span data-ttu-id="e07d9-116">Xamarin.Android 8.0 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e07d9-116">Xamarin.Android 8.0 or later</span></span>
- <span data-ttu-id="e07d9-117">通用 Windows 平台 10.0.16299 或更高版本</span><span class="sxs-lookup"><span data-stu-id="e07d9-117">Universal Windows Platform 10.0.16299 or later</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="e07d9-118">.NET Standard 2.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="e07d9-118">What's new in the .NET Standard 2.0</span></span>

<span data-ttu-id="e07d9-119">.NET Standard 2.0 新增了以下功能：</span><span class="sxs-lookup"><span data-stu-id="e07d9-119">The .NET Standard 2.0 includes the following new features:</span></span>

### <a name="a-vastly-expanded-set-of-apis"></a><span data-ttu-id="e07d9-120">大幅扩展了 API 集</span><span class="sxs-lookup"><span data-stu-id="e07d9-120">A vastly expanded set of APIs</span></span>

<span data-ttu-id="e07d9-121">.NET Standard 版本 1.6 中包含了相对较小的一部分 API。</span><span class="sxs-lookup"><span data-stu-id="e07d9-121">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="e07d9-122">不包含的 API 许多都是 .NET Framework 或 Xamarin 中的常用 API。</span><span class="sxs-lookup"><span data-stu-id="e07d9-122">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="e07d9-123">这样一来，开发变得更为棘手，因为开发人员必须在开发定目标到多个 .NET 实现的应用和库时，寻找常用 API 的合适替代项。</span><span class="sxs-lookup"><span data-stu-id="e07d9-123">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="e07d9-124">为了消除此限制，.NET Standard 2.0 向 Standard 旧版本 .NET Standard 1.6 中的可用 API 补充了 20,000 多个 API。</span><span class="sxs-lookup"><span data-stu-id="e07d9-124">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="e07d9-125">有关添加到 .NET Standard 2.0 的 API 列表，请参阅 [.NET Standard 2.0 与 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)。</span><span class="sxs-lookup"><span data-stu-id="e07d9-125">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span>

<span data-ttu-id="e07d9-126">.NET Standard 2.0 的 <xref:System> 命名空间中新增的一些功能包括：</span><span class="sxs-lookup"><span data-stu-id="e07d9-126">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="e07d9-127">支持 <xref:System.AppDomain> 类。</span><span class="sxs-lookup"><span data-stu-id="e07d9-127">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="e07d9-128">更好地支持通过 <xref:System.Array> 类中的附加成员处理数组。</span><span class="sxs-lookup"><span data-stu-id="e07d9-128">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="e07d9-129">更好地支持通过 <xref:System.Attribute> 类中的附加成员处理属性。</span><span class="sxs-lookup"><span data-stu-id="e07d9-129">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="e07d9-130">改进了日历支持，并附加了 <xref:System.DateTime> 值的格式设置选项。</span><span class="sxs-lookup"><span data-stu-id="e07d9-130">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="e07d9-131">附加了 <xref:System.Decimal> 舍入功能。</span><span class="sxs-lookup"><span data-stu-id="e07d9-131">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="e07d9-132">在 <xref:System.Environment> 类中附加了功能。</span><span class="sxs-lookup"><span data-stu-id="e07d9-132">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="e07d9-133">增强了通过 <xref:System.GC> 类控制垃圾回收器。</span><span class="sxs-lookup"><span data-stu-id="e07d9-133">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="e07d9-134">增强了 <xref:System.String> 类中的字符串比较、枚举和规范化支持。</span><span class="sxs-lookup"><span data-stu-id="e07d9-134">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="e07d9-135"><xref:System.TimeZoneInfo.AdjustmentRule> 和 <xref:System.TimeZoneInfo.TransitionTime> 类支持夏令时调整和时间转换。</span><span class="sxs-lookup"><span data-stu-id="e07d9-135">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="e07d9-136">显著改进了 <xref:System.Type> 类中的功能。</span><span class="sxs-lookup"><span data-stu-id="e07d9-136">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="e07d9-137">通过添加包含 <xref:System.Runtime.Serialization.SerializationInfo> 和 <xref:System.Runtime.Serialization.StreamingContext> 参数的异常构造函数，改进了对异常对象反序列化的支持。</span><span class="sxs-lookup"><span data-stu-id="e07d9-137">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

### <a name="support-for-net-framework-libraries"></a><span data-ttu-id="e07d9-138">支持 .NET Framework 库</span><span class="sxs-lookup"><span data-stu-id="e07d9-138">Support for .NET Framework libraries</span></span>

<span data-ttu-id="e07d9-139">绝大多数库定目标到 .NET Framework，而不是 .NET Standard。</span><span class="sxs-lookup"><span data-stu-id="e07d9-139">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="e07d9-140">不过，这些库大多调用的是 .NET Standard 2.0 中的 API。</span><span class="sxs-lookup"><span data-stu-id="e07d9-140">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="e07d9-141">自 .NET Standard 2.0 起，可以使用[兼容性垫片](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification)从 .NET Standard 库访问 .NET Framework 库。</span><span class="sxs-lookup"><span data-stu-id="e07d9-141">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/planning/netstandard-2.0/README.md#assembly-unification).</span></span> <span data-ttu-id="e07d9-142">此兼容性层对开发人员透明；无需执行任何操作，即可使用 .NET Framework 库。</span><span class="sxs-lookup"><span data-stu-id="e07d9-142">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="e07d9-143">只有一项要求就是，.NET Framework 类库调用的 API 必须是 .NET Standard 2.0 中的 API。</span><span class="sxs-lookup"><span data-stu-id="e07d9-143">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

### <a name="support-for-visual-basic"></a><span data-ttu-id="e07d9-144">支持 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e07d9-144">Support for Visual Basic</span></span>

<span data-ttu-id="e07d9-145">现在可以使用 Visual Basic 开发 .NET Standard 库。</span><span class="sxs-lookup"><span data-stu-id="e07d9-145">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="e07d9-146">如果 Visual Basic 开发人员使用的是已安装 .NET Core 工作负载的 Visual Studio 2017 版本 15.3 或更高版本，现在可以使用 Visual Studio 中的 .NET Standard 类库模板。</span><span class="sxs-lookup"><span data-stu-id="e07d9-146">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="e07d9-147">对于使用其他开发工具和环境的 Visual Basic 开发人员，可以使用 [dotnet new](../../core/tools/dotnet-new.md) 命令创建 .NET Standard 库项目。</span><span class="sxs-lookup"><span data-stu-id="e07d9-147">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="e07d9-148">有关详细信息，请参阅 [.NET Standard 库的工具支持](#tooling-support-for-net-standard-libraries)。</span><span class="sxs-lookup"><span data-stu-id="e07d9-148">For more information, see the [Tooling support for .NET Standard libraries](#tooling-support-for-net-standard-libraries).</span></span>

### <a name="tooling-support-for-net-standard-libraries"></a><span data-ttu-id="e07d9-149">.NET Standard 库的工具支持</span><span class="sxs-lookup"><span data-stu-id="e07d9-149">Tooling support for .NET Standard libraries</span></span>

<span data-ttu-id="e07d9-150">随着 .NET Core 2.0 和 .NET Standard 2.0 发布，Visual Studio 2017 和 [.NET Core 命令行接口 (CLI)](../../core/tools/index.md) 均包含创建 .NET Standard 库所需的工具支持。</span><span class="sxs-lookup"><span data-stu-id="e07d9-150">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span>

<span data-ttu-id="e07d9-151">如果安装含 .NET Core 跨平台开发工作负荷的 Visual Studio，可以使用项目模板创建 .NET Standard 2.0 库项目，如下图所示：</span><span class="sxs-lookup"><span data-stu-id="e07d9-151">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows:</span></span>

# <a name="ctabcsharp"></a>[<span data-ttu-id="e07d9-152">C#</span><span class="sxs-lookup"><span data-stu-id="e07d9-152">C#</span></span>](#tab/csharp)

![添加新的 .NET Standard 库项目](./media/std-project-cs.png)

<span data-ttu-id="e07d9-154">如果使用的是 .NET Core CLI，可以运行下面的 [dotnet new](../../core/tools/dotnet-new.md) 命令，以创建定目标到 .NET Standard 2.0 的类库项目：</span><span class="sxs-lookup"><span data-stu-id="e07d9-154">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```
dotnet new classlib
```

# <a name="visual-basictabvb"></a>[<span data-ttu-id="e07d9-155">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e07d9-155">Visual Basic</span></span>](#tab/vb)

![添加新的 .NET Standard 库项目](./media/std-project-vb.png)

<span data-ttu-id="e07d9-157">如果使用的是 .NET Core CLI，可以运行下面的 [dotnet new](../../core/tools/dotnet-new.md) 命令，以创建定目标到 .NET Standard 2.0 的类库项目：</span><span class="sxs-lookup"><span data-stu-id="e07d9-157">If you're using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0:</span></span>

```
dotnet new classlib -lang vb
```

---

## <a name="see-also"></a><span data-ttu-id="e07d9-158">请参阅</span><span class="sxs-lookup"><span data-stu-id="e07d9-158">See also</span></span>

- [<span data-ttu-id="e07d9-159">.NET Standard</span><span class="sxs-lookup"><span data-stu-id="e07d9-159">.NET Standard</span></span>](../net-standard.md)  
- [<span data-ttu-id="e07d9-160">.NET Standard 简介</span><span class="sxs-lookup"><span data-stu-id="e07d9-160">Introducing .NET Standard</span></span>](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)
