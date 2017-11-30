---
title: "什么是.NET 标准中的新增功能"
ms.custom: updateeachrelease
ms.date: 11/08/2017
ms.prod: .net
ms.topic: article
ms.technology: dotnet-standard
ms.##devlang: dotnet
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e938c009b79af3b2f36094bbb74f4d38baeeac0b
ms.sourcegitcommit: 281070dee88db86ec3bb4634d5f558d1a4e159dd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2017
---
# <a name="whats-new-in-the-net-standard"></a><span data-ttu-id="e64d3-102">什么是.NET 标准中的新增功能</span><span class="sxs-lookup"><span data-stu-id="e64d3-102">What's new in the .NET Standard</span></span>

<span data-ttu-id="e64d3-103">.NET 标准是定义必须在符合标准的该版本的.NET 实现上可用的 Api 版本控制组形式规范。</span><span class="sxs-lookup"><span data-stu-id="e64d3-103">The .NET Standard is a formal specification that defines a versioned set of APIs which must be available on .NET implementations that comply with that version of the standard.</span></span> <span data-ttu-id="e64d3-104">.NET Standard 面向库开发者。</span><span class="sxs-lookup"><span data-stu-id="e64d3-104">The .NET Standard is targeted at library developers.</span></span> <span data-ttu-id="e64d3-105">在任何支持的标准，该版本的.NET Framework、.NET 核心或 Xamarin 实现中，可以使用面向.NET 标准版本的库。</span><span class="sxs-lookup"><span data-stu-id="e64d3-105">A library that targets a .NET Standard version can be used on any .NET Framework, .NET Core, or Xamarin implementation that supports that version of the standard.</span></span>

<span data-ttu-id="e64d3-106">.NET 标准的最新版本为 2.0。</span><span class="sxs-lookup"><span data-stu-id="e64d3-106">The most recent version of the .NET Standard is 2.0.</span></span> <span data-ttu-id="e64d3-107">包含它是与.NET 核心 2.0 SDK，以及 Visual Studio 2017 版本 15.3 与安装.NET 核心工作负荷。</span><span class="sxs-lookup"><span data-stu-id="e64d3-107">It is included with the .NET Core 2.0 SDK, as well as with Visual Studio 2017 Version 15.3 with the .NET Core workload installed.</span></span>

## <a name="supported-net-implementations"></a><span data-ttu-id="e64d3-108">受支持的.NET 实现</span><span class="sxs-lookup"><span data-stu-id="e64d3-108">Supported .NET implementations</span></span>

<span data-ttu-id="e64d3-109">.NET 标准 2.0 支持以下.NET 实现：</span><span class="sxs-lookup"><span data-stu-id="e64d3-109">The .NET Standard 2.0 is supported by the following .NET implementations:</span></span>

- <span data-ttu-id="e64d3-110">.NET 核心 2.0</span><span class="sxs-lookup"><span data-stu-id="e64d3-110">.NET Core 2.0</span></span>
- <span data-ttu-id="e64d3-111">.NET Framework 4.6.1</span><span class="sxs-lookup"><span data-stu-id="e64d3-111">.NET Framework 4.6.1</span></span>
- <span data-ttu-id="e64d3-112">Mono 5.4</span><span class="sxs-lookup"><span data-stu-id="e64d3-112">Mono 5.4</span></span>
- <span data-ttu-id="e64d3-113">Xamarin.iOS 10.14</span><span class="sxs-lookup"><span data-stu-id="e64d3-113">Xamarin.iOS 10.14</span></span>
- <span data-ttu-id="e64d3-114">Xamarin.Mac 3.8</span><span class="sxs-lookup"><span data-stu-id="e64d3-114">Xamarin.Mac 3.8</span></span>
- <span data-ttu-id="e64d3-115">Xamarin.Android 8.0</span><span class="sxs-lookup"><span data-stu-id="e64d3-115">Xamarin.Android 8.0</span></span>
- <span data-ttu-id="e64d3-116">通用 Windows 平台 10.0.16299</span><span class="sxs-lookup"><span data-stu-id="e64d3-116">Universal Windows Platform 10.0.16299</span></span>

