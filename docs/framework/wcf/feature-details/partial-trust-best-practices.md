---
title: "部分信任最佳实践"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d052bc0-5b98-4c50-8bb5-270cc8a8b145
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 817f7aeeb7adece1c375bb8b0cc455a17fb54185
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="partial-trust-best-practices"></a><span data-ttu-id="3017b-102">部分信任最佳实践</span><span class="sxs-lookup"><span data-stu-id="3017b-102">Partial Trust Best Practices</span></span>
<span data-ttu-id="3017b-103">本主题描述在部分信任环境中运行 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 时的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="3017b-103">This topic describes best practices when running [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a partial trust environment.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="3017b-104">序列化</span><span class="sxs-lookup"><span data-stu-id="3017b-104">Serialization</span></span>  
 <span data-ttu-id="3017b-105">当在部分受信任的应用程序中使用 <xref:System.Runtime.Serialization.DataContractSerializer> 时，请应用以下做法。</span><span class="sxs-lookup"><span data-stu-id="3017b-105">Apply the following practices when using the <xref:System.Runtime.Serialization.DataContractSerializer> in a partially-trusted application.</span></span>  
  
-   <span data-ttu-id="3017b-106">必须使用 `[DataContract]` 属性显式标记所有可序列化类型。</span><span class="sxs-lookup"><span data-stu-id="3017b-106">All serializable types must be explicitly marked with the `[DataContract]` attribute.</span></span> <span data-ttu-id="3017b-107">在部分信任环境中不支持以下技术：</span><span class="sxs-lookup"><span data-stu-id="3017b-107">The following techniques are not supported in a partial trust environment:</span></span>  
  
-   <span data-ttu-id="3017b-108">使用 <xref:System.SerializableAttribute> 标记要序列化的类。</span><span class="sxs-lookup"><span data-stu-id="3017b-108">Marking classes to be serialized with the <xref:System.SerializableAttribute>.</span></span>  
  
-   <span data-ttu-id="3017b-109">实现 <xref:System.Runtime.Serialization.ISerializable> 接口以允许类控制其序列化过程。</span><span class="sxs-lookup"><span data-stu-id="3017b-109">Implementing the <xref:System.Runtime.Serialization.ISerializable> interface to allow a class to control its serialization process.</span></span>  
  
### <a name="using-datacontractserializer"></a><span data-ttu-id="3017b-110">使用 DataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3017b-110">Using DataContractSerializer</span></span>  
  
-   <span data-ttu-id="3017b-111">使用 `[DataContract]` 属性标记的所有类型都必须是公共的。</span><span class="sxs-lookup"><span data-stu-id="3017b-111">All types marked with the `[DataContract]` attribute must be public.</span></span> <span data-ttu-id="3017b-112">在部分信任环境中无法序列化非公共类型。</span><span class="sxs-lookup"><span data-stu-id="3017b-112">Non-public types cannot be serialized in a partial trust environment.</span></span>  
  
-   <span data-ttu-id="3017b-113">可序列化 `[DataContract]` 类型中的所有 `[DataContract]` 成员都必须是公共的。</span><span class="sxs-lookup"><span data-stu-id="3017b-113">All `[DataContract]` members in a serializable `[DataContract]` type must be public.</span></span> <span data-ttu-id="3017b-114">在部分信任环境中无法序列化具有非公共 `[DataMember]` 的类型。</span><span class="sxs-lookup"><span data-stu-id="3017b-114">A type with a non-public `[DataMember]` cannot be serialized in a partial trust environment.</span></span>  
  
-   <span data-ttu-id="3017b-115">必须将处理序列化事件的方法（如 `OnSerializing`、`OnSerialized`、`OnDeserializing` 和 `OnDeserialized`）声明为公共的。</span><span class="sxs-lookup"><span data-stu-id="3017b-115">Methods that handle serialization events (such as `OnSerializing`, `OnSerialized`, `OnDeserializing`, and `OnDeserialized`) must be declared as public.</span></span> <span data-ttu-id="3017b-116">但是，同时支持 <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> 的显式实现和隐式实现。</span><span class="sxs-lookup"><span data-stu-id="3017b-116">However, both explicit and implicit implementations of <xref:System.Runtime.Serialization.IDeserializationCallback.OnDeserialization%28System.Object%29> are supported.</span></span>  
  
-   <span data-ttu-id="3017b-117">在程序集中实现的、使用 `[DataContract]` 标记的 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 类型不得在类型构造函数中执行与安全相关的操作，因为在反序列化期间 <xref:System.Runtime.Serialization.DataContractSerializer> 不调用新实例化的对象的构造函数。</span><span class="sxs-lookup"><span data-stu-id="3017b-117">`[DataContract]` types implemented in assemblies marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> must not perform security-related actions in the type constructor, as the <xref:System.Runtime.Serialization.DataContractSerializer> does not call the constructor of the newly-instantiated object during deserialization.</span></span> <span data-ttu-id="3017b-118">具体说来，对于 `[DataContract]` 类型，必须避免使用以下常见安全技术：</span><span class="sxs-lookup"><span data-stu-id="3017b-118">Specifically, the following common security techniques must be avoided for `[DataContract]` types:</span></span>  
  
-   <span data-ttu-id="3017b-119">尝试通过使类型的构造函数变为内部或私有来限制部分信任访问。</span><span class="sxs-lookup"><span data-stu-id="3017b-119">Attempting to restrict partial trust access by making the type's constructor internal or private.</span></span>  
  
-   <span data-ttu-id="3017b-120">通过将 `[LinkDemand]` 添加到类型的构造函数来限制对该类型的访问。</span><span class="sxs-lookup"><span data-stu-id="3017b-120">Restricting access to the type by adding a `[LinkDemand]` to the type's constructor.</span></span>  
  
-   <span data-ttu-id="3017b-121">假定由于已成功实例化对象，构造函数强制执行的任何验证检查已成功通过。</span><span class="sxs-lookup"><span data-stu-id="3017b-121">Assuming that because the object has been successfully instantiated, any validation checks enforced by the constructor have passed successfully.</span></span>  
  
### <a name="using-ixmlserializable"></a><span data-ttu-id="3017b-122">使用 IXmlSerializable</span><span class="sxs-lookup"><span data-stu-id="3017b-122">Using IXmlSerializable</span></span>  
 <span data-ttu-id="3017b-123">以下最佳实践适用于实现 <xref:System.Xml.Serialization.IXmlSerializable> 且使用 <xref:System.Runtime.Serialization.DataContractSerializer> 进行序列化的类型：</span><span class="sxs-lookup"><span data-stu-id="3017b-123">The following best practices apply for types that implement <xref:System.Xml.Serialization.IXmlSerializable> and are serialized using the <xref:System.Runtime.Serialization.DataContractSerializer>:</span></span>  
  
-   <span data-ttu-id="3017b-124"><xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> 静态方法实现必须为 `public`。</span><span class="sxs-lookup"><span data-stu-id="3017b-124">The <xref:System.Xml.Serialization.IXmlSerializable.GetSchema%2A> static method implementations must be `public`.</span></span>  
  
-   <span data-ttu-id="3017b-125">实现 <xref:System.Xml.Serialization.IXmlSerializable> 接口的实例方法必须为 `public`。</span><span class="sxs-lookup"><span data-stu-id="3017b-125">The instance methods that implement the <xref:System.Xml.Serialization.IXmlSerializable> interface must be `public`.</span></span>  
  
## <a name="using-wcf-from-fully-trusted-platform-code-that-allows-calls-from-partially-trusted-callers"></a><span data-ttu-id="3017b-126">从允许来自部分受信任的调用方的调用的完全受信任平台代码使用 WCF</span><span class="sxs-lookup"><span data-stu-id="3017b-126">Using WCF from Fully-Trusted Platform Code that Allows Calls from Partially Trusted Callers</span></span>  
 <span data-ttu-id="3017b-127">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 部分信任安全性模型假定 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 公共方法或属性的任何调用方在承载应用程序的代码访问安全性 (CAS) 上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="3017b-127">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] partial trust security model assumes that any caller of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] public method or property is running in the code access security (CAS) context of the hosting application.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="3017b-128"> 还假定对于每个 <xref:System.AppDomain> 只存在一个应用程序安全性上下文，并由受信任的主机（例如，通过调用 <xref:System.AppDomain> 或由 ASP.NET 应用程序管理器）在 <xref:System.AppDomain.CreateDomain%2A> 创建时建立此上下文。</span><span class="sxs-lookup"><span data-stu-id="3017b-128"> also assumes that only one application security context exists for each <xref:System.AppDomain>, and that this context is established at <xref:System.AppDomain> creation time by a trusted host (for example, by a call to <xref:System.AppDomain.CreateDomain%2A> or by the ASP.NET Application Manager).</span></span>  
  
 <span data-ttu-id="3017b-129">此安全模型适用于无法断言其他 CAS 权限的用户编写应用程序，如在 Medium Trust ASP.NET 应用程序中运行的用户代码。</span><span class="sxs-lookup"><span data-stu-id="3017b-129">This security model applies to user-written applications that cannot assert additional CAS permissions, such as user code running in a Medium Trust ASP.NET application.</span></span> <span data-ttu-id="3017b-130">但是，在代表部分受信任的应用程序调用到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中时，必须当心完全受信任的平台代码（例如，在全局程序集缓存中安装并接受来自部分受信任代码的调用的第三方程序集），以免引入应用程序级安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="3017b-130">However, fully-trusted platform code (for example, a third-party assembly that is installed in the global assembly cache and accepts calls from partially-trusted code) must take explicit care when calling into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] on behalf of a partially-trusted application to avoid introducing application-level security vulnerabilities.</span></span>  
  
 <span data-ttu-id="3017b-131">在代表部分受信任的代码调用 <xref:System.Security.PermissionSet.Assert%2A> API 之前，完全信任代码应该避免更改当前线程的 CAS 权限集（通过调用 <xref:System.Security.PermissionSet.PermitOnly%2A>、<xref:System.Security.PermissionSet.Deny%2A> 或 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 更改）。</span><span class="sxs-lookup"><span data-stu-id="3017b-131">Full-trust code should avoid altering the CAS permission set of the current thread (by calling <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, or <xref:System.Security.PermissionSet.Deny%2A>) prior to calling [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] APIs on behalf of partially-trusted code.</span></span> <span data-ttu-id="3017b-132">断言、拒绝或通过其他方式创建特定于线程且独立于应用程序级安全上下文的权限上下文可能会导致意外行为。</span><span class="sxs-lookup"><span data-stu-id="3017b-132">Asserting, denying, or otherwise creating a thread-specific permission context that is independent of the application-level security context can result in unexpected behavior.</span></span> <span data-ttu-id="3017b-133">根据应用程序，此行为可能会导致应用程序级安全漏洞。</span><span class="sxs-lookup"><span data-stu-id="3017b-133">Depending on the application, this behavior may result in application-level security vulnerabilities.</span></span>  
  
 <span data-ttu-id="3017b-134">必须准备好使用线程特定的权限上下文调用到 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中的代码，才能处理可能出现的以下情况：</span><span class="sxs-lookup"><span data-stu-id="3017b-134">Code that calls into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] using a thread-specific permission context must be prepared to handle the following situations that may arise:</span></span>  
  
