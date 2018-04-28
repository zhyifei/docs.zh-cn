---
title: 如何：为安全会话创建安全上下文令牌
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 640676b6-c75a-4ff7-aea4-b1a1524d71b2
caps.latest.revision: 14
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload:
- dotnet
ms.openlocfilehash: 579a980d8d71b5fe3e21e49e84a602b3be37eff1
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="how-to-create-a-security-context-token-for-a-secure-session"></a><span data-ttu-id="2c9e1-102">如何：为安全会话创建安全上下文令牌</span><span class="sxs-lookup"><span data-stu-id="2c9e1-102">How to: Create a Security Context Token for a Secure Session</span></span>
<span data-ttu-id="2c9e1-103">通过在安全会话中使用有状态安全上下文令牌 (SCT)，可以使该会话避免因为重新使用服务而受到影响。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-103">By using a stateful security context token (SCT) in a secure session, the session can withstand the service being recycled.</span></span> <span data-ttu-id="2c9e1-104">例如，如果在安全会话中使用了无状态 SCT 并且 Internet 信息服务 (IIS) 被重置，则与该服务相关联的会话数据将丢失。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-104">For instance, when a stateless SCT is used in a secure session and Internet Information Services (IIS) is reset, then the session data that is associated with the service is lost.</span></span> <span data-ttu-id="2c9e1-105">这些会话数据包括一个 SCT 令牌缓存。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-105">This session data includes an SCT token cache.</span></span> <span data-ttu-id="2c9e1-106">因此，当客户端下一次向该服务发送无状态 SCT 时，将返回错误，这是因为无法检索到与该 SCT 相关联的密钥。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-106">So, the next time a client sends the service a stateless SCT, an error is returned, because the key that is associated with the SCT cannot be retrieved.</span></span> <span data-ttu-id="2c9e1-107">但是，如果使用有状态 SCT，则与该 SCT 相关联的密钥将包含在该 SCT 中。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-107">If, however, a stateful SCT is used, then the key that is associated with the SCT is contained within the SCT.</span></span> <span data-ttu-id="2c9e1-108">由于密钥包含在 SCT 中并因而包含在消息中，因此安全会话不会因为重新使用服务而受到影响。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-108">Because the key is contained within the SCT and thus contained within the message, the secure session is not affected by the service being recycled.</span></span> <span data-ttu-id="2c9e1-109">默认情况下，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 在安全会话中使用无状态 SCT。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-109">By default, [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses stateless SCTs in a secure session.</span></span> <span data-ttu-id="2c9e1-110">本主题详细介绍如何在安全会话中使用有状态 SCT。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-110">This topic details how to use stateful SCTs in a secure session.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c9e1-111">如果安全会话涉及到派生自 <xref:System.ServiceModel.Channels.IDuplexChannel> 的协定，则无法在该安全会话中使用有状态 SCT。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-111">Stateful SCTs cannot be used in a secure session that involves a contract that derives from <xref:System.ServiceModel.Channels.IDuplexChannel>.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c9e1-112">对于在安全会话中使用有状态 SCT 的应用程序，服务的线程标识必须是具有关联用户配置文件的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-112">For applications that use stateful SCTs in a secure session, the thread identity for the service must be a user account that has an associated user profile.</span></span> <span data-ttu-id="2c9e1-113">如果服务在不具有用户配置文件的帐户下运行（如 `Local Service`），则可能引发异常。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-113">When the service is run under an account that does not have a user profile, such as `Local Service`, an exception may be thrown.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2c9e1-114">当需要在 Windows XP 上进行模拟时，请不要在安全会话中使用有状态 SCT。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-114">When impersonation is required on Windows XP, use a secure session without a stateful SCT.</span></span> <span data-ttu-id="2c9e1-115">如果在模拟时使用有状态 SCT，则会引发 <xref:System.InvalidOperationException>。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-115">When stateful SCTs are used with impersonation, an <xref:System.InvalidOperationException> is thrown.</span></span> <span data-ttu-id="2c9e1-116">有关详细信息，请参阅[不支持的方案](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md)。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-116">For more information, see [Unsupported Scenarios](../../../../docs/framework/wcf/feature-details/unsupported-scenarios.md).</span></span>  
  
### <a name="to-use-stateful-scts-in-a-secure-session"></a><span data-ttu-id="2c9e1-117">在安全会话中使用有状态 SCT</span><span class="sxs-lookup"><span data-stu-id="2c9e1-117">To use stateful SCTs in a secure session</span></span>  
  
