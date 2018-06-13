---
title: 代码安全维护指南
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- managed wrapper to native code implementation
- secure coding
- reusable components
- library code that exposes protected resources
- code, security
- code security
- secure coding, options
- components [.NET Framework], security
- code security, options
- security-neutral code
- security [.NET Framework], coding guidelines
ms.assetid: 4f882d94-262b-4494-b0a6-ba9ba1f5f177
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8d61e76a657c7341ec7dfcede6d7dc9943d4659
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588156"
---
# <a name="secure-coding-guidelines"></a><span data-ttu-id="d2cab-102">代码安全维护指南</span><span class="sxs-lookup"><span data-stu-id="d2cab-102">Secure Coding Guidelines</span></span>
<span data-ttu-id="d2cab-103">基于证据的安全性和代码访问安全性提供非常强大的显式机制来实现安全。</span><span class="sxs-lookup"><span data-stu-id="d2cab-103">Evidence-based security and code access security provide very powerful, explicit mechanisms to implement security.</span></span> <span data-ttu-id="d2cab-104">大多数应用程序代码就可以使用由 .NET Framework 实现的基础结构。</span><span class="sxs-lookup"><span data-stu-id="d2cab-104">Most application code can simply use the infrastructure implemented by the .NET Framework.</span></span> <span data-ttu-id="d2cab-105">在某些情况下，需要额外的应用程序特定的安全性，或通过扩展安全系统或通过使用全新临时方法构建。</span><span class="sxs-lookup"><span data-stu-id="d2cab-105">In some cases, additional application-specific security is required, built either by extending the security system or by using new ad hoc methods.</span></span>  
  
 <span data-ttu-id="d2cab-106">在代码中使用 .NET Framework 强制实施的权限和其他强制，则应建立屏障，以防止恶意代码获取不希望其具有的信息或执行其他不需要的操作。</span><span class="sxs-lookup"><span data-stu-id="d2cab-106">Using the .NET Framework-enforced permissions and other enforcement in your code, you should erect barriers to prevent malicious code from obtaining information that you do not want it to have or performing other undesirable actions.</span></span> <span data-ttu-id="d2cab-107">此外，必须在使用受信任代码的所有预期方案中平衡安全性和可用性。</span><span class="sxs-lookup"><span data-stu-id="d2cab-107">Additionally, you must strike a balance between security and usability in all the expected scenarios using trusted code.</span></span>  
  
 <span data-ttu-id="d2cab-108">本概述介绍代码可以用于处理安全系统的不同方式。</span><span class="sxs-lookup"><span data-stu-id="d2cab-108">This overview describes the different ways code can be designed to work with the security system.</span></span>  
  
## <a name="securing-resource-access"></a><span data-ttu-id="d2cab-109">保护资源访问</span><span class="sxs-lookup"><span data-stu-id="d2cab-109">Securing Resource Access</span></span>  
 <span data-ttu-id="d2cab-110">设计和编写代码时，尤其是在使用或调用来源未知的代码时，需要保护和限制该代码对资源的访问。</span><span class="sxs-lookup"><span data-stu-id="d2cab-110">When designing and writing your code, you need to protect and limit the access that code has to resources, especially when using or invoking code of unknown origin.</span></span> <span data-ttu-id="d2cab-111">因此，请记住以下可确保代码安全的方法：</span><span class="sxs-lookup"><span data-stu-id="d2cab-111">So, keep in mind the following techniques to ensure your code is secure:</span></span>  
  
-   <span data-ttu-id="d2cab-112">不使用代码访问安全性 (CAS)。</span><span class="sxs-lookup"><span data-stu-id="d2cab-112">Do not use Code Access Security (CAS).</span></span>  
  
-   <span data-ttu-id="d2cab-113">不使用部分信任的代码。</span><span class="sxs-lookup"><span data-stu-id="d2cab-113">Do not use partial trusted code.</span></span>  
  
-   <span data-ttu-id="d2cab-114">不使用 .NET 远程处理。</span><span class="sxs-lookup"><span data-stu-id="d2cab-114">Do not use .NET Remoting.</span></span>  
  
-   <span data-ttu-id="d2cab-115">不使用分布式组件对象模型 (DCOM)。</span><span class="sxs-lookup"><span data-stu-id="d2cab-115">Do not use Distributed Component Object Model (DCOM).</span></span>  
  
