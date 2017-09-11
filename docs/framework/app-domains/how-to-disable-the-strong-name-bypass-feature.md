---
title: "如何：禁用强名称跳过功能"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strong-name bypass feature
- strong-named assemblies, loading into trusted application domains
ms.assetid: 234e088c-3b11-495a-8817-e0962be79d82
caps.latest.revision: 30
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 0af565c6d27be6a5a22bfb0fd1f90e4e46deec33
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-disable-the-strong-name-bypass-feature"></a><span data-ttu-id="c9bed-102">如何：禁用强名称跳过功能</span><span class="sxs-lookup"><span data-stu-id="c9bed-102">How to: Disable the Strong-Name Bypass Feature</span></span>
<span data-ttu-id="c9bed-103">从 .NET Framework 3.5 版 Service Pack 1 (SP1) 开始，当程序集加载到完全信任的 <xref:System.AppDomain> 对象（如 `MyComputer` 区域的默认 <xref:System.AppDomain>）时，不会验证强名称签名。</span><span class="sxs-lookup"><span data-stu-id="c9bed-103">Starting with the .NET Framework version 3.5 Service Pack 1 (SP1), strong-name signatures are not validated when an assembly is loaded into a full-trust <xref:System.AppDomain> object, such as the default <xref:System.AppDomain> for the `MyComputer` zone.</span></span> <span data-ttu-id="c9bed-104">这被称之为强名称跳过功能。</span><span class="sxs-lookup"><span data-stu-id="c9bed-104">This is referred to as the strong-name bypass feature.</span></span> <span data-ttu-id="c9bed-105">在完全信任的环境中，对于已签名的完全信任的程序集，无需考虑其签名，对 <xref:System.Security.Permissions.StrongNameIdentityPermission> 的要求总是成功。</span><span class="sxs-lookup"><span data-stu-id="c9bed-105">In a full-trust environment, demands for <xref:System.Security.Permissions.StrongNameIdentityPermission> always succeed for signed, full-trust assemblies regardless of their signature.</span></span> <span data-ttu-id="c9bed-106">唯一的限制是该程序集必须完全受信任，因为其区域是完全受信任的。</span><span class="sxs-lookup"><span data-stu-id="c9bed-106">The only restriction is that the assembly must be fully trusted because its zone is fully trusted.</span></span> <span data-ttu-id="c9bed-107">因为在这些条件下，强名称不是决定性因素，所以没有理由验证强名称。</span><span class="sxs-lookup"><span data-stu-id="c9bed-107">Because the strong name is not a determining factor under these conditions, there is no reason for it to be validated.</span></span> <span data-ttu-id="c9bed-108">跳过验证强名称签名可显著提高性能。</span><span class="sxs-lookup"><span data-stu-id="c9bed-108">Bypassing the validation of strong-name signatures provides significant performance improvements.</span></span>  
  
 <span data-ttu-id="c9bed-109">该跳过功能适用于未被延迟签名的任何完全信任程序集，以及从其 <xref:System.AppDomain> 属性指定的目录加载到任何完全信任的 <xref:System.AppDomainSetup.ApplicationBase%2A> 中的完全信任程序集。</span><span class="sxs-lookup"><span data-stu-id="c9bed-109">The bypass feature applies to any full-trust assembly that is not delay-signed and that is loaded into any full-trust <xref:System.AppDomain> from the directory specified by its <xref:System.AppDomainSetup.ApplicationBase%2A> property.</span></span>  
  
 <span data-ttu-id="c9bed-110">可通过设置注册表项值来替代计算机中所有应用程序的跳过功能。</span><span class="sxs-lookup"><span data-stu-id="c9bed-110">You can override the bypass feature for all applications on a computer by setting a registry key value.</span></span> <span data-ttu-id="c9bed-111">可使用应用程序配置文件来替代单个应用程序的设置。</span><span class="sxs-lookup"><span data-stu-id="c9bed-111">You can override the setting for a single application by using an application configuration file.</span></span> <span data-ttu-id="c9bed-112">如果注册表项禁用了单个应用程序的跳过功能，则无法恢复该功能。</span><span class="sxs-lookup"><span data-stu-id="c9bed-112">You cannot reinstate the bypass feature for a single application if it has been disabled by the registry key.</span></span>  
  
 <span data-ttu-id="c9bed-113">替代跳过功能后，将只验证强名称的正确性，而不检查其 <xref:System.Security.Permissions.StrongNameIdentityPermission>。</span><span class="sxs-lookup"><span data-stu-id="c9bed-113">When you override the bypass feature, the strong name is validated only for correctness; it is not checked for a <xref:System.Security.Permissions.StrongNameIdentityPermission>.</span></span> <span data-ttu-id="c9bed-114">如果要确认某个特定的强名称，必须单独执行该检查。</span><span class="sxs-lookup"><span data-stu-id="c9bed-114">If you want to confirm a specific strong name, you have to perform that check separately.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="c9bed-115">如下面的过程所述，是否能强制执行强名称验证取决于注册表项。</span><span class="sxs-lookup"><span data-stu-id="c9bed-115">The ability to force strong-name validation depends on a registry key, as described in the following procedure.</span></span> <span data-ttu-id="c9bed-116">如果运行应用程序时使用的帐户没有访问该注册表项的访问控制列表 (ACL) 权限，则该设置无效。</span><span class="sxs-lookup"><span data-stu-id="c9bed-116">If an application is running under an account that does not have access control list (ACL) permission to access that registry key, the setting is ineffective.</span></span> <span data-ttu-id="c9bed-117">必须确保配置了此注册表项的 ACL 权限，使所有程序集均可读取此项。</span><span class="sxs-lookup"><span data-stu-id="c9bed-117">You must ensure that ACL rights are configured for this key so that it can be read for all assemblies.</span></span>  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-all-applications"></a><span data-ttu-id="c9bed-118">对所有应用程序禁用强名称跳过功能</span><span class="sxs-lookup"><span data-stu-id="c9bed-118">To disable the strong-name bypass feature for all applications</span></span>  
  
