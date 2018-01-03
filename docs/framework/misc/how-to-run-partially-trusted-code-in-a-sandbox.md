---
title: "如何：运行沙盒中部分受信任的代码"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- partially trusted code
- sandboxing
- partial trust
- restricted security environment
- code security, sandboxing
ms.assetid: d1ad722b-5b49-4040-bff3-431b94bb8095
caps.latest.revision: "27"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: fc335bfef4993f6e730dca93cd645d886a9d13b4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-run-partially-trusted-code-in-a-sandbox"></a><span data-ttu-id="82d7d-102">如何：运行沙盒中部分受信任的代码</span><span class="sxs-lookup"><span data-stu-id="82d7d-102">How to: Run Partially Trusted Code in a Sandbox</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="82d7d-103">沙盒处理是在受限制的安全环境中运行代码的做法，从而限制授予代码的访问权限。</span><span class="sxs-lookup"><span data-stu-id="82d7d-103">Sandboxing is the practice of running code in a restricted security environment, which limits the access permissions granted to the code.</span></span> <span data-ttu-id="82d7d-104">例如，如果你有来自不完全信任的源的托管库，则不应将其作为完全受信任运行。</span><span class="sxs-lookup"><span data-stu-id="82d7d-104">For example, if you have a managed library from a source you do not completely trust, you should not run it as fully trusted.</span></span> <span data-ttu-id="82d7d-105">相反，应将代码放在将权限限制为预计需要的权限（例如 <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> 权限）的沙盒中。</span><span class="sxs-lookup"><span data-stu-id="82d7d-105">Instead, you should place the code in a sandbox that limits its permissions to those that you expect it to need (for example, <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission).</span></span>  
  
 <span data-ttu-id="82d7d-106">沙盒处理还可用于测试将在部分受信任环境中运行的分发的代码。</span><span class="sxs-lookup"><span data-stu-id="82d7d-106">You can also use sandboxing to test code you will be distributing that will run in partially trusted environments.</span></span>  
  
 <span data-ttu-id="82d7d-107"><xref:System.AppDomain> 是为托管应用程序提供沙盒的有效途径。</span><span class="sxs-lookup"><span data-stu-id="82d7d-107">An <xref:System.AppDomain> is an effective way of providing a sandbox for managed applications.</span></span> <span data-ttu-id="82d7d-108">用于运行部分受信任的代码的应用程序域具有定义受保护资源的权限，这些资源在于 <xref:System.AppDomain> 内运行时可用。</span><span class="sxs-lookup"><span data-stu-id="82d7d-108">Application domains that are used for running partially trusted code have permissions that define the protected resources that are available when running within that <xref:System.AppDomain>.</span></span> <span data-ttu-id="82d7d-109">在 <xref:System.AppDomain> 内运行的代码由与 <xref:System.AppDomain> 关联的权限约束并且仅能访问指定的资源。</span><span class="sxs-lookup"><span data-stu-id="82d7d-109">Code that runs inside the <xref:System.AppDomain> is bound by the permissions associated with the <xref:System.AppDomain> and is allowed to access only the specified resources.</span></span> <span data-ttu-id="82d7d-110"><xref:System.AppDomain> 还包括用于标识程序集（作为完全受信任的程序集加载）的 <xref:System.Security.Policy.StrongName> 数组。</span><span class="sxs-lookup"><span data-stu-id="82d7d-110">The <xref:System.AppDomain> also includes a <xref:System.Security.Policy.StrongName> array that is used to identify assemblies that are to be loaded as fully trusted.</span></span> <span data-ttu-id="82d7d-111">这使 <xref:System.AppDomain> 的创建者能启动新沙盒域，该域允许特定的帮助程序程序集为完全受信任的程序集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-111">This enables the creator of an <xref:System.AppDomain> to start a new sandboxed domain that allows specific helper assemblies to be fully trusted.</span></span> <span data-ttu-id="82d7d-112">将程序集加载为完全受信任的程序集的另一种方法是：将其放在全局程序集缓存中；但是，这会在该计算机上创建的所有应用程序域中将程序集加载为完全受信任的程序集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-112">Another option for loading assemblies as fully trusted is to place them in the global assembly cache; however, that will load assemblies as fully trusted in all application domains created on that computer.</span></span> <span data-ttu-id="82d7d-113">强名称列表支持提供更多限制性决定的每个 <xref:System.AppDomain> 的决策。</span><span class="sxs-lookup"><span data-stu-id="82d7d-113">The list of strong names supports a per-<xref:System.AppDomain> decision that provides more restrictive determination.</span></span>  
  
 <span data-ttu-id="82d7d-114">可以使用 <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> 方法重载为在沙盒中运行的应用程序指定权限集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-114">You can use the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29?displayProperty=nameWithType> method overload to specify the permission set for applications that run in a sandbox.</span></span> <span data-ttu-id="82d7d-115">此重载使你能够指定所需代码访问安全性的确切级别。</span><span class="sxs-lookup"><span data-stu-id="82d7d-115">This overload enables you to specify the exact level of code access security you want.</span></span> <span data-ttu-id="82d7d-116">使用此重载加载到 <xref:System.AppDomain> 中的程序集可以仅具有指定的授予集，也可以是完全受信任的程序集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-116">Assemblies that are loaded into an <xref:System.AppDomain> by using this overload can either have the specified grant set only, or can be fully trusted.</span></span> <span data-ttu-id="82d7d-117">如果程序集位于全局程序集缓存中或在 `fullTrustAssemblies`（<xref:System.Security.Policy.StrongName>）数组参数中列出，则该程序集被授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="82d7d-117">The assembly is granted full trust if it is in the global assembly cache or listed in the `fullTrustAssemblies` (the <xref:System.Security.Policy.StrongName>) array parameter.</span></span> <span data-ttu-id="82d7d-118">只应将已知完全受信任的程序集添加到 `fullTrustAssemblies` 列表中。</span><span class="sxs-lookup"><span data-stu-id="82d7d-118">Only assemblies known to be fully trusted should be added to the `fullTrustAssemblies` list.</span></span>  
  
 <span data-ttu-id="82d7d-119">重载具有以下签名：</span><span class="sxs-lookup"><span data-stu-id="82d7d-119">The overload has the following signature:</span></span>  
  
