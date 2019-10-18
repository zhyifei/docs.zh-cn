---
title: 如何：指定客户端凭据类型
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security credentials, adding to SOAP messages
- WCF, security
ms.assetid: 10f51bee-5f92-4c1a-9126-fa5418535d8f
ms.openlocfilehash: d62011728b6b03023ef4039480cea8dfa0ec8f02
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321287"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="72291-102">如何：指定客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="72291-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="72291-103">设置安全模式（传输或消息）后，您可以设置客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="72291-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="72291-104">此属性指定客户端必须向服务提供以进行身份验证的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="72291-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="72291-105">有关设置安全模式（设置客户端凭据类型前的必需步骤）的详细信息，请参阅[如何：设置安全模式](how-to-set-the-security-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="72291-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="72291-106">在代码中设置客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="72291-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="72291-107">创建服务将使用的绑定的实例。</span><span class="sxs-lookup"><span data-stu-id="72291-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="72291-108">本示例使用 <xref:System.ServiceModel.WSHttpBinding> 绑定。</span><span class="sxs-lookup"><span data-stu-id="72291-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="72291-109">将 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="72291-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="72291-110">本示例使用 Message 模式。</span><span class="sxs-lookup"><span data-stu-id="72291-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="72291-111">将 <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="72291-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="72291-112">本示例将其设置为使用 Windows 身份验证 (<xref:System.ServiceModel.MessageCredentialType.Windows>)。</span><span class="sxs-lookup"><span data-stu-id="72291-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="72291-113">在配置中设置客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="72291-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="72291-114">向配置文件添加一个[\<system 的 >](../configure-apps/file-schema/wcf/system-servicemodel.md)元素。</span><span class="sxs-lookup"><span data-stu-id="72291-114">Add a [\<system.serviceModel>](../configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="72291-115">作为子元素，添加一个[\<bindings >](../configure-apps/file-schema/wcf/bindings.md)元素。</span><span class="sxs-lookup"><span data-stu-id="72291-115">As a child element, add a [\<bindings>](../configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="72291-116">添加一个相应的绑定。</span><span class="sxs-lookup"><span data-stu-id="72291-116">Add an appropriate binding.</span></span> <span data-ttu-id="72291-117">此示例使用[\<wsHttpBinding >](../configure-apps/file-schema/wcf/wshttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="72291-117">This example uses the [\<wsHttpBinding>](../configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="72291-118">添加一个[\<binding >](../misc/binding.md)元素，并将 `name` 特性设置为合适的值。</span><span class="sxs-lookup"><span data-stu-id="72291-118">Add a [\<binding>](../misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="72291-119">本示例使用名称“SecureBinding”。</span><span class="sxs-lookup"><span data-stu-id="72291-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="72291-120">添加一个 `<security>` 绑定。</span><span class="sxs-lookup"><span data-stu-id="72291-120">Add a `<security>` binding.</span></span> <span data-ttu-id="72291-121">将 `mode` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="72291-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="72291-122">本示例将其设置为 `"Message"`。</span><span class="sxs-lookup"><span data-stu-id="72291-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="72291-123">添加一个 `<message>` 或 `<transport>` 元素，具体由安全模式确定。</span><span class="sxs-lookup"><span data-stu-id="72291-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="72291-124">将 `clientCredentialType` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="72291-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="72291-125">本示例使用 `"Windows"`。</span><span class="sxs-lookup"><span data-stu-id="72291-125">This example uses `"Windows"`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="72291-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="72291-126">See also</span></span>

- [<span data-ttu-id="72291-127">保护服务</span><span class="sxs-lookup"><span data-stu-id="72291-127">Securing Services</span></span>](securing-services.md)
- [<span data-ttu-id="72291-128">如何：设置安全模式</span><span class="sxs-lookup"><span data-stu-id="72291-128">How to: Set the Security Mode</span></span>](how-to-set-the-security-mode.md)
