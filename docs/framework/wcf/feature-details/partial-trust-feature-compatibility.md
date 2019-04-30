---
title: 部分信任功能兼容性
ms.date: 03/30/2017
ms.assetid: a36a540b-1606-4e63-88e0-b7c59e0e6ab7
ms.openlocfilehash: b0d9b7bd8bd5f33ca344ea5674d08507ced209f5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039060"
---
# <a name="partial-trust-feature-compatibility"></a><span data-ttu-id="3c2b3-102">部分信任功能兼容性</span><span class="sxs-lookup"><span data-stu-id="3c2b3-102">Partial Trust Feature Compatibility</span></span>
<span data-ttu-id="3c2b3-103">在部分受信任的环境中运行时，Windows Communication Foundation (WCF) 支持有限的功能子集。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-103">Windows Communication Foundation (WCF) supports a limited subset of functionality when running in a partially-trusted environment.</span></span> <span data-ttu-id="3c2b3-104">部分信任中支持的功能围绕 [Supported Deployment Scenarios](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md) 主题中所述的一组特定的方案而设计。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-104">The features supported in partial trust are designed around a specific set of scenarios as described in the [Supported Deployment Scenarios](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md) topic.</span></span>  
  
## <a name="minimum-permission-requirements"></a><span data-ttu-id="3c2b3-105">最低权限要求</span><span class="sxs-lookup"><span data-stu-id="3c2b3-105">Minimum Permission Requirements</span></span>  
 <span data-ttu-id="3c2b3-106">WCF 支持以下标准命名的权限集下运行的应用程序中的功能子集：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-106">WCF supports a subset of features in applications running under either of the following standard named permission sets:</span></span>  
  
- <span data-ttu-id="3c2b3-107">“中等信任”权限</span><span class="sxs-lookup"><span data-stu-id="3c2b3-107">Medium Trust permissions</span></span>  
  
- <span data-ttu-id="3c2b3-108">“Internet 区域”权限</span><span class="sxs-lookup"><span data-stu-id="3c2b3-108">Internet Zone permissions</span></span>  
  
 <span data-ttu-id="3c2b3-109">尝试使用 WCF 在部分受信任应用程序中使用限制性更强的权限可能会导致在运行时的安全异常。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-109">Attempting to use WCF in partially-trusted applications with more restrictive permissions may result in security exceptions at runtime.</span></span>  
  
## <a name="contracts"></a><span data-ttu-id="3c2b3-110">协定</span><span class="sxs-lookup"><span data-stu-id="3c2b3-110">Contracts</span></span>  
 <span data-ttu-id="3c2b3-111">在部分信任环境下运行时，协定受到以下限制：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-111">Contracts are subject to the following restrictions when running under partial trust:</span></span>  
  
- <span data-ttu-id="3c2b3-112">实现 `[ServiceContract]` 接口的服务类必须为 `public` 类，且必须有一个 `public` 构造函数。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-112">The service class that implements the `[ServiceContract]` interface must be `public` and have a `public` constructor.</span></span> <span data-ttu-id="3c2b3-113">如果该服务类定义 `[OperationContract]` 方法，则这些方法必须为 `public`方法。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-113">If it defines `[OperationContract]` methods, these must be `public`.</span></span> <span data-ttu-id="3c2b3-114">如果该服务类实现 `[ServiceContract]` 接口，且 `private`接口为 `[ServiceContract]` 接口，则这些方法实现可以为显式实现或 `public`实现。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-114">If it instead implements a `[ServiceContract]` interface, those method implementations can be explicit or `private`, provided that the `[ServiceContract]` interface is `public`.</span></span>  
  
- <span data-ttu-id="3c2b3-115">在使用 `[ServiceKnownType]` 属性时，指定的方法必须为 `public`方法。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-115">When using the `[ServiceKnownType]` attribute, the method specified must be `public`.</span></span>  
  