```  
AppDomain.CreateDomain( string friendlyName,  
                        Evidence securityInfo,  
                        AppDomainSetup info,  
                        PermissionSet grantSet,  
                        params StrongName[] fullTrustAssemblies);  
```  
  
 <span data-ttu-id="82d7d-120"><xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> 方法重载的参数指定 <xref:System.AppDomain> 的名称、<xref:System.AppDomain> 的证据、标识沙盒的应用程序基的 <xref:System.AppDomainSetup> 对象、要使用的权限集和完全受信任的程序集的强名称。</span><span class="sxs-lookup"><span data-stu-id="82d7d-120">The parameters for the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload specify the name of the <xref:System.AppDomain>, the evidence for the <xref:System.AppDomain>, the <xref:System.AppDomainSetup> object that identifies the application base for the sandbox, the permission set to use, and the strong names for fully trusted assemblies.</span></span>  
  
 <span data-ttu-id="82d7d-121">出于安全原因，在 `info` 参数中指定的应用程序基不应为宿主应用程序的应用程序基。</span><span class="sxs-lookup"><span data-stu-id="82d7d-121">For security reasons, the application base specified in the `info` parameter should not be the application base for the hosting application.</span></span>  
  
 <span data-ttu-id="82d7d-122">对于 `grantSet` 参数，可以指定已显式创建的权限集或由 <xref:System.Security.SecurityManager.GetStandardSandbox%2A> 方法创建的标准权限集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-122">For the `grantSet` parameter, you can specify either a permission set you have explicitly created, or a standard permission set created by the <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method.</span></span>  
  
 <span data-ttu-id="82d7d-123">与大多数 <xref:System.AppDomain> 加载不同，<xref:System.AppDomain> 的证据（由 `securityInfo` 参数提供）不用于确定部分受信任的程序集的授予集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-123">Unlike most <xref:System.AppDomain> loads, the evidence for the <xref:System.AppDomain> (which is provided by the `securityInfo` parameter) is not used to determine the grant set for the partially trusted assemblies.</span></span> <span data-ttu-id="82d7d-124">相反，它由 `grantSet` 参数单独指定。</span><span class="sxs-lookup"><span data-stu-id="82d7d-124">Instead, it is independently specified by the `grantSet` parameter.</span></span> <span data-ttu-id="82d7d-125">但证据可以用于其它目的，例如确定独立存储范围。</span><span class="sxs-lookup"><span data-stu-id="82d7d-125">However, the evidence can be used for other purposes such as determining the isolated storage scope.</span></span>  
  