-   <span data-ttu-id="c9bed-119">在 32 位计算机上的系统注册表中，在 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework 项下创建名为 `AllowStrongNameBypass`，值为 0 的 DWORD 项。</span><span class="sxs-lookup"><span data-stu-id="c9bed-119">On 32-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework key.</span></span>  
  
-   <span data-ttu-id="c9bed-120">在 64 位计算机上的系统注册表中，在 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework 和HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework 项下创建名为 `AllowStrongNameBypass`，值为 0 的 DWORD 项。</span><span class="sxs-lookup"><span data-stu-id="c9bed-120">On 64-bit computers, in the system registry, create a DWORD entry with a value of 0 named `AllowStrongNameBypass` under the HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework and HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\\.NETFramework keys.</span></span>  
  
### <a name="to-disable-the-strong-name-bypass-feature-for-a-single-application"></a><span data-ttu-id="c9bed-121">对单个应用程序禁用强名称跳过功能</span><span class="sxs-lookup"><span data-stu-id="c9bed-121">To disable the strong-name bypass feature for a single application</span></span>  
  
1.  <span data-ttu-id="c9bed-122">打开或创建应用程序配置文件。</span><span class="sxs-lookup"><span data-stu-id="c9bed-122">Open or create the application configuration file.</span></span>  
  
     <span data-ttu-id="c9bed-123">有关此文件的详细信息，请参阅[配置应用](../../../docs/framework/configure-apps/index.md)中的“应用程序配置文件”一节。</span><span class="sxs-lookup"><span data-stu-id="c9bed-123">For more information about this file, see the Application Configuration Files section in [Configuring Apps](../../../docs/framework/configure-apps/index.md).</span></span>  
  
2.  <span data-ttu-id="c9bed-124">添加以下项：</span><span class="sxs-lookup"><span data-stu-id="c9bed-124">Add the following entry:</span></span>  
  
    ```xml  
    <configuration>  
      <runtime>  
        <bypassTrustedAppStrongNames enabled="false" />  
      </runtime>  
    </configuration>  
    ```  
  
 <span data-ttu-id="c9bed-125">通过删除配置文件设置或将属性设置为“true”，可以还原应用程序的跳过功能。</span><span class="sxs-lookup"><span data-stu-id="c9bed-125">You can restore the bypass feature for the application by removing the configuration file setting or by setting the attribute to "true".</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c9bed-126">只有对计算机启用了跳过功能，才能打开和关闭针对应用程序的强名称验证。</span><span class="sxs-lookup"><span data-stu-id="c9bed-126">You can turn strong-name validation on and off for an application only if the bypass feature is enabled for the computer.</span></span> <span data-ttu-id="c9bed-127">如果对计算机关闭了跳过功能，将对所有应用程序验证强名称，并且不能对单个应用程序跳过验证。</span><span class="sxs-lookup"><span data-stu-id="c9bed-127">If the bypass feature has been turned off for the computer, strong names are validated for all applications and you cannot bypass validation for a single application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9bed-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c9bed-128">See Also</span></span>  
 <span data-ttu-id="c9bed-129">[Sn.exe（强名称工具）](../../../docs/framework/tools/sn-exe-strong-name-tool.md) </span><span class="sxs-lookup"><span data-stu-id="c9bed-129">[Sn.exe (Strong Name Tool)](../../../docs/framework/tools/sn-exe-strong-name-tool.md) </span></span>  
 <span data-ttu-id="c9bed-130">[\<bypassTrustedAppStrongNames> Element](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md) </span><span class="sxs-lookup"><span data-stu-id="c9bed-130">[\<bypassTrustedAppStrongNames> Element](../../../docs/framework/configure-apps/file-schema/runtime/bypasstrustedappstrongnames-element.md) </span></span>  
 [<span data-ttu-id="c9bed-131">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="c9bed-131">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)

