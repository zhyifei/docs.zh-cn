---
title: 安全透明的代码
ms.date: 03/30/2017
helpviewer_keywords:
- transparent code
- security-transparent code
ms.assetid: 4f3dd841-82f7-4659-aab0-6d2db2166c65
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5cb528bbb4f85cd4502b4e2efabbcf592ac6bd0c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868740"
---
# <a name="security-transparent-code"></a><span data-ttu-id="8c27b-102">安全透明的代码</span><span class="sxs-lookup"><span data-stu-id="8c27b-102">Security-Transparent Code</span></span>

<a name="top"></a>

[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]

<span data-ttu-id="8c27b-103">安全性涉及三个交互部分：沙盒处理、权限和强制。</span><span class="sxs-lookup"><span data-stu-id="8c27b-103">Security involves three interacting pieces: sandboxing, permissions, and enforcement.</span></span> <span data-ttu-id="8c27b-104">沙盒处理是指创建隔离域的做法，在隔离域中某些代码被视为完全信任，而其他代码则被限制为沙盒授予集中的权限。</span><span class="sxs-lookup"><span data-stu-id="8c27b-104">Sandboxing refers to the practice of creating isolated domains where some code is treated as fully trusted and other code is restricted to the permissions in the grant set for the sandbox.</span></span> <span data-ttu-id="8c27b-105">在沙盒授予集内运行的应用程序代码被视为透明的，也就是说，它不能执行任何影响安全性的操作。</span><span class="sxs-lookup"><span data-stu-id="8c27b-105">The application code that runs within the grant set of the sandbox is considered to be transparent; that is, it cannot perform any operations that can affect security.</span></span> <span data-ttu-id="8c27b-106">沙盒的授予集由证据（<xref:System.Security.Policy.Evidence> 类）决定。</span><span class="sxs-lookup"><span data-stu-id="8c27b-106">The grant set for the sandbox is determined by evidence (<xref:System.Security.Policy.Evidence> class).</span></span> <span data-ttu-id="8c27b-107">证据标识沙盒需要哪些特定权限，以及可以创建哪种沙盒。</span><span class="sxs-lookup"><span data-stu-id="8c27b-107">Evidence identifies what specific permissions are required by sandboxes, and what kinds of sandboxes can be created.</span></span> <span data-ttu-id="8c27b-108">强制是指允许透明代码仅在其授予集内执行。</span><span class="sxs-lookup"><span data-stu-id="8c27b-108">Enforcement refers to allowing transparent code to execute only within its grant set.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c27b-109">安全策略是旧版 .NET Framework 中的关键元素。</span><span class="sxs-lookup"><span data-stu-id="8c27b-109">Security policy was a key element in previous versions of the .NET Framework.</span></span> <span data-ttu-id="8c27b-110">从开始[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]，安全策略已过时。</span><span class="sxs-lookup"><span data-stu-id="8c27b-110">Starting with the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)], security policy is obsolete.</span></span> <span data-ttu-id="8c27b-111">安全策略的取消独立于安全透明度。</span><span class="sxs-lookup"><span data-stu-id="8c27b-111">The elimination of security policy is separate from security transparency.</span></span> <span data-ttu-id="8c27b-112">有关此更改的影响的信息，请参阅[代码访问安全策略兼容性和迁移](../../../docs/framework/misc/code-access-security-policy-compatibility-and-migration.md)。</span><span class="sxs-lookup"><span data-stu-id="8c27b-112">For information about the effects of this change, see [Code Access Security Policy Compatibility and Migration](../../../docs/framework/misc/code-access-security-policy-compatibility-and-migration.md).</span></span>

<span data-ttu-id="8c27b-113">本主题更详细地介绍透明度模型。</span><span class="sxs-lookup"><span data-stu-id="8c27b-113">This topic describes the transparency model in more detail.</span></span> <span data-ttu-id="8c27b-114">它包含下列部分：</span><span class="sxs-lookup"><span data-stu-id="8c27b-114">It contains the following sections:</span></span>