### <a name="to-run-an-application-in-a-sandbox"></a><span data-ttu-id="82d7d-126">在沙盒中运行应用程序</span><span class="sxs-lookup"><span data-stu-id="82d7d-126">To run an application in a sandbox</span></span>  
  
1.  <span data-ttu-id="82d7d-127">创建要授予给不受信任的应用程序的权限集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-127">Create the permission set to be granted to the untrusted application.</span></span> <span data-ttu-id="82d7d-128">可以授予的最小权限是 <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> 权限。</span><span class="sxs-lookup"><span data-stu-id="82d7d-128">The minimum permission you can grant is <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span> <span data-ttu-id="82d7d-129">还可以授予其它你认为可能对不受信任的代码安全的权限；例如，<xref:System.Security.Permissions.IsolatedStorageFilePermission>。</span><span class="sxs-lookup"><span data-stu-id="82d7d-129">You can also grant additional permissions you think might be safe for untrusted code; for example, <xref:System.Security.Permissions.IsolatedStorageFilePermission>.</span></span> <span data-ttu-id="82d7d-130">下面的代码创建仅具有 <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> 权限的新权限集。</span><span class="sxs-lookup"><span data-stu-id="82d7d-130">The following code creates a new permission set with only <xref:System.Security.Permissions.SecurityPermissionFlag.Execution> permission.</span></span>  
  
    ```  
    PermissionSet permSet = new PermissionSet(PermissionState.None);  
    permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
    ```  
  
     <span data-ttu-id="82d7d-131">或者，可以使用现有的已命名权限集，如 Internet。</span><span class="sxs-lookup"><span data-stu-id="82d7d-131">Alternatively, you can use an existing named permission set, such as Internet.</span></span>  
  
    ```  
    Evidence ev = new Evidence();  
    ev.AddHostEvidence(new Zone(SecurityZone.Internet));  
    PermissionSet internetPS = SecurityManager.GetStandardSandbox(ev);  
    ```  
  
     <span data-ttu-id="82d7d-132"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> 方法返回 `Internet` 权限集或 `LocalIntranet` 权限集，具体取决于证据中的区域。</span><span class="sxs-lookup"><span data-stu-id="82d7d-132">The <xref:System.Security.SecurityManager.GetStandardSandbox%2A> method returns either an `Internet` permission set or a `LocalIntranet` permission set depending on the zone in the evidence.</span></span> <span data-ttu-id="82d7d-133"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> 还为一些作为引用传递的证据对象构造标识权限。</span><span class="sxs-lookup"><span data-stu-id="82d7d-133"><xref:System.Security.SecurityManager.GetStandardSandbox%2A> also constructs identity permissions for some of the evidence objects passed as references.</span></span>  
  
2.  <span data-ttu-id="82d7d-134">为包含调用不受信任的代码的宿主类（在此示例中，命名为 `Sandboxer`）的程序集签名。</span><span class="sxs-lookup"><span data-stu-id="82d7d-134">Sign the assembly that contains the hosting class (named `Sandboxer` in this example) that calls the untrusted code.</span></span> <span data-ttu-id="82d7d-135">将用于对程序集签名的 <xref:System.Security.Policy.StrongName> 添加到 <xref:System.AppDomain.CreateDomain%2A> 调用的 `fullTrustAssemblies` 参数的 <xref:System.Security.Policy.StrongName> 数组中。</span><span class="sxs-lookup"><span data-stu-id="82d7d-135">Add the <xref:System.Security.Policy.StrongName> used to sign the assembly to the <xref:System.Security.Policy.StrongName> array of the `fullTrustAssemblies` parameter of the <xref:System.AppDomain.CreateDomain%2A> call.</span></span> <span data-ttu-id="82d7d-136">宿主类必须作为完全受信任的类运行，以启用部分信任代码的执行或为部分信任应用程序提供服务。</span><span class="sxs-lookup"><span data-stu-id="82d7d-136">The hosting class must run as fully trusted to enable the execution of the partial-trust code or to offer services to the partial-trust application.</span></span> <span data-ttu-id="82d7d-137">这就是读取程序集的 <xref:System.Security.Policy.StrongName> 的方式：</span><span class="sxs-lookup"><span data-stu-id="82d7d-137">This is how you read the <xref:System.Security.Policy.StrongName> of an assembly:</span></span>  
  
    ```  
    StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
    ```  
  
     <span data-ttu-id="82d7d-138">不需要将 .NET framework 程序集（如 mscorlib 和 System.dll）添加到完全信任列表中，因为它们是作为完全受信任的程序集从全局程序集缓存中加载的。</span><span class="sxs-lookup"><span data-stu-id="82d7d-138">.NET Framework assemblies such as mscorlib and System.dll do not have to be added to the full-trust list because they are loaded as fully trusted from the global assembly cache.</span></span>  
  
