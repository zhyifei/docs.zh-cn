---
title: "语言功能与库类型之间的关系 |Microsoft 文档"
description: "语言功能通常依赖于要实现的库类型。 了解该关系。"
keywords: "C# 语言设计, 标准库"
author: billwagner
ms.author: wiwagn
ms.date: 07/20/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: b7de4fdb4356e8822dba6aaaf67d615980ff09cd
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="relationships-between-language-features-and-library-types"></a><span data-ttu-id="6b44b-105">语言功能与库类型之间的关系</span><span class="sxs-lookup"><span data-stu-id="6b44b-105">Relationships between language features and library types</span></span>

<span data-ttu-id="6b44b-106">C# 语言定义要求标准库拥有某些类型以及这些类型的特定可访问成员。</span><span class="sxs-lookup"><span data-stu-id="6b44b-106">The C# language definition requires a standard library to have certain types and certain accessible members on those types.</span></span> <span data-ttu-id="6b44b-107">编译器针对多种不同语言功能生成使用这些必需类型和成员的代码。</span><span class="sxs-lookup"><span data-stu-id="6b44b-107">The compiler generates code that uses these required types and members for many different language features.</span></span> <span data-ttu-id="6b44b-108">如有必要，在针对尚未部署这些类型或成员的环境编写代码时，可使用包含较新版本的语言所需类型的 NuGet 包。</span><span class="sxs-lookup"><span data-stu-id="6b44b-108">When necessary, there are NuGet packages that contain types needed for newer versions of the language when writing code for environments where those types or members have not been deployed yet.</span></span>

<span data-ttu-id="6b44b-109">此标准库功能的依赖项自其第一个版本起就是 C# 语言的一部分。</span><span class="sxs-lookup"><span data-stu-id="6b44b-109">This dependency on standard library functionality has been part of the C# language since its first version.</span></span> <span data-ttu-id="6b44b-110">在该版本中，相关示例包括：</span><span class="sxs-lookup"><span data-stu-id="6b44b-110">In that version, examples included:</span></span>

* <span data-ttu-id="6b44b-111"><xref:System.Exception> - 用于编译器生成的所有异常。</span><span class="sxs-lookup"><span data-stu-id="6b44b-111"><xref:System.Exception> - used for all compiler generated exceptions.</span></span>
* <span data-ttu-id="6b44b-112"><xref:System.String> - C# `string` 类型是 <xref:System.String> 的同义词。</span><span class="sxs-lookup"><span data-stu-id="6b44b-112"><xref:System.String> - the C# `string` type is a synonym for <xref:System.String>.</span></span>
* <span data-ttu-id="6b44b-113"><xref:System.Int32> - `int` 的同义词。</span><span class="sxs-lookup"><span data-stu-id="6b44b-113"><xref:System.Int32> - synonym of `int`.</span></span>

<span data-ttu-id="6b44b-114">第一个版本很简单：编译器和标准库一起提供，且各自都只有一个版本。</span><span class="sxs-lookup"><span data-stu-id="6b44b-114">That first version was simple: the compiler and the standard library shipped together, and there was only one version of each.</span></span>

<span data-ttu-id="6b44b-115">后续版本的 C# 偶尔会向依赖项添加新类型或成员。</span><span class="sxs-lookup"><span data-stu-id="6b44b-115">Subsequent versions of C# have occasionally added new types or members to the dependencies.</span></span> <span data-ttu-id="6b44b-116">相关示例包括：<xref:System.Runtime.CompilerServices.INotifyCompletion>、<xref:System.Runtime.CompilerServices.CallerFilePathAttribute> 和 <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>。</span><span class="sxs-lookup"><span data-stu-id="6b44b-116">Examples include: <xref:System.Runtime.CompilerServices.INotifyCompletion>, <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> and <xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>.</span></span> <span data-ttu-id="6b44b-117">C# 7.0 继续添加 <xref:System.ValueTuple> 的依赖项，以实现[元组](../tuples.md)语言功能。</span><span class="sxs-lookup"><span data-stu-id="6b44b-117">C# 7.0 continues this by adding a dependency on <xref:System.ValueTuple> to implement the [tuples](../tuples.md) language feature.</span></span>

<span data-ttu-id="6b44b-118">语言设计团队致力于最小化符合标准的标准库所需的类型和成员的外围应用。</span><span class="sxs-lookup"><span data-stu-id="6b44b-118">The language design team works to minimize the surface area of the types and members required in a compliant standard library.</span></span> <span data-ttu-id="6b44b-119">该目标针对新库功能无缝集成到语言的简洁设计进行了平衡。</span><span class="sxs-lookup"><span data-stu-id="6b44b-119">That goal is balanced against a clean design where new library features are incorporated seamlessly into the language.</span></span> <span data-ttu-id="6b44b-120">未来版本的 C# 中还会包括需要标准库中的新类型和成员的新功能。</span><span class="sxs-lookup"><span data-stu-id="6b44b-120">There will be new features in future versions of C# that require new types and members in a standard library.</span></span> <span data-ttu-id="6b44b-121">必须了解如何管理工作中的这些依赖项。</span><span class="sxs-lookup"><span data-stu-id="6b44b-121">It's important to understand how to manage those dependencies in your work.</span></span>

## <a name="managing-your-dependencies"></a><span data-ttu-id="6b44b-122">管理依赖项</span><span class="sxs-lookup"><span data-stu-id="6b44b-122">Managing your dependencies</span></span>

<span data-ttu-id="6b44b-123">C# 编译器工具现在从支持的平台上 .NET 库的发布周期分离。</span><span class="sxs-lookup"><span data-stu-id="6b44b-123">C# compiler tools are now decoupled from the release cycle of the .NET libraries on supported platforms.</span></span> <span data-ttu-id="6b44b-124">实际上，不同的 .NET 库有不同的发布周期：Windows 上的 .NET Framework 作为 Windows 更新发布，.NET Core 在单独的计划中提供，Xamarin 版本的库更新随适用于每个目标平台的 Xamarin 工具提供。</span><span class="sxs-lookup"><span data-stu-id="6b44b-124">In fact, different .NET libraries have different release cycles: the .NET Framework on Windows is released as a Windows Update, .NET Core ships on a separate schedule, and the Xamarin versions of library updates ship with the Xamarin tools for each target platform.</span></span>

<span data-ttu-id="6b44b-125">大多数时候，用户都不会注意到这些更改。</span><span class="sxs-lookup"><span data-stu-id="6b44b-125">The majority of time, you won't notice these changes.</span></span> <span data-ttu-id="6b44b-126">但是，如果使用的较新版本语言需要该平台上的 .NET 库中尚未包含的功能，则会引用 NuGet 包以提供这些新类型。</span><span class="sxs-lookup"><span data-stu-id="6b44b-126">However, when you are working with a newer version of the language that requires features not yet in the .NET libraries on that platform, you'll reference the NuGet packages to provide those new types.</span></span>
<span data-ttu-id="6b44b-127">应用支持的平台会随着新框架的安装而更新，因此可以删除额外的引用。</span><span class="sxs-lookup"><span data-stu-id="6b44b-127">As the platforms your app supports are updated with new framework installations, you can remove the extra reference.</span></span>

<span data-ttu-id="6b44b-128">此分离意味着即使面向没有相应框架的计算机，仍可使用新语言功能。</span><span class="sxs-lookup"><span data-stu-id="6b44b-128">This separation means you can use new language features even when you are targeting machines that may not have the corresponding framework.</span></span>
