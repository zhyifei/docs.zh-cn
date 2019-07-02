---
title: 评估 NET Core 中的中断性变更
description: 了解 .NET Core 为开发人员保持各 .NET 版本兼容性所使用的方法。
author: rpetrusha
ms.author: ronpet
ms.date: 06/10/2019
ms.openlocfilehash: b58edd9ff0bd56b12b861162cc92d484a3b36c8b
ms.sourcegitcommit: a970268118ea61ce14207e0916e17243546a491f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/21/2019
ms.locfileid: "67307538"
---
# <a name="evaluate-breaking-changes-in-net-core"></a><span data-ttu-id="3a754-103">评估 .NET Core 中的中断性变更</span><span class="sxs-lookup"><span data-stu-id="3a754-103">Evaluate breaking changes in .NET Core</span></span>

<span data-ttu-id="3a754-104">在 .NET 的整个历史记录中，它都尝试在版本之间以及 .NET 各个风格之间保持高级别的兼容性。</span><span class="sxs-lookup"><span data-stu-id="3a754-104">Throughout its history, .NET has attempted to maintain a high level of compatibility from version to version and across flavors of .NET.</span></span> <span data-ttu-id="3a754-105">.NET Core 将继续坚守这个准则。</span><span class="sxs-lookup"><span data-stu-id="3a754-105">This continues to be true for .NET Core.</span></span> <span data-ttu-id="3a754-106">尽管可以将 .NET Core 视为独立于 .NET Framework 的新技术，但下面的两个因素使 .NET Core 无法脱离 .NET Framework：</span><span class="sxs-lookup"><span data-stu-id="3a754-106">Although .NET Core can be considered as a new technology that is independent of the .NET Framework, two major factors limit the ability of .NET Core to diverge from .NET Framework:</span></span>

- <span data-ttu-id="3a754-107">有许多最初开发过或在继续开发 .NET Framework 应用程序的开发人员。</span><span class="sxs-lookup"><span data-stu-id="3a754-107">A large number of developers either originally developed or continue to develop .NET Framework applications.</span></span> <span data-ttu-id="3a754-108">他们希望各个 .NET 实现中的行为保持一致。</span><span class="sxs-lookup"><span data-stu-id="3a754-108">They expect consistent behavior across .NET implementations.</span></span>

- <span data-ttu-id="3a754-109">.NET Standard 库项目允许开发人员创建面向 .NET Core 和 .NET Framework 共享的通用 API 的库。</span><span class="sxs-lookup"><span data-stu-id="3a754-109">.NET Standard library projects allow developers to create libraries that target common APIs shared by .NET Core and .NET Framework.</span></span> <span data-ttu-id="3a754-110">开发人员希望用于 .NET Core 应用程序的库与用于 .NET Framework 应用程序的同一个库的行为相同。</span><span class="sxs-lookup"><span data-stu-id="3a754-110">Developers expect that a library used in a .NET Core application should behave identically to the same library used in a .NET Framework application.</span></span>

<span data-ttu-id="3a754-111">在希望保持各个 .NET 实现之间的兼容性的同时，开发人员还希望在各个 .NET Core 版本之间保持高级别的兼容性。</span><span class="sxs-lookup"><span data-stu-id="3a754-111">Along with compatibility across .NET implementations, developers expect a high level of compatibility across .NET Core versions.</span></span> <span data-ttu-id="3a754-112">具体而言，为 .NET Core 早期版本编写的代码应在较高版本的 .NET Core 上无缝运行。</span><span class="sxs-lookup"><span data-stu-id="3a754-112">In particular, code written for an earlier version of .NET Core should run seamlessly on a later version of .NET Core.</span></span> <span data-ttu-id="3a754-113">实际上，许多开发人员都希望新发布的 .NET Core 版本中的新 API 也应该与引入这些 API 的预发布版本兼容。</span><span class="sxs-lookup"><span data-stu-id="3a754-113">In fact, many developers expect that the new APIs found in newly released versions of .NET Core should also be compatible with the pre-release versions in which those APIs were introduced.</span></span>

<span data-ttu-id="3a754-114">本文概述了兼容性变更（或中断性变更）的类别，以及 .NET 团队如何评估各个类别中的变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-114">This article outlines the categories of compatibility changes (or breaking changes) and the way in which the .NET team evaluates changes in each of these categories.</span></span> <span data-ttu-id="3a754-115">开发人员在 [dotnet/corefx](https://github.com/dotnet/corefx) GitHub 存储库中发布拉取请求来修改现有 API 的行为时，如果了解 .NET 团队如何处理可能的中断性变更，这将非常有用。</span><span class="sxs-lookup"><span data-stu-id="3a754-115">Understanding how the .NET team approaches possible breaking changes is particularly helpful for developers who are opening pull requests in the [dotnet/corefx](https://github.com/dotnet/corefx) GitHub repository that modify the behavior of existing APIs.</span></span>

> [!NOTE]
> <span data-ttu-id="3a754-116">若要查看兼容性类别的定义，如二进制兼容性和向后兼容性，请参阅[中断性变更类别](categories.md)。</span><span class="sxs-lookup"><span data-stu-id="3a754-116">For a definition of compatibility categories, such as binary compatibility and backward compatibility, see [Breaking change categories](categories.md).</span></span>

<span data-ttu-id="3a754-117">以下各个部分说明了 .NET Core API 的变更类别，以及它们对应用程序兼容性的影响。</span><span class="sxs-lookup"><span data-stu-id="3a754-117">The following sections describes the categories of changes made to .NET Core APIs and their impact on application compatibility.</span></span> <span data-ttu-id="3a754-118">✔️ 图标表示允许某个特定的变更类别， 表示禁止某个类别， 表示可能允许也可能不允许某个变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-118">The ✔️ icon indicates that a particular kind of change is allowed, ❌ indicates that it is disallowed, and  ❓ indicates a change that may or may not be allowed.</span></span> <span data-ttu-id="3a754-119">最后一个类别中的变更需要评判之前的行为的可预测性、显著性和一致性。</span><span class="sxs-lookup"><span data-stu-id="3a754-119">Changes in this last category require judgment and an evaluation of how predictable, obvious, and consistent the previous behavior was.</span></span>

> [!NOTE]
> <span data-ttu-id="3a754-120">除了将这些准则用作 .NET Core 库变更评估指南以外，库开发人员还可以使用它们评估他们自己的面向多个 .NET 实现和版本的库更改。</span><span class="sxs-lookup"><span data-stu-id="3a754-120">In addition to serving as a guide to how changes to .NET Core libraries are evaluated, library developers can also use these criteria to evaluate changes to their libraries that target multiple .NET implementations and versions.</span></span>

## <a name="modifications-to-the-public-contract"></a><span data-ttu-id="3a754-121">公共协定修改</span><span class="sxs-lookup"><span data-stu-id="3a754-121">Modifications to the public contract</span></span>

