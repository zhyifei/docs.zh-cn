---
title: 安全透明的代码，级别 2
ms.date: 03/30/2017
helpviewer_keywords:
- transparency
- level 2 transparency
- security-transparent code
- security-critical code
ms.assetid: 4d05610a-0da6-4f08-acea-d54c9d6143c0
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9c3970823557d1d1b24405fd4b390b81006533a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "59977309"
---
# <a name="security-transparent-code-level-2"></a><span data-ttu-id="7e4a3-102">安全透明的代码，级别 2</span><span class="sxs-lookup"><span data-stu-id="7e4a3-102">Security-Transparent Code, Level 2</span></span>

<a name="top"></a>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="7e4a3-103">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中引入了 2 级透明度。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-103">Level 2 transparency was introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="7e4a3-104">此模型的三条原则是透明代码、安全可靠关键代码和安全关键代码。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-104">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="7e4a3-105">透明代码（包括以完全信任权限运行的代码）只能调用其他透明代码或安全可靠关键代码。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-105">Transparent code, including code that is running as full trust, can call other transparent code or security-safe-critical code only.</span></span> <span data-ttu-id="7e4a3-106">它只能执行域的部分信任权限集（如果存在）允许的操作。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-106">It can only perform actions allowed by the domain’s partial trust permission set (if one exists).</span></span> <span data-ttu-id="7e4a3-107">透明代码不能：</span><span class="sxs-lookup"><span data-stu-id="7e4a3-107">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="7e4a3-108">执行 <xref:System.Security.CodeAccessPermission.Assert%2A> 或特权提升。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-108">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> or elevation of privilege.</span></span>

  - <span data-ttu-id="7e4a3-109">包含不安全或不可验证的代码。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-109">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="7e4a3-110">直接调用关键代码。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-110">Directly call critical code.</span></span>

  - <span data-ttu-id="7e4a3-111">调用本机代码或具有 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 特性的代码。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-111">Call native code or code with the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="7e4a3-112">调用受 <xref:System.Security.Permissions.SecurityAction.LinkDemand> 保护的成员。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-112">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="7e4a3-113">从关键类型继承。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-113">Inherit from critical types.</span></span>

  <span data-ttu-id="7e4a3-114">此外，透明方法不能重写关键虚拟方法或实现关键接口方法。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-114">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="7e4a3-115">可靠关键代码是完全信任的代码，且可被透明代码调用的代码。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-115">Safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="7e4a3-116">它公开完全信任代码的有限外围应用；可靠关键代码中会进行准确性和安全性验证。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-116">It exposes a limited surface area of full-trust code; correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="7e4a3-117">安全关键代码可以调用完全信任的任何代码，但不能被透明代码调用。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-117">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

<span data-ttu-id="7e4a3-118">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="7e4a3-118">This topic contains the following sections:</span></span>