-   <span data-ttu-id="d2cab-116">不使用二进制格式化程序。</span><span class="sxs-lookup"><span data-stu-id="d2cab-116">Do not use binary formatters.</span></span>  
  
 <span data-ttu-id="d2cab-117">未来不支持将代码访问安全性和安全透明代码用作部分信任代码的安全边界。</span><span class="sxs-lookup"><span data-stu-id="d2cab-117">Code Access Security and Security-Transparent Code will not be supported as a security boundary with partially trusted code.</span></span> <span data-ttu-id="d2cab-118">建议在未实施其他安全措施的情况下，不要加载和执行未知来源的代码。</span><span class="sxs-lookup"><span data-stu-id="d2cab-118">We advise against loading and executing code of unknown origins without putting alternative security measures in place.</span></span> <span data-ttu-id="d2cab-119">其他安全措施包括：</span><span class="sxs-lookup"><span data-stu-id="d2cab-119">The alternative security measures are:</span></span>  
  
-   <span data-ttu-id="d2cab-120">虚拟化</span><span class="sxs-lookup"><span data-stu-id="d2cab-120">Virtualization</span></span>  
  
-   <span data-ttu-id="d2cab-121">AppContainers</span><span class="sxs-lookup"><span data-stu-id="d2cab-121">AppContainers</span></span>  
  
-   <span data-ttu-id="d2cab-122">操作系统 (OS) 用户和权限</span><span class="sxs-lookup"><span data-stu-id="d2cab-122">Operating system (OS) users and permissions</span></span>  
  
-   <span data-ttu-id="d2cab-123">Hyper-V 容器</span><span class="sxs-lookup"><span data-stu-id="d2cab-123">Hyper-V containers</span></span>  
  
## <a name="security-neutral-code"></a><span data-ttu-id="d2cab-124">非特定于安全性的代码</span><span class="sxs-lookup"><span data-stu-id="d2cab-124">Security-Neutral Code</span></span>  
 <span data-ttu-id="d2cab-125">非特定于安全性的代码不对任何安全系统进行显示处理。</span><span class="sxs-lookup"><span data-stu-id="d2cab-125">Security-neutral code does nothing explicit with the security system.</span></span> <span data-ttu-id="d2cab-126">它通过所接收的任何权限来运行。</span><span class="sxs-lookup"><span data-stu-id="d2cab-126">It runs with whatever permissions it receives.</span></span> <span data-ttu-id="d2cab-127">虽然无法捕获与受保护操作（例如使用文件、网络等）相关联安全异常的应用程序可导致未经处理的异常，但非特定于安全性的代码还是利用 .NET Framework 安全技术。</span><span class="sxs-lookup"><span data-stu-id="d2cab-127">Although applications that fail to catch security exceptions associated with protected operations (such as using files, networking, and so on) can result in an unhandled exception, security-neutral code still takes advantage of the .NET Framework security technologies.</span></span>  
  
 <span data-ttu-id="d2cab-128">非特定于安全性的库具有你应了解的特殊性质。</span><span class="sxs-lookup"><span data-stu-id="d2cab-128">A security-neutral library has special characteristics that you should understand.</span></span> <span data-ttu-id="d2cab-129">假设你的库提供了使用文件或调用非托管代码的 API 元素；如果你的代码没有相应的权限，则不会如所述运行。</span><span class="sxs-lookup"><span data-stu-id="d2cab-129">Suppose your library provides API elements that use files or call unmanaged code; if your code does not have the corresponding permission, it will not run as described.</span></span> <span data-ttu-id="d2cab-130">但是，即使代码具有权限，调用它的任何应用程序代码必须具有相同的权限才能正常运行。</span><span class="sxs-lookup"><span data-stu-id="d2cab-130">However, even if the code has the permission, any application code that calls it must have the same permission in order to work.</span></span> <span data-ttu-id="d2cab-131">如果调用代码没有正确的权限，<xref:System.Security.SecurityException>将作为代码访问安全堆栈审核结果显示。</span><span class="sxs-lookup"><span data-stu-id="d2cab-131">If the calling code does not have the right permission, a <xref:System.Security.SecurityException> appears as a result of the code access security stack walk.</span></span>  
  