<span data-ttu-id="3a754-122">此类别中的变更将修改类型的公共外围应用。 </span><span class="sxs-lookup"><span data-stu-id="3a754-122">Changes in this category *modify* the public surface area of a type.</span></span> <span data-ttu-id="3a754-123">禁止此类别中的多数变更，因为它们违反了向后兼容性（使用早期 API 版本生成的应用程序的功能：无需在较高版本上重新编译即可运行）。 </span><span class="sxs-lookup"><span data-stu-id="3a754-123">Most of the changes in this category are disallowed since they violate *backwards compatibility* (the ability of an application that was developed with a previous version of an API to execute without recompilation on a later version).</span></span>

### <a name="types"></a><span data-ttu-id="3a754-124">类型</span><span class="sxs-lookup"><span data-stu-id="3a754-124">Types</span></span>

- <span data-ttu-id="3a754-125">**✔️ 基类型已实现接口时，从类型中删除接口实现**</span><span class="sxs-lookup"><span data-stu-id="3a754-125">**✔️ Removing an interface implementation from a type when the interface is already implemented by a base type**</span></span>

- <span data-ttu-id="3a754-126">**向类型添加新的接口实现**</span><span class="sxs-lookup"><span data-stu-id="3a754-126">**❓ Adding a new interface implementation to a type**</span></span>

  <span data-ttu-id="3a754-127">此为可接受的变更，因为它不会对现有客户端产生不良影响。</span><span class="sxs-lookup"><span data-stu-id="3a754-127">This is an acceptable change because it does not adversely affect existing clients.</span></span> <span data-ttu-id="3a754-128">对此类型的任何变更必须在此处定义的可接受变更的边界内工作，新实现才能继续成为可接受的实现。</span><span class="sxs-lookup"><span data-stu-id="3a754-128">Any changes to the type must work within the boundaries of acceptable changes defined here for the new implementation to remain acceptable.</span></span> <span data-ttu-id="3a754-129">添加直接影响设计器或序列化程序功能（生成无法供低级使用的代码或数据的功能）的接口时，需要格外注意。</span><span class="sxs-lookup"><span data-stu-id="3a754-129">Extreme caution is necessary when adding interfaces that directly affect the ability of a designer or serializer to generate code or data that cannot be consumed down-level.</span></span> <span data-ttu-id="3a754-130">例如 <xref:System.Runtime.Serialization.ISerializable> 接口。</span><span class="sxs-lookup"><span data-stu-id="3a754-130">An example is the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span>

- <span data-ttu-id="3a754-131">**引入新的基类**</span><span class="sxs-lookup"><span data-stu-id="3a754-131">**❓ Introducing a new base class**</span></span>

  <span data-ttu-id="3a754-132">若类型未引入任何新的[抽象](../../csharp/language-reference/keywords/abstract.md)成员且未更改现有类型的语义或行为，可以将它引入到两个现有类型之间的层次结构。</span><span class="sxs-lookup"><span data-stu-id="3a754-132">A type can be introduced into an hierarchy between two existing types if it doesn't introduce any new [abstract](../../csharp/language-reference/keywords/abstract.md) members or change the semantics or behavior of existing types.</span></span> <span data-ttu-id="3a754-133">例如，在 .NET Framework 2.0 中，<xref:System.Data.Common.DbConnection> 类成为之前直接派生自 <xref:System.ComponentModel.Component> 的 <xref:System.Data.SqlClient.SqlConnection> 的新基类。</span><span class="sxs-lookup"><span data-stu-id="3a754-133">For example, in .NET Framework 2.0, the <xref:System.Data.Common.DbConnection> class became a new base class for <xref:System.Data.SqlClient.SqlConnection>, which had previously derived directly from <xref:System.ComponentModel.Component>.</span></span>

- <span data-ttu-id="3a754-134">**✔️ 将某个程序集中的类型移动到另一个程序集中**</span><span class="sxs-lookup"><span data-stu-id="3a754-134">**✔️ Moving a type from one assembly to another**</span></span>

  <span data-ttu-id="3a754-135">请注意，旧程序集必须标有指向新程序集的 <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute>  。</span><span class="sxs-lookup"><span data-stu-id="3a754-135">Note that the *old* assembly must be marked with the <xref:System.Runtime.CompilerServices.TypeForwardedToAttribute> that points to the new assembly.</span></span>

- <span data-ttu-id="3a754-136">**✔️ 将 [struct](../../csharp/language-reference/keywords/struct.md) 类型更改为 `readonly struct` 类型**</span><span class="sxs-lookup"><span data-stu-id="3a754-136">**✔️ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `readonly struct` type**</span></span>

  <span data-ttu-id="3a754-137">请注意，不允许将 `readonly struct` 类型更改为 `struct` 类型。</span><span class="sxs-lookup"><span data-stu-id="3a754-137">Note that changing a `readonly struct` type to a `struct` type is not allowed.</span></span>
  
- <span data-ttu-id="3a754-138">**✔️ 没有可访问的（公共或受保护的）构造函数时，向类型添加 [sealed](../../csharp/language-reference/keywords/sealed.md) 或 [abstract](../../csharp/language-reference/keywords/abstract.md) 关键字** </span><span class="sxs-lookup"><span data-stu-id="3a754-138">**✔️ Adding the [sealed](../../csharp/language-reference/keywords/sealed.md) or [abstract](../../csharp/language-reference/keywords/abstract.md) keyword to a type when there are no *accessible* (public or protected) constructors**</span></span>

- <span data-ttu-id="3a754-139">**✔️ 扩展类型的可见性**</span><span class="sxs-lookup"><span data-stu-id="3a754-139">**✔️ Expanding the visibility of a type**</span></span>

- <span data-ttu-id="3a754-140">**更改类型的命名空间或名称**</span><span class="sxs-lookup"><span data-stu-id="3a754-140">**❌ Changing the namespace or name of a type**</span></span>

- <span data-ttu-id="3a754-141">**重命名或删除公共类型**</span><span class="sxs-lookup"><span data-stu-id="3a754-141">**❌ Renaming or removing a public type**</span></span>

   <span data-ttu-id="3a754-142">这将中断使用重命名的或删除的类型的所有代码。</span><span class="sxs-lookup"><span data-stu-id="3a754-142">This breaks all code that uses the renamed or removed type.</span></span>

- <span data-ttu-id="3a754-143">**更改枚举的基础类型**</span><span class="sxs-lookup"><span data-stu-id="3a754-143">**❌ Changing the underlying type of an enumeration**</span></span>

   <span data-ttu-id="3a754-144">此为编译时和行为中断性变更，此外它还是可能会导致属性参数不可分析的二进制中断性更改。</span><span class="sxs-lookup"><span data-stu-id="3a754-144">This is a compile-time and behavioral breaking change as well as a binary breaking change that can make attribute arguments unparsable.</span></span>