## <a name="whats-new-in-the-net-standard-20"></a><span data-ttu-id="e64d3-117">什么是.NET 标准 2.0 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="e64d3-117">What's new in the .NET Standard 2.0</span></span>
 
<span data-ttu-id="e64d3-118">.NET 标准 2.0 包括以下新功能：</span><span class="sxs-lookup"><span data-stu-id="e64d3-118">The .NET Standard 2.0 includes the following new features:</span></span>

<span data-ttu-id="e64d3-119">**一组大大扩展的 Api**</span><span class="sxs-lookup"><span data-stu-id="e64d3-119">**A vastly expanded set of APIs**</span></span>

<span data-ttu-id="e64d3-120">通过版本 1.6，.NET 标准包含 Api 的一个相对较小子集。</span><span class="sxs-lookup"><span data-stu-id="e64d3-120">Through version 1.6, the .NET Standard included a comparatively small subset of APIs.</span></span> <span data-ttu-id="e64d3-121">在的中排除了许多通常在.NET Framework 或 Xamarin 中使用的 Api。</span><span class="sxs-lookup"><span data-stu-id="e64d3-121">Among those excluded were many APIs that were commonly used in the .NET Framework or Xamarin.</span></span> <span data-ttu-id="e64d3-122">这将增加复杂性开发，因为它要求开发人员查找合适的替代手段，对于熟悉 Api，当它们开发应用程序和面向多个.NET 实现库中时。</span><span class="sxs-lookup"><span data-stu-id="e64d3-122">This complicates development, since it requires that developers find suitable replacements for familiar APIs when they develop applications and libraries that target multiple .NET implementations.</span></span> <span data-ttu-id="e64d3-123">.NET 标准 2.0 通过添加超过 20000 详细 Api 不是.NET 标准 1.6，标准的以前版本中可用来解决此限制。</span><span class="sxs-lookup"><span data-stu-id="e64d3-123">The .NET Standard 2.0 addresses this limitation by adding over 20,000 more APIs than were available in .NET Standard 1.6, the previous version of the standard.</span></span> <span data-ttu-id="e64d3-124">已添加到.NET 标准 2.0 的 Api 的列表，请参阅[.NET 标准 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md)。</span><span class="sxs-lookup"><span data-stu-id="e64d3-124">For a list of the APIs that have been added to the .NET Standard 2.0, see [.NET Standard 2.0 vs 1.6](https://raw.githubusercontent.com/dotnet/standard/master/docs/versions/netstandard2.0_diff.md).</span></span> 

<span data-ttu-id="e64d3-125">某些上述元素添加到<xref:System>.NET 标准 2.0 中的命名空间包括：</span><span class="sxs-lookup"><span data-stu-id="e64d3-125">Some of the additions to the <xref:System> namespace in .NET Standard 2.0 include:</span></span>

- <span data-ttu-id="e64d3-126">支持<xref:System.AppDomain>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-126">Support for the <xref:System.AppDomain> class.</span></span>
- <span data-ttu-id="e64d3-127">更好地支持与从中其他成员的数组一起使用<xref:System.Array>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-127">Better support for working with arrays from additional members in the <xref:System.Array> class.</span></span>
- <span data-ttu-id="e64d3-128">更好地支持使用从中其他成员的特性<xref:System.Attribute>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-128">Better support for working with attributes from additional members in the <xref:System.Attribute> class.</span></span>
- <span data-ttu-id="e64d3-129">更好地日历支持和其他格式设置选项<xref:System.DateTime>值。</span><span class="sxs-lookup"><span data-stu-id="e64d3-129">Better calendar support and additional formatting options for <xref:System.DateTime> values.</span></span>
- <span data-ttu-id="e64d3-130">其他<xref:System.Decimal>舍入功能。</span><span class="sxs-lookup"><span data-stu-id="e64d3-130">Additional <xref:System.Decimal> rounding functionality.</span></span>
- <span data-ttu-id="e64d3-131">中的其他功能<xref:System.Environment>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-131">Additional functionality in the <xref:System.Environment> class.</span></span>
- <span data-ttu-id="e64d3-132">增强垃圾回收器通过控制<xref:System.GC>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-132">Enhanced control over the garbage collector through the <xref:System.GC> class.</span></span>
- <span data-ttu-id="e64d3-133">对字符串比较、 枚举和中的标准化的增强支持<xref:System.String>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-133">Enhanced support for string comparison, enumeration, and normalization in the <xref:System.String> class.</span></span>
- <span data-ttu-id="e64d3-134">夏时制调整和中的过渡时间支持<xref:System.TimeZoneInfo.AdjustmentRule>和<xref:System.TimeZoneInfo.TransitionTime>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-134">Support for daylight saving adjustments and transition times in the <xref:System.TimeZoneInfo.AdjustmentRule> and <xref:System.TimeZoneInfo.TransitionTime> classes.</span></span>
- <span data-ttu-id="e64d3-135">得到显著增强功能中的<xref:System.Type>类。</span><span class="sxs-lookup"><span data-stu-id="e64d3-135">Significantly enhanced functionality in the <xref:System.Type> class.</span></span>
- <span data-ttu-id="e64d3-136">更好地支持通过添加具有的异常构造函数的异常对象的反序列化<xref:System.Runtime.Serialization.SerializationInfo>和<xref:System.Runtime.Serialization.StreamingContext>参数。</span><span class="sxs-lookup"><span data-stu-id="e64d3-136">Better support for deserialization of exception objects by adding an exception constructor with <xref:System.Runtime.Serialization.SerializationInfo> and <xref:System.Runtime.Serialization.StreamingContext> parameters.</span></span>

<span data-ttu-id="e64d3-137">**.NET Framework 库的支持**</span><span class="sxs-lookup"><span data-stu-id="e64d3-137">**Support for .NET Framework libraries**</span></span>

<span data-ttu-id="e64d3-138">绝大多数库的目标.NET Framework 而不是.NET 标准。</span><span class="sxs-lookup"><span data-stu-id="e64d3-138">The overwhelming majority of libraries target the .NET Framework rather than .NET Standard.</span></span> <span data-ttu-id="e64d3-139">但是，大部分这些库中的调用都是对.NET 标准 2.0 中包含的 Api。</span><span class="sxs-lookup"><span data-stu-id="e64d3-139">However, most of the calls in those libraries are to APIs that are included in the .NET Standard 2.0.</span></span> <span data-ttu-id="e64d3-140">从.NET 标准 2.0 开始，你可以访问.NET Framework 库从.NET 标准库通过使用[兼容性填充码](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification)。</span><span class="sxs-lookup"><span data-stu-id="e64d3-140">Starting with the .NET Standard 2.0, you can access .NET Framework libraries from a .NET Standard library by using a [compatibility shim](https://github.com/dotnet/standard/blob/master/docs/netstandard-20/README.md#assembly-unification).</span></span> <span data-ttu-id="e64d3-141">此兼容性层是透明的开发人员;你无需执行任何操作即可利用.NET Framework 库。</span><span class="sxs-lookup"><span data-stu-id="e64d3-141">This compatibility layer is transparent to developers; you don't have to do anything to take advantage of .NET Framework libraries.</span></span>

<span data-ttu-id="e64d3-142">单个的要求是必须.NET 标准 2.0 中包含的.NET Framework 类库所调用的 Api。</span><span class="sxs-lookup"><span data-stu-id="e64d3-142">The single requirement is that the APIs called by the .NET Framework class library must be included in the .NET Standard 2.0.</span></span>

<span data-ttu-id="e64d3-143">**适用于 Visual Basic 支持**</span><span class="sxs-lookup"><span data-stu-id="e64d3-143">**Support for Visual Basic**</span></span>

<span data-ttu-id="e64d3-144">现在，你可以开发在 Visual Basic 中的标准.NET 库。</span><span class="sxs-lookup"><span data-stu-id="e64d3-144">You can now develop .NET Standard libraries in Visual Basic.</span></span> <span data-ttu-id="e64d3-145">有关 Visual Basic 开发人员使用 Visual Studio 2017 版本 15.3 或更高版本与安装的.NET 核心工作负荷，Visual Studio 现在包含.NET 标准类库模板。</span><span class="sxs-lookup"><span data-stu-id="e64d3-145">For Visual Basic developers using Visual Studio 2017 Version 15.3 or later with the .NET Core workload installed, Visual Studio now includes a .NET Standard Class Library template.</span></span> <span data-ttu-id="e64d3-146">对于 Visual Basic 开发人员可以使用其他开发工具和环境，你可以使用[dotnet 新](../../core/tools/dotnet-new.md)命令以创建.NET 标准库项目。</span><span class="sxs-lookup"><span data-stu-id="e64d3-146">For Visual Basic developers who use other development tools and environments, you can use the [dotnet new](../../core/tools/dotnet-new.md) command to create a .NET Standard Library project.</span></span> <span data-ttu-id="e64d3-147">有关详细信息，请参阅[工具支持的标准.NET 库](#tooling)。</span><span class="sxs-lookup"><span data-stu-id="e64d3-147">For more information, see the [Tooling support for .NET Standard libraries](#tooling).</span></span>

<span data-ttu-id="e64d3-148"><a name="tooling" />**对.NET 标准库工具支持**</span><span class="sxs-lookup"><span data-stu-id="e64d3-148"><a name="tooling" />**Tooling support for .NET Standard libraries**</span></span>

<span data-ttu-id="e64d3-149">对于版本的.NET 核心 2.0 和.NET 标准 2.0，这两个 Visual Studio 2017 和[.NET 核心命令行界面 (CLI)](../../core/tools/index.md)包括工具用于创建标准.NET 库的支持。</span><span class="sxs-lookup"><span data-stu-id="e64d3-149">With the release of .NET Core 2.0 and .NET Standard 2.0, both Visual Studio 2017 and the [.NET Core Command Line Interface (CLI)](../../core/tools/index.md) include tooling support for creating .NET Standard libraries.</span></span> 

<span data-ttu-id="e64d3-150">如果在安装 Visual Studio 与**.NET 核心跨平台开发**工作负荷，你可以通过使用项目模板，如下图所示创建.NET 标准 2.0 库项目。</span><span class="sxs-lookup"><span data-stu-id="e64d3-150">If you install Visual Studio with the **.NET Core cross-platform development** workload, you can create a .NET Standard 2.0 library project by using a project template, as the following figure shows.</span></span> 

# <a name="ctabcsharp"></a>[<span data-ttu-id="e64d3-151">C#</span><span class="sxs-lookup"><span data-stu-id="e64d3-151">C#</span></span>](#tab/csharp)
![添加新.NET 标准库项目](./media/std-project-cs.png)
# <a name="visual-basictabvisual-basic"></a>[<span data-ttu-id="e64d3-153">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e64d3-153">Visual Basic</span></span>](#tab/visual-basic)
<a name="add-new-net-standard-library-projectmediastd-project-vbpng"></a>![添加新.NET 标准库项目](./media/std-project-vb.png)
---

<span data-ttu-id="e64d3-155">如果你使用.NET 核心 CLI，以下[dotnet 新](../../core/tools/dotnet-new.md)命令创建一个类库项目面向.NET 标准 2.0。</span><span class="sxs-lookup"><span data-stu-id="e64d3-155">If you are using the .NET Core CLI, the following [dotnet new](../../core/tools/dotnet-new.md) command creates a class library project that targets the .NET Standard 2.0.</span></span>

```csharp
dotnet new classlib
```
```vb
dotnet new classlib -lang vb
```
  
## <a name="see-also"></a><span data-ttu-id="e64d3-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e64d3-156">See Also</span></span>
<span data-ttu-id="e64d3-157">[.NET 标准](../net-standard.md)
[引入.NET 标准](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span><span class="sxs-lookup"><span data-stu-id="e64d3-157">[.NET Standard](../net-standard.md)
[Introducing .NET Standard](https://blogs.msdn.microsoft.com/dotnet/2016/09/26/introducing-net-standard/)</span></span>