- [<span data-ttu-id="8c27b-115">透明度模型的用途</span><span class="sxs-lookup"><span data-stu-id="8c27b-115">Purpose of the Transparency Model</span></span>](#purpose)

- [<span data-ttu-id="8c27b-116">指定透明度级别</span><span class="sxs-lookup"><span data-stu-id="8c27b-116">Specifying the Transparency Level</span></span>](#level)

- [<span data-ttu-id="8c27b-117">透明度强制</span><span class="sxs-lookup"><span data-stu-id="8c27b-117">Transparency Enforcement</span></span>](#enforcement)

<a name="purpose"></a>

## <a name="purpose-of-the-transparency-model"></a><span data-ttu-id="8c27b-118">透明度模型的用途</span><span class="sxs-lookup"><span data-stu-id="8c27b-118">Purpose of the Transparency Model</span></span>

<span data-ttu-id="8c27b-119">透明度是一种强制机制，用于将作为应用程序的一部分运行的代码与作为基础结构的一部分运行代码区分开来。</span><span class="sxs-lookup"><span data-stu-id="8c27b-119">Transparency is an enforcement mechanism that separates code that runs as part of the application from code that runs as part of the infrastructure.</span></span> <span data-ttu-id="8c27b-120">透明度在可以执行特许事件（例如调用本机代码）的代码（关键代码）和无法执行的代码（透明代码）之间绘制一个屏障。</span><span class="sxs-lookup"><span data-stu-id="8c27b-120">Transparency draws a barrier between code that can do privileged things (critical code), such as calling native code, and code that cannot (transparent code).</span></span> <span data-ttu-id="8c27b-121">透明代码可以在其运行的权限集边界内执行命令，但不能执行、派生自或包含关键代码。</span><span class="sxs-lookup"><span data-stu-id="8c27b-121">Transparent code can execute commands within the bounds of the permission set it is operating in, but cannot execute, derive from, or contain critical code.</span></span>

<span data-ttu-id="8c27b-122">透明度强制的主要目标是提供简单而有效的机制，以基于特权隔离不同的代码组。</span><span class="sxs-lookup"><span data-stu-id="8c27b-122">The primary goal of transparency enforcement is to provide a simple, effective mechanism for isolating different groups of code based on privilege.</span></span> <span data-ttu-id="8c27b-123">在沙盒处理模型的上下文中，这些特权组是完全信任的（即不受限制）或部分信任的（即限于授予沙盒的权限集）。</span><span class="sxs-lookup"><span data-stu-id="8c27b-123">Within the context of the sandboxing model, these privilege groups are either fully trusted (that is, not restricted) or partially trusted (that is, restricted to the permission set granted to the sandbox).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c27b-124">透明度模型优于代码访问安全性。</span><span class="sxs-lookup"><span data-stu-id="8c27b-124">The transparency model transcends code access security.</span></span> <span data-ttu-id="8c27b-125">透明度由实时编译器强制执行，并保持有效，而不考虑程序集的授予集（包括完全信任）。</span><span class="sxs-lookup"><span data-stu-id="8c27b-125">Transparency is enforced by the just-in-time compiler and remains in effect regardless of the grant set for an assembly, including full trust.</span></span>

<span data-ttu-id="8c27b-126">.NET Framework 2.0 版中引入了透明度，用于简化安全模型，使其更易于编写和部署安全库和应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c27b-126">Transparency was introduced in the .NET Framework version 2.0 to simplify the security model, and to make it easier to write and deploy secure libraries and applications.</span></span> <span data-ttu-id="8c27b-127">Microsoft Silverlight 中也使用了透明代码，用于简化部分信任的应用程序的开发。</span><span class="sxs-lookup"><span data-stu-id="8c27b-127">Transparent code is also used in Microsoft Silverlight, to simplify the development of partially trusted applications.</span></span>

> [!NOTE]
> <span data-ttu-id="8c27b-128">当开发部分信任的应用程序时，必须知道目标主机的权限要求。</span><span class="sxs-lookup"><span data-stu-id="8c27b-128">When you develop a partially trusted application, you have to be aware of the permission requirements for your target hosts.</span></span> <span data-ttu-id="8c27b-129">你可以开发使用某些主机不允许的资源的应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c27b-129">You can develop an application that uses resources that are not allowed by some hosts.</span></span> <span data-ttu-id="8c27b-130">此应用程序编译时不会出错，但将无法加载到托管环境中。</span><span class="sxs-lookup"><span data-stu-id="8c27b-130">This application will compile without error, but will fail when it is loaded into the hosted environment.</span></span> <span data-ttu-id="8c27b-131">如果已使用 Visual Studio 开发了应用程序，就可以在部分信任的环境中启用调试或在开发环境中启用受限的权限集。</span><span class="sxs-lookup"><span data-stu-id="8c27b-131">If you have developed your application using Visual Studio, you can enable debugging in partial trust or in a restricted permission set from the development environment.</span></span> <span data-ttu-id="8c27b-132">有关详细信息，请参阅[如何：使用受限权限调试 ClickOnce 应用程序](/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions)。</span><span class="sxs-lookup"><span data-stu-id="8c27b-132">For more information, see [How to: Debug a ClickOnce Application with Restricted Permissions](/visualstudio/deployment/how-to-debug-a-clickonce-application-with-restricted-permissions).</span></span> <span data-ttu-id="8c27b-133">为 ClickOnce 应用程序提供的计算权限功能也可用于部分信任的任何应用程序。</span><span class="sxs-lookup"><span data-stu-id="8c27b-133">The Calculate Permissions feature provided for ClickOnce applications is also available for any partially trusted application.</span></span>

[<span data-ttu-id="8c27b-134">返回页首</span><span class="sxs-lookup"><span data-stu-id="8c27b-134">Back to top</span></span>](#top)

<a name="level"></a>

## <a name="specifying-the-transparency-level"></a><span data-ttu-id="8c27b-135">指定透明度级别</span><span class="sxs-lookup"><span data-stu-id="8c27b-135">Specifying the Transparency Level</span></span>

<span data-ttu-id="8c27b-136">程序集级别的 <xref:System.Security.SecurityRulesAttribute> 特性显式选择该程序集将遵循的 <xref:System.Security.SecurityRuleSet> 规则。</span><span class="sxs-lookup"><span data-stu-id="8c27b-136">The assembly-level <xref:System.Security.SecurityRulesAttribute> attribute explicitly selects the <xref:System.Security.SecurityRuleSet> rules that the assembly will follow.</span></span> <span data-ttu-id="8c27b-137">这些规则在数字级别系统下组织，级别越高表示安全规则的强制性越高。</span><span class="sxs-lookup"><span data-stu-id="8c27b-137">The rules are organized under a numeric level system, where higher levels mean tighter enforcement of security rules.</span></span>

<span data-ttu-id="8c27b-138">级别如下：</span><span class="sxs-lookup"><span data-stu-id="8c27b-138">The levels are as follows:</span></span>

- <span data-ttu-id="8c27b-139">2 级 (<xref:System.Security.SecurityRuleSet.Level2>) – [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 透明度规则。</span><span class="sxs-lookup"><span data-stu-id="8c27b-139">Level 2 (<xref:System.Security.SecurityRuleSet.Level2>) – the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] transparency rules.</span></span>

- <span data-ttu-id="8c27b-140">1 级 (<xref:System.Security.SecurityRuleSet.Level1>) –.NET Framework 2.0 透明度规则。</span><span class="sxs-lookup"><span data-stu-id="8c27b-140">Level 1 (<xref:System.Security.SecurityRuleSet.Level1>) – the .NET Framework 2.0 transparency rules.</span></span>

<span data-ttu-id="8c27b-141">这两个透明度级别之间的主要区别是 1 级不对程序集外部的调用强制实施透明度规则，并且预期仅用于实现兼容性。</span><span class="sxs-lookup"><span data-stu-id="8c27b-141">The primary difference between the two transparency levels is that level 1 does not enforce transparency rules for calls from outside the assembly and is intended only for compatibility.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c27b-142">你应仅出于兼容性目的指定 1 级透明度，也就是说，仅为使用 .NET Framework 3.5 或更早版本（这些版本使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 属性或不使用透明度模型）开发的代码指定 1 级。</span><span class="sxs-lookup"><span data-stu-id="8c27b-142">You should specify level 1 transparency for compatibility only; that is, specify level 1 only for code that was developed with the .NET Framework 3.5 or earlier that uses the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute or does not use the transparency model.</span></span> <span data-ttu-id="8c27b-143">例如，对允许从部分信任的调用方 (APTCA) 调用的 .NET Framework 2.0 程序集使用 1 级透明度。</span><span class="sxs-lookup"><span data-stu-id="8c27b-143">For example, use level 1 transparency for .NET Framework 2.0 assemblies that allow calls from partially trusted callers (APTCA).</span></span> <span data-ttu-id="8c27b-144">为 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 开发的代码始终使用 2 级透明度。</span><span class="sxs-lookup"><span data-stu-id="8c27b-144">For code that is developed for the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], always use level 2 transparency.</span></span>

### <a name="level-2-transparency"></a><span data-ttu-id="8c27b-145">2 级透明度</span><span class="sxs-lookup"><span data-stu-id="8c27b-145">Level 2 Transparency</span></span>

<span data-ttu-id="8c27b-146">[!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中引入了 2 级透明度。</span><span class="sxs-lookup"><span data-stu-id="8c27b-146">Level 2 transparency was introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="8c27b-147">此模型的三条原则是透明代码、安全可靠关键代码和安全关键代码。</span><span class="sxs-lookup"><span data-stu-id="8c27b-147">The three tenets of this model are transparent code, security-safe-critical code, and security-critical code.</span></span>

- <span data-ttu-id="8c27b-148">透明代码（无论授予什么样的权限）可以调用其他透明代码或安全可靠关键代码。</span><span class="sxs-lookup"><span data-stu-id="8c27b-148">Transparent code, regardless of the permissions it is granted (including full trust), can call only other transparent code or security-safe-critical code.</span></span> <span data-ttu-id="8c27b-149">如果代码是部分信任的代码，那么它只能执行域权限集允许的操作。</span><span class="sxs-lookup"><span data-stu-id="8c27b-149">If the code is partially trusted, it can only perform actions that are allowed by the domain’s permission set.</span></span> <span data-ttu-id="8c27b-150">透明代码不能：</span><span class="sxs-lookup"><span data-stu-id="8c27b-150">Transparent code cannot do the following:</span></span>

  - <span data-ttu-id="8c27b-151">执行 <xref:System.Security.CodeAccessPermission.Assert%2A> 操作或特权提升。</span><span class="sxs-lookup"><span data-stu-id="8c27b-151">Perform an <xref:System.Security.CodeAccessPermission.Assert%2A> operation or elevation of privilege.</span></span>

  - <span data-ttu-id="8c27b-152">包含不安全或不可验证的代码。</span><span class="sxs-lookup"><span data-stu-id="8c27b-152">Contain unsafe or unverifiable code.</span></span>

  - <span data-ttu-id="8c27b-153">直接调用关键代码。</span><span class="sxs-lookup"><span data-stu-id="8c27b-153">Directly call critical code.</span></span>

  - <span data-ttu-id="8c27b-154">调用本机代码或具有 <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> 特性的代码。</span><span class="sxs-lookup"><span data-stu-id="8c27b-154">Call native code or code that has the <xref:System.Security.SuppressUnmanagedCodeSecurityAttribute> attribute.</span></span>

  - <span data-ttu-id="8c27b-155">调用受 <xref:System.Security.Permissions.SecurityAction.LinkDemand> 保护的成员。</span><span class="sxs-lookup"><span data-stu-id="8c27b-155">Call a member that is protected by a <xref:System.Security.Permissions.SecurityAction.LinkDemand>.</span></span>

  - <span data-ttu-id="8c27b-156">从关键类型继承。</span><span class="sxs-lookup"><span data-stu-id="8c27b-156">Inherit from critical types.</span></span>

    <span data-ttu-id="8c27b-157">此外，透明方法不能重写关键虚拟方法或实现关键接口方法。</span><span class="sxs-lookup"><span data-stu-id="8c27b-157">In addition, transparent methods cannot override critical virtual methods or implement critical interface methods.</span></span>

- <span data-ttu-id="8c27b-158">安全可靠关键代码是完全信任的代码，且可被透明代码调用的代码。</span><span class="sxs-lookup"><span data-stu-id="8c27b-158">Security-safe-critical code is fully trusted but is callable by transparent code.</span></span> <span data-ttu-id="8c27b-159">它公开完全信任代码的有限外围应用。</span><span class="sxs-lookup"><span data-stu-id="8c27b-159">It exposes a limited surface area of full-trust code.</span></span> <span data-ttu-id="8c27b-160">可靠关键代码中会进行正确性和安全性验证。</span><span class="sxs-lookup"><span data-stu-id="8c27b-160">Correctness and security verifications happen in safe-critical code.</span></span>

- <span data-ttu-id="8c27b-161">安全关键代码可以调用完全信任的任何代码，但不能被透明代码调用。</span><span class="sxs-lookup"><span data-stu-id="8c27b-161">Security-critical code can call any code and is fully trusted, but it cannot be called by transparent code.</span></span>

### <a name="level-1-transparency"></a><span data-ttu-id="8c27b-162">1 级透明度</span><span class="sxs-lookup"><span data-stu-id="8c27b-162">Level 1 Transparency</span></span>

<span data-ttu-id="8c27b-163">.NET Framework 2.0 版中引入了 1 级透明度模型，目的是便于开发人员减少需要接受安全性审核的代码数量。</span><span class="sxs-lookup"><span data-stu-id="8c27b-163">The level 1 transparency model was introduced in the .NET Framework version 2.0 to enable developers to reduce the amount of code that is subject to a security audit.</span></span> <span data-ttu-id="8c27b-164">虽然 1 级透明度在 2.0 版中公开提供，但它主要仅在 Microsoft 内部用于安全性审核目的。</span><span class="sxs-lookup"><span data-stu-id="8c27b-164">Although level 1 transparency was publicly available in version 2.0, it was primarily used only within Microsoft for security auditing purposes.</span></span> <span data-ttu-id="8c27b-165">开发人员可以通过批注声明哪些类型和成员可以执行安全提升和其他信任操作（安全关键），哪些不能执行（安全透明）。</span><span class="sxs-lookup"><span data-stu-id="8c27b-165">Through annotations, developers are able to declare which types and members can perform security elevations and other trusted actions (security-critical) and which cannot (security-transparent).</span></span> <span data-ttu-id="8c27b-166">标识为透明的代码不需要高度的安全性审核。</span><span class="sxs-lookup"><span data-stu-id="8c27b-166">Code that is identified as transparent does not require a high degree of security auditing.</span></span> <span data-ttu-id="8c27b-167">1 级透明度表明透明度强制仅限于程序集内部。</span><span class="sxs-lookup"><span data-stu-id="8c27b-167">Level 1 transparency states that the transparency enforcement is limited to within the assembly.</span></span> <span data-ttu-id="8c27b-168">换而言之，标识为安全关键的任何公共类型或成员仅在该程序集内部是安全关键的。</span><span class="sxs-lookup"><span data-stu-id="8c27b-168">In other words, any public types or members that are identified as security-critical are security-critical only within the assembly.</span></span> <span data-ttu-id="8c27b-169">如果希望在从程序集外部调用这些类型和成员时对它们强制实施安全性，则必须使用完全信任的链接要求。</span><span class="sxs-lookup"><span data-stu-id="8c27b-169">If you want to enforce security for those types and members when they are called from outside the assembly, you must use link demands for full trust.</span></span> <span data-ttu-id="8c27b-170">如果不这样做，则公开可见的安全关键类型和成员将被视为安全可靠关键，并且可在程序集外部被部分信任的代码调用。</span><span class="sxs-lookup"><span data-stu-id="8c27b-170">If you do not, publicly visible security-critical types and members are treated as security-safe-critical and can be called by partially trusted code outside the assembly.</span></span>

<span data-ttu-id="8c27b-171">1 级透明度模型具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="8c27b-171">The level 1 transparency model has the following limitations:</span></span>

- <span data-ttu-id="8c27b-172">安全关键类型和成员是公开的，可从安全透明代码访问。</span><span class="sxs-lookup"><span data-stu-id="8c27b-172">Security-critical types and members that are public are accessible from security-transparent code.</span></span>

- <span data-ttu-id="8c27b-173">只能在程序集内部强制进行透明度批注。</span><span class="sxs-lookup"><span data-stu-id="8c27b-173">The transparency annotations are enforced only within an assembly.</span></span>

- <span data-ttu-id="8c27b-174">安全关键类型和成员必须使用链接要求才能对程序集外部的调用强制实施安全性。</span><span class="sxs-lookup"><span data-stu-id="8c27b-174">Security-critical types and members must use link demands to enforce security for calls from outside the assembly.</span></span>

- <span data-ttu-id="8c27b-175">不会强制执行继承规则。</span><span class="sxs-lookup"><span data-stu-id="8c27b-175">Inheritance rules are not enforced.</span></span>

- <span data-ttu-id="8c27b-176">在完全信任模式下运行时，透明代码可能会执行有害的操作。</span><span class="sxs-lookup"><span data-stu-id="8c27b-176">The potential exists for transparent code to do harmful things when run in full trust.</span></span>

[<span data-ttu-id="8c27b-177">返回页首</span><span class="sxs-lookup"><span data-stu-id="8c27b-177">Back to top</span></span>](#top)

<a name="enforcement"></a>

## <a name="transparency-enforcement"></a><span data-ttu-id="8c27b-178">透明度强制</span><span class="sxs-lookup"><span data-stu-id="8c27b-178">Transparency Enforcement</span></span>

<span data-ttu-id="8c27b-179">在计算透明度之前，不会强制执行透明度规则。</span><span class="sxs-lookup"><span data-stu-id="8c27b-179">Transparency rules are not enforced until transparency is calculated.</span></span> <span data-ttu-id="8c27b-180">那时，如果违反了透明度规则，则将引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="8c27b-180">At that time, an <xref:System.InvalidOperationException> is thrown if a transparency rule is violated.</span></span> <span data-ttu-id="8c27b-181">计算透明度的时间取决于多种因素，并且无法预测。</span><span class="sxs-lookup"><span data-stu-id="8c27b-181">The time that transparency is calculated depends on multiple factors and cannot be predicted.</span></span> <span data-ttu-id="8c27b-182">应尽可能晚地计算。</span><span class="sxs-lookup"><span data-stu-id="8c27b-182">It is calculated as late as possible.</span></span> <span data-ttu-id="8c27b-183">在 [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 中，程序集级别的透明度计算比 .NET Framework 2.0 中发生得更快。</span><span class="sxs-lookup"><span data-stu-id="8c27b-183">In the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], assembly-level transparency calculation occurs sooner than it does in the .NET Framework 2.0.</span></span> <span data-ttu-id="8c27b-184">只能保证透明度计算将在需要的时间之前发生。</span><span class="sxs-lookup"><span data-stu-id="8c27b-184">The only guarantee is that transparency calculation will occur by the time it is needed.</span></span> <span data-ttu-id="8c27b-185">这类似于在编译某种方法且在该方法中检测到错误时实时 (JIT) 编译器将如何更改时间点。</span><span class="sxs-lookup"><span data-stu-id="8c27b-185">This is similar to how the just-in-time (JIT) compiler can change the point when a method is compiled and any errors in that method are detected.</span></span> <span data-ttu-id="8c27b-186">如果你的代码没有透明度错误，则透明度计算是不可见的。</span><span class="sxs-lookup"><span data-stu-id="8c27b-186">Transparency calculation is invisible if your code does not have any transparency errors.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c27b-187">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c27b-187">See also</span></span>

- [<span data-ttu-id="8c27b-188">安全透明代码，级别 1</span><span class="sxs-lookup"><span data-stu-id="8c27b-188">Security-Transparent Code, Level 1</span></span>](../../../docs/framework/misc/security-transparent-code-level-1.md)
- [<span data-ttu-id="8c27b-189">安全透明代码，级别 2</span><span class="sxs-lookup"><span data-stu-id="8c27b-189">Security-Transparent Code, Level 2</span></span>](../../../docs/framework/misc/security-transparent-code-level-2.md)