## <a name="application-code-that-is-not-a-reusable-component"></a><span data-ttu-id="d2cab-132">不是可重用组件的应用程序代码</span><span class="sxs-lookup"><span data-stu-id="d2cab-132">Application Code That Is Not a Reusable Component</span></span>  
 <span data-ttu-id="d2cab-133">如果代码是不会由其他代码调用的应用程序的一部分，则实现安全很简单，可能不需要特殊的编码。</span><span class="sxs-lookup"><span data-stu-id="d2cab-133">If your code is part of an application that will not be called by other code, security is simple and special coding might not be required.</span></span> <span data-ttu-id="d2cab-134">但请记住，恶意代码可以调用你的代码。</span><span class="sxs-lookup"><span data-stu-id="d2cab-134">However, remember that malicious code can call your code.</span></span> <span data-ttu-id="d2cab-135">代码访问安全性可能会阻止恶意代码访问资源，而此类代码仍然可以读取你的字段或可能包含敏感信息的属性的值。</span><span class="sxs-lookup"><span data-stu-id="d2cab-135">While code access security might stop malicious code from accessing resources, such code could still read values of your fields or properties that might contain sensitive information.</span></span>  
  
 <span data-ttu-id="d2cab-136">此外，如果你的代码接受来自 Internet 或其他不可靠来源的用户输入，则务必要小心恶意输入。</span><span class="sxs-lookup"><span data-stu-id="d2cab-136">Additionally, if your code accepts user input from the Internet or other unreliable sources, you must be careful about malicious input.</span></span>  
  
## <a name="managed-wrapper-to-native-code-implementation"></a><span data-ttu-id="d2cab-137">本机代码实现的托管包装</span><span class="sxs-lookup"><span data-stu-id="d2cab-137">Managed Wrapper to Native Code Implementation</span></span>  
 <span data-ttu-id="d2cab-138">通常在这种情况下，某些有用功能是在你想要提供给托管代码的本机代码中实现的。</span><span class="sxs-lookup"><span data-stu-id="d2cab-138">Typically in this scenario, some useful functionality is implemented in native code that you want to make available to managed code.</span></span> <span data-ttu-id="d2cab-139">托管包装器可通过使用平台调用或 COM 互操作轻松写入。</span><span class="sxs-lookup"><span data-stu-id="d2cab-139">Managed wrappers are easy to write using either platform invoke or COM interop.</span></span> <span data-ttu-id="d2cab-140">但如果你这样做，包装器的调用方必须具有非托管代码权限才能成功。</span><span class="sxs-lookup"><span data-stu-id="d2cab-140">However, if you do this, callers of your wrappers must have unmanaged code rights in order to succeed.</span></span> <span data-ttu-id="d2cab-141">在默认策略下，这意味着从 Intranet 或 Internet 下载的代码不适用于此包装器。</span><span class="sxs-lookup"><span data-stu-id="d2cab-141">Under default policy, this means that code downloaded from an intranet or the Internet will not work with the wrappers.</span></span>  
  
 <span data-ttu-id="d2cab-142">相较于为所有使用这些包装器的应用程序提供非托管代码权限而言，仅对包装器代码提供这些权限是更好的做法。</span><span class="sxs-lookup"><span data-stu-id="d2cab-142">Instead of giving all applications that use these wrappers unmanaged code rights, it is better to give these rights only to the wrapper code.</span></span> <span data-ttu-id="d2cab-143">如果基础功能没有公开任何资源，且实现同样也安全，则包装器只需断言其权限，这可使任何代码通过它进行调用。</span><span class="sxs-lookup"><span data-stu-id="d2cab-143">If the underlying functionality exposes no resources and the implementation is likewise safe, the wrapper only needs to assert its rights, which enables any code to call through it.</span></span> <span data-ttu-id="d2cab-144">当涉及资源时，安全编码应该与下一节中所述的库代码案例相同。</span><span class="sxs-lookup"><span data-stu-id="d2cab-144">When resources are involved, security coding should be the same as the library code case described in the next section.</span></span> <span data-ttu-id="d2cab-145">因为包装器可能对这些资源公开调用方，所以仔细验证本机代码的安全性是必要的，这是包装器的责任。</span><span class="sxs-lookup"><span data-stu-id="d2cab-145">Because the wrapper is potentially exposing callers to these resources, careful verification of the safety of the native code is necessary and is the wrapper's responsibility.</span></span>  
  