-   <span data-ttu-id="3017b-135">在操作期间可能未维护线程特定的安全上下文，这导致潜在的安全异常。</span><span class="sxs-lookup"><span data-stu-id="3017b-135">The thread-specific security context may not be maintained for the duration of the operation, which results in potential security exceptions.</span></span>  
  
-   <span data-ttu-id="3017b-136">内部 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 代码以及用户提供的任何回调均可能在与最初启动调用所在的安全上下文不同的安全上下文中运行。</span><span class="sxs-lookup"><span data-stu-id="3017b-136">Internal [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] code as well as any user-provided callbacks may run in a different security context than the one under which the call was originally initiated.</span></span> <span data-ttu-id="3017b-137">这些上下文包括：</span><span class="sxs-lookup"><span data-stu-id="3017b-137">These contexts include:</span></span>  
  
    -   <span data-ttu-id="3017b-138">应用程序权限上下文。</span><span class="sxs-lookup"><span data-stu-id="3017b-138">The application permission context.</span></span>  
  
    -   <span data-ttu-id="3017b-139">其他用户线程以前创建的任何线程特定的权限上下文，用于在当前正在运行的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的生存期内调入 <xref:System.AppDomain>。</span><span class="sxs-lookup"><span data-stu-id="3017b-139">Any thread-specific permission context previously created by other user threads used to call into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] during the lifetime of the currently running <xref:System.AppDomain>.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="3017b-140"> 可保证部分受信任的代码无法获取完全信任权限，除非此类权限在调入 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 公共 API 中之前已由完全受信任的组件断言。</span><span class="sxs-lookup"><span data-stu-id="3017b-140"> guarantees that partially-trusted code cannot obtain full-trust permissions unless such permissions are asserted by a fully-trusted component prior to calling into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] public APIs.</span></span> <span data-ttu-id="3017b-141">但是，它不保证断言完全信任的效果隔离到特定的线程、操作或用户操作。</span><span class="sxs-lookup"><span data-stu-id="3017b-141">However, it does not guarantee that the effects of asserting full trust is isolated to a particular thread, operation, or user action.</span></span>  
  
 <span data-ttu-id="3017b-142">作为最佳实践，避免通过调用 <xref:System.Security.PermissionSet.Assert%2A>、<xref:System.Security.PermissionSet.PermitOnly%2A> 或 <xref:System.Security.PermissionSet.Deny%2A> 创建线程特定的权限上下文。</span><span class="sxs-lookup"><span data-stu-id="3017b-142">As a best practice, avoid creating thread-specific permission context by calling <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.PermitOnly%2A>, or <xref:System.Security.PermissionSet.Deny%2A>.</span></span> <span data-ttu-id="3017b-143">而是对应用程序本身授予或拒绝特权，以便不需要 <xref:System.Security.PermissionSet.Assert%2A>、<xref:System.Security.PermissionSet.Deny%2A> 或 <xref:System.Security.PermissionSet.PermitOnly%2A>。</span><span class="sxs-lookup"><span data-stu-id="3017b-143">Instead, grant or deny the privilege to the application itself, so that no <xref:System.Security.PermissionSet.Assert%2A>, <xref:System.Security.PermissionSet.Deny%2A>, or <xref:System.Security.PermissionSet.PermitOnly%2A> is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3017b-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="3017b-144">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 <xref:System.Xml.Serialization.IXmlSerializable>