- [<span data-ttu-id="7e4a3-119">用法示例和行为</span><span class="sxs-lookup"><span data-stu-id="7e4a3-119">Usage Examples and Behaviors</span></span>](#examples)

- [<span data-ttu-id="7e4a3-120">重写模式</span><span class="sxs-lookup"><span data-stu-id="7e4a3-120">Override Patterns</span></span>](#override)

- [<span data-ttu-id="7e4a3-121">继承规则</span><span class="sxs-lookup"><span data-stu-id="7e4a3-121">Inheritance Rules</span></span>](#inheritance)

- [<span data-ttu-id="7e4a3-122">其他信息和规则</span><span class="sxs-lookup"><span data-stu-id="7e4a3-122">Additional Information and Rules</span></span>](#additional)

<a name="examples"></a>

## <a name="usage-examples-and-behaviors"></a><span data-ttu-id="7e4a3-123">用法示例和行为</span><span class="sxs-lookup"><span data-stu-id="7e4a3-123">Usage Examples and Behaviors</span></span>

<span data-ttu-id="7e4a3-124">若要指定 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 规则（ 2 级透明度），请对程序集使用以下批注：</span><span class="sxs-lookup"><span data-stu-id="7e4a3-124">To specify [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules (level 2 transparency), use the following annotation for an assembly:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level2)]
```

<span data-ttu-id="7e4a3-125">若要锁定至 .NET Framework 2.0 规则（1 级透明度），请使用以下批注：</span><span class="sxs-lookup"><span data-stu-id="7e4a3-125">To lock into the .NET Framework 2.0 rules (level 1 transparency), use the following annotation:</span></span>

```csharp
[assembly: SecurityRules(SecurityRuleSet.Level1)]
```

<span data-ttu-id="7e4a3-126">如果不对程序集进行批注，则默认使用 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 规则。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-126">If you do not annotate an assembly, the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] rules are used by default.</span></span> <span data-ttu-id="7e4a3-127">但是，建议的最佳做法是使用<xref:System.Security.SecurityRulesAttribute>特性而不是依赖默认值。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-127">However, the recommended best practice is to use the <xref:System.Security.SecurityRulesAttribute> attribute instead of depending on the default.</span></span>

### <a name="assembly-wide-annotation"></a><span data-ttu-id="7e4a3-128">程序集范围的批注</span><span class="sxs-lookup"><span data-stu-id="7e4a3-128">Assembly-wide Annotation</span></span>

<span data-ttu-id="7e4a3-129">以下规则适用于程序集级别的特性使用：</span><span class="sxs-lookup"><span data-stu-id="7e4a3-129">The following rules apply to the use of attributes at the assembly level:</span></span>

- <span data-ttu-id="7e4a3-130">没有属性：如果未指定任何属性，在运行时将所有代码解释为安全关键的除非安全关键违反继承规则 (例如，当重写或实现透明虚拟或接口方法)。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-130">No attributes: If you do not specify any attributes, the runtime interprets all code as security-critical, except where being security-critical violates an inheritance rule (for example, when overriding or implementing a transparent virtual or interface method).</span></span> <span data-ttu-id="7e4a3-131">在这些情况下，方法是可靠关键方法。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-131">In those cases, the methods are safe-critical.</span></span> <span data-ttu-id="7e4a3-132">指定无特性会导致公用语言运行时为你确定透明度规则。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-132">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span>

- <span data-ttu-id="7e4a3-133">`SecurityTransparent`：所有代码都是透明的;整个程序集不会执行任何特权或不安全。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-133">`SecurityTransparent`: All code is transparent; the entire assembly will not do anything privileged or unsafe.</span></span>

- <span data-ttu-id="7e4a3-134">`SecurityCritical`：由此类型引入此程序集的所有代码都是关键代码；其他所有代码都是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-134">`SecurityCritical`: All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="7e4a3-135">这种情况类似于不指定任何特性，但公共语言运行时不会自动确定透明度规则。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-135">This scenario is similar to not specifying any attributes; however, the common language runtime does not automatically determine the transparency rules.</span></span> <span data-ttu-id="7e4a3-136">例如，如果重写虚拟方法或抽象方法或者实现接口方法，默认情况下，该方法是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-136">For example, if you override a virtual or abstract method or implement an interface method, by default, that method is transparent.</span></span> <span data-ttu-id="7e4a3-137">你必须将方法显式批注为 `SecurityCritical` 或 `SecuritySafeCritical`；否则加载时将引发 <xref:System.TypeLoadException>。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-137">You must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`; otherwise, a <xref:System.TypeLoadException> will be thrown at load time.</span></span> <span data-ttu-id="7e4a3-138">当基类和派生类位于相同的程序集时，此规则也适用。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-138">This rule also applies when both the base class and the derived class are in the same assembly.</span></span>

- <span data-ttu-id="7e4a3-139">`AllowPartiallyTrustedCallers` （级别 2 仅）：所有代码默认都是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-139">`AllowPartiallyTrustedCallers` (level 2 only): All code defaults to transparent.</span></span> <span data-ttu-id="7e4a3-140">但是，各个类型和成员可以有其他特性。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-140">However, individual types and members can have other attributes.</span></span>

<span data-ttu-id="7e4a3-141">下表比较了 2 级与 1 级的程序集级别行为。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-141">The following table compares the assembly level behavior for Level 2 with Level 1.</span></span>

|<span data-ttu-id="7e4a3-142">Assembly 特性</span><span class="sxs-lookup"><span data-stu-id="7e4a3-142">Assembly attribute</span></span>|<span data-ttu-id="7e4a3-143">级别2</span><span class="sxs-lookup"><span data-stu-id="7e4a3-143">Level 2</span></span>|<span data-ttu-id="7e4a3-144">等级 1</span><span class="sxs-lookup"><span data-stu-id="7e4a3-144">Level 1</span></span>|
|------------------------|-------------|-------------|
|<span data-ttu-id="7e4a3-145">部分信任的程序集上无特性</span><span class="sxs-lookup"><span data-stu-id="7e4a3-145">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="7e4a3-146">类型和成员默认是透明的，但可以是安全关键或安全可靠关键的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-146">Types and members are by default transparent, but can be security-critical or security-safe-critical.</span></span>|<span data-ttu-id="7e4a3-147">所有类型和成员都是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-147">All types and members are transparent.</span></span>|
|<span data-ttu-id="7e4a3-148">无特性</span><span class="sxs-lookup"><span data-stu-id="7e4a3-148">No attribute</span></span>|<span data-ttu-id="7e4a3-149">指定无特性会导致公用语言运行时为你确定透明度规则。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-149">Specifying no attribute causes the common language runtime to determine the transparency rules for you.</span></span> <span data-ttu-id="7e4a3-150">所有类型和成员都是安全关键的，除非安全关键违反继承规则。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-150">All types and members are security-critical, except where being security-critical violates an inheritance rule.</span></span>|<span data-ttu-id="7e4a3-151">在完全信任的程序集上（在全局程序缓集缓存或 `AppDomain` 中标识为完全信任的程序集中），所有类型都是透明的，所有成员都是安全可靠关键的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-151">On a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`) all types are transparent and all members are security-safe-critical.</span></span>|
|`SecurityTransparent`|<span data-ttu-id="7e4a3-152">所有类型和成员都是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-152">All types and members are transparent.</span></span>|<span data-ttu-id="7e4a3-153">所有类型和成员都是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-153">All types and members are transparent.</span></span>|
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="7e4a3-154">不适用。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-154">Not applicable.</span></span>|<span data-ttu-id="7e4a3-155">所有类型和成员都是安全关键的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-155">All types and members are security-critical.</span></span>|
|`SecurityCritical`|<span data-ttu-id="7e4a3-156">由此类型引入此程序集的所有代码都是关键代码；其他所有代码都是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-156">All code that is introduced by types in this assembly is critical; all other code is transparent.</span></span> <span data-ttu-id="7e4a3-157">如果重写虚拟方法或抽象方法或者实现接口方法，则必须将方法显式批注为 `SecurityCritical` 或 `SecuritySafeCritical`。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-157">If you override a virtual or abstract method or implement an interface method, you must explicitly annotate the method as `SecurityCritical` or `SecuritySafeCritical`.</span></span>|<span data-ttu-id="7e4a3-158">所有代码默认都是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-158">All code defaults to transparent.</span></span> <span data-ttu-id="7e4a3-159">但是，各个类型和成员可以有其他特性。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-159">However, individual types and members can have other attributes.</span></span>|

### <a name="type-and-member-annotation"></a><span data-ttu-id="7e4a3-160">类型和成员批注</span><span class="sxs-lookup"><span data-stu-id="7e4a3-160">Type and Member Annotation</span></span>

<span data-ttu-id="7e4a3-161">适用于安全类型的安全特性也适用于该类型引入的成员。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-161">The security attributes that are applied to a type also apply to the members that are introduced by the type.</span></span> <span data-ttu-id="7e4a3-162">但是，这些规则不适用于基类或接口实现的虚拟或抽象重写。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-162">However, they do not apply to virtual or abstract overrides of the base class or interface implementations.</span></span> <span data-ttu-id="7e4a3-163">以下规则适用于类型和成员级别的特性使用：</span><span class="sxs-lookup"><span data-stu-id="7e4a3-163">The following rules apply to the use of attributes at the type and member level:</span></span>

- <span data-ttu-id="7e4a3-164">`SecurityCritical`：类型或成员至关重要，可以通过完全信任代码调用。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-164">`SecurityCritical`: The type or member is critical and can be called only by full-trust code.</span></span> <span data-ttu-id="7e4a3-165">安全关键类型中引入的方法是关键的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-165">Methods that are introduced in a security-critical type are critical.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7e4a3-166">基类或接口中引入的以及安全关键类中重写或实现的虚拟和抽象方法默认是透明的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-166">Virtual and abstract methods that are introduced in base classes or interfaces, and overridden or implemented in a security-critical class are transparent by default.</span></span> <span data-ttu-id="7e4a3-167">这些方法必须标识为 `SecuritySafeCritical` 或 `SecurityCritical`。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-167">They must be identified as either `SecuritySafeCritical` or `SecurityCritical`.</span></span>

- <span data-ttu-id="7e4a3-168">`SecuritySafeCritical`：类型或成员是可靠关键的。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-168">`SecuritySafeCritical`: The type or member is safe-critical.</span></span> <span data-ttu-id="7e4a3-169">但是，类型或成员可以从透明（部分信任的）代码调用，并且与任何其他关键代码一样。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-169">However, the type or member can be called from transparent (partially trusted) code and is as capable as any other critical code.</span></span> <span data-ttu-id="7e4a3-170">必须审核代码的安全性。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-170">The code must be audited for security.</span></span>

[<span data-ttu-id="7e4a3-171">返回页首</span><span class="sxs-lookup"><span data-stu-id="7e4a3-171">Back to top</span></span>](#top)

<a name="override"></a>

## <a name="override-patterns"></a><span data-ttu-id="7e4a3-172">重写模式</span><span class="sxs-lookup"><span data-stu-id="7e4a3-172">Override Patterns</span></span>

<span data-ttu-id="7e4a3-173">下表显示 2 级透明度允许的方法重写。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-173">The following table shows the method overrides allowed for level 2 transparency.</span></span>

|<span data-ttu-id="7e4a3-174">基虚拟/接口成员</span><span class="sxs-lookup"><span data-stu-id="7e4a3-174">Base virtual/interface member</span></span>|<span data-ttu-id="7e4a3-175">重写/接口</span><span class="sxs-lookup"><span data-stu-id="7e4a3-175">Override/interface</span></span>|
|------------------------------------|-------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

[<span data-ttu-id="7e4a3-176">返回页首</span><span class="sxs-lookup"><span data-stu-id="7e4a3-176">Back to top</span></span>](#top)

<a name="inheritance"></a>

## <a name="inheritance-rules"></a><span data-ttu-id="7e4a3-177">继承规则</span><span class="sxs-lookup"><span data-stu-id="7e4a3-177">Inheritance Rules</span></span>

<span data-ttu-id="7e4a3-178">在此部分中，基于访问权限和功能对 `Transparent`、`Critical` 和 `SafeCritical` 代码指定以下顺序：</span><span class="sxs-lookup"><span data-stu-id="7e4a3-178">In this section, the following order is assigned to `Transparent`, `Critical`, and `SafeCritical` code based on access and capabilities:</span></span>

`Transparent` < `SafeCritical` < `Critical`

- <span data-ttu-id="7e4a3-179">类型的规则：我们从左到右，访问变得更具限制性。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-179">Rules for types: Going from left to right, access becomes more restrictive.</span></span> <span data-ttu-id="7e4a3-180">派生类型至少必须与基类型具有相同的受限访问权限。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-180">Derived types must be at least as restrictive as the base type.</span></span>

- <span data-ttu-id="7e4a3-181">方法的规则：派生的方法不能从基方法更改可访问性。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-181">Rules for methods: Derived methods cannot change accessibility from the base method.</span></span> <span data-ttu-id="7e4a3-182">对于默认行为，不带批注的所有派生方法都是 `Transparent`。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-182">For default behavior, all derived methods that are not annotated are `Transparent`.</span></span> <span data-ttu-id="7e4a3-183">如果重写方法未显示批注为 `SecurityCritical`，则派生关键类型会导致引发异常。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-183">Derivatives of critical types cause an exception to be thrown if the overridden method is not explicitly annotated as `SecurityCritical`.</span></span>

<span data-ttu-id="7e4a3-184">下表显示允许的类型继承模式。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-184">The following table shows the allowed type inheritance patterns.</span></span>

|<span data-ttu-id="7e4a3-185">基类</span><span class="sxs-lookup"><span data-stu-id="7e4a3-185">Base class</span></span>|<span data-ttu-id="7e4a3-186">派生类可以是</span><span class="sxs-lookup"><span data-stu-id="7e4a3-186">Derived class can be</span></span>|
|----------------|--------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`Transparent`|`Critical`|
|`SafeCritical`|`SafeCritical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Critical`|

<span data-ttu-id="7e4a3-187">下表显示不允许的类型继承模式。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-187">The following table shows the disallowed type inheritance patterns.</span></span>

|<span data-ttu-id="7e4a3-188">基类</span><span class="sxs-lookup"><span data-stu-id="7e4a3-188">Base class</span></span>|<span data-ttu-id="7e4a3-189">派生类不可以是</span><span class="sxs-lookup"><span data-stu-id="7e4a3-189">Derived class cannot be</span></span>|
|----------------|-----------------------------|
|`SafeCritical`|`Transparent`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

<span data-ttu-id="7e4a3-190">下表显示允许的方法继承模式。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-190">The following table shows the allowed method inheritance patterns.</span></span>

|<span data-ttu-id="7e4a3-191">基方法</span><span class="sxs-lookup"><span data-stu-id="7e4a3-191">Base method</span></span>|<span data-ttu-id="7e4a3-192">派生方法可以是</span><span class="sxs-lookup"><span data-stu-id="7e4a3-192">Derived method can be</span></span>|
|-----------------|---------------------------|
|`Transparent`|`Transparent`|
|`Transparent`|`SafeCritical`|
|`SafeCritical`|`Transparent`|
|`SafeCritical`|`SafeCritical`|
|`Critical`|`Critical`|

<span data-ttu-id="7e4a3-193">下表显示不允许的方法继承模式。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-193">The following table shows the disallowed method inheritance patterns.</span></span>

|<span data-ttu-id="7e4a3-194">基方法</span><span class="sxs-lookup"><span data-stu-id="7e4a3-194">Base method</span></span>|<span data-ttu-id="7e4a3-195">派生方法不可以是</span><span class="sxs-lookup"><span data-stu-id="7e4a3-195">Derived method cannot be</span></span>|
|-----------------|------------------------------|
|`Transparent`|`Critical`|
|`SafeCritical`|`Critical`|
|`Critical`|`Transparent`|
|`Critical`|`SafeCritical`|

> [!NOTE]
> <span data-ttu-id="7e4a3-196">这些继承规则适用于 2 级类型和成员。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-196">These inheritance rules apply to level 2 types and members.</span></span> <span data-ttu-id="7e4a3-197">1 级程序集中的类型可以从 2 级安全关键类型和成员继承。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-197">Types in level 1 assemblies can inherit from level 2 security-critical types and members.</span></span> <span data-ttu-id="7e4a3-198">因此，2 级类型和成员必须与 1 级继承者具有不同的继承需求。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-198">Therefore, level 2 types and members must have separate inheritance demands for level 1 inheritors.</span></span>

[<span data-ttu-id="7e4a3-199">返回页首</span><span class="sxs-lookup"><span data-stu-id="7e4a3-199">Back to top</span></span>](#top)

<a name="additional"></a>

## <a name="additional-information-and-rules"></a><span data-ttu-id="7e4a3-200">其他信息和规则</span><span class="sxs-lookup"><span data-stu-id="7e4a3-200">Additional Information and Rules</span></span>

### <a name="linkdemand-support"></a><span data-ttu-id="7e4a3-201">LinkDemand 支持</span><span class="sxs-lookup"><span data-stu-id="7e4a3-201">LinkDemand Support</span></span>

<span data-ttu-id="7e4a3-202">2 级透明度模型将 <xref:System.Security.Permissions.SecurityAction.LinkDemand> 替换为 <xref:System.Security.SecurityCriticalAttribute> 特性。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-202">The level 2 transparency model replaces the <xref:System.Security.Permissions.SecurityAction.LinkDemand> with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="7e4a3-203">在遗留（1 级）代码中，<xref:System.Security.Permissions.SecurityAction.LinkDemand> 自动被视为 <xref:System.Security.Permissions.SecurityAction.Demand>。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-203">In legacy (level 1) code, a <xref:System.Security.Permissions.SecurityAction.LinkDemand> is automatically treated as a <xref:System.Security.Permissions.SecurityAction.Demand>.</span></span>

### <a name="reflection"></a><span data-ttu-id="7e4a3-204">映像</span><span class="sxs-lookup"><span data-stu-id="7e4a3-204">Reflection</span></span>

<span data-ttu-id="7e4a3-205">调用关键方法或读取关键字段会触发对完全信任权限的要求（就像调用私有方法或字段一样）。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-205">Invoking a critical method or reading a critical field triggers a demand for full trust (just as if you were invoking a private method or field).</span></span> <span data-ttu-id="7e4a3-206">因此，完全信任的代码可以调用关键方法，而部分信任的代码则不能。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-206">Therefore, full-trust code can invoke a critical method, whereas partial-trust code cannot.</span></span>

<span data-ttu-id="7e4a3-207">以下属性已添加到 <xref:System.Reflection> 命名空间，以确定类型、方法或字段是否为 `SecurityCritical``SecuritySafeCritical` 或 `SecurityTransparent`：<xref:System.Type.IsSecurityCritical%2A>、<xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A> 和 <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-207">The following properties have been added to the <xref:System.Reflection> namespace to determine whether the type, method, or field is `SecurityCritical`, `SecuritySafeCritical`, or `SecurityTransparent`:  <xref:System.Type.IsSecurityCritical%2A>, <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, and <xref:System.Reflection.MethodBase.IsSecurityTransparent%2A>.</span></span> <span data-ttu-id="7e4a3-208">使用这些属性可通过反射而非检查特性是否存在确定透明度。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-208">Use these properties to determine transparency by using reflection instead of checking for the presence of the attribute.</span></span> <span data-ttu-id="7e4a3-209">透明度规则比较复杂，检查特性可能不够充分。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-209">The transparency rules are complex, and checking for the attribute may not be sufficient.</span></span>

> [!NOTE]
> <span data-ttu-id="7e4a3-210">一个`SafeCritical`方法将返回`true`同时<xref:System.Type.IsSecurityCritical%2A>并<xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>，这是因为`SafeCritical`事实上是关键的 （它具有相同的功能与关键代码，但它可以从透明代码调用）。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-210">A `SafeCritical` method returns `true` for both <xref:System.Type.IsSecurityCritical%2A> and <xref:System.Reflection.MethodBase.IsSecuritySafeCritical%2A>, because `SafeCritical` is indeed critical (it has the same capabilities as critical code, but it can be called from transparent code).</span></span>

<span data-ttu-id="7e4a3-211">动态方法继承其附加到的模块的透明度；他们不继承类型的透明度（如果它们附加到一个类型）。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-211">Dynamic methods inherit the transparency of the modules they are attached to; they do not inherit the transparency of the type (if they are attached to a type).</span></span>

### <a name="skip-verification-in-full-trust"></a><span data-ttu-id="7e4a3-212">在完全信任的环境中跳过验证</span><span class="sxs-lookup"><span data-stu-id="7e4a3-212">Skip Verification in Full Trust</span></span>

<span data-ttu-id="7e4a3-213">你可以通过在 <xref:System.Security.SecurityRulesAttribute> 特性中将 <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 属性设置为 `true`，跳过完全信任的透明程序集的验证。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-213">You can skip verification for fully trusted transparent assemblies by setting the <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property to `true` in the <xref:System.Security.SecurityRulesAttribute> attribute:</span></span>

`[assembly: SecurityRules(SecurityRuleSet.Level2, SkipVerificationInFullTrust = true)]`

<span data-ttu-id="7e4a3-214"><xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> 属性默认为 `false`，因此该属性必须设置为 `true` 才能跳过验证。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-214">The <xref:System.Security.SecurityRulesAttribute.SkipVerificationInFullTrust%2A> property is `false` by default, so the property must be set to `true` to skip verification.</span></span> <span data-ttu-id="7e4a3-215">只能出于优化目的跳过验证。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-215">This should be done for optimization purposes only.</span></span> <span data-ttu-id="7e4a3-216">应确保在程序集中的透明代码是通过使用验证`transparent`选项[PEVerify 工具](../../../docs/framework/tools/peverify-exe-peverify-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="7e4a3-216">You should ensure that the transparent code in the assembly is verifiable by using the `transparent` option in the [PEVerify tool](../../../docs/framework/tools/peverify-exe-peverify-tool.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7e4a3-217">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e4a3-217">See also</span></span>

- [<span data-ttu-id="7e4a3-218">安全透明代码，级别 1</span><span class="sxs-lookup"><span data-stu-id="7e4a3-218">Security-Transparent Code, Level 1</span></span>](../../../docs/framework/misc/security-transparent-code-level-1.md)
- [<span data-ttu-id="7e4a3-219">安全更改</span><span class="sxs-lookup"><span data-stu-id="7e4a3-219">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)