- <span data-ttu-id="3a754-145">**密封之前未密封的类型**</span><span class="sxs-lookup"><span data-stu-id="3a754-145">**❌ Sealing a type that was previously unsealed**</span></span>

- <span data-ttu-id="3a754-146">**向接口的一组基类型添加接口**</span><span class="sxs-lookup"><span data-stu-id="3a754-146">**❌ Adding an interface to the set of base types of an interface**</span></span>

   <span data-ttu-id="3a754-147">若接口实现它未曾实现过的接口，将中断实现此接口的原始版本的所有类型。</span><span class="sxs-lookup"><span data-stu-id="3a754-147">If an interface implements an interface that it previously did not implement, all types that implemented the original version of the interface are broken.</span></span>

- <span data-ttu-id="3a754-148">**从一组基类删除某个类，或从一组实现的接口删除某个接口**</span><span class="sxs-lookup"><span data-stu-id="3a754-148">**❓ Removing a class from the set of base classes or an interface from the set of implemented interfaces**</span></span>

  <span data-ttu-id="3a754-149">接口删除规则有一个例外情况：可以添加派生自删除的接口的接口实现。</span><span class="sxs-lookup"><span data-stu-id="3a754-149">There is one exception to the rule for interface removal: you can add the implementation of an interface that derives from the removed interface.</span></span> <span data-ttu-id="3a754-150">例如，如果类型或接口现在实现将实现 <xref:System.IDisposable> 的 <xref:System.ComponentModel.IComponent>，则可以删除 <xref:System.IDisposable>。</span><span class="sxs-lookup"><span data-stu-id="3a754-150">For example, you can remove <xref:System.IDisposable> if the type or interface now implements <xref:System.ComponentModel.IComponent>, which implements <xref:System.IDisposable>.</span></span>

- <span data-ttu-id="3a754-151">**将 `readonly struct` 类型更改为 [struct](../../csharp/language-reference/keywords/struct.md) 类型**</span><span class="sxs-lookup"><span data-stu-id="3a754-151">**❌ Changing a `readonly struct` type to a [struct](../../csharp/language-reference/keywords/struct.md) type**</span></span>

  <span data-ttu-id="3a754-152">请注意，允许将 `struct` 类型更改为 `readonly struct` 类型。</span><span class="sxs-lookup"><span data-stu-id="3a754-152">Note that the change of a `struct` type to a `readonly struct` type is allowed.</span></span>

- <span data-ttu-id="3a754-153">**将 [struct](../../csharp/language-reference/keywords/struct.md) 类型更改为 `ref struct` 类型，反之亦然**</span><span class="sxs-lookup"><span data-stu-id="3a754-153">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) type to a `ref struct` type, and vice versa**</span></span>

- <span data-ttu-id="3a754-154">**降低类型的可见性**</span><span class="sxs-lookup"><span data-stu-id="3a754-154">**❌ Reducing the visibility of a type**</span></span>

   <span data-ttu-id="3a754-155">但允许增大类型的可见性。</span><span class="sxs-lookup"><span data-stu-id="3a754-155">However, increasing the visibility of a type is allowed.</span></span>

### <a name="members"></a><span data-ttu-id="3a754-156">成员</span><span class="sxs-lookup"><span data-stu-id="3a754-156">Members</span></span>