3.  <span data-ttu-id="82d7d-139">初始化 <xref:System.AppDomain.CreateDomain%2A> 方法的 <xref:System.AppDomainSetup> 参数。</span><span class="sxs-lookup"><span data-stu-id="82d7d-139">Initialize the <xref:System.AppDomainSetup> parameter of the <xref:System.AppDomain.CreateDomain%2A> method.</span></span> <span data-ttu-id="82d7d-140">使用此参数，可以控制新的 <xref:System.AppDomain> 的许多设置。</span><span class="sxs-lookup"><span data-stu-id="82d7d-140">With this parameter, you can control many of the settings of the new <xref:System.AppDomain>.</span></span> <span data-ttu-id="82d7d-141"><xref:System.AppDomainSetup.ApplicationBase%2A> 属性是一个重要设置，并且应不同于宿主应用程序的 <xref:System.AppDomain> 的 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="82d7d-141">The <xref:System.AppDomainSetup.ApplicationBase%2A> property is an important setting, and should be different from the <xref:System.AppDomainSetup.ApplicationBase%2A> property for the <xref:System.AppDomain> of the hosting application.</span></span> <span data-ttu-id="82d7d-142">如果 <xref:System.AppDomainSetup.ApplicationBase%2A> 设置相同，则部分信任应用程序可以获取宿主应用程序以加载（作为完全受信任的应用程序）它定义的异常，从而攻击它。</span><span class="sxs-lookup"><span data-stu-id="82d7d-142">If the <xref:System.AppDomainSetup.ApplicationBase%2A> settings are the same, the partial-trust application can get the hosting application to load (as fully trusted) an exception it defines, thus exploiting it.</span></span> <span data-ttu-id="82d7d-143">这是为什么不建议使用 catch（异常）的另一个原因。</span><span class="sxs-lookup"><span data-stu-id="82d7d-143">This is another reason why a catch (exception) is not recommended.</span></span> <span data-ttu-id="82d7d-144">将主机的应用程序基设置为与沙盒应用程序的应用程序基不同，这可降低攻击风险。</span><span class="sxs-lookup"><span data-stu-id="82d7d-144">Setting the application base of the host differently from the application base of the sandboxed application mitigates the risk of exploits.</span></span>  
  
    ```  
    AppDomainSetup adSetup = new AppDomainSetup();  
    adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
    ```  
  
