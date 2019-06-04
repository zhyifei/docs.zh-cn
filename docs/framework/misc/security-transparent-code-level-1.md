---
title: 安全透明代码，级别 1
ms.date: 03/30/2017
helpviewer_keywords:
- transparent
- SecurityTreatAsSafeAttribute
- SecurityTransparentAttribute
- SecurityCriticalAttribute
- security-transparent code
- security [.NET Framework], security-transparent code
ms.assetid: 5fd8f46d-3961-46a7-84af-2eb1f48e75cf
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fd594ef1fea4c8723965ad483a5a124892bcf00
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487871"
---
# <a name="security-transparent-code-level-1"></a><span data-ttu-id="2afe7-102">安全透明代码，级别 1</span><span class="sxs-lookup"><span data-stu-id="2afe7-102">Security-Transparent Code, Level 1</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="2afe7-103">透明度可帮助开发人员编写更安全的 .NET Framework 库来向部分信任的代码公开功能。</span><span class="sxs-lookup"><span data-stu-id="2afe7-103">Transparency helps developers write more secure .NET Framework libraries that expose functionality to partially trusted code.</span></span> <span data-ttu-id="2afe7-104">.NET Framework 2.0 版中引入了 1 级透明度，此透明度主要仅供 Microsoft 内部使用。</span><span class="sxs-lookup"><span data-stu-id="2afe7-104">Level 1 transparency was introduced in the .NET Framework version 2.0 and was primarily used only within Microsoft.</span></span> <span data-ttu-id="2afe7-105">从.NET Framework 4 开始，你可以使用[2 级透明度](../../../docs/framework/misc/security-transparent-code-level-2.md)。</span><span class="sxs-lookup"><span data-stu-id="2afe7-105">Starting with the .NET Framework 4, you can use [level 2 transparency](../../../docs/framework/misc/security-transparent-code-level-2.md).</span></span> <span data-ttu-id="2afe7-106">但是，已保留 1 级透明度，以便可以确定必须使用以前的安全规则运行的旧代码。</span><span class="sxs-lookup"><span data-stu-id="2afe7-106">However, level 1 transparency has been retained so that you can identify legacy code that must run with the earlier security rules.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2afe7-107">应仅出于兼容性目的而指定 1 级透明度；也就是说，仅为使用 .NET Framework 3.5 或以前的版本（使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 或不使用透明度模型）开发的代码指定 1 级透明度。</span><span class="sxs-lookup"><span data-stu-id="2afe7-107">You should specify level 1 transparency for compatibility only; that is, specify level 1 only for code that was developed with the .NET Framework 3.5 or earlier that uses the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> or does not use the transparency model.</span></span> <span data-ttu-id="2afe7-108">例如，对允许从部分信任的调用方 (APTCA) 调用的 .NET Framework 2.0 程序集使用 1 级透明度。</span><span class="sxs-lookup"><span data-stu-id="2afe7-108">For example, use level 1 transparency for .NET Framework 2.0 assemblies that allow calls from partially trusted callers (APTCA).</span></span> <span data-ttu-id="2afe7-109">对于针对.NET Framework 4 开发的代码，始终使用 2 级透明度。</span><span class="sxs-lookup"><span data-stu-id="2afe7-109">For code that is developed for the .NET Framework 4, always use level 2 transparency.</span></span>  
  
 <span data-ttu-id="2afe7-110">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="2afe7-110">This topic contains the following sections:</span></span>  
  