- <span data-ttu-id="3a754-157">**✔️ 扩展非 [成员的可见性](../../csharp/language-reference/keywords/sealed.md)**</span><span class="sxs-lookup"><span data-stu-id="3a754-157">**✔️ Expanding the visibility of a member that is not [virtual](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="3a754-158">\*\*✔️ 向不包含任何可访问的（公共或受保护的）构造函数或为 [sealed](../../csharp/language-reference/keywords/sealed.md) 类型的公共类型添加抽象成员  \*\*</span><span class="sxs-lookup"><span data-stu-id="3a754-158">**✔️ Adding an abstract member to a public type that has no *accessible* (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

  <span data-ttu-id="3a754-159">但不允许向包含可访问的（公共或受保护的）构造函数且非 `sealed` 类型的类型添加抽象成员。</span><span class="sxs-lookup"><span data-stu-id="3a754-159">However, adding an abstract member to a type that has accessible (public or protected) constructors and is not `sealed` is not allowed.</span></span>

- <span data-ttu-id="3a754-160">**✔️ 类型不包含任何可访问的（公共或受保护的）构造函数或类型为 [sealed](../../csharp/language-reference/keywords/sealed.md) 类型时，限制 [protected](../../csharp/language-reference/keywords/protected.md) 成员的可见性**</span><span class="sxs-lookup"><span data-stu-id="3a754-160">**✔️ Restricting the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when the type has no accessible (public or protected) constructors, or the type is [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="3a754-161">**✔️ 将成员移动到层次结构中高于删除的成员所在的类型的类**</span><span class="sxs-lookup"><span data-stu-id="3a754-161">**✔️ Moving a member into a class higher in the hierarchy than the type from which it was removed**</span></span>

- <span data-ttu-id="3a754-162">**✔️ 添加或删除重写**</span><span class="sxs-lookup"><span data-stu-id="3a754-162">**✔️ Adding or removing an override**</span></span>

  <span data-ttu-id="3a754-163">请注意，引入重写可能会导致先前的使用者在调用[基](../../csharp/language-reference/keywords/base.md)时跳过重写。</span><span class="sxs-lookup"><span data-stu-id="3a754-163">Note that introducing an override might cause previous consumers to skip over the override when calling [base](../../csharp/language-reference/keywords/base.md).</span></span>

- <span data-ttu-id="3a754-164">**✔️ 若类过去不包含任何构造函数，向类添加构造函数及默认的（无参数）构造函数**</span><span class="sxs-lookup"><span data-stu-id="3a754-164">**✔️ Adding a constructor to a class, along with a default (parameterless) constructor if the class previously had no constructors**</span></span>

   <span data-ttu-id="3a754-165">但是，不允许在未对过去不包含任何构造函数的类添加默认构造函数的情况下向其添加构造函数。 </span><span class="sxs-lookup"><span data-stu-id="3a754-165">However, adding a constructor to a class that previously had no constructors *without* adding the default constructor is not allowed.</span></span>

- <span data-ttu-id="3a754-166">**✔️ 将成员从 [abstract](../../csharp/language-reference/keywords/abstract.md) 更改为 [virtual](../../csharp/language-reference/keywords/virtual.md)**</span><span class="sxs-lookup"><span data-stu-id="3a754-166">**✔️ Changing a member from [abstract](../../csharp/language-reference/keywords/abstract.md) to [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

- <span data-ttu-id="3a754-167">**✔️ 从 `ref readonly` 更改为 `ref` 返回值（虚拟方法或接口除外）**</span><span class="sxs-lookup"><span data-stu-id="3a754-167">**✔️ Changing from a `ref readonly` to a `ref` return value (except for virtual methods or interfaces)**</span></span>

- <span data-ttu-id="3a754-168">**✔️ 若字段的静态类型为非可变的值类型，从字段删除 [readonly](../../csharp/language-reference/keywords/readonly.md)**</span><span class="sxs-lookup"><span data-stu-id="3a754-168">**✔️ Removing [readonly](../../csharp/language-reference/keywords/readonly.md) from a field, unless the static type of the field is a mutable value type**</span></span>

- <span data-ttu-id="3a754-169">**✔️ 调用未曾定义的新事件**</span><span class="sxs-lookup"><span data-stu-id="3a754-169">**✔️ Calling a new event that wasn't previously defined**</span></span>

- <span data-ttu-id="3a754-170">**向类型添加新实例字段**</span><span class="sxs-lookup"><span data-stu-id="3a754-170">**❓ Adding a new instance field to a type**</span></span>

   <span data-ttu-id="3a754-171">此变更影响序列化。</span><span class="sxs-lookup"><span data-stu-id="3a754-171">This change impacts serialization.</span></span>

- <span data-ttu-id="3a754-172">**重命名或删除公共成员或参数**</span><span class="sxs-lookup"><span data-stu-id="3a754-172">**❌ Renaming or removing a public member or parameter**</span></span>

   <span data-ttu-id="3a754-173">这将中断使用重命名的或删除的成员或参数的所有代码。</span><span class="sxs-lookup"><span data-stu-id="3a754-173">This breaks all code that uses the renamed or removed member, or parameter.</span></span>

   <span data-ttu-id="3a754-174">请注意，这包括删除或重命名属性中的 Getter 或资源库，以及重命名或删除枚举成员。</span><span class="sxs-lookup"><span data-stu-id="3a754-174">Note that this includes removing or renaming a getter or setter from a property, as well as renaming or removing enumeration members.</span></span>

- <span data-ttu-id="3a754-175">**向接口添加成员**</span><span class="sxs-lookup"><span data-stu-id="3a754-175">**❌ Adding a member to an interface**</span></span>

- <span data-ttu-id="3a754-176">**更改公共常量或枚举成员的值**</span><span class="sxs-lookup"><span data-stu-id="3a754-176">**❌ Changing the value of a public constant or enumeration member**</span></span>

- <span data-ttu-id="3a754-177">**更改属性类型、字段、参数或返回值**</span><span class="sxs-lookup"><span data-stu-id="3a754-177">**❌ Changing the type of a property, field, parameter, or return value**</span></span>

- <span data-ttu-id="3a754-178">**添加、删除、或更改参数的顺序**</span><span class="sxs-lookup"><span data-stu-id="3a754-178">**❌ Adding, removing, or changing the order of parameters**</span></span>

- <span data-ttu-id="3a754-179">**从参数中添加或删除 [in](../../csharp/language-reference/keywords/in.md)、[out](../../csharp/language-reference/keywords/out.md) 或 [ref](../../csharp/language-reference/keywords/ref.md) 关键字**</span><span class="sxs-lookup"><span data-stu-id="3a754-179">**❌ Adding or removing the [in](../../csharp/language-reference/keywords/in.md), [out](../../csharp/language-reference/keywords/out.md) , or [ref](../../csharp/language-reference/keywords/ref.md) keyword from a parameter**</span></span>

- <span data-ttu-id="3a754-180">**重命名参数（包括更改其大小写）**</span><span class="sxs-lookup"><span data-stu-id="3a754-180">**❌ Renaming a parameter (including changing its case)**</span></span>

  <span data-ttu-id="3a754-181">鉴于以下两个原因将此视为中断性变更：</span><span class="sxs-lookup"><span data-stu-id="3a754-181">This is considered breaking for two reasons:</span></span>
  
  - <span data-ttu-id="3a754-182">它将中断后期绑定方案，如 Visual Basic 中的后期绑定功能和 C# 的 [dynamic](../../csharp/language-reference/keywords/dynamic.md)。</span><span class="sxs-lookup"><span data-stu-id="3a754-182">It breaks late-bound scenarios such as the late binding feature in Visual Basic and [dynamic](../../csharp/language-reference/keywords/dynamic.md) in C#.</span></span>
  
  - <span data-ttu-id="3a754-183">如果开发人员使用[命名参数](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments)，它将中断[源兼容性](categories.md#source-compatibility)。</span><span class="sxs-lookup"><span data-stu-id="3a754-183">It breaks [source compatibility](categories.md#source-compatibility) when developers use [named arguments](../../csharp/programming-guide/classes-and-structs/named-and-optional-arguments.md#named-arguments).</span></span>

- <span data-ttu-id="3a754-184">**从 `ref` 返回值更改为 `ref readonly` 返回值**</span><span class="sxs-lookup"><span data-stu-id="3a754-184">**❌ Changing from a `ref` return value to a `ref readonly` return value**</span></span>

- <span data-ttu-id="3a754-185">**️ 在虚拟方法或接口上从 `ref readonly` 更改为 `ref` 返回值**</span><span class="sxs-lookup"><span data-stu-id="3a754-185">**❌️ Changing from a `ref readonly` to a `ref` return value on a virtual method or interface**</span></span>

- <span data-ttu-id="3a754-186">**从成员添加或删除 [abstract](../../csharp/language-reference/keywords/abstract.md)**</span><span class="sxs-lookup"><span data-stu-id="3a754-186">**❌ Adding or removing [abstract](../../csharp/language-reference/keywords/abstract.md) from a member**</span></span>

- <span data-ttu-id="3a754-187">**从成员删除 [virtual](../../csharp/language-reference/keywords/virtual.md) 关键字**</span><span class="sxs-lookup"><span data-stu-id="3a754-187">**❌ Removing the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword from a member**</span></span>

  <span data-ttu-id="3a754-188">通常这不属于中断性变更，因为 C# 编译器通常会发出 [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) 中间语言 (IL) 指令来调用非虚拟方法（`callvirt` 执行 null 检查，而常规调用不会执行此检查），鉴于下列原因此行为非恒定：</span><span class="sxs-lookup"><span data-stu-id="3a754-188">While this often is not a breaking change because the C# compiler tends to emit [callvirt](<xref:System.Reflection.Emit.OpCodes.Callvirt>) Intermediate Language (IL) instructions to call non-virtual methods (`callvirt` performs a null check, while a normal call doesn't), this behavior is not invariable for several reasons:</span></span>
  - <span data-ttu-id="3a754-189">C# 并非 .NET 面向的唯一语言。</span><span class="sxs-lookup"><span data-stu-id="3a754-189">C# is not the only language that .NET targets.</span></span>
  
  - <span data-ttu-id="3a754-190">目标方法为非虚拟且可能非 null 时（如通过 [?. null 传播运算符](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)访问的方法），C# 编译器逐渐尝将 `callvirt` 优化为常规调用。</span><span class="sxs-lookup"><span data-stu-id="3a754-190">The C# compiler increasingly tries to optimize `callvirt` to a normal call whenever the target method is non-virtual and is probably not null (such as a method accessed through the [?. null propagation operator](../../csharp/language-reference/operators/member-access-operators.md#null-conditional-operators--and-)).</span></span>
  
  <span data-ttu-id="3a754-191">使方法成为虚拟方法意味着使用者代码通常最终要以非虚拟方式调用它。</span><span class="sxs-lookup"><span data-stu-id="3a754-191">Making a method virtual means that the consumer code would often end up calling it non-virtually.</span></span>

- <span data-ttu-id="3a754-192">**向成员添加 [virtual](../../csharp/language-reference/keywords/virtual.md) 关键字**</span><span class="sxs-lookup"><span data-stu-id="3a754-192">**❌ Adding the [virtual](../../csharp/language-reference/keywords/virtual.md) keyword to a member**</span></span>

- <span data-ttu-id="3a754-193">**使虚拟成员成为抽象成员**</span><span class="sxs-lookup"><span data-stu-id="3a754-193">**❌ Making a virtual member abstract**</span></span>

  <span data-ttu-id="3a754-194">[抽象成员](../../csharp/language-reference/keywords/virtual.md)提供可以由派生类重写的方法实现。 </span><span class="sxs-lookup"><span data-stu-id="3a754-194">A [virtual member](../../csharp/language-reference/keywords/virtual.md) provides a method implementation that *can be* overridden by a derived class.</span></span> <span data-ttu-id="3a754-195">[抽象成员](../../csharp/language-reference/keywords/abstract.md)不提供任何实现，且必须重写。 </span><span class="sxs-lookup"><span data-stu-id="3a754-195">An [abstract member](../../csharp/language-reference/keywords/abstract.md) provides no implementation and *must be* overridden.</span></span>

- <span data-ttu-id="3a754-196">**向包含可访问的（公共或受保护的）构造函数且非[密封](../../csharp/language-reference/keywords/sealed.md)类型的公共类型添加抽象成员**</span><span class="sxs-lookup"><span data-stu-id="3a754-196">**❌ Adding an abstract member to a public type that has accessible (public or protected) constructors and that is not [sealed](../../csharp/language-reference/keywords/sealed.md)**</span></span>

- <span data-ttu-id="3a754-197">**从成员添加或删除 [static](../../csharp/language-reference/keywords/static.md) 关键字**</span><span class="sxs-lookup"><span data-stu-id="3a754-197">**❌ Adding or removing the [static](../../csharp/language-reference/keywords/static.md) keyword from a member**</span></span>

- <span data-ttu-id="3a754-198">**添加排除现有重载并定义其他行为的重载**</span><span class="sxs-lookup"><span data-stu-id="3a754-198">**❌ Adding an overload that precludes an existing overload and defines a different behavior**</span></span>

  <span data-ttu-id="3a754-199">这将中断已绑定先前重载的现有客户端。</span><span class="sxs-lookup"><span data-stu-id="3a754-199">This breaks existing clients that were bound to the previous overload.</span></span> <span data-ttu-id="3a754-200">例如，若类包含单个接受 <xref:System.UInt32> 的方法的版本，传递 <xref:System.Int32> 值时，现有使用者将成功地绑定该重载。</span><span class="sxs-lookup"><span data-stu-id="3a754-200">For example, if a class has a single version of a method that accepts a <xref:System.UInt32>, an existing consumer will successfully bind to that overload when passing a <xref:System.Int32> value.</span></span> <span data-ttu-id="3a754-201">但是，如果添加接受 <xref:System.Int32> 的重载，重新编译或使用晚期绑定时，编译器现在将绑定新的重载。</span><span class="sxs-lookup"><span data-stu-id="3a754-201">However, if you add an overload that accepts an <xref:System.Int32>, when recompiling or using late-binding, the compiler now binds to the new overload.</span></span> <span data-ttu-id="3a754-202">若生成不同的行为，则它属于中断性变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-202">If different behavior results, this is a breaking change.</span></span>

- <span data-ttu-id="3a754-203">**在未对过去不包含任何构造函数的类添加默认构造函数的情况下向其添加构造函数**</span><span class="sxs-lookup"><span data-stu-id="3a754-203">**❌ Adding a constructor to a class that previously had no constructor without adding the default constructor**</span></span>

- <span data-ttu-id="3a754-204">**️ 向字段添加 [readonly](../../csharp/language-reference/keywords/readonly.md)**</span><span class="sxs-lookup"><span data-stu-id="3a754-204">**❌️ Adding [readonly](../../csharp/language-reference/keywords/readonly.md) to a field**</span></span>

- <span data-ttu-id="3a754-205">**降低成员的可见性**</span><span class="sxs-lookup"><span data-stu-id="3a754-205">**❌ Reducing the visibility of a member**</span></span>

   <span data-ttu-id="3a754-206">这包括在存在可访问的（公共或受保护的）构造函数且类型非 [sealed](../../csharp/language-reference/keywords/sealed.md) 的情况下降低 [protected](../../csharp/language-reference/keywords/protected.md) 成员的可见性。  </span><span class="sxs-lookup"><span data-stu-id="3a754-206">This includes reducing the visibility of a [protected](../../csharp/language-reference/keywords/protected.md) member when there are *accessible* (public or protected) constructors and the type is *not* [sealed](../../csharp/language-reference/keywords/sealed.md).</span></span> <span data-ttu-id="3a754-207">若不属于上述情况，则允许降低受保护的成员的可见性。</span><span class="sxs-lookup"><span data-stu-id="3a754-207">If this is not the case, reducing the visibility of a protected member is allowed.</span></span>

   <span data-ttu-id="3a754-208">请注意，允许增大成员的可见性。</span><span class="sxs-lookup"><span data-stu-id="3a754-208">Note that increasing the visibility of a member is allowed.</span></span>

- <span data-ttu-id="3a754-209">**更改成员的类型**</span><span class="sxs-lookup"><span data-stu-id="3a754-209">**❌ Changing the type of a member**</span></span>

   <span data-ttu-id="3a754-210">不可修改方法的返回值、属性类型或字段。</span><span class="sxs-lookup"><span data-stu-id="3a754-210">The return value of a method or the type of a property or field cannot be modified.</span></span> <span data-ttu-id="3a754-211">例如，不可将返回 <xref:System.Object> 的方法的签名更改为返回 <xref:System.String>，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="3a754-211">For example, the signature of a method that returns an <xref:System.Object> cannot be changed to return a <xref:System.String>, or vice versa.</span></span>

- <span data-ttu-id="3a754-212">**向先前没有任何状态的结构添加字段**</span><span class="sxs-lookup"><span data-stu-id="3a754-212">**❌ Adding a field to a struct that previously had no state**</span></span>

  <span data-ttu-id="3a754-213">有明确的分配规则规定，只要变量类型为无状态结构，即允许使用未初始化的变量。</span><span class="sxs-lookup"><span data-stu-id="3a754-213">Definite assignment rules allow the use of uninitialized variables so long as the variable type is a stateless struct.</span></span> <span data-ttu-id="3a754-214">若结构成为有状态结构，代码可能最终成为未初始化的数据。</span><span class="sxs-lookup"><span data-stu-id="3a754-214">If the struct is made stateful, code could end up with uninitialized data.</span></span> <span data-ttu-id="3a754-215">这可能既是源中断性变更，又是二进制中断性变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-215">This is both potentially a source breaking and a binary breaking change.</span></span>

- <span data-ttu-id="3a754-216">**触发先前从未触发过的现有事件**</span><span class="sxs-lookup"><span data-stu-id="3a754-216">**❌ Firing an existing event when it was never fired before**</span></span>

## <a name="behavioral-changes"></a><span data-ttu-id="3a754-217">行为变更</span><span class="sxs-lookup"><span data-stu-id="3a754-217">Behavioral changes</span></span>

### <a name="assemblies"></a><span data-ttu-id="3a754-218">程序集</span><span class="sxs-lookup"><span data-stu-id="3a754-218">Assemblies</span></span>

- <span data-ttu-id="3a754-219">**✔️ 使程序集成为可移植的程序集并且仍支持同样的平台**</span><span class="sxs-lookup"><span data-stu-id="3a754-219">**✔️ Making an assembly portable when the same platforms are still supported**</span></span>

- <span data-ttu-id="3a754-220">**更改程序集的名称**</span><span class="sxs-lookup"><span data-stu-id="3a754-220">**❌ Changing the name of an assembly**</span></span>
- <span data-ttu-id="3a754-221">**更改程序集的公钥**</span><span class="sxs-lookup"><span data-stu-id="3a754-221">**❌ Changing the public key of an assembly**</span></span>

### <a name="properties-fields-parameters-and-return-values"></a><span data-ttu-id="3a754-222">属性、字段、参数和返回值</span><span class="sxs-lookup"><span data-stu-id="3a754-222">Properties, fields, parameters, and return values</span></span>

- <span data-ttu-id="3a754-223">**✔️ 将属性、字段、返回值或 [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数的值更改为派生程度更大的类型**</span><span class="sxs-lookup"><span data-stu-id="3a754-223">**✔️ Changing the value of a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter to a more derived type**</span></span>

  <span data-ttu-id="3a754-224">例如，返回 <xref:System.Object> 的类型的方法可能返回 <xref:System.String> 实例。</span><span class="sxs-lookup"><span data-stu-id="3a754-224">For example, a method that returns a type of <xref:System.Object> can return a <xref:System.String> instance.</span></span> <span data-ttu-id="3a754-225">（但是不可更改方法签名。）</span><span class="sxs-lookup"><span data-stu-id="3a754-225">(However, the method signature cannot change.)</span></span>

- <span data-ttu-id="3a754-226">**✔️ 在成员为非 [virtual](../../csharp/language-reference/keywords/virtual.md) 成员时，扩大属性或参数的可接受值的范围**</span><span class="sxs-lookup"><span data-stu-id="3a754-226">**✔️ Increasing the range of accepted values for a property or parameter if the member is not [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

  <span data-ttu-id="3a754-227">请注意，可以扩展可传递到方法或由成员返回的值范围，但不可扩展参数或成员类型。</span><span class="sxs-lookup"><span data-stu-id="3a754-227">Note that while the range of values that can be passed to the method or are returned by the member can expand, the parameter or member type cannot.</span></span> <span data-ttu-id="3a754-228">例如，传递到方法的值可以从 0-124 扩展到 0-255，但参数类型不可从 <xref:System.Byte> 更改为 <xref:System.Int32>。</span><span class="sxs-lookup"><span data-stu-id="3a754-228">For example, while the values passed to a method can expand from 0-124 to 0-255, the parameter type cannot change from <xref:System.Byte> to <xref:System.Int32>.</span></span>

- <span data-ttu-id="3a754-229">**在成员为 [virtual](../../csharp/language-reference/keywords/virtual.md) 成员时，扩大属性或参数的可接受值的范围**</span><span class="sxs-lookup"><span data-stu-id="3a754-229">**❌ Increasing the range of accepted values for a property or parameter if the member is [virtual](../../csharp/language-reference/keywords/virtual.md)**</span></span>

   <span data-ttu-id="3a754-230">此变更将中断已重写的现有成员，面向扩展的值范围时它们将无法正常运行。</span><span class="sxs-lookup"><span data-stu-id="3a754-230">This change breaks existing overridden members, which will not function correctly for the extended range of values.</span></span>

- <span data-ttu-id="3a754-231">**缩小属性或参数的可接受值的范围**</span><span class="sxs-lookup"><span data-stu-id="3a754-231">**❌ Decreasing the range of accepted values for a property or parameter**</span></span>

- <span data-ttu-id="3a754-232">**扩大属性的返回值范围、字段、返回值或 [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数**</span><span class="sxs-lookup"><span data-stu-id="3a754-232">**❌ Increasing the range of returned values for a property, field, return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="3a754-233">**更改属性的返回值、字段、方法返回值或 [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) 参数**</span><span class="sxs-lookup"><span data-stu-id="3a754-233">**❌ Changing the returned values for a property, field, method return value, or [out](../../csharp/language-reference/keywords/out-parameter-modifier.md) parameter**</span></span>

- <span data-ttu-id="3a754-234">**更改属性、字段或参数的默认值**</span><span class="sxs-lookup"><span data-stu-id="3a754-234">**❌ Changing the default value of a property, field, or parameter**</span></span>

- <span data-ttu-id="3a754-235">**更改数值返回值的精度**</span><span class="sxs-lookup"><span data-stu-id="3a754-235">**❌ Changing the precision of a numeric return value**</span></span>

- <span data-ttu-id="3a754-236">**关于输入分析和新异常引发的变更（尽管本文档未指定分析行为）**</span><span class="sxs-lookup"><span data-stu-id="3a754-236">**❓ A change in the parsing of input and throwing new exceptions (even if parsing behavior is not specified in the documentation**</span></span>

### <a name="exceptions"></a><span data-ttu-id="3a754-237">异常</span><span class="sxs-lookup"><span data-stu-id="3a754-237">Exceptions</span></span>

- <span data-ttu-id="3a754-238">**✔️ 引发派生程度高于现有异常的异常**</span><span class="sxs-lookup"><span data-stu-id="3a754-238">**✔️ Throwing a more derived exception than an existing exception**</span></span>

  <span data-ttu-id="3a754-239">由于新异常是现有异常的子类，先前的异常处理代码将继续处理异常。</span><span class="sxs-lookup"><span data-stu-id="3a754-239">Because the new exception is a subclass of an existing exception, previous exception handling code continues to handle the exception.</span></span> <span data-ttu-id="3a754-240">例如，在 .NET Framework 4 中，找不到区域性时，区域性生成和检索方法开始引发 <xref:System.Globalization.CultureNotFoundException> 而不引发 <xref:System.ArgumentException>。</span><span class="sxs-lookup"><span data-stu-id="3a754-240">For example, in .NET Framework 4, culture creation and retrieval methods began to throw a <xref:System.Globalization.CultureNotFoundException> instead of an <xref:System.ArgumentException> if the culture could not be found.</span></span> <span data-ttu-id="3a754-241">由于 <xref:System.Globalization.CultureNotFoundException> 派生自 <xref:System.ArgumentException>，因此这是可接受的变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-241">Because <xref:System.Globalization.CultureNotFoundException> derives from <xref:System.ArgumentException>, this is an acceptable change.</span></span>

- <span data-ttu-id="3a754-242">**✔️ 引发比 <xref:System.NotSupportedException>、<xref:System.NotImplementedException>、<xref:System.NullReferenceException> 更加具体的异常**</span><span class="sxs-lookup"><span data-stu-id="3a754-242">**✔️ Throwing a more specific exception than <xref:System.NotSupportedException>, <xref:System.NotImplementedException>, <xref:System.NullReferenceException>**</span></span>

- <span data-ttu-id="3a754-243">**✔️ 引发被视为无法恢复的异常**</span><span class="sxs-lookup"><span data-stu-id="3a754-243">**✔️ Throwing an exception that is considered unrecoverable**</span></span>

  <span data-ttu-id="3a754-244">不应捕获无法恢复的异常，而应该由高级别的全部捕获处理程序处理它们。</span><span class="sxs-lookup"><span data-stu-id="3a754-244">Unrecoverable exceptions should not be caught but instead should be handled by a high-level catch-all handler.</span></span> <span data-ttu-id="3a754-245">因此，用户不应该拥有捕获这些显式异常的代码。</span><span class="sxs-lookup"><span data-stu-id="3a754-245">Therefore, users are not expected to have code that catches these explicit exceptions.</span></span> <span data-ttu-id="3a754-246">无法恢复的异常包括：</span><span class="sxs-lookup"><span data-stu-id="3a754-246">The unrecoverable exceptions are:</span></span>

  - <xref:System.AccessViolationException>
  - <xref:System.ExecutionEngineException>
  - <xref:System.Runtime.InteropServices.SEHException>
  - <xref:System.StackOverflowException>

- <span data-ttu-id="3a754-247">**✔️ 在新的代码路径中引发新的异常**</span><span class="sxs-lookup"><span data-stu-id="3a754-247">**✔️ Throwing a new exception in a new code path**</span></span>

  <span data-ttu-id="3a754-248">异常必须仅适用于使用新参数值或状态执行并且无法由面向先前版本的现有代码执行的新代码路径。</span><span class="sxs-lookup"><span data-stu-id="3a754-248">The exception must apply only to a new code-path which is executed with new parameter values or state, and that can't be executed by existing code that targets the previous version.</span></span>

- <span data-ttu-id="3a754-249">**✔️ 删除异常，以启用更可靠的行为或新方案**</span><span class="sxs-lookup"><span data-stu-id="3a754-249">**✔️ Removing an exception to enable more robust behavior or new scenarios**</span></span>

  <span data-ttu-id="3a754-250">例如，可以以其他方式将先前仅处理正值并引发 <xref:System.ArgumentOutOfRangeException> 的 `Divide` 方法更改为同时支持正值和负值并且不引发异常。</span><span class="sxs-lookup"><span data-stu-id="3a754-250">For example, a `Divide` method that previously only handled positive values and threw an <xref:System.ArgumentOutOfRangeException> otherwise can be changed to support both negative and positive values without throwing an exception.</span></span>

- <span data-ttu-id="3a754-251">**✔️ 更改错误消息的文本**</span><span class="sxs-lookup"><span data-stu-id="3a754-251">**✔️ Changing the text of an error message**</span></span>

  <span data-ttu-id="3a754-252">开发人员不应依赖也会基于用户区域性更改的错误消息文本。</span><span class="sxs-lookup"><span data-stu-id="3a754-252">Developers should not rely on the text of error messages, which also change based on the user's culture.</span></span>

- <span data-ttu-id="3a754-253">**在上文未列出的任何其他的情况下引发异常**</span><span class="sxs-lookup"><span data-stu-id="3a754-253">**❌ Throwing an exception in any other case not listed above**</span></span>

- <span data-ttu-id="3a754-254">**在上文未列出的任何其他的情况下删除异常**</span><span class="sxs-lookup"><span data-stu-id="3a754-254">**❌ Removing an exception in any other case not listed above**</span></span>

### <a name="attributes"></a><span data-ttu-id="3a754-255">特性</span><span class="sxs-lookup"><span data-stu-id="3a754-255">Attributes</span></span>

- <span data-ttu-id="3a754-256">\*\*✔️ 更改不可观测的属性的值  \*\*</span><span class="sxs-lookup"><span data-stu-id="3a754-256">**✔️ Changing the value of an attribute that is *not* observable**</span></span>

- <span data-ttu-id="3a754-257">\*\*更改可观测的属性的值  \*\*</span><span class="sxs-lookup"><span data-stu-id="3a754-257">**❌ Changing the value of an attribute that *is* observable**</span></span>

- <span data-ttu-id="3a754-258">**删除属性**</span><span class="sxs-lookup"><span data-stu-id="3a754-258">**❓ Removing an attribute**</span></span>

  <span data-ttu-id="3a754-259">多数情况下，删除属性（如 <xref:System.NonSerializedAttribute>）为中断性变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-259">In most cases, removing an attribute (such as <xref:System.NonSerializedAttribute>) is a breaking change.</span></span>

## <a name="platform-support"></a><span data-ttu-id="3a754-260">平台支持</span><span class="sxs-lookup"><span data-stu-id="3a754-260">Platform support</span></span>

- <span data-ttu-id="3a754-261">**✔️ 在平台上支持先前不支持的操作**</span><span class="sxs-lookup"><span data-stu-id="3a754-261">**✔️ Supporting an operation on a platform that was previously not supported**</span></span>

- <span data-ttu-id="3a754-262">**对于平台先前支持的操作，不再支持或者现在需要特定服务包**</span><span class="sxs-lookup"><span data-stu-id="3a754-262">**❌ Not supporting or now requiring a specific service pack for an operation that was previously supported on a platform**</span></span>

## <a name="internal-implementation-changes"></a><span data-ttu-id="3a754-263">内部实现变更</span><span class="sxs-lookup"><span data-stu-id="3a754-263">Internal implementation changes</span></span>

- <span data-ttu-id="3a754-264">**更改内部类型的外围应用**</span><span class="sxs-lookup"><span data-stu-id="3a754-264">**❓ Changing the surface area of an internal type**</span></span>

   <span data-ttu-id="3a754-265">尽管此类更改将中断私有反射，但通常允许这些变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-265">Such changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="3a754-266">如果常用的第三方库或大量开发人员依赖内部 API，在这些情况下，可能不允许此类变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-266">In some cases, where popular third-party libraries or a large number of developers depend on the internal APIs, such changes may not be allowed.</span></span>

- <span data-ttu-id="3a754-267">**更改成员的内部实现**</span><span class="sxs-lookup"><span data-stu-id="3a754-267">**❓ Changing the internal implementation of a member**</span></span>

  <span data-ttu-id="3a754-268">尽管此类更改将中断私有反射，但通常允许这些变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-268">These changes are generally allowed, although they break private reflection.</span></span> <span data-ttu-id="3a754-269">如果客户代码频繁依赖私有反射，或者变更引入意外的负面影响，在这些情况下，可能不允许这些变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-269">In some cases, where customer code frequently depends on private reflection or where the change introduces unintended side effects, these changes may not be allowed.</span></span>

- <span data-ttu-id="3a754-270">**✔️ 提高操作的性能**</span><span class="sxs-lookup"><span data-stu-id="3a754-270">**✔️ Improving the performance of an operation**</span></span>

   <span data-ttu-id="3a754-271">修改操作性能的功能必不可少，但此类变更可能会中断依赖操作的当前速度的代码。</span><span class="sxs-lookup"><span data-stu-id="3a754-271">The ability to modify the performance of an operation is essential, but such changes can break code that relies upon the current speed of an operation.</span></span> <span data-ttu-id="3a754-272">这一点尤其适用于对于依赖异步操作计时的代码。</span><span class="sxs-lookup"><span data-stu-id="3a754-272">This is particularly true of code that depends on the timing of asynchronous operations.</span></span> <span data-ttu-id="3a754-273">请注意，性能更改应不影响所说的 API 的其他行为；否则，变更将属于中断性变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-273">Note that the performance change should have no effect on other behavior of the API in question; otherwise, the change will be breaking.</span></span>

- <span data-ttu-id="3a754-274">**✔️ 间接更改操作性能（通常产生的是负面影响）**</span><span class="sxs-lookup"><span data-stu-id="3a754-274">**✔️ Indirectly (and often adversely) changing the performance of an operation**</span></span>

  <span data-ttu-id="3a754-275">若出于某些其他的原因未将所说的变更归类为中断性变更，这是可以接受的。</span><span class="sxs-lookup"><span data-stu-id="3a754-275">If the change in question is not categorized as breaking for some other reason, this is acceptable.</span></span> <span data-ttu-id="3a754-276">通常需要执行可能包含额外操作或添加新功能的操作。</span><span class="sxs-lookup"><span data-stu-id="3a754-276">Often, actions need to be taken that may include extra operations or that add new functionality.</span></span> <span data-ttu-id="3a754-277">这几乎都会影响性能，但对于使所说的 API 按预期方式运行而言它可能必不可少。</span><span class="sxs-lookup"><span data-stu-id="3a754-277">This will almost always affect performance but may be essential to make the API in question function as expected.</span></span>

- <span data-ttu-id="3a754-278">**将同步 API 更改为异步（反之亦然）**</span><span class="sxs-lookup"><span data-stu-id="3a754-278">**❌ Changing a synchronous API to asynchronous (and vice versa)**</span></span>

## <a name="code-changes"></a><span data-ttu-id="3a754-279">代码更改</span><span class="sxs-lookup"><span data-stu-id="3a754-279">Code changes</span></span>

- <span data-ttu-id="3a754-280">**✔️ 向参数添加 [params](../../csharp/language-reference/keywords/params.md)**</span><span class="sxs-lookup"><span data-stu-id="3a754-280">**✔️ Adding [params](../../csharp/language-reference/keywords/params.md) to a parameter**</span></span>

- <span data-ttu-id="3a754-281">**将 [struct](../../csharp/language-reference/keywords/struct.md) 更改为 [class](../../csharp/language-reference/keywords/class.md)，反之亦然**</span><span class="sxs-lookup"><span data-stu-id="3a754-281">**❌ Changing a [struct](../../csharp/language-reference/keywords/struct.md) to a [class](../../csharp/language-reference/keywords/class.md) and vice versa**</span></span>

- <span data-ttu-id="3a754-282">**向代码块添加 [checked](../../csharp/language-reference/keywords/virtual.md) 关键字**</span><span class="sxs-lookup"><span data-stu-id="3a754-282">**❌ Adding the [checked](../../csharp/language-reference/keywords/virtual.md) keyword to a code block**</span></span>

   <span data-ttu-id="3a754-283">此变更可能导致先前执行的代码引发 <xref:System.OverflowException>，此为不可接受的变更。</span><span class="sxs-lookup"><span data-stu-id="3a754-283">This change may cause code that previously executed to throw an <xref:System.OverflowException> and is unacceptable.</span></span>

- <span data-ttu-id="3a754-284">**从参数删除 [params](../../csharp/language-reference/keywords/params.md)**</span><span class="sxs-lookup"><span data-stu-id="3a754-284">**❌ Removing [params](../../csharp/language-reference/keywords/params.md) from a parameter**</span></span>

- <span data-ttu-id="3a754-285">**更改事件的触发顺序**</span><span class="sxs-lookup"><span data-stu-id="3a754-285">**❌ Changing the order in which events are fired**</span></span>

  <span data-ttu-id="3a754-286">开发人员可以合理地期望事件按相同的顺序触发，开发人员代码频繁依赖事件的触发顺序。</span><span class="sxs-lookup"><span data-stu-id="3a754-286">Developers can reasonably expect events to fire in the same order, and developer code frequently depends on the order in which events are fired.</span></span>

- <span data-ttu-id="3a754-287">**删除给定操作上的事件引发**</span><span class="sxs-lookup"><span data-stu-id="3a754-287">**❌ Removing the raising of an event on a given action**</span></span>

- <span data-ttu-id="3a754-288">**更改给定事件的调用次数**</span><span class="sxs-lookup"><span data-stu-id="3a754-288">**❌ Changing the number of times given events are called**</span></span>

- <span data-ttu-id="3a754-289">**向枚举类型添加 <xref:System.FlagsAttribute>**</span><span class="sxs-lookup"><span data-stu-id="3a754-289">**❌ Adding the <xref:System.FlagsAttribute> to an enumeration type**</span></span>