4.  <span data-ttu-id="82d7d-145">使用已指定的参数调用 <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> 方法重载来创建应用程序域。</span><span class="sxs-lookup"><span data-stu-id="82d7d-145">Call the <xref:System.AppDomain.CreateDomain%28System.String%2CSystem.Security.Policy.Evidence%2CSystem.AppDomainSetup%2CSystem.Security.PermissionSet%2CSystem.Security.Policy.StrongName%5B%5D%29> method overload to create the application domain using the parameters we have specified.</span></span>  
  
     <span data-ttu-id="82d7d-146">此方法的签名是：</span><span class="sxs-lookup"><span data-stu-id="82d7d-146">The signature for this method is:</span></span>  
  
    ```  
    public static AppDomain CreateDomain(string friendlyName,   
        Evidence securityInfo, AppDomainSetup info, PermissionSet grantSet,   
        params StrongName[] fullTrustAssemblies)  
    ```  
  
     <span data-ttu-id="82d7d-147">其他信息：</span><span class="sxs-lookup"><span data-stu-id="82d7d-147">Additional information:</span></span>  
  
    -   <span data-ttu-id="82d7d-148">这是唯一将 <xref:System.Security.PermissionSet> 作为参数的 <xref:System.AppDomain.CreateDomain%2A> 方法的重载，因而它是唯一允许以部分信任设置加载应用程序的重载。</span><span class="sxs-lookup"><span data-stu-id="82d7d-148">This is the only overload of the <xref:System.AppDomain.CreateDomain%2A> method that takes a <xref:System.Security.PermissionSet> as a parameter, and thus the only overload that lets you load an application in a partial-trust setting.</span></span>  
  
    -   <span data-ttu-id="82d7d-149">`evidence` 参数不用于计算权限集；它由 .NET Framework 的其它功能用于标识。</span><span class="sxs-lookup"><span data-stu-id="82d7d-149">The `evidence` parameter is not used to calculate a permission set; it is used for identification by other features of the .NET Framework.</span></span>  
  
    -   <span data-ttu-id="82d7d-150">此重载必须设置`info` 参数的 <xref:System.AppDomainSetup.ApplicationBase%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="82d7d-150">Setting the <xref:System.AppDomainSetup.ApplicationBase%2A> property of the `info` parameter is mandatory for this overload.</span></span>  
  
    -   <span data-ttu-id="82d7d-151">`fullTrustAssemblies` 参数具有 `params` 关键字，这意味着不需要创建 <xref:System.Security.Policy.StrongName> 数组。</span><span class="sxs-lookup"><span data-stu-id="82d7d-151">The `fullTrustAssemblies` parameter has the `params` keyword, which means that it is not necessary to create a <xref:System.Security.Policy.StrongName> array.</span></span> <span data-ttu-id="82d7d-152">允许将 0、1 或更多强名称作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="82d7d-152">Passing 0, 1, or more strong names as parameters is allowed.</span></span>  
  
    -   <span data-ttu-id="82d7d-153">要用于创建应用程序域的代码是：</span><span class="sxs-lookup"><span data-stu-id="82d7d-153">The code to create the application domain is:</span></span>  
  
    ```  
    AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
    ```  
  
5.  <span data-ttu-id="82d7d-154">将代码加载到已创建的沙盒 <xref:System.AppDomain> 中。</span><span class="sxs-lookup"><span data-stu-id="82d7d-154">Load the code into the sandboxing <xref:System.AppDomain> that you created.</span></span> <span data-ttu-id="82d7d-155">有两种方法可以做到这一点：</span><span class="sxs-lookup"><span data-stu-id="82d7d-155">This can be done in two ways:</span></span>  
  
    -   <span data-ttu-id="82d7d-156">调用程序集的 <xref:System.AppDomain.ExecuteAssembly%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="82d7d-156">Call the <xref:System.AppDomain.ExecuteAssembly%2A> method for the assembly.</span></span>  
  
    -   <span data-ttu-id="82d7d-157">使用 <xref:System.Activator.CreateInstanceFrom%2A> 方法来创建派生自新的 <xref:System.AppDomain> 中的 <xref:System.MarshalByRefObject> 的类的实例。</span><span class="sxs-lookup"><span data-stu-id="82d7d-157">Use the <xref:System.Activator.CreateInstanceFrom%2A> method to create an instance of a class derived from <xref:System.MarshalByRefObject> in the new <xref:System.AppDomain>.</span></span>  
  
     <span data-ttu-id="82d7d-158">第二种方法非常可取，因为这样可以更轻松地将参数传递给新的 <xref:System.AppDomain> 实例。</span><span class="sxs-lookup"><span data-stu-id="82d7d-158">The second method is preferable, because it makes it easier to pass parameters to the new <xref:System.AppDomain> instance.</span></span> <span data-ttu-id="82d7d-159"><xref:System.Activator.CreateInstanceFrom%2A> 方法提供两大重要功能：</span><span class="sxs-lookup"><span data-stu-id="82d7d-159">The <xref:System.Activator.CreateInstanceFrom%2A> method provides two important features:</span></span>  
  
    -   <span data-ttu-id="82d7d-160">可以使用指向不包含你的程序集的位置的基本代码。</span><span class="sxs-lookup"><span data-stu-id="82d7d-160">You can use a code base that points to a location that does not contain your assembly.</span></span>  
  
    -   <span data-ttu-id="82d7d-161">可以在完全信任 (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>) 的 <xref:System.Security.CodeAccessPermission.Assert%2A> 下进行创建，这样就可以创建关键类的一个实例。</span><span class="sxs-lookup"><span data-stu-id="82d7d-161">You can do the creation under an <xref:System.Security.CodeAccessPermission.Assert%2A> for full-trust (<xref:System.Security.Permissions.PermissionState.Unrestricted?displayProperty=nameWithType>), which enables you to create an instance of a critical class.</span></span> <span data-ttu-id="82d7d-162">（每当你的程序集没有透明度标记并作为完全受信任的程序集加载时就会发生这种情况。）因此，必须谨慎地使用此函数只创建你信任的代码，建议在新的应用程序域中只创建完全受信任的类的实例。</span><span class="sxs-lookup"><span data-stu-id="82d7d-162">(This happens whenever your assembly has no transparency markings and is loaded as fully trusted.) Therefore, you have to be careful to create only code that you trust with this function, and we recommend that you create only instances of fully trusted classes in the new application domain.</span></span>  
  
    ```  
    ObjectHandle handle = Activator.CreateInstanceFrom(  
    newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
           typeof(Sandboxer).FullName );  
    ```  
  
     <span data-ttu-id="82d7d-163">请注意，若要创建新域中的类的实例，该类必须扩展 <xref:System.MarshalByRefObject> 类</span><span class="sxs-lookup"><span data-stu-id="82d7d-163">Note that in order to create an instance of a class in a new domain, the class has to extend the <xref:System.MarshalByRefObject> class</span></span>  
  
    ```  
    class Sandboxer:MarshalByRefObject  
    ```  
  