- [<span data-ttu-id="2afe7-111">1 级透明度模型</span><span class="sxs-lookup"><span data-stu-id="2afe7-111">The Level 1 Transparency Model</span></span>](#the_level_1_transparency_model)  
  
- [<span data-ttu-id="2afe7-112">透明性属性</span><span class="sxs-lookup"><span data-stu-id="2afe7-112">Transparency Attributes</span></span>](#transparency_attributes)  
  
- [<span data-ttu-id="2afe7-113">安全透明度示例</span><span class="sxs-lookup"><span data-stu-id="2afe7-113">Security Transparency Examples</span></span>](#security_transparency_examples)  
  
<a name="the_level_1_transparency_model"></a>   
## <a name="the-level-1-transparency-model"></a><span data-ttu-id="2afe7-114">1 级透明度模型</span><span class="sxs-lookup"><span data-stu-id="2afe7-114">The Level 1 Transparency Model</span></span>  
 <span data-ttu-id="2afe7-115">使用 1 级透明度时，你会使用一种安全模型，该模型将代码分成三类方法：安全透明的方法、安全可靠关键的方法和安全关键的方法。</span><span class="sxs-lookup"><span data-stu-id="2afe7-115">When you use Level 1 transparency, you are using a security model that separates code into security-transparent, security-safe-critical, and security-critical methods.</span></span>  
  
 <span data-ttu-id="2afe7-116">可将整个程序集、程序集中的某些类或类中的某些方法标记为安全透明。</span><span class="sxs-lookup"><span data-stu-id="2afe7-116">You can mark a whole assembly, some classes in an assembly, or some methods in a class as security-transparent.</span></span> <span data-ttu-id="2afe7-117">安全透明的代码不能提升特权。</span><span class="sxs-lookup"><span data-stu-id="2afe7-117">Security-transparent code cannot elevate privileges.</span></span> <span data-ttu-id="2afe7-118">此限制会造成三个后果：</span><span class="sxs-lookup"><span data-stu-id="2afe7-118">This restriction has three consequences:</span></span>  
  
- <span data-ttu-id="2afe7-119">安全透明的代码不能执行 <xref:System.Security.Permissions.SecurityAction.Assert> 操作。</span><span class="sxs-lookup"><span data-stu-id="2afe7-119">Security-transparent code cannot perform <xref:System.Security.Permissions.SecurityAction.Assert> actions.</span></span>  
  
- <span data-ttu-id="2afe7-120">安全透明的代码将满足的任何链接要求都会变成完全要求。</span><span class="sxs-lookup"><span data-stu-id="2afe7-120">Any link demand that would be satisfied by security-transparent code becomes a full demand.</span></span>  
  
- <span data-ttu-id="2afe7-121">若有任何必须在安全透明的代码中执行的不安全代码（不可验证的代码），都会引起对 <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> 安全权限的完全要求。</span><span class="sxs-lookup"><span data-stu-id="2afe7-121">Any unsafe (unverifiable) code that must execute in security-transparent code causes a full demand for the <xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode> security permission.</span></span>  
  
 <span data-ttu-id="2afe7-122">在执行期间，公共语言运行时 (CLR) 会强制执行这些规则。</span><span class="sxs-lookup"><span data-stu-id="2afe7-122">These rules are enforced during execution by the common language runtime (CLR).</span></span> <span data-ttu-id="2afe7-123">安全透明的代码会将其调用的代码的所有安全需求全部传递回调用方。</span><span class="sxs-lookup"><span data-stu-id="2afe7-123">Security-transparent code passes all the security requirements of the code it calls back to its callers.</span></span> <span data-ttu-id="2afe7-124">流过安全透明代码的要求不能提升特权。</span><span class="sxs-lookup"><span data-stu-id="2afe7-124">Demands that flow through the security-transparent code cannot elevate privileges.</span></span> <span data-ttu-id="2afe7-125">如果低信任应用程序调用安全透明的代码并导致对高特权的要求，该要求将流回低信任代码并失败。</span><span class="sxs-lookup"><span data-stu-id="2afe7-125">If a low-trust application calls security-transparent code and causes a demand for high privilege, the demand will flow back to the low-trust code and fail.</span></span> <span data-ttu-id="2afe7-126">由于安全透明的代码不能执行断言操作，因此该代码不能停止该要求。</span><span class="sxs-lookup"><span data-stu-id="2afe7-126">The security-transparent code cannot stop the demand because it cannot perform assert actions.</span></span> <span data-ttu-id="2afe7-127">从完全信任代码中调用相同的安全透明代码将使要求成功。</span><span class="sxs-lookup"><span data-stu-id="2afe7-127">The same security-transparent code called from full-trust code results in a successful demand.</span></span>  
  
 <span data-ttu-id="2afe7-128">安全关键与安全透明相反。</span><span class="sxs-lookup"><span data-stu-id="2afe7-128">Security-critical is the opposite of security-transparent.</span></span> <span data-ttu-id="2afe7-129">安全关键代码以完全信任模式执行，可以执行所有特权操作。</span><span class="sxs-lookup"><span data-stu-id="2afe7-129">Security-critical code executes with full trust and can perform all privileged operations.</span></span> <span data-ttu-id="2afe7-130">安全可靠关键代码是特权代码，并经过全面的安全审核，已确认它不允许部分信任的调用方使用它们无权访问的资源。</span><span class="sxs-lookup"><span data-stu-id="2afe7-130">Security-safe-critical code is privileged code that has been through an extensive security audit to confirm that it does not allow partially trusted callers to use resources they do not have permission to access.</span></span>  
  
 <span data-ttu-id="2afe7-131">必须显式应用透明度。</span><span class="sxs-lookup"><span data-stu-id="2afe7-131">You have to apply transparency explicitly.</span></span> <span data-ttu-id="2afe7-132">通常，处理数据操作和逻辑的大部分代码都可以标记为安全透明，而执行特权提升的少量代码则标记为安全关键或安全可靠关键。</span><span class="sxs-lookup"><span data-stu-id="2afe7-132">The majority of your code that handles data manipulation and logic can typically be marked as security-transparent, whereas the lesser amount of code that performs elevations of privileges is marked as security-critical or security-safe-critical.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2afe7-133">1 级透明度限于程序集范围，不能跨程序集实施。</span><span class="sxs-lookup"><span data-stu-id="2afe7-133">Level 1 transparency is limited to assembly scope; it is not enforced between assemblies.</span></span> <span data-ttu-id="2afe7-134">1 级透明度主要在 Microsoft 内部出于安全审核的目的使用。</span><span class="sxs-lookup"><span data-stu-id="2afe7-134">Level 1 transparency was primarily used within Microsoft for security audit purposes.</span></span> <span data-ttu-id="2afe7-135">1 级程序集中的安全关键类型和成员可由其他程序集中的安全透明代码访问。</span><span class="sxs-lookup"><span data-stu-id="2afe7-135">Security-critical types and members within a level 1 assembly can be accessed by security-transparent code in other assemblies.</span></span> <span data-ttu-id="2afe7-136">在所有 1 级安全关键类型和成员中，都必须执行针对完全信任的链接要求。</span><span class="sxs-lookup"><span data-stu-id="2afe7-136">It is important that you perform link demands for full trust in all your level 1 security-critical types and members.</span></span> <span data-ttu-id="2afe7-137">对于安全可靠关键类型或成员所访问的受保护资源，该类型和成员还必须确认调用方拥有访问这些资源的权限。</span><span class="sxs-lookup"><span data-stu-id="2afe7-137">Security-safe-critical types and members must also confirm that callers have permissions for protected resources that are accessed by the type or member.</span></span>  
  
 <span data-ttu-id="2afe7-138">为了向后兼容 .NET Framework 的早期版本，所有未用透明度特性批注的成员都被视为安全可靠关键成员。</span><span class="sxs-lookup"><span data-stu-id="2afe7-138">For backward compatibility with earlier versions of the .NET Framework, all members that are not annotated with transparency attributes are considered to be security-safe-critical.</span></span> <span data-ttu-id="2afe7-139">所有未进行此类批注的类型都被视为是透明的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-139">All types that are not annotated are considered to be transparent.</span></span> <span data-ttu-id="2afe7-140">没有用于验证透明度的静态分析规则。</span><span class="sxs-lookup"><span data-stu-id="2afe7-140">There are no static analysis rules to validate transparency.</span></span> <span data-ttu-id="2afe7-141">因此，你可能需要在运行时调试透明度错误。</span><span class="sxs-lookup"><span data-stu-id="2afe7-141">Therefore, you may need to debug transparency errors at run time.</span></span>  
  
<a name="transparency_attributes"></a>   
## <a name="transparency-attributes"></a><span data-ttu-id="2afe7-142">透明度特性</span><span class="sxs-lookup"><span data-stu-id="2afe7-142">Transparency Attributes</span></span>  
 <span data-ttu-id="2afe7-143">下表介绍可用于批注代码透明度的三个特性。</span><span class="sxs-lookup"><span data-stu-id="2afe7-143">The following table describes the three attributes that you use to annotate your code for transparency.</span></span>  
  
|<span data-ttu-id="2afe7-144">特性</span><span class="sxs-lookup"><span data-stu-id="2afe7-144">Attribute</span></span>|<span data-ttu-id="2afe7-145">描述</span><span class="sxs-lookup"><span data-stu-id="2afe7-145">Description</span></span>|  
|---------------|-----------------|  
|<xref:System.Security.SecurityTransparentAttribute>|<span data-ttu-id="2afe7-146">只允许在程序集级别上应用。</span><span class="sxs-lookup"><span data-stu-id="2afe7-146">Allowed only at the assembly level.</span></span> <span data-ttu-id="2afe7-147">将程序集中的所有类型和成员都标识为安全透明。</span><span class="sxs-lookup"><span data-stu-id="2afe7-147">Identifies all types and members in the assembly as security-transparent.</span></span> <span data-ttu-id="2afe7-148">程序集不能包含任何安全关键代码。</span><span class="sxs-lookup"><span data-stu-id="2afe7-148">The assembly cannot contain any security-critical code.</span></span>|  
|<xref:System.Security.SecurityCriticalAttribute>|<span data-ttu-id="2afe7-149">不带 <xref:System.Security.SecurityCriticalAttribute.Scope%2A> 属性在程序集级别使用时，默认将程序集中的所有代码都标识为安全透明的代码，但会指出程序集可能包含安全关键代码。</span><span class="sxs-lookup"><span data-stu-id="2afe7-149">When used at the assembly level without the <xref:System.Security.SecurityCriticalAttribute.Scope%2A> property, identifies all code in the assembly as security-transparent by default, but indicates that the assembly may contain security-critical code.</span></span><br /><br /> <span data-ttu-id="2afe7-150">在类级别使用时，将类或方法标识为安全关键，但不会如此标识类的成员。</span><span class="sxs-lookup"><span data-stu-id="2afe7-150">When used at the class level, identifies the class or method as security-critical, but not the members of the class.</span></span> <span data-ttu-id="2afe7-151">若要使所有成员都成为安全关键成员，请将 <xref:System.Security.SecurityCriticalAttribute.Scope%2A> 属性设置为 <xref:System.Security.SecurityCriticalScope.Everything>。</span><span class="sxs-lookup"><span data-stu-id="2afe7-151">To make all the members security-critical, set the <xref:System.Security.SecurityCriticalAttribute.Scope%2A> property to <xref:System.Security.SecurityCriticalScope.Everything>.</span></span><br /><br /> <span data-ttu-id="2afe7-152">在成员级别使用时，特性仅应用于相应的成员。</span><span class="sxs-lookup"><span data-stu-id="2afe7-152">When used at the member level, the attribute applies only to that member.</span></span><br /><br /> <span data-ttu-id="2afe7-153">标识为安全关键的类或成员可以执行特权提升。</span><span class="sxs-lookup"><span data-stu-id="2afe7-153">The class or member identified as security-critical can perform elevations of privilege.</span></span> <span data-ttu-id="2afe7-154">**重要提示：** 在 1 级透明度中，当从程序集外部调用安全关键类型和成员时，该类型或成员被视为是安全可靠关键的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-154">**Important:**  In level 1 transparency, security-critical types and members are treated as security-safe-critical when they are called from outside the assembly.</span></span> <span data-ttu-id="2afe7-155">应该通过针对完全信任的链接要求来保护安全关键类型和成员，以避免未经授权的特权提升。</span><span class="sxs-lookup"><span data-stu-id="2afe7-155">You should protect security-critical types and members with a link demand for full trust to avoid unauthorized elevation of privilege.</span></span>|  
|<xref:System.Security.SecuritySafeCriticalAttribute>|<span data-ttu-id="2afe7-156">标识可以由程序集中的安全透明代码访问的安全关键代码。</span><span class="sxs-lookup"><span data-stu-id="2afe7-156">Identifies security-critical code that can be accessed by security-transparent code in the assembly.</span></span> <span data-ttu-id="2afe7-157">否则，安全透明的代码将不能访问同一程序集中的私有或内部安全关键成员。</span><span class="sxs-lookup"><span data-stu-id="2afe7-157">Otherwise, security-transparent code cannot access private or internal security-critical members in the same assembly.</span></span> <span data-ttu-id="2afe7-158">执行此操作将影响安全关键代码，并且可能会引起意外的特权提升。</span><span class="sxs-lookup"><span data-stu-id="2afe7-158">Doing so would influence security-critical code and make unexpected elevations of privilege possible.</span></span> <span data-ttu-id="2afe7-159">安全可靠关键代码应该经过严格的安全审核。</span><span class="sxs-lookup"><span data-stu-id="2afe7-159">Security-safe-critical code should undergo a rigorous security audit.</span></span> <span data-ttu-id="2afe7-160">**注意：** 安全可靠关键类型和成员必须验证调用方的权限，以确定调用方是否有权访问受保护的资源。</span><span class="sxs-lookup"><span data-stu-id="2afe7-160">**Note:**  Security-safe-critical types and members must validate the permissions of callers to determine whether the caller has authority to access protected resources.</span></span>|  
  
 <span data-ttu-id="2afe7-161"><xref:System.Security.SecuritySafeCriticalAttribute> 特性使得安全透明的代码可以访问同一程序集中的安全关键成员。</span><span class="sxs-lookup"><span data-stu-id="2afe7-161">The <xref:System.Security.SecuritySafeCriticalAttribute> attribute enables security-transparent code to access security-critical members in the same assembly.</span></span> <span data-ttu-id="2afe7-162">将程序集中的安全透明代码和安全关键代码视为两个程序集中的代码。</span><span class="sxs-lookup"><span data-stu-id="2afe7-162">Consider the security-transparent and security-critical code in your assembly as separated into two assemblies.</span></span> <span data-ttu-id="2afe7-163">安全透明的代码将不能查看安全关键代码的私有或内部成员。</span><span class="sxs-lookup"><span data-stu-id="2afe7-163">The security-transparent code would not be able to see the private or internal members of the security-critical code.</span></span> <span data-ttu-id="2afe7-164">此外，通常会对安全关键代码进行审核，以核查对其公共接口的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2afe7-164">Additionally, the security-critical code is generally audited for access to its public interface.</span></span> <span data-ttu-id="2afe7-165">你不希望可在程序集外访问私有或内部状态，而希望将该状态保持隔离。</span><span class="sxs-lookup"><span data-stu-id="2afe7-165">You would not expect a private or internal state to be accessible outside the assembly; you would want to keep the state isolated.</span></span> <span data-ttu-id="2afe7-166"><xref:System.Security.SecuritySafeCriticalAttribute> 特性可在安全透明代码和安全关键代码之间保持状态隔离，同时允许在必要时替代该隔离。</span><span class="sxs-lookup"><span data-stu-id="2afe7-166">The <xref:System.Security.SecuritySafeCriticalAttribute> attribute maintains the isolation of state between security-transparent and security-critical code while providing the ability to override the isolation when it is necessary.</span></span> <span data-ttu-id="2afe7-167">安全透明的代码不能访问私有或内部安全关键代码，除非这些成员已标记有 <xref:System.Security.SecuritySafeCriticalAttribute>.</span><span class="sxs-lookup"><span data-stu-id="2afe7-167">Security-transparent code cannot access private or internal security-critical code unless those members have been marked with <xref:System.Security.SecuritySafeCriticalAttribute>.</span></span> <span data-ttu-id="2afe7-168">在应用 <xref:System.Security.SecuritySafeCriticalAttribute> 之前，将该成员视为公共公开的成员对其进行审核。</span><span class="sxs-lookup"><span data-stu-id="2afe7-168">Before applying the <xref:System.Security.SecuritySafeCriticalAttribute>, audit that member as if it were publicly exposed.</span></span>  
  
### <a name="assembly-wide-annotation"></a><span data-ttu-id="2afe7-169">程序集范围的批注</span><span class="sxs-lookup"><span data-stu-id="2afe7-169">Assembly-wide Annotation</span></span>  
 <span data-ttu-id="2afe7-170">下表描述在程序集级别使用安全特性所产生的作用。</span><span class="sxs-lookup"><span data-stu-id="2afe7-170">The following table describes the effects of using security attributes at the assembly level.</span></span>  
  
|<span data-ttu-id="2afe7-171">Assembly 特性</span><span class="sxs-lookup"><span data-stu-id="2afe7-171">Assembly attribute</span></span>|<span data-ttu-id="2afe7-172">程序集状态</span><span class="sxs-lookup"><span data-stu-id="2afe7-172">Assembly state</span></span>|  
|------------------------|--------------------|  
|<span data-ttu-id="2afe7-173">部分信任的程序集上无特性</span><span class="sxs-lookup"><span data-stu-id="2afe7-173">No attribute on a partially trusted assembly</span></span>|<span data-ttu-id="2afe7-174">所有类型和成员都是透明的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-174">All types and members are transparent.</span></span>|  
|<span data-ttu-id="2afe7-175">完全信任的程序集上无特性（对于全局程序集缓存中的程序集，或者在 `AppDomain` 中标识为完全信任的程序集）</span><span class="sxs-lookup"><span data-stu-id="2afe7-175">No attribute on a fully trusted assembly (in the global assembly cache or identified as full trust in the `AppDomain`)</span></span>|<span data-ttu-id="2afe7-176">所有类型都是透明的，所有成员都是安全可靠关键的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-176">All types are transparent and all members are security-safe-critical.</span></span>|  
|`SecurityTransparent`|<span data-ttu-id="2afe7-177">所有类型和成员都是透明的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-177">All types and members are transparent.</span></span>|  
|`SecurityCritical(SecurityCriticalScope.Everything)`|<span data-ttu-id="2afe7-178">所有类型和成员都是安全关键的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-178">All types and members are security-critical.</span></span>|  
|`SecurityCritical`|<span data-ttu-id="2afe7-179">所有代码默认都是透明的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-179">All code defaults to transparent.</span></span> <span data-ttu-id="2afe7-180">但是，各个类型和成员可以有其他特性。</span><span class="sxs-lookup"><span data-stu-id="2afe7-180">However, individual types and members can have other attributes.</span></span>|  
  
<a name="security_transparency_examples"></a>   
## <a name="security-transparency-examples"></a><span data-ttu-id="2afe7-181">安全透明度示例</span><span class="sxs-lookup"><span data-stu-id="2afe7-181">Security Transparency Examples</span></span>  
 <span data-ttu-id="2afe7-182">若要使用 .NET Framework 2.0 透明度规则（1 级透明度），请使用下面的程序集批注：</span><span class="sxs-lookup"><span data-stu-id="2afe7-182">To use the .NET Framework 2.0 transparency rules (level 1 transparency), use the following assembly annotation:</span></span>  
  
```  
[assembly: SecurityRules(SecurityRuleSet.Level1)]  
```  
  
 <span data-ttu-id="2afe7-183">如果要使整个程序集透明以指示该程序集不包含任何关键代码并且不以任何方式提升特权，则可通过以下特性显式增加程序集的透明度：</span><span class="sxs-lookup"><span data-stu-id="2afe7-183">If you want to make a whole assembly transparent to indicate that the assembly does not contain any critical code and does not elevate privileges in any way, you can explicitly add transparency to the assembly with the following attribute:</span></span>  
  
```  
[assembly: SecurityTransparent]  
```  
  
 <span data-ttu-id="2afe7-184">如果要在同一程序集中混合关键代码和透明代码，则可首先用 <xref:System.Security.SecurityCriticalAttribute> 特性标记该程序集，以指示该程序集可以包含关键代码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2afe7-184">If you want to mix critical and transparent code in the same assembly, start by marking the assembly with the <xref:System.Security.SecurityCriticalAttribute> attribute to indicate that the assembly can contain critical code, as follows:</span></span>  
  
```  
[assembly: SecurityCritical]  
```  
  
 <span data-ttu-id="2afe7-185">如果要执行安全关键操作，则必须用另一个 <xref:System.Security.SecurityCriticalAttribute> 特性显式标记将执行关键操作的代码，如下面的代码示例中所示：</span><span class="sxs-lookup"><span data-stu-id="2afe7-185">If you want to perform security-critical actions, you must explicitly mark the code that will perform the critical action with another <xref:System.Security.SecurityCriticalAttribute> attribute, as shown in the following code example:</span></span>  
  
```  
[assembly: SecurityCritical]  
Public class A  
{  
    [SecurityCritical]  
    private void Critical()  
    {  
        // critical  
    }  
  
    public int SomeProperty  
    {  
        get {/* transparent */ }  
        set {/* transparent */ }  
    }  
}  
public class B  
{      
    internal string SomeOtherProperty  
    {  
        get { /* transparent */ }  
        set { /* transparent */ }  
    }  
}  
```  
  
 <span data-ttu-id="2afe7-186">除 `Critical` 方法显式标记为安全关键之外，前面的代码都是透明的。</span><span class="sxs-lookup"><span data-stu-id="2afe7-186">The previous code is transparent except for the `Critical` method, which is explicitly marked as security-critical.</span></span> <span data-ttu-id="2afe7-187">即使使用程序集级别的 <xref:System.Security.SecurityCriticalAttribute> 特性，透明度也是默认设置。</span><span class="sxs-lookup"><span data-stu-id="2afe7-187">Transparency is the default setting, even with the assembly-level <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2afe7-188">请参阅</span><span class="sxs-lookup"><span data-stu-id="2afe7-188">See also</span></span>

- [<span data-ttu-id="2afe7-189">安全透明代码，级别 2</span><span class="sxs-lookup"><span data-stu-id="2afe7-189">Security-Transparent Code, Level 2</span></span>](../../../docs/framework/misc/security-transparent-code-level-2.md)
- [<span data-ttu-id="2afe7-190">安全更改</span><span class="sxs-lookup"><span data-stu-id="2afe7-190">Security Changes</span></span>](../../../docs/framework/security/security-changes.md)