- <span data-ttu-id="3c2b3-116">`[MessageContract]` 类及其成员可以为 `public`。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-116">`[MessageContract]` classes and their members can be `public`.</span></span> <span data-ttu-id="3c2b3-117">如果 `[MessageContract]` 类是在应用程序程序集中定义的，则该类可以为 `internal` 类并拥有 `internal` 成员。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-117">If the `[MessageContract]` class is defined in the application assembly it can be `internal` and have `internal` members.</span></span>  
  
## <a name="system-provided-bindings"></a><span data-ttu-id="3c2b3-118">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="3c2b3-118">System-Provided Bindings</span></span>  
 <span data-ttu-id="3c2b3-119">在部分信任环境中完全支持 <xref:System.ServiceModel.BasicHttpBinding> 和 <xref:System.ServiceModel.WebHttpBinding> 。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-119">The <xref:System.ServiceModel.BasicHttpBinding> and <xref:System.ServiceModel.WebHttpBinding> are fully supported in a partial trust environment.</span></span> <span data-ttu-id="3c2b3-120">仅对传输安全模式支持 <xref:System.ServiceModel.WSHttpBinding> 。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-120">The <xref:System.ServiceModel.WSHttpBinding> is supported for Transport security mode only.</span></span>  
  
 <span data-ttu-id="3c2b3-121">在部分信任环境中运行时，不支持使用除 HTTP 之外的传输的绑定（例如 <xref:System.ServiceModel.NetTcpBinding>、 <xref:System.ServiceModel.NetNamedPipeBinding>或 <xref:System.ServiceModel.NetMsmqBinding>）。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-121">Bindings that use transports other than HTTP, such as the <xref:System.ServiceModel.NetTcpBinding>, the <xref:System.ServiceModel.NetNamedPipeBinding>, or the <xref:System.ServiceModel.NetMsmqBinding>, are not supported when running in a partial trust environment.</span></span>  
  
## <a name="custom-bindings"></a><span data-ttu-id="3c2b3-122">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="3c2b3-122">Custom Bindings</span></span>  
 <span data-ttu-id="3c2b3-123">在部分信任环境中可以创建和使用自定义绑定，但必须遵循本节中指定的限制。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-123">Custom bindings can be created and used in a partial trust environment, but must follow the restrictions specified in this section.</span></span>  
  
### <a name="transports"></a><span data-ttu-id="3c2b3-124">传输</span><span class="sxs-lookup"><span data-stu-id="3c2b3-124">Transports</span></span>  
 <span data-ttu-id="3c2b3-125">允许的传输绑定元素仅为 <xref:System.ServiceModel.Channels.HttpTransportBindingElement> 和 <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-125">The only allowed transport binding elements are <xref:System.ServiceModel.Channels.HttpTransportBindingElement> and <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>.</span></span>  
  
### <a name="encoders"></a><span data-ttu-id="3c2b3-126">编码器</span><span class="sxs-lookup"><span data-stu-id="3c2b3-126">Encoders</span></span>  
 <span data-ttu-id="3c2b3-127">允许以下编码器：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-127">The following encoders are allowed:</span></span>  
  
- <span data-ttu-id="3c2b3-128">文本编码器 (<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>)。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-128">The text encoder (<xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>).</span></span>  
  
- <span data-ttu-id="3c2b3-129">二进制编码器 (<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>)。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-129">The binary encoder (<xref:System.ServiceModel.Channels.BinaryMessageEncodingBindingElement>).</span></span>  
  
- <span data-ttu-id="3c2b3-130">Web 消息编码器 (<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>)。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-130">The Web Message encoder (<xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>).</span></span>  
  
 <span data-ttu-id="3c2b3-131">不支持消息传输优化机制 (MTOM) 编码器。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-131">The Message Transmission Optimization Mechanism (MTOM) encoders are not supported.</span></span>  
  
### <a name="security"></a><span data-ttu-id="3c2b3-132">安全性</span><span class="sxs-lookup"><span data-stu-id="3c2b3-132">Security</span></span>  
 <span data-ttu-id="3c2b3-133">部分受信任的应用程序可以使用 WCF 的传输级安全功能来保护其通信。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-133">Partially-trusted applications can use WCF's transport-level security features for securing their communication.</span></span> <span data-ttu-id="3c2b3-134">不支持消息级安全。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-134">Message-level security is not supported.</span></span> <span data-ttu-id="3c2b3-135">将绑定配置为使用消息级别的安全会在运行时导致异常。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-135">Configuring a binding to use message-level security results in an exception at runtime.</span></span>  
  
