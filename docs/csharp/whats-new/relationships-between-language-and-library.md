---
title: "语言功能和库类型之间的关系 |Microsoft 文档"
description: "语言功能通常依赖于实现的库类型。 了解该关系。"
keywords: "C# 语言设计中，标准库"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 93fd26a72743fcf45df3904cb8d0c787d8a228a8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2017
---
# <a name="relationships-between-language-features-and-library-types"></a><span data-ttu-id="53477-105">语言功能和库类型之间的关系</span><span class="sxs-lookup"><span data-stu-id="53477-105">Relationships between language features and library types</span></span>

<span data-ttu-id="53477-106">C# 语言定义需要能够在这些类型上的某些类型和某些可访问的成员的标准库。</span><span class="sxs-lookup"><span data-stu-id="53477-106">The C# language definition requires a standard library to have certain types and certain accessible members on those types.</span></span> <span data-ttu-id="53477-107">编译器将生成用于许多不同的语言功能的这些必需的类型和成员的代码。</span><span class="sxs-lookup"><span data-stu-id="53477-107">The compiler generates code that uses these required types and members for many different language features.</span></span> <span data-ttu-id="53477-108">如有必要，有包含所需的较新版本的语言，在编写代码，这些类型或成员具有尚未部署的环境时的类型的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="53477-108">When necessary, there are NuGet packages that contain types needed for newer versions of the language when writing code for environments where those types or members have not been deployed yet.</span></span>

<span data-ttu-id="53477-109">此依赖于标准库功能已被自其第一个版本以来 C# 语言的一部分。</span><span class="sxs-lookup"><span data-stu-id="53477-109">This dependency on standard library functionality has been part of the C# language since its first version.</span></span> <span data-ttu-id="53477-110">在该版本中，包括示例：</span><span class="sxs-lookup"><span data-stu-id="53477-110">In that version, examples included:</span></span>

* <span data-ttu-id="53477-111"><xref:System.Exception>-用于编译器生成的所有异常。</span><span class="sxs-lookup"><span data-stu-id="53477-111"><xref:System.Exception> - used for all compiler generated exceptions.</span></span>
* <span data-ttu-id="53477-112"><xref:System.String>-C#`string`类型是同义词<xref:System.String>。</span><span class="sxs-lookup"><span data-stu-id="53477-112"><xref:System.String> - the C# `string` type is a synonym for <xref:System.String>.</span></span>
* <span data-ttu-id="53477-113"><xref:System.Int32>-的同义词`int`。</span><span class="sxs-lookup"><span data-stu-id="53477-113"><xref:System.Int32> - synonym of `int`.</span></span>

<span data-ttu-id="53477-114">该第一个版本很简单： 编译器和标准库提供的在一起，且每个只有一个版本。</span><span class="sxs-lookup"><span data-stu-id="53477-114">That first version was simple: the compiler and the standard library shipped together, and there was only one version of each.</span></span>

<span data-ttu-id="53477-115">后续版本的 C# 具有偶尔添加新类型或成员的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="53477-115">Subsequent versions of C# have occasionally added new types or members to the dependencies.</span></span> <span data-ttu-id="53477-116">示例包括： <xref:System.Runtime.CompilerServices.INotifyCompletion>，<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>和<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>。</span><span class="sxs-lookup"><span data-stu-id="53477-116">Examples include: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> and <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>.</span></span> <span data-ttu-id="53477-117">通过上添加依赖关系的 C# 7.0 继续这<xref:System.ValueTuple>实现[元组](../tuples.md)语言功能。</span><span class="sxs-lookup"><span data-stu-id="53477-117">C# 7.0 continues this by adding a dependency on <xref:System.ValueTuple> to implement the [tuples](../tuples.md) language feature.</span></span>

<span data-ttu-id="53477-118">语言设计团队将采取措施以最小化的类型和成员在符合标准库中所需的外围应用。</span><span class="sxs-lookup"><span data-stu-id="53477-118">The language design team works to minimize the surface area of the types and members required in a compliant standard library.</span></span> <span data-ttu-id="53477-119">该目标是针对其中新的库功能并入无缝语言的干净设计平衡。</span><span class="sxs-lookup"><span data-stu-id="53477-119">That goal is balanced against a clean design where new library features are incorporated seamlessly into the language.</span></span> <span data-ttu-id="53477-120">将需要新类型的将来版本的 C# 中的新增功能和标准库中的成员。</span><span class="sxs-lookup"><span data-stu-id="53477-120">There will be new features in future versions of C# that require new types and members in a standard library.</span></span> <span data-ttu-id="53477-121">请务必了解如何管理你的工作中的这些依赖关系。</span><span class="sxs-lookup"><span data-stu-id="53477-121">It's important to understand how to manage those dependencies in your work.</span></span>

## <a name="managing-your-dependencies"></a><span data-ttu-id="53477-122">管理依赖项</span><span class="sxs-lookup"><span data-stu-id="53477-122">Managing your dependencies</span></span>

<span data-ttu-id="53477-123">从支持的平台上的.NET 库的发行周期将 C# 编译器工具现在会分离。</span><span class="sxs-lookup"><span data-stu-id="53477-123">C# compiler tools are now decoupled from the release cycle of the .NET libraries on supported platforms.</span></span> <span data-ttu-id="53477-124">实际上，不同的.NET 库有不同的发布周期： 在 Windows 上的.NET Framework 是 relesed 与 Windows 更新，在单独的计划，以及 Xamarin 版本的库更新附带了适用于每个目标平台的 Xamarin 工具附带的.NET 核心。</span><span class="sxs-lookup"><span data-stu-id="53477-124">In fact, different .NET libraries have different release cycles: the .NET Framework on Windows is relesed as a Windows Update, .NET Core ships on a separate schedule, and the Xamarin versions of library updates ship with the Xamarin tools for each target platform.</span></span>

<span data-ttu-id="53477-125">大多数时间，你不会注意到这些更改。</span><span class="sxs-lookup"><span data-stu-id="53477-125">The majority of time, you won't notice these changes.</span></span> <span data-ttu-id="53477-126">但是，当你正在使用的语言不需要功能尚未.NET 库中的较新版本在该平台上，你将引用 NuGet 程序包，以提供这些新类型。</span><span class="sxs-lookup"><span data-stu-id="53477-126">However, when you are working with a newer version of the language that requires features not yet in the .NET libraries on that platform, you'll reference the NuGet packages to provide those new types.</span></span>
<span data-ttu-id="53477-127">作为新的 framework 安装更新，你的应用程序支持的平台，你可以删除额外的引用。</span><span class="sxs-lookup"><span data-stu-id="53477-127">As the platforms your app supports are updated with new framework installations, you can remove the extra reference.</span></span>

<span data-ttu-id="53477-128">这种分离意味着你可以使用新语言功能，即使你将可能没有相应的 framework 的计算机。</span><span class="sxs-lookup"><span data-stu-id="53477-128">This separation means you can use new language features even when you are targeting machines that may not have the corresponding framework.</span></span>