## <a name="library-code-that-exposes-protected-resources"></a><span data-ttu-id="d2cab-146">用于公开受保护资源的库代码</span><span class="sxs-lookup"><span data-stu-id="d2cab-146">Library Code That Exposes Protected Resources</span></span>  
 <span data-ttu-id="d2cab-147">这是最强大的，因而对安全编码具有潜在的危险性（如未正确执行）：你的库作为其他代码访问某些资源的接口（否则无法访问该资源），就像 .NET Framework 的类强制执行所使用资源的权限。</span><span class="sxs-lookup"><span data-stu-id="d2cab-147">This is the most powerful and hence potentially dangerous (if done incorrectly) approach for security coding: Your library serves as an interface for other code to access certain resources that are not otherwise available, just as the classes of the .NET Framework enforce permissions for the resources they use.</span></span> <span data-ttu-id="d2cab-148">只要公开资源，你的代码首先就必须要求相应资源的权限（也就是说，必须执行安全检查），然后通常断言其权限来执行实际的操作。</span><span class="sxs-lookup"><span data-stu-id="d2cab-148">Wherever you expose a resource, your code must first demand the permission appropriate to the resource (that is, it must perform a security check) and then typically assert its rights to perform the actual operation.</span></span>  
  
## <a name="related-topics"></a><span data-ttu-id="d2cab-149">相关主题</span><span class="sxs-lookup"><span data-stu-id="d2cab-149">Related Topics</span></span>  
  
|<span data-ttu-id="d2cab-150">标题</span><span class="sxs-lookup"><span data-stu-id="d2cab-150">Title</span></span>|<span data-ttu-id="d2cab-151">描述</span><span class="sxs-lookup"><span data-stu-id="d2cab-151">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d2cab-152">保护状态数据</span><span class="sxs-lookup"><span data-stu-id="d2cab-152">Securing State Data</span></span>](../../../docs/standard/security/securing-state-data.md)|<span data-ttu-id="d2cab-153">说明如何保护私有成员。</span><span class="sxs-lookup"><span data-stu-id="d2cab-153">Describes how to protect private members.</span></span>|  
|[<span data-ttu-id="d2cab-154">安全性和用户输入</span><span class="sxs-lookup"><span data-stu-id="d2cab-154">Security and User Input</span></span>](../../../docs/standard/security/security-and-user-input.md)|<span data-ttu-id="d2cab-155">说明用于接受用户输入的应用程序的安全问题。</span><span class="sxs-lookup"><span data-stu-id="d2cab-155">Describes security concerns for applications that accept user input.</span></span>|  
|[<span data-ttu-id="d2cab-156">安全性和争用条件</span><span class="sxs-lookup"><span data-stu-id="d2cab-156">Security and Race Conditions</span></span>](../../../docs/standard/security/security-and-race-conditions.md)|<span data-ttu-id="d2cab-157">说明如何避免代码中的争用条件。</span><span class="sxs-lookup"><span data-stu-id="d2cab-157">Describes how to avoid race conditions in your code.</span></span>|  
|[<span data-ttu-id="d2cab-158">安全性和进行中的代码生成</span><span class="sxs-lookup"><span data-stu-id="d2cab-158">Security and On-the-Fly Code Generation</span></span>](../../../docs/standard/security/security-and-on-the-fly-code-generation.md)|<span data-ttu-id="d2cab-159">说明用于生成动态代码的应用程序的安全问题。</span><span class="sxs-lookup"><span data-stu-id="d2cab-159">Describes security concerns for applications that generate dynamic code.</span></span>|  
|[<span data-ttu-id="d2cab-160">基于角色的安全性</span><span class="sxs-lookup"><span data-stu-id="d2cab-160">Role-Based Security</span></span>](../../../docs/standard/security/role-based-security.md)|<span data-ttu-id="d2cab-161">详细说明 .NET Framework 中基于角色的安全性，并提供有关在代码中使用的说明。</span><span class="sxs-lookup"><span data-stu-id="d2cab-161">Describes .NET Framework role-based security in detail and provides instructions for using it in your code.</span></span>|