6.  <span data-ttu-id="82d7d-164">将新的域实例解包到此域中的引用中。</span><span class="sxs-lookup"><span data-stu-id="82d7d-164">Unwrap the new domain instance into a reference in this domain.</span></span> <span data-ttu-id="82d7d-165">此引用用于执行不受信任的代码。</span><span class="sxs-lookup"><span data-stu-id="82d7d-165">This reference is used to execute the untrusted code.</span></span>  
  
    ```  
    Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
    ```  
  
7.  <span data-ttu-id="82d7d-166">调用你刚刚创建的 `Sandboxer` 类的实例中的 `ExecuteUntrustedCode` 方法。</span><span class="sxs-lookup"><span data-stu-id="82d7d-166">Call the `ExecuteUntrustedCode` method in the instance of the `Sandboxer` class you just created.</span></span>  
  
    ```  
    newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    ```  
  
     <span data-ttu-id="82d7d-167">此调用在具有受限权限的沙盒应用程序域中执行。</span><span class="sxs-lookup"><span data-stu-id="82d7d-167">This call is executed in the sandboxed application domain, which has restricted permissions.</span></span>  
  
    ```  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
        {  
            //Load the MethodInfo for a method in the new assembly. This might be a method you know, or   
            //you can use Assembly.EntryPoint to get to the entry point in an executable.  
            MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
            try  
            {  
                // Invoke the method.  
                target.Invoke(null, parameters);  
            }  
            catch (Exception ex)  
            {  
            //When information is obtained from a SecurityException extra information is provided if it is   
            //accessed in full-trust.  
                (new PermissionSet(PermissionState.Unrestricted)).Assert();  
                Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
    CodeAccessPermission.RevertAssert();  
                Console.ReadLine();  
            }  
        }  
    ```  
  
     <span data-ttu-id="82d7d-168"><xref:System.Reflection> 用于获取部分受信任的程序集中的方法的句柄。</span><span class="sxs-lookup"><span data-stu-id="82d7d-168"><xref:System.Reflection> is used to get a handle of a method in the partially trusted assembly.</span></span> <span data-ttu-id="82d7d-169">该句柄可以用于以安全的方式、使用最小权限来执行代码。</span><span class="sxs-lookup"><span data-stu-id="82d7d-169">The handle can be used to execute code in a safe way with minimum permissions.</span></span>  
  
     <span data-ttu-id="82d7d-170">在前面的代码中，请在打印 <xref:System.Security.SecurityException> 之前备注完全信任权限的 <xref:System.Security.PermissionSet.Assert%2A>。</span><span class="sxs-lookup"><span data-stu-id="82d7d-170">In the previous code, note the <xref:System.Security.PermissionSet.Assert%2A> for the full-trust permission before printing the <xref:System.Security.SecurityException>.</span></span>  
  
    ```  
    new PermissionSet(PermissionState.Unrestricted)).Assert()  
    ```  
  
     <span data-ttu-id="82d7d-171">完全信任断言用于从 <xref:System.Security.SecurityException> 中获取扩展信息。</span><span class="sxs-lookup"><span data-stu-id="82d7d-171">The full-trust assert is used to obtain extended information from the <xref:System.Security.SecurityException>.</span></span> <span data-ttu-id="82d7d-172">没有 <xref:System.Security.PermissionSet.Assert%2A>，则 <xref:System.Security.SecurityException> 的 <xref:System.Security.SecurityException.ToString%2A> 方法将发现堆栈上有部分受信任的代码，并将限制返回的信息。</span><span class="sxs-lookup"><span data-stu-id="82d7d-172">Without the <xref:System.Security.PermissionSet.Assert%2A>, the <xref:System.Security.SecurityException.ToString%2A> method of <xref:System.Security.SecurityException> will discover that there is partially trusted code on the stack and will restrict the information returned.</span></span> <span data-ttu-id="82d7d-173">如果部分信任代码可以读取该信息，可能会导致安全问题，但可以通过不授予 <xref:System.Security.Permissions.UIPermission> 来缓解此风险。</span><span class="sxs-lookup"><span data-stu-id="82d7d-173">This could cause security issues if the partial-trust code could read that information, but the risk is mitigated by not granting <xref:System.Security.Permissions.UIPermission>.</span></span> <span data-ttu-id="82d7d-174">完全信任断言应慎用，且仅在确定不允许部分信任代码提升为完全信任代码时使用。</span><span class="sxs-lookup"><span data-stu-id="82d7d-174">The full-trust assert should be used sparingly and only when you are sure that you are not allowing partial-trust code to elevate to full trust.</span></span> <span data-ttu-id="82d7d-175">一般来说，不要调用同一函数中不信任的代码，也不要在调用完全信任断言后调用代码。</span><span class="sxs-lookup"><span data-stu-id="82d7d-175">As a rule, do not call code you do not trust in the same function and after you called an assert for full trust.</span></span> <span data-ttu-id="82d7d-176">始终在完成使用断言后还原断言，这是个好做法。</span><span class="sxs-lookup"><span data-stu-id="82d7d-176">It is good practice to always revert the assert when you have finished using it.</span></span>  
  