### <a name="unsupported-bindings"></a><span data-ttu-id="3c2b3-136">不支持的绑定</span><span class="sxs-lookup"><span data-stu-id="3c2b3-136">Unsupported Bindings</span></span>  
 <span data-ttu-id="3c2b3-137">不支持使用可靠消息传递、事务或消息级安全的绑定。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-137">Bindings that use reliable messaging, transactions, or message-level security are not supported.</span></span>  
  
## <a name="serialization"></a><span data-ttu-id="3c2b3-138">序列化</span><span class="sxs-lookup"><span data-stu-id="3c2b3-138">Serialization</span></span>  
 <span data-ttu-id="3c2b3-139">在部分信任环境中支持 <xref:System.Runtime.Serialization.DataContractSerializer> 和 <xref:System.Xml.Serialization.XmlSerializer> 。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-139">Both the <xref:System.Runtime.Serialization.DataContractSerializer> and the <xref:System.Xml.Serialization.XmlSerializer> are supported in a partial trust environment.</span></span> <span data-ttu-id="3c2b3-140">但是，使用 <xref:System.Runtime.Serialization.DataContractSerializer> 时需要遵循以下条件：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-140">However, use of the <xref:System.Runtime.Serialization.DataContractSerializer> is subject to the following conditions:</span></span>  
  
- <span data-ttu-id="3c2b3-141">所有可序列化的 `[DataContract]` 类型必须为 `public`。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-141">All serializable `[DataContract]` types must be `public`.</span></span>  
  
