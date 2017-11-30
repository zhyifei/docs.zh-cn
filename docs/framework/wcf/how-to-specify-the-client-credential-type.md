---
title: "如何：指定客户端凭据类型"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 35c3b5ee429f7c9337fa3c3e3eb0d0476e3f56d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="fb0d9-102">如何：指定客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="fb0d9-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="fb0d9-103">设置安全模式（传输或消息）后，您可以设置客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="fb0d9-104">此属性指定客户端必须向服务提供以进行身份验证的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="fb0d9-105">设置安全模式 （一项必要步骤之前设置客户端凭据类型），请参阅[如何： 将安全模式设置](../../../docs/framework/wcf/how-to-set-the-security-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-105"> setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="fb0d9-106">在代码中设置客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="fb0d9-106">To set the client credential type in code</span></span>  
  
1.  <span data-ttu-id="fb0d9-107">创建服务将使用的绑定的实例。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="fb0d9-108">本示例使用 <xref:System.ServiceModel.WSHttpBinding> 绑定。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2.  <span data-ttu-id="fb0d9-109">将 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="fb0d9-110">本示例使用 Message 模式。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-110">This example uses the Message mode.</span></span>  
  
3.  <span data-ttu-id="fb0d9-111">将 <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="fb0d9-112">本示例将其设置为使用 Windows 身份验证 (<xref:System.ServiceModel.MessageCredentialType.Windows>)。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="fb0d9-113">在配置中设置客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="fb0d9-113">To set the client credential type in configuration</span></span>  
  
1.  <span data-ttu-id="fb0d9-114">添加[ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)到配置文件的元素。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2.  <span data-ttu-id="fb0d9-115">作为子元素添加[\<绑定 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)元素。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3.  <span data-ttu-id="fb0d9-116">添加一个相应的绑定。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-116">Add an appropriate binding.</span></span> <span data-ttu-id="fb0d9-117">此示例使用[ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4.  <span data-ttu-id="fb0d9-118">添加[\<绑定 >](../../../docs/framework/misc/binding.md)元素，并设置`name`属性设为适当的值。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="fb0d9-119">本示例使用名称“SecureBinding”。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-119">This example uses the name "SecureBinding".</span></span>  
  
5.  <span data-ttu-id="fb0d9-120">添加一个 `<security>` 绑定。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-120">Add a `<security>` binding.</span></span> <span data-ttu-id="fb0d9-121">将 `mode` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="fb0d9-122">本示例将其设置为 `"Message"`。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-122">This example sets it to `"Message"`.</span></span>  
  
6.  <span data-ttu-id="fb0d9-123">添加一个 `<message>` 或 `<transport>` 元素，具体由安全模式确定。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="fb0d9-124">将 `clientCredentialType` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="fb0d9-125">本示例使用 `"Windows"`。</span><span class="sxs-lookup"><span data-stu-id="fb0d9-125">This example uses `"Windows"`.</span></span>  
  
    ```xml  
    <system.serviceModel>  
      <bindings>  
        <wsHttpBinding>  
          <binding name="SecureBinding">  
            <security mode="Message">  
                 <message clientCredentialType="Windows" />  
             </security>  
          </binding>  
        </wsHttpBinding>  
      </bindings>  
    </system.serviceModel>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fb0d9-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb0d9-126">See Also</span></span>  
 [<span data-ttu-id="fb0d9-127">保护服务</span><span class="sxs-lookup"><span data-stu-id="fb0d9-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 [<span data-ttu-id="fb0d9-128">如何：设置安全模式</span><span class="sxs-lookup"><span data-stu-id="fb0d9-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