## <a name="example"></a><span data-ttu-id="82d7d-177">示例</span><span class="sxs-lookup"><span data-stu-id="82d7d-177">Example</span></span>  
 <span data-ttu-id="82d7d-178">下面的示例实现前一部分中的过程。</span><span class="sxs-lookup"><span data-stu-id="82d7d-178">The following example implements the procedure in the previous section.</span></span> <span data-ttu-id="82d7d-179">在此示例中，Visual Studio 解决方案中一个名为 `Sandboxer` 的项目还包含一个名为 `UntrustedCode` 的项目（该项目实现类 `UntrustedClass`）。</span><span class="sxs-lookup"><span data-stu-id="82d7d-179">In the example, a project named `Sandboxer` in a Visual Studio solution also contains a project named `UntrustedCode`, which implements the class `UntrustedClass`.</span></span> <span data-ttu-id="82d7d-180">此方案假定你已下载库程序集，该程序集包含应该返回 `true` 或 `false` 的方法，以指示你提供的数字是否为斐波纳契数。</span><span class="sxs-lookup"><span data-stu-id="82d7d-180">This scenario assumes that you have downloaded a library assembly containing a method that is expected to return `true` or `false` to indicate whether the number you provided is a Fibonacci number.</span></span> <span data-ttu-id="82d7d-181">相反，该方法会尝试从你的计算机中读取文件。</span><span class="sxs-lookup"><span data-stu-id="82d7d-181">Instead, the method attempts to read a file from your computer.</span></span> <span data-ttu-id="82d7d-182">下面的示例演示不受信任的代码。</span><span class="sxs-lookup"><span data-stu-id="82d7d-182">The following example shows the untrusted code.</span></span>  
  