- <span data-ttu-id="3c2b3-142">`[DataMember]` 类型中的所有可序列化的 `[DataContract]` 字段或属性必须是公共字段或属性并且可以读取/写入。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-142">All serializable `[DataMember]` fields or properties in a `[DataContract]` type must be public and read/write.</span></span> <span data-ttu-id="3c2b3-143">序列化和反序列化[readonly](https://go.microsoft.com/fwlink/?LinkID=98854)部分受信任的应用程序中运行 WCF 时，不支持字段。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-143">The serialization and deserialization of [readonly](https://go.microsoft.com/fwlink/?LinkID=98854) fields is not supported when running WCF in a partially-trusted application.</span></span>  
  
- <span data-ttu-id="3c2b3-144">在部分信任环境中， `[Serializable]`/ISerializable 编程模型不受支持。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-144">The `[Serializable]`/ISerializable programming model is not supported in a partial trust environment.</span></span>  
  
- <span data-ttu-id="3c2b3-145">必须在代码或计算机级别配置 (machine.config) 中指定已知类型。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-145">Known types must be specified in code or machine-level configuration (machine.config).</span></span> <span data-ttu-id="3c2b3-146">出于安全方面的原因，不能在应用程序级配置中指定已知类型。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-146">Known types cannot be specified in application-level configuration for security reasons.</span></span>  
  
- <span data-ttu-id="3c2b3-147">实现 <xref:System.Runtime.Serialization.IObjectReference> 的类型在部分受信任的环境中会引发异常。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-147">Types that implement <xref:System.Runtime.Serialization.IObjectReference> throw an exception in a partially-trusted environment.</span></span>  
  
 <span data-ttu-id="3c2b3-148">有关在部分受信任的应用程序中安全使用 [T:System.Runtime.Serialization.DataContractSerializer](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) 的更多安全信息，请参见 <xref:System.Runtime.Serialization.DataContractSerializer> 中的“序列化”一节。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-148">See the Serialization section in [Partial Trust Best Practices](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md) for more information about security when using <xref:System.Runtime.Serialization.DataContractSerializer> safely in a partially-trusted application.</span></span>  
  
### <a name="collection-types"></a><span data-ttu-id="3c2b3-149">集合类型</span><span class="sxs-lookup"><span data-stu-id="3c2b3-149">Collection Types</span></span>  
 <span data-ttu-id="3c2b3-150">一些集合类型可实现 <xref:System.Collections.Generic.IEnumerable%601> 和 <xref:System.Collections.IEnumerable>。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-150">Some collection types implement both <xref:System.Collections.Generic.IEnumerable%601> and <xref:System.Collections.IEnumerable>.</span></span> <span data-ttu-id="3c2b3-151">示例包括实现 <xref:System.Collections.Generic.ICollection%601>的类型。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-151">Examples include types that implement <xref:System.Collections.Generic.ICollection%601>.</span></span> <span data-ttu-id="3c2b3-152">这些类型可以实现 `public` 的 `GetEnumerator()`实现和 `GetEnumerator()`的显式实现。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-152">Such types can implement a `public` implementation of `GetEnumerator()`, and an explicit implementation of `GetEnumerator()`.</span></span> <span data-ttu-id="3c2b3-153">在此情况下， <xref:System.Runtime.Serialization.DataContractSerializer> 调用 `public` 的 `GetEnumerator()`，而不调用 `GetEnumerator()`的显式实现。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-153">In this case, <xref:System.Runtime.Serialization.DataContractSerializer> invokes the `public` implementation of `GetEnumerator()`, and not the explicit implementation of `GetEnumerator()`.</span></span> <span data-ttu-id="3c2b3-154">如果所有 `GetEnumerator()` 实现都不是 `public` 而全部是显式实现，则 <xref:System.Runtime.Serialization.DataContractSerializer> 调用 `IEnumerable.GetEnumerator()`。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-154">If none of the `GetEnumerator()` implementations are `public` and all are explicit implementations, then <xref:System.Runtime.Serialization.DataContractSerializer> invokes `IEnumerable.GetEnumerator()`.</span></span>  
  
 <span data-ttu-id="3c2b3-155">对于集合类型，如果没有任何 WCF 在部分信任环境中，运行时`GetEnumerator()`实现`public`，或其中任何一个是显式接口实现，则引发安全异常。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-155">For collection types when WCF is running in a partial trust environment, if none of the `GetEnumerator()` implementations are `public`, or none of them are explicit interface implementations, then a security exception is thrown.</span></span>  
  
### <a name="netdatacontractserializer"></a><span data-ttu-id="3c2b3-156">NetDataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="3c2b3-156">NetDataContractSerializer</span></span>  
 <span data-ttu-id="3c2b3-157">在部分信任环境中， <xref:System.Collections.Generic.List%601>不支持许多 .NET Framework 集合类型，如 <xref:System.Collections.ArrayList>、 <xref:System.Collections.Generic.Dictionary%602> 、 <xref:System.Collections.Hashtable> 和 <xref:System.Runtime.Serialization.NetDataContractSerializer> 。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-157">Many .NET Framework collection types such as <xref:System.Collections.Generic.List%601>, <xref:System.Collections.ArrayList>, <xref:System.Collections.Generic.Dictionary%602> and <xref:System.Collections.Hashtable> are not supported by the <xref:System.Runtime.Serialization.NetDataContractSerializer> in partial trust.</span></span> <span data-ttu-id="3c2b3-158">这些类型设置了 `[Serializable]` 属性，如前面“序列化”一节中所述，此属性在部分信任环境中不受支持。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-158">These types have the `[Serializable]` attribute set, and as stated previously in the Serialization section, this attribute is not supported in partial trust.</span></span> <span data-ttu-id="3c2b3-159"><xref:System.Runtime.Serialization.DataContractSerializer> 以特殊方式处理集合，因而能够避开此限制， <xref:System.Runtime.Serialization.NetDataContractSerializer> 没有这类机制可避开此限制。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-159">The <xref:System.Runtime.Serialization.DataContractSerializer> treats collections in a special way and is thus able to get around this restriction, but the <xref:System.Runtime.Serialization.NetDataContractSerializer> has no such mechanism to circumvent this restriction.</span></span>  
  
 <span data-ttu-id="3c2b3-160">在部分信任环境中， <xref:System.DateTimeOffset> 不支持 <xref:System.Runtime.Serialization.NetDataContractSerializer> 类型。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-160">The <xref:System.DateTimeOffset> type is not supported by the <xref:System.Runtime.Serialization.NetDataContractSerializer> in partial trust.</span></span>  
  
 <span data-ttu-id="3c2b3-161">在部分信任环境中运行时，无法将代理项用于 <xref:System.Runtime.Serialization.NetDataContractSerializer> （使用 <xref:System.Runtime.Serialization.SurrogateSelector> 机制）。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-161">A surrogate cannot be used with the <xref:System.Runtime.Serialization.NetDataContractSerializer> (using the <xref:System.Runtime.Serialization.SurrogateSelector> mechanism) when running in partial trust.</span></span> <span data-ttu-id="3c2b3-162">请注意，此限制适用于使用代理项，而不适用于序列化代理项。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-162">Note that this restriction applies to using a surrogate, not to serializing it.</span></span>  
  
## <a name="enabling-common-behaviors-to-run"></a><span data-ttu-id="3c2b3-163">使常见行为能够运行</span><span class="sxs-lookup"><span data-stu-id="3c2b3-163">Enabling Common Behaviors to Run</span></span>  
 <span data-ttu-id="3c2b3-164">服务或终结点行为未标有<xref:System.Security.AllowPartiallyTrustedCallersAttribute>特性 (APTCA) 添加到[ \<commonBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)节的配置文件，则不运行应用程序在部分信任环境中运行时发生这种情况时，将引发环境和任何异常。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-164">Service or endpoint behaviors not marked with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute (APTCA) that are added to the [\<commonBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md) section of a configuration file are not run when the application runs in a partial trust environment and no exception is thrown when this occurs.</span></span> <span data-ttu-id="3c2b3-165">若要强制运行常见行为，必须执行下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-165">To enforce the running of common behaviors, you must do one of the following options:</span></span>  
  
- <span data-ttu-id="3c2b3-166">使用 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 属性标记常见行为，以使其在部署为部分信任应用程序时能够运行。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-166">Mark your common behavior with the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute so that it can run when deployed as a partial trust application.</span></span> <span data-ttu-id="3c2b3-167">请注意，可以在计算机上设置注册表项，以防运行标有 APTCA 的程序集。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-167">Note that a registry entry can be set on the computer to prevent APTCA-marked assemblies from running.</span></span> <span data-ttu-id="3c2b3-168">方法。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-168">.</span></span>  
  
- <span data-ttu-id="3c2b3-169">确保在将应用程序作为完全受信任的应用程序部署时，用户不能修改代码访问安全设置，从而无法在部分信任环境中运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-169">Ensure that if the application is deployed as a fully-trusted application that users cannot modify the code-access security settings to run the application in a partial trust environment.</span></span> <span data-ttu-id="3c2b3-170">如果用户可以这样做，则不会运行该行为，且不引发任何异常。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-170">If they can do so, the behavior does not run and no exception is thrown.</span></span> <span data-ttu-id="3c2b3-171">若要确保这一点，请参阅**levelfinal**选项使用[Caspol.exe （代码访问安全策略工具）](../../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-171">To ensure this, see the **levelfinal** option using [Caspol.exe (Code Access Security Policy Tool)](../../../../docs/framework/tools/caspol-exe-code-access-security-policy-tool.md).</span></span>  
  
 <span data-ttu-id="3c2b3-172">有关常见行为的一个示例，请参阅[如何：在企业中的锁定终结点](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-172">For an example of a common behavior, see [How to: Lock Down Endpoints in the Enterprise](../../../../docs/framework/wcf/extending/how-to-lock-down-endpoints-in-the-enterprise.md).</span></span>  
  
## <a name="configuration"></a><span data-ttu-id="3c2b3-173">配置</span><span class="sxs-lookup"><span data-stu-id="3c2b3-173">Configuration</span></span>  
 <span data-ttu-id="3c2b3-174">有一个例外，部分受信任的代码只能加载本地 WCF 配置节`app.config`文件。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-174">With one exception, partially-trusted code can only load WCF configuration sections in the local `app.config` file.</span></span> <span data-ttu-id="3c2b3-175">若要加载 WCF 配置节引用 WCF 节在 machine.config 或根中的 web.config 文件需要 configurationpermission （unrestricted）。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-175">To load WCF configuration sections that reference WCF sections in machine.config or in a root web.config file requires ConfigurationPermission(Unrestricted).</span></span> <span data-ttu-id="3c2b3-176">如果没有此权限引用向 WCF 配置节 （行为、 绑定） 之外的本地配置文件会引发异常时加载配置。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-176">Without this permission, references to WCF configuration sections (behaviors, bindings) outside of the local configuration file results in an exception when the configuration is loaded.</span></span>  
  
 <span data-ttu-id="3c2b3-177">一个例外情况是序列化的已知类型配置，如本主题中的“序列化”一节所述。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-177">The one exception is known-type configuration for serialization, as described in the Serialization section of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="3c2b3-178">仅当在完全信任环境下运行时，才支持配置扩展。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-178">Configuration extensions are only supported when running under Full Trust.</span></span>  
  
## <a name="diagnostics"></a><span data-ttu-id="3c2b3-179">诊断</span><span class="sxs-lookup"><span data-stu-id="3c2b3-179">Diagnostics</span></span>  
  
### <a name="event-logging"></a><span data-ttu-id="3c2b3-180">事件日志记录</span><span class="sxs-lookup"><span data-stu-id="3c2b3-180">Event Logging</span></span>  
 <span data-ttu-id="3c2b3-181">部分信任环境下支持有限的事件日志记录。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-181">Limited event logging is supported under partial trust.</span></span> <span data-ttu-id="3c2b3-182">事件日志中仅记录服务激活错误和跟踪/消息日志记录错误。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-182">Only service activation faults and tracing/message logging failures are logged to the Event Log.</span></span> <span data-ttu-id="3c2b3-183">为了避免向事件日志写入过多消息，一个进程最多可以记录 5 个事件。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-183">The maximum number of events that can be logged by a process is 5, to avoid writing excessive messages to the Event Log.</span></span>  
  
### <a name="message-logging"></a><span data-ttu-id="3c2b3-184">消息日志记录</span><span class="sxs-lookup"><span data-stu-id="3c2b3-184">Message Logging</span></span>  
 <span data-ttu-id="3c2b3-185">时在部分信任环境中运行 WCF 消息日志记录无效。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-185">Message logging does not work when WCF is run in a partial trust environment.</span></span> <span data-ttu-id="3c2b3-186">如果在部分信任下启用消息日志记录，不会出现服务激活失败，但不记录消息。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-186">If enabled under partial trust, it does not fail service activation, but no message is logged.</span></span>  
  
### <a name="tracing"></a><span data-ttu-id="3c2b3-187">跟踪</span><span class="sxs-lookup"><span data-stu-id="3c2b3-187">Tracing</span></span>  
 <span data-ttu-id="3c2b3-188">在部分信任环境中运行时可使用有限的跟踪功能。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-188">Restricted tracing functionality is available when running in a partial trust environment.</span></span> <span data-ttu-id="3c2b3-189">在 <`listeners`> 配置文件中的元素，可以添加的类型仅有<xref:System.Diagnostics.TextWriterTraceListener>和新<xref:System.Diagnostics.EventSchemaTraceListener>。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-189">In the <`listeners`> element in the configuration file, the only types that you can add are <xref:System.Diagnostics.TextWriterTraceListener> and the new <xref:System.Diagnostics.EventSchemaTraceListener>.</span></span> <span data-ttu-id="3c2b3-190">使用标准的 <xref:System.Diagnostics.XmlWriterTraceListener> 可能会造成日志不完整或不正确。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-190">Use of the standard <xref:System.Diagnostics.XmlWriterTraceListener> may result in incomplete or incorrect logs.</span></span>  
  
 <span data-ttu-id="3c2b3-191">支持的跟踪源有：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-191">Supported trace sources are:</span></span>  
  
- <xref:System.ServiceModel>  
  
- <xref:System.Runtime.Serialization>  
  
- <span data-ttu-id="3c2b3-192"><xref:System.IdentityModel.Claims>、 <xref:System.IdentityModel.Policy>、 <xref:System.IdentityModel.Selectors>和 <xref:System.IdentityModel.Tokens>。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-192"><xref:System.IdentityModel.Claims>, <xref:System.IdentityModel.Policy>, <xref:System.IdentityModel.Selectors>, and <xref:System.IdentityModel.Tokens>.</span></span>  
  
 <span data-ttu-id="3c2b3-193">不支持下面的跟踪源：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-193">The following trace sources are not supported:</span></span>  
  
- <span data-ttu-id="3c2b3-194">CardSpace</span><span class="sxs-lookup"><span data-stu-id="3c2b3-194">CardSpace</span></span>  
  
- <xref:System.IO.Log>  

- <span data-ttu-id="3c2b3-195">[System.ServiceModel.Internal.TransactionBridge](https://docs.microsoft.com/previous-versions/aa346556(v=vs.110))]</span><span class="sxs-lookup"><span data-stu-id="3c2b3-195">[System.ServiceModel.Internal.TransactionBridge](https://docs.microsoft.com/previous-versions/aa346556(v=vs.110))]</span></span>
  
 <span data-ttu-id="3c2b3-196">不应指定下面的 <xref:System.Diagnostics.TraceOptions> 枚举成员：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-196">The following members of the <xref:System.Diagnostics.TraceOptions> enumeration should not be specified:</span></span>  
  
- <xref:System.Diagnostics.TraceOptions.Callstack?displayProperty=nameWithType>  
  
- <xref:System.Diagnostics.TraceOptions.ProcessId?displayProperty=nameWithType>  
  
 <span data-ttu-id="3c2b3-197">在部分信任环境中使用跟踪时，应确保应用程序具有足够的权限来存储跟踪侦听器的输出。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-197">When using tracing in a partial trust environment, ensure that the application has sufficient permissions to store the output of the trace listener.</span></span> <span data-ttu-id="3c2b3-198">例如，在使用 <xref:System.Diagnostics.TextWriterTraceListener> 将跟踪输出写入到文本文件中时，应确保应用程序具有成功写入到跟踪文件中所需的必要的 FileIOPermission。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-198">For example, when using the <xref:System.Diagnostics.TextWriterTraceListener> to write trace output to a text file, ensure that the application has the necessary FileIOPermission required to successfully write to the trace file.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c2b3-199">若要避免填满出现重复的错误的跟踪文件，WCF 会禁用资源或后第一次安全失败操作的跟踪。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-199">To avoid flooding the trace files with duplicate errors, WCF disables tracing of the resource or action after the first security failure.</span></span> <span data-ttu-id="3c2b3-200">对于在第一次尝试访问资源或执行操作时出现的每个失败的资源访问，将会有一个异常跟踪。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-200">There is one exception trace for each failed resource access, the first time an attempt is made to access the resource or perform the action.</span></span>  
  
## <a name="wcf-service-host"></a><span data-ttu-id="3c2b3-201">WCF 服务主机</span><span class="sxs-lookup"><span data-stu-id="3c2b3-201">WCF Service Host</span></span>  
 <span data-ttu-id="3c2b3-202">WCF 服务主机不支持部分信任。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-202">WCF service host does not support partial trust.</span></span> <span data-ttu-id="3c2b3-203">如果你想要在部分信任环境中使用的 WCF 服务，不要使用 WCF 服务库项目模板在 Visual Studio 中生成服务。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-203">If you want to use a WCF service in partial trust, do not use the WCF Service Library Project template in Visual Studio to build your service.</span></span> <span data-ttu-id="3c2b3-204">相反，新的 Web 站点在 Visual Studio 中通过选择创建 WCF 服务网站模板，可以托管在其支持 WCF 部分信任的 Web 服务器中的服务。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-204">Instead, create a new Web site in Visual Studio by choosing the WCF service Web site template, which can host the service in a Web server on which WCF partial trust is supported.</span></span>  
  
## <a name="other-limitations"></a><span data-ttu-id="3c2b3-205">其他限制</span><span class="sxs-lookup"><span data-stu-id="3c2b3-205">Other Limitations</span></span>  
 <span data-ttu-id="3c2b3-206">WCF 是通常仅适用于主机应用程序带来的安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-206">WCF is generally limited to the security considerations imposed upon it by the hosting application.</span></span> <span data-ttu-id="3c2b3-207">例如，如果 WCF 托管在 XAML 浏览器应用程序 (XBAP) 中，则遵守 XBAP 限制，如中所述[Windows Presentation Foundation 部分信任安全](https://go.microsoft.com/fwlink/?LinkId=89138)。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-207">For example, if WCF is hosted in a XAML Browser Application (XBAP), it is subject to XBAP limitations, as described in [Windows Presentation Foundation Partial Trust Security](https://go.microsoft.com/fwlink/?LinkId=89138).</span></span>  
  
 <span data-ttu-id="3c2b3-208">在部分信任环境中运行 indigo2 时，不启用以下的其他功能：</span><span class="sxs-lookup"><span data-stu-id="3c2b3-208">The following additional features are not enabled when running indigo2 in a partial trust environment:</span></span>  
  
- <span data-ttu-id="3c2b3-209">Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="3c2b3-209">Windows Management Instrumentation (WMI)</span></span>  
  
- <span data-ttu-id="3c2b3-210">事件日志记录仅部分启用（请参见“ **诊断** ”一节的讨论）。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-210">Event logging is only partially enabled (see discussion in **Diagnostics** section).</span></span>  
  
- <span data-ttu-id="3c2b3-211">性能计数器</span><span class="sxs-lookup"><span data-stu-id="3c2b3-211">Performance counters</span></span>  
  
 <span data-ttu-id="3c2b3-212">使用不支持在部分信任环境中的 WCF 功能可能会导致在运行时异常。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-212">Use of WCF features that are not supported in a partial trust environment may result in exceptions at runtime.</span></span>  
  
## <a name="unlisted-features"></a><span data-ttu-id="3c2b3-213">未列出的功能</span><span class="sxs-lookup"><span data-stu-id="3c2b3-213">Unlisted Features</span></span>  
 <span data-ttu-id="3c2b3-214">若要在部分信任环境中运行时发现不可用的信息或操作，最好的方法是尝试在 `try` 块的内部访问资源或执行操作，然后 `catch` 失败。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-214">The best way to discover that a piece of information or action is unavailable when running in a partial trust environment is to try to access the resource or do the action inside of a `try` block, and then `catch` the failure.</span></span> <span data-ttu-id="3c2b3-215">若要避免填满出现重复的错误的跟踪文件，WCF 会禁用资源或后第一次安全失败操作的跟踪。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-215">To avoid flooding the trace files with duplicate errors, WCF disables tracing of the resource or action after the first security failure.</span></span> <span data-ttu-id="3c2b3-216">对于在第一次尝试访问资源或执行操作时出现的每个失败的资源访问，将会有一个异常跟踪。</span><span class="sxs-lookup"><span data-stu-id="3c2b3-216">There is one exception trace for each failed resource access, the first time an attempt is made to access the resource or perform the action.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c2b3-217">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c2b3-217">See also</span></span>

- <xref:System.ServiceModel.Channels.HttpTransportBindingElement>
- <xref:System.ServiceModel.Channels.HttpsTransportBindingElement>
- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
- <xref:System.ServiceModel.Channels.WebMessageEncodingBindingElement>
- [<span data-ttu-id="3c2b3-218">支持的部署方案</span><span class="sxs-lookup"><span data-stu-id="3c2b3-218">Supported Deployment Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/supported-deployment-scenarios.md)
- [<span data-ttu-id="3c2b3-219">部分信任最佳做法</span><span class="sxs-lookup"><span data-stu-id="3c2b3-219">Partial Trust Best Practices</span></span>](../../../../docs/framework/wcf/feature-details/partial-trust-best-practices.md)
