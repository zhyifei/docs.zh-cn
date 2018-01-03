---
title: "代码访问安全策略兼容性和迁移"
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: article
helpviewer_keywords:
- policy migration, compatibility
- CLR poliicy migration
ms.assetid: 19cb4d39-e38a-4262-b507-458915303115
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9feb4553b1b9e013c5c299d867d74499a09e1434
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="code-access-security-policy-compatibility-and-migration"></a><span data-ttu-id="bb1d4-102">代码访问安全策略兼容性和迁移</span><span class="sxs-lookup"><span data-stu-id="bb1d4-102">Code Access Security Policy Compatibility and Migration</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="bb1d4-103">代码访问安全性 (CAS) 的策略部分在 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)] 中已过时。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-103">The policy portion of code access security (CAS) has been made obsolete in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="bb1d4-104">因此，你可能会遇到编译警告和运行时异常如果调用过时的策略类型和成员[显式](#explicit_use)或[隐式](#implicit_use)（通过其他类型和成员）。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-104">As a result, you may encounter compilation warnings and runtime exceptions if you call the obsolete policy types and members [explicitly](#explicit_use) or [implicitly](#implicit_use) (through other types and members).</span></span>  
  
 <span data-ttu-id="bb1d4-105">可以通过以下任一方法来避免这些警告和错误：</span><span class="sxs-lookup"><span data-stu-id="bb1d4-105">You can avoid the warnings and errors by either:</span></span>  
  
-   <span data-ttu-id="bb1d4-106">[迁移](#migration)到[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]替换已过时的调用。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-106">[Migrating](#migration) to the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] replacements for the obsolete calls.</span></span>  
  
     <span data-ttu-id="bb1d4-107">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="bb1d4-107">\- or -</span></span>  
  
-   <span data-ttu-id="bb1d4-108">使用[< NetFx40_LegacySecurityPolicy > 配置元素](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)选择使用旧版 CAS 策略行为。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-108">Using the [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) to opt into the legacy CAS policy behavior.</span></span>  
  
 <span data-ttu-id="bb1d4-109">本主题包含以下各节：</span><span class="sxs-lookup"><span data-stu-id="bb1d4-109">This topic contains the following sections:</span></span>  
  
-   [<span data-ttu-id="bb1d4-110">显式使用</span><span class="sxs-lookup"><span data-stu-id="bb1d4-110">Explicit Use</span></span>](#explicit_use)  
  
-   [<span data-ttu-id="bb1d4-111">隐式使用</span><span class="sxs-lookup"><span data-stu-id="bb1d4-111">Implicit Use</span></span>](#implicit_use)  
  
-   [<span data-ttu-id="bb1d4-112">错误和警告</span><span class="sxs-lookup"><span data-stu-id="bb1d4-112">Errors and Warnings</span></span>](#errors_and_warnings)  
  
-   [<span data-ttu-id="bb1d4-113">迁移： 替换已过时的调用</span><span class="sxs-lookup"><span data-stu-id="bb1d4-113">Migration: Replacement for Obsolete Calls</span></span>](#migration)  
  
-   [<span data-ttu-id="bb1d4-114">兼容性： 使用 CAS 策略旧版选项</span><span class="sxs-lookup"><span data-stu-id="bb1d4-114">Compatibility: Using the CAS Policy Legacy Option</span></span>](#compatibility)  
  
<a name="explicit_use"></a>   
## <a name="explicit-use"></a><span data-ttu-id="bb1d4-115">显式使用</span><span class="sxs-lookup"><span data-stu-id="bb1d4-115">Explicit Use</span></span>  
 <span data-ttu-id="bb1d4-116">直接操作安全策略或需要沙盒的 CAS 策略的成员已过时，并且默认情况下将产生错误。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-116">Members that directly manipulate security policy or require CAS policy to sandbox are obsolete and will produce errors by default.</span></span>  
  
 <span data-ttu-id="bb1d4-117">这方面的示例如下：</span><span class="sxs-lookup"><span data-stu-id="bb1d4-117">Examples of these are:</span></span>  
  
-   <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.HostSecurityManager.DomainPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.Policy.PolicyLevel.CreateAppDomainLevel%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromString%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.LoadPolicyLevelFromFile%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolveSystemPolicy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.ResolvePolicyGroups%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.PolicyHierarchy%2A?displayProperty=nameWithType>  
  
-   <xref:System.Security.SecurityManager.SavePolicy%2A?displayProperty=nameWithType>  
  
<a name="implicit_use"></a>   
## <a name="implicit-use"></a><span data-ttu-id="bb1d4-118">隐式使用</span><span class="sxs-lookup"><span data-stu-id="bb1d4-118">Implicit Use</span></span>  
 <span data-ttu-id="bb1d4-119">由于若干程序集加载重载隐式使用 CAS 策略，因此它们产生错误。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-119">Several assembly loading overloads produce errors because of their implicit use of CAS policy.</span></span> <span data-ttu-id="bb1d4-120">这些重载采用用于解决 CAS 策略的 <xref:System.Security.Policy.Evidence> 参数，并为程序集提供权限授予集。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-120">These overloads take an <xref:System.Security.Policy.Evidence> parameter that is used to resolve CAS policy and provide a permission grant set for an assembly.</span></span>  
  
 <span data-ttu-id="bb1d4-121">以下是一些示例。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-121">Here are some examples.</span></span> <span data-ttu-id="bb1d4-122">过时的重载是使用 <xref:System.Security.Policy.Evidence> 作为参数的重载：</span><span class="sxs-lookup"><span data-stu-id="bb1d4-122">The obsolete overloads are those that take <xref:System.Security.Policy.Evidence> as a parameter:</span></span>  
  
-   <xref:System.Activator.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.CreateInstanceAndUnwrap%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.DefineDynamicAssembly%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.ExecuteAssemblyByName%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.LoadFrom%2A?displayProperty=nameWithType>  
  
<a name="errors_and_warnings"></a>   
## <a name="errors-and-warnings"></a><span data-ttu-id="bb1d4-123">错误和警告</span><span class="sxs-lookup"><span data-stu-id="bb1d4-123">Errors and Warnings</span></span>  
 <span data-ttu-id="bb1d4-124">当使用过时的类型和成员时，会产生下列错误消息。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-124">The obsolete types and members produce the following error messages when they are used.</span></span> <span data-ttu-id="bb1d4-125">请注意，<xref:System.Security.Policy.Evidence?displayProperty=nameWithType> 类型本身并未过时。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-125">Note that the <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> type itself is not obsolete.</span></span>  
  
 <span data-ttu-id="bb1d4-126">编译时警告：</span><span class="sxs-lookup"><span data-stu-id="bb1d4-126">Compile-time warning:</span></span>  
  
 `warning CS0618: '<API Name>' is obsolete: 'This method is obsolete and will be removed in a future release of the .NET Framework. Please use <suggested alternate API>. See <link> for more information.'`  
  
 <span data-ttu-id="bb1d4-127">运行时异常：</span><span class="sxs-lookup"><span data-stu-id="bb1d4-127">Run-time exception:</span></span>  
  
 <span data-ttu-id="bb1d4-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span><span class="sxs-lookup"><span data-stu-id="bb1d4-128"><xref:System.NotSupportedException>: `This method uses CAS policy, which has been obsoleted by the .NET Framework. In order to enable CAS policy for compatibility reasons, please use the <NetFx40_LegacySecurityPolicy> configuration switch. Please see <link> for more information.`</span></span>  
  
<a name="migration"></a>   
## <a name="migration-replacement-for-obsolete-calls"></a><span data-ttu-id="bb1d4-129">迁移：替换已过时的调用</span><span class="sxs-lookup"><span data-stu-id="bb1d4-129">Migration: Replacement for Obsolete Calls</span></span>  
  
### <a name="determining-an-assemblys-trust-level"></a><span data-ttu-id="bb1d4-130">确定程序集的信任级别</span><span class="sxs-lookup"><span data-stu-id="bb1d4-130">Determining an Assembly’s Trust Level</span></span>  
 <span data-ttu-id="bb1d4-131">CAS 策略通常用于确定程序集或应用程序域的权限授予集或信任级别。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-131">CAS policy is often used to determine an assembly’s or application domain’s permission grant set or trust level.</span></span> <span data-ttu-id="bb1d4-132">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] 公开以下无需解析安全策略的有用属性：</span><span class="sxs-lookup"><span data-stu-id="bb1d4-132">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes the following useful properties that do not need to resolve security policy:</span></span>  
  
-   <xref:System.Reflection.Assembly.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.Reflection.Assembly.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.PermissionSet%2A?displayProperty=nameWithType>  
  
-   <xref:System.AppDomain.IsFullyTrusted%2A?displayProperty=nameWithType>  
  
### <a name="application-domain-sandboxing"></a><span data-ttu-id="bb1d4-133">应用程序域沙盒</span><span class="sxs-lookup"><span data-stu-id="bb1d4-133">Application Domain Sandboxing</span></span>  
 <span data-ttu-id="bb1d4-134"><xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> 方法通常用于对应用程序域中的程序集进行沙盒处理。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-134">The <xref:System.AppDomain.SetAppDomainPolicy%2A?displayProperty=nameWithType> method is typically used for sandboxing the assemblies in an application domain.</span></span> <span data-ttu-id="bb1d4-135">[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]公开不需要使用的成员<xref:System.Security.Policy.PolicyLevel>为此目的。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-135">The [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] exposes members that do not have to use <xref:System.Security.Policy.PolicyLevel> for this purpose.</span></span> <span data-ttu-id="bb1d4-136">有关详细信息，请参阅[如何： 运行部分受信任的代码在沙盒中](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-136">For more information, see [How to: Run Partially Trusted Code in a Sandbox](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md).</span></span>  
  
### <a name="determining-a-safe-or-reasonable-permission-set-for-partially-trusted-code"></a><span data-ttu-id="bb1d4-137">确定部分受信任的代码的“安全”或“合理”权限集</span><span class="sxs-lookup"><span data-stu-id="bb1d4-137">Determining a Safe or Reasonable Permission Set for Partially Trusted Code</span></span>  
 <span data-ttu-id="bb1d4-138">主机通常需要确定适用于沙盒处理托管代码的权限。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-138">Hosts often need to determine the permissions that are appropriate for sandboxing hosted code.</span></span> <span data-ttu-id="bb1d4-139">之前[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]，CAS 策略提供一种解决办法这一点与<xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-139">Before the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], CAS policy provided a way to do this with the <xref:System.Security.SecurityManager.ResolvePolicy%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bb1d4-140">作为替代，[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]提供<xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType>方法，为提供的证据返回安全且标准的权限集。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-140">As a replacement, [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)] provides the <xref:System.Security.SecurityManager.GetStandardSandbox%2A?displayProperty=nameWithType> method, which returns a safe, standard permission set for the provided evidence.</span></span>  
  
### <a name="non-sandboxing-scenarios-overloads-for-assembly-loads"></a><span data-ttu-id="bb1d4-141">非沙盒处理方案：程序集加载的重载</span><span class="sxs-lookup"><span data-stu-id="bb1d4-141">Non-Sandboxing Scenarios: Overloads for Assembly Loads</span></span>  
 <span data-ttu-id="bb1d4-142">使用程序集加载重载的原因可能是为了使用不可通过其他方式使用的参数，而不是对程序集进行沙盒处理。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-142">The reason for using an assembly load overload might be to use parameters that are not otherwise available, instead of sandboxing the assembly.</span></span> <span data-ttu-id="bb1d4-143">从开始[!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)]，不需要的程序集加载重载<xref:System.Security.Policy.Evidence?displayProperty=nameWithType>对象作为参数，例如， <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>，启用此方案。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-143">Starting with the [!INCLUDE[net_v40_short](../../../includes/net-v40-short-md.md)], assembly load overloads that do not require a <xref:System.Security.Policy.Evidence?displayProperty=nameWithType> object as a parameter, for example, <xref:System.AppDomain.ExecuteAssembly%28System.String%2CSystem.String%5B%5D%2CSystem.Byte%5B%5D%2CSystem.Configuration.Assemblies.AssemblyHashAlgorithm%29?displayProperty=nameWithType>, enable this scenario.</span></span>  
  
 <span data-ttu-id="bb1d4-144">如果要对程序集进行沙盒处理，请使用 <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> 重载。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-144">If you want to sandbox an assembly, use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> overload.</span></span>  
  
<a name="compatibility"></a>   
## <a name="compatibility-using-the-cas-policy-legacy-option"></a><span data-ttu-id="bb1d4-145">兼容性：使用 CAS 策略旧版选项</span><span class="sxs-lookup"><span data-stu-id="bb1d4-145">Compatibility: Using the CAS Policy Legacy Option</span></span>  
 <span data-ttu-id="bb1d4-146">[< NetFx40_LegacySecurityPolicy > 配置元素](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md)可指定进程或库使用旧版 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-146">The [<NetFx40_LegacySecurityPolicy> configuration element](../../../docs/framework/configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) lets you specify that a process or library uses legacy CAS policy.</span></span> <span data-ttu-id="bb1d4-147">启用此元素时，策略和证据重载将与其在 Framework 以前版本中进行的操作相同。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-147">When you enable this element, the policy and evidence overloads will work as they did in previous versions of the framework.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb1d4-148">CAS 策略行为是在运行时版本的基础上指定的，因此修改一个运行时版本的 CAS 策略不会影响另一个版本的 CAS 策略。</span><span class="sxs-lookup"><span data-stu-id="bb1d4-148">CAS policy behavior is specified on a runtime version basis, so modifying CAS policy for one runtime version does not affect the CAS policy of another version.</span></span>  
  
```xml  
<configuration>  
   <runtime>  
      <NetFx40_LegacySecurityPolicy enabled="true"/>  
   </runtime>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb1d4-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb1d4-149">See Also</span></span>  
 [<span data-ttu-id="bb1d4-150">如何：运行沙盒中部分受信任的代码</span><span class="sxs-lookup"><span data-stu-id="bb1d4-150">How to: Run Partially Trusted Code in a Sandbox</span></span>](../../../docs/framework/misc/how-to-run-partially-trusted-code-in-a-sandbox.md)  
 [<span data-ttu-id="bb1d4-151">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="bb1d4-151">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