```  
using System;  
using System.IO;  
namespace UntrustedCode  
{  
    public class UntrustedClass  
    {  
        // Pretend to be a method checking if a number is a Fibonacci  
        // but which actually attempts to read a file.  
        public static bool IsFibonacci(int number)  
        {  
           File.ReadAllText("C:\\Temp\\file.txt");  
           return false;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="82d7d-183">下面的示例演示执行不受信任的代码的 `Sandboxer` 应用程序代码。</span><span class="sxs-lookup"><span data-stu-id="82d7d-183">The following example shows the `Sandboxer` application code that executes the untrusted code.</span></span>  
  
```  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.IO;  
using System.Security;  
using System.Security.Policy;  
using System.Security.Permissions;  
using System.Reflection;  
using System.Runtime.Remoting;  
  
//The Sandboxer class needs to derive from MarshalByRefObject so that we can create it in another   
// AppDomain and refer to it from the default AppDomain.  
class Sandboxer : MarshalByRefObject  
{  
    const string pathToUntrusted = @"..\..\..\UntrustedCode\bin\Debug";  
    const string untrustedAssembly = "UntrustedCode";  
    const string untrustedClass = "UntrustedCode.UntrustedClass";  
    const string entryPoint = "IsFibonacci";  
    private static Object[] parameters = { 45 };  
    static void Main()  
    {  
        //Setting the AppDomainSetup. It is very important to set the ApplicationBase to a folder   
        //other than the one in which the sandboxer resides.  
        AppDomainSetup adSetup = new AppDomainSetup();  
        adSetup.ApplicationBase = Path.GetFullPath(pathToUntrusted);  
  
        //Setting the permissions for the AppDomain. We give the permission to execute and to   
        //read/discover the location where the untrusted code is loaded.  
        PermissionSet permSet = new PermissionSet(PermissionState.None);  
        permSet.AddPermission(new SecurityPermission(SecurityPermissionFlag.Execution));  
  
        //We want the sandboxer assembly's strong name, so that we can add it to the full trust list.  
        StrongName fullTrustAssembly = typeof(Sandboxer).Assembly.Evidence.GetHostEvidence<StrongName>();  
  
        //Now we have everything we need to create the AppDomain, so let's create it.  
        AppDomain newDomain = AppDomain.CreateDomain("Sandbox", null, adSetup, permSet, fullTrustAssembly);  
  
        //Use CreateInstanceFrom to load an instance of the Sandboxer class into the  
        //new AppDomain.   
        ObjectHandle handle = Activator.CreateInstanceFrom(  
            newDomain, typeof(Sandboxer).Assembly.ManifestModule.FullyQualifiedName,  
            typeof(Sandboxer).FullName  
            );  
        //Unwrap the new domain instance into a reference in this domain and use it to execute the   
        //untrusted code.  
        Sandboxer newDomainInstance = (Sandboxer) handle.Unwrap();  
        newDomainInstance.ExecuteUntrustedCode(untrustedAssembly, untrustedClass, entryPoint, parameters);  
    }  
    public void ExecuteUntrustedCode(string assemblyName, string typeName, string entryPoint, Object[] parameters)  
    {  
        //Load the MethodInfo for a method in the new Assembly. This might be a method you know, or   
        //you can use Assembly.EntryPoint to get to the main function in an executable.  
        MethodInfo target = Assembly.Load(assemblyName).GetType(typeName).GetMethod(entryPoint);  
        try  
        {  
            //Now invoke the method.  
            bool retVal = (bool)target.Invoke(null, parameters);  
        }  
        catch (Exception ex)  
        {  
            // When we print informations from a SecurityException extra information can be printed if we are   
            //calling it with a full-trust stack.  
            (new PermissionSet(PermissionState.Unrestricted)).Assert();  
            Console.WriteLine("SecurityException caught:\n{0}", ex.ToString());  
            CodeAccessPermission.RevertAssert();  
            Console.ReadLine();  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="82d7d-184">请参阅</span><span class="sxs-lookup"><span data-stu-id="82d7d-184">See Also</span></span>  
 [<span data-ttu-id="82d7d-185">安全编码准则</span><span class="sxs-lookup"><span data-stu-id="82d7d-185">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
