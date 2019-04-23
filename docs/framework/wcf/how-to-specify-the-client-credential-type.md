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
ms.openlocfilehash: 775c6a297047c7a0e16db091f9a22686fdb01efb
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59339393"
---
# <a name="how-to-specify-the-client-credential-type"></a><span data-ttu-id="dbced-102">如何：指定客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="dbced-102">How to: Specify the Client Credential Type</span></span>
<span data-ttu-id="dbced-103">设置安全模式（传输或消息）后，您可以设置客户端凭据类型。</span><span class="sxs-lookup"><span data-stu-id="dbced-103">After setting a security mode (either transport or message), you have the option of setting the client credential type.</span></span> <span data-ttu-id="dbced-104">此属性指定客户端必须向服务提供以进行身份验证的凭据类型。</span><span class="sxs-lookup"><span data-stu-id="dbced-104">This property specifies what type of credential the client must provide to the service for authentication.</span></span> <span data-ttu-id="dbced-105">有关设置安全模式 （设置客户端凭据类型前的必需步骤） 的详细信息，请参阅[如何：将安全模式设置](../../../docs/framework/wcf/how-to-set-the-security-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="dbced-105">For more information about setting the security mode (a necessary step before setting the client credential type), see [How to: Set the Security Mode](../../../docs/framework/wcf/how-to-set-the-security-mode.md).</span></span>  
  
### <a name="to-set-the-client-credential-type-in-code"></a><span data-ttu-id="dbced-106">在代码中设置客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="dbced-106">To set the client credential type in code</span></span>  
  
1. <span data-ttu-id="dbced-107">创建服务将使用的绑定的实例。</span><span class="sxs-lookup"><span data-stu-id="dbced-107">Create an instance of the binding that the service will use.</span></span> <span data-ttu-id="dbced-108">本示例使用 <xref:System.ServiceModel.WSHttpBinding> 绑定。</span><span class="sxs-lookup"><span data-stu-id="dbced-108">This example uses the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span>  
  
2. <span data-ttu-id="dbced-109">将 <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="dbced-109">Set the <xref:System.ServiceModel.WSHttpSecurity.Mode%2A> property to an appropriate value.</span></span> <span data-ttu-id="dbced-110">本示例使用 Message 模式。</span><span class="sxs-lookup"><span data-stu-id="dbced-110">This example uses the Message mode.</span></span>  
  
3. <span data-ttu-id="dbced-111">将 <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="dbced-111">Set the <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> property to an appropriate value.</span></span> <span data-ttu-id="dbced-112">本示例将其设置为使用 Windows 身份验证 (<xref:System.ServiceModel.MessageCredentialType.Windows>)。</span><span class="sxs-lookup"><span data-stu-id="dbced-112">This example sets it to use Windows authentication (<xref:System.ServiceModel.MessageCredentialType.Windows>).</span></span>  
  
     [!code-csharp[c_ProgrammingSecurity#14](../../../samples/snippets/csharp/VS_Snippets_CFX/c_programmingsecurity/cs/source.cs#14)]
     [!code-vb[c_ProgrammingSecurity#14](../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_programmingsecurity/vb/source.vb#14)]  
  
### <a name="to-set-the-client-credential-type-in-configuration"></a><span data-ttu-id="dbced-113">在配置中设置客户端凭据类型</span><span class="sxs-lookup"><span data-stu-id="dbced-113">To set the client credential type in configuration</span></span>  
  
1. <span data-ttu-id="dbced-114">添加[ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)到配置文件的元素。</span><span class="sxs-lookup"><span data-stu-id="dbced-114">Add a [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element to the configuration file.</span></span>  
  
2. <span data-ttu-id="dbced-115">作为子元素添加[\<绑定 >](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)元素。</span><span class="sxs-lookup"><span data-stu-id="dbced-115">As a child element, add a [\<bindings>](../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
3. <span data-ttu-id="dbced-116">添加一个相应的绑定。</span><span class="sxs-lookup"><span data-stu-id="dbced-116">Add an appropriate binding.</span></span> <span data-ttu-id="dbced-117">此示例使用[ \<wsHttpBinding >](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)元素。</span><span class="sxs-lookup"><span data-stu-id="dbced-117">This example uses the [\<wsHttpBinding>](../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>  
  
4. <span data-ttu-id="dbced-118">添加[\<绑定 >](../../../docs/framework/misc/binding.md)元素，并设置`name`属性为适当的值。</span><span class="sxs-lookup"><span data-stu-id="dbced-118">Add a [\<binding>](../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="dbced-119">本示例使用名称“SecureBinding”。</span><span class="sxs-lookup"><span data-stu-id="dbced-119">This example uses the name "SecureBinding".</span></span>  
  
5. <span data-ttu-id="dbced-120">添加一个 `<security>` 绑定。</span><span class="sxs-lookup"><span data-stu-id="dbced-120">Add a `<security>` binding.</span></span> <span data-ttu-id="dbced-121">将 `mode` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="dbced-121">Set the `mode` attribute to an appropriate value.</span></span> <span data-ttu-id="dbced-122">本示例将其设置为 `"Message"`。</span><span class="sxs-lookup"><span data-stu-id="dbced-122">This example sets it to `"Message"`.</span></span>  
  
6. <span data-ttu-id="dbced-123">添加一个 `<message>` 或 `<transport>` 元素，具体由安全模式确定。</span><span class="sxs-lookup"><span data-stu-id="dbced-123">Add either a `<message>` or `<transport>` element, as determined by the security mode.</span></span> <span data-ttu-id="dbced-124">将 `clientCredentialType` 属性设置为适当的值。</span><span class="sxs-lookup"><span data-stu-id="dbced-124">Set the `clientCredentialType` attribute to an appropriate value.</span></span> <span data-ttu-id="dbced-125">本示例使用 `"Windows"`。</span><span class="sxs-lookup"><span data-stu-id="dbced-125">This example uses `"Windows"`.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="dbced-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="dbced-126">See also</span></span>

- [<span data-ttu-id="dbced-127">保护服务</span><span class="sxs-lookup"><span data-stu-id="dbced-127">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)
- [<span data-ttu-id="dbced-128">如何：将安全模式设置</span><span class="sxs-lookup"><span data-stu-id="dbced-128">How to: Set the Security Mode</span></span>](../../../docs/framework/wcf/how-to-set-the-security-mode.md)