-   <span data-ttu-id="2c9e1-118">创建一个自定义绑定，该绑定指定由使用有状态 SCT 的安全会话来保护 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-118">Create a custom binding that specifies that SOAP messages are protected by a secure session that uses a stateful SCT.</span></span>  
  
    1.  <span data-ttu-id="2c9e1-119">通过添加定义自定义绑定， [ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)到服务的配置文件。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-119">Define a custom binding, by adding a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) to the configuration file for the service.</span></span>  
  
        ```xml  
        <customBinding>  
        ```  
  
    2.  <span data-ttu-id="2c9e1-120">添加[\<绑定 >](../../../../docs/framework/misc/binding.md)到的子元素[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-120">Add a [\<binding>](../../../../docs/framework/misc/binding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="2c9e1-121">通过在配置文件中将 `name` 属性设置为一个唯一的名称，指定一个绑定名称。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-121">Specify a binding name by setting the `name` attribute to a unique name within the configuration file.</span></span>  
  
        ```xml  
        <binding name="StatefulSCTSecureSession">  
        ```  
  
    3.  <span data-ttu-id="2c9e1-122">指定与此服务所发送的添加消息的身份验证模式[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)到的子元素[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-122">Specify the authentication mode for messages sent to and from this service by adding a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) child element to the [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md).</span></span>  
  
         <span data-ttu-id="2c9e1-123">通过将 `authenticationMode` 属性设置为 `SecureConversation`，指定使用安全会话。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-123">Specify that a secure session is used by setting the `authenticationMode` attribute to `SecureConversation`.</span></span> <span data-ttu-id="2c9e1-124">通过将 `requireSecurityContextCancellation` 属性设置为 `false`，指定使用有状态 SCT。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-124">Specify that stateful SCTs are used by setting the `requireSecurityContextCancellation` attribute to `false`.</span></span>  
  
        ```xml  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
        ```  
  
    4.  <span data-ttu-id="2c9e1-125">指定如何客户端进行身份验证通过添加建立安全会话时[ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)到的子元素[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-125">Specify how the client is authenticated while the secure session is established by adding a [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) child element to the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).</span></span>  
  
         <span data-ttu-id="2c9e1-126">通过设置 `authenticationMode` 属性，指定如何对客户端进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-126">Specify how the client is authenticated by setting the `authenticationMode` attribute.</span></span>  
  
        ```xml  
        <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        ```  
  
    5.  <span data-ttu-id="2c9e1-127">指定通过添加一个编码的元素，如消息编码[ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-127">Specify the message encoding by adding an encoding element, such as [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
        ```xml  
        <textMessageEncoding />  
        ```  
  
    6.  <span data-ttu-id="2c9e1-128">通过添加一个传输元素，如指定的传输[ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-128">Specify the transport by adding a transport element, such as the [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
        ```xml  
        <httpTransport />  
        ```  
  
     <span data-ttu-id="2c9e1-129">下面的代码示例使用配置来指定一个自定义绑定，消息可以将该绑定与安全会话中的有状态 SCT 结合使用。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-129">The following code example uses configuration to specify a custom binding that messages can use with stateful SCTs in a secure session.</span></span>  
  
    ```xml  
    <customBinding>  
      <binding name="StatefulSCTSecureSession">  
        <security authenticationMode="SecureConversation"  
                  requireSecurityContextCancellation="false">  
          <secureConversationBootstrap authenticationMode="UserNameForCertificate" />  
        </security>  
        <textMessageEncoding />  
        <httpTransport />  
      </binding>  
    </customBinding>  
    ```  
  
## <a name="example"></a><span data-ttu-id="2c9e1-130">示例</span><span class="sxs-lookup"><span data-stu-id="2c9e1-130">Example</span></span>  
 <span data-ttu-id="2c9e1-131">下面的代码示例创建一个自定义绑定，该绑定使用 <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 身份验证模式启动安全会话。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-131">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
 [!code-csharp[c_CreateStatefulSCT#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createstatefulsct/cs/secureservice.cs#2)]
 [!code-vb[c_CreateStatefulSCT#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createstatefulsct/vb/secureservice.vb#2)]  
  
 <span data-ttu-id="2c9e1-132">在将 Windows 身份验证与有状态 SCT 结合起来使用时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 不使用实际调用方的标识来填充 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 属性，而是将该属性设置为匿名。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-132">When Windows authentication is used in combination with a stateful SCT, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not populate the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property with the actual caller's identity but instead sets the property to anonymous.</span></span> <span data-ttu-id="2c9e1-133">由于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 安全必须为来自传入 SCT 的每个请求重新创建服务安全上下文的内容，因此服务器不会跟踪内存中的安全会话。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-133">Because [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security must re-create the content of the service security context for every request from the incoming SCT, the server does not keep track of the security session in the memory.</span></span> <span data-ttu-id="2c9e1-134">因为不可能将 <xref:System.Security.Principal.WindowsIdentity> 实例序列化为 SCT，所以 <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> 属性返回一个匿名标识。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-134">Because it is impossible to serialize the <xref:System.Security.Principal.WindowsIdentity> instance into the SCT, the <xref:System.ServiceModel.ServiceSecurityContext.WindowsIdentity%2A> property returns an anonymous identity.</span></span>  
  
 <span data-ttu-id="2c9e1-135">下面的配置演示这一行为。</span><span class="sxs-lookup"><span data-stu-id="2c9e1-135">The following configuration exhibits this behavior.</span></span>  
  
```xml  
<customBinding>  
  <binding name="Cancellation">  
       <textMessageEncoding />  
        <security   
            requireSecurityContextCancellation="false">  
              <secureConversationBootstrap />  
      </security>  
    <httpTransport />  
  </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2c9e1-136">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c9e1-136">See Also</span></span>  
 [<span data-ttu-id="2c9e1-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="2c9e1-137">\<customBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
