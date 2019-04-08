---
title: 如何：设置最大时钟偏差
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MaxClockSkew property
- WCF, custom bindings
ms.assetid: 491d1705-eb29-43c2-a44c-c0cf996f74eb
ms.openlocfilehash: e487da6316ec381c2009ee33575848dd80df8ab2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59076623"
---
# <a name="how-to-set-a-max-clock-skew"></a><span data-ttu-id="52fc1-102">如何：设置最大时钟偏差</span><span class="sxs-lookup"><span data-stu-id="52fc1-102">How to: Set a Max Clock Skew</span></span>
<span data-ttu-id="52fc1-103">如果两台计算机上的时钟设置不同，时间关键函数可能无法正常执行。</span><span class="sxs-lookup"><span data-stu-id="52fc1-103">Time-critical functions can be derailed if the clock settings on two computers are different.</span></span> <span data-ttu-id="52fc1-104">若要减小这种可能性，可以将 `MaxClockSkew` 属性设置为一个 <xref:System.TimeSpan>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-104">To mitigate this possibility, you can set the `MaxClockSkew` property to a <xref:System.TimeSpan>.</span></span> <span data-ttu-id="52fc1-105">可在两个类上获得此属性：</span><span class="sxs-lookup"><span data-stu-id="52fc1-105">This property is available on two classes:</span></span>  
  
 <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>  
  
 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>  
  
> [!IMPORTANT]
>  <span data-ttu-id="52fc1-106">重要事项对于安全对话，更改为`MaxClockSkew`引导服务或客户端时，必须考虑属性。</span><span class="sxs-lookup"><span data-stu-id="52fc1-106">Important   For a secure conversation, changes to the `MaxClockSkew` property  must be made when the service or client is bootstrapped.</span></span> <span data-ttu-id="52fc1-107">若要执行此操作，必须设置该属性上<xref:System.ServiceModel.Channels.SecurityBindingElement>返回的<xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-107">To do this, you must set the property on the <xref:System.ServiceModel.Channels.SecurityBindingElement> returned by the <xref:System.ServiceModel.Security.Tokens.SecureConversationSecurityTokenParameters.BootstrapSecurityBindingElement%2A>.</span></span>  
  
 <span data-ttu-id="52fc1-108">若要更改系统提供的绑定之一上的属性，必须在绑定集合中找到安全绑定元素，然后将 `MaxClockSkew` 属性设置为一个新值。</span><span class="sxs-lookup"><span data-stu-id="52fc1-108">To change the property on one of the system-provided bindings, you must find the security binding element in the collection of bindings and set the `MaxClockSkew` property to a new value.</span></span> <span data-ttu-id="52fc1-109">两个类派生自 <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 和 <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-109">Two classes derive from the <xref:System.ServiceModel.Channels.SecurityBindingElement>: <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> and <xref:System.ServiceModel.Channels.AsymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="52fc1-110">从该集合中检索安全绑定时，必须将其强制转换为上述类型之一，以便正确设置 `MaxClockSkew` 属性。</span><span class="sxs-lookup"><span data-stu-id="52fc1-110">When retrieving the security binding from the collection, you must cast to one of these types in order to correctly set the `MaxClockSkew` property.</span></span> <span data-ttu-id="52fc1-111">下面的示例使用了一个 <xref:System.ServiceModel.WSHttpBinding>，它使用了 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-111">The following example uses a <xref:System.ServiceModel.WSHttpBinding>, which uses the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement>.</span></span> <span data-ttu-id="52fc1-112">指定哪种类型的安全绑定，以在每个系统提供的绑定中使用的列表，请参阅[System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="52fc1-112">For a list that specifies which type of security binding to use in each system-provided binding, see [System-Provided Bindings](../../../../docs/framework/wcf/system-provided-bindings.md).</span></span>  
  
### <a name="to-create-a-custom-binding-with-a-new-clock-skew-value-in-code"></a><span data-ttu-id="52fc1-113">在代码中使用新的时钟偏差值创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="52fc1-113">To create a custom binding with a new clock skew value in code</span></span>  
  
1.  > [!WARNING]
    >  <span data-ttu-id="52fc1-114">请注意添加到你的代码中的以下命名空间的引用： <xref:System.ServiceModel.Channels>， <xref:System.ServiceModel.Description>， <xref:System.Security.Permissions>，和<xref:System.ServiceModel.Security.Tokens>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-114">Note   Add references to the following namespaces in your code: <xref:System.ServiceModel.Channels>, <xref:System.ServiceModel.Description>, <xref:System.Security.Permissions>, and <xref:System.ServiceModel.Security.Tokens>.</span></span>  
  
     <span data-ttu-id="52fc1-115">创建 <xref:System.ServiceModel.WSHttpBinding> 类的一个实例，并将其安全模式设置为 <xref:System.ServiceModel.SecurityMode.Message>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-115">Create an instance of a <xref:System.ServiceModel.WSHttpBinding> class and set its security mode to <xref:System.ServiceModel.SecurityMode.Message>.</span></span>  
  
2.  <span data-ttu-id="52fc1-116">调用 <xref:System.ServiceModel.Channels.BindingElementCollection> 方法，以此创建 <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> 的一个新实例。</span><span class="sxs-lookup"><span data-stu-id="52fc1-116">Create a new instance of the <xref:System.ServiceModel.Channels.BindingElementCollection> class by calling the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3.  <span data-ttu-id="52fc1-117">使用 <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> 类的 <xref:System.ServiceModel.Channels.BindingElementCollection> 方法来查找安全绑定元素。</span><span class="sxs-lookup"><span data-stu-id="52fc1-117">Use the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method of the <xref:System.ServiceModel.Channels.BindingElementCollection> class to find the security binding element.</span></span>  
  
4.  <span data-ttu-id="52fc1-118">使用 <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> 方法时，将其强制转换为实际类型。</span><span class="sxs-lookup"><span data-stu-id="52fc1-118">When using the <xref:System.ServiceModel.Channels.BindingElementCollection.Find%2A> method, cast to the actual type.</span></span> <span data-ttu-id="52fc1-119">下面的示例将其强制转换为 <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> 类型。</span><span class="sxs-lookup"><span data-stu-id="52fc1-119">The example below casts to the <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> type.</span></span>  
  
5.  <span data-ttu-id="52fc1-120">设置安全绑定元素上的 <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="52fc1-120">Set the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.MaxClockSkew%2A> property on the security binding element.</span></span>  
  
6.  <span data-ttu-id="52fc1-121">使用适当的服务类型和基址创建一个 <xref:System.ServiceModel.ServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-121">Create a <xref:System.ServiceModel.ServiceHost> with an appropriate service type and base address.</span></span>  
  
7.  <span data-ttu-id="52fc1-122">使用 <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> 方法添加一个终结点并包含该 <xref:System.ServiceModel.Channels.CustomBinding>。</span><span class="sxs-lookup"><span data-stu-id="52fc1-122">Use the <xref:System.ServiceModel.ServiceHost.AddServiceEndpoint%2A> method to add an endpoint and include the <xref:System.ServiceModel.Channels.CustomBinding>.</span></span>  
  
     [!code-csharp[c_MaxClockSkew#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_maxclockskew/cs/source.cs#1)]
     [!code-vb[c_MaxClockSkew#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_maxclockskew/vb/source.vb#1)]  
  
### <a name="to-set-the-maxclockskew-in-configuration"></a><span data-ttu-id="52fc1-123">在配置中设置 MaxClockSkew</span><span class="sxs-lookup"><span data-stu-id="52fc1-123">To set the MaxClockSkew in configuration</span></span>  
  
1.  <span data-ttu-id="52fc1-124">创建[ \<customBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)中[\<绑定 >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)元素节的配置。</span><span class="sxs-lookup"><span data-stu-id="52fc1-124">Create a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) in the [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element section.</span></span>  
  
2.  <span data-ttu-id="52fc1-125">创建[\<绑定 >](../../../../docs/framework/misc/binding.md)元素，并设置`name`属性为适当的值。</span><span class="sxs-lookup"><span data-stu-id="52fc1-125">Create a [\<binding>](../../../../docs/framework/misc/binding.md) element and set the `name` attribute to an appropriate value.</span></span> <span data-ttu-id="52fc1-126">下面的示例将其设置为 `MaxClockSkewBinding`。</span><span class="sxs-lookup"><span data-stu-id="52fc1-126">The following example sets it to `MaxClockSkewBinding`.</span></span>  
  
3.  <span data-ttu-id="52fc1-127">添加一个编码元素。</span><span class="sxs-lookup"><span data-stu-id="52fc1-127">Add an encoding element.</span></span> <span data-ttu-id="52fc1-128">下面的示例添加[ \<textMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md)。</span><span class="sxs-lookup"><span data-stu-id="52fc1-128">The example below adds a [\<textMessageEncoding>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md).</span></span>  
  
4.  <span data-ttu-id="52fc1-129">添加[\<安全 >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)元素，并设置`authenticationMode`属性为适当的设置。</span><span class="sxs-lookup"><span data-stu-id="52fc1-129">Add a [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) element and set the `authenticationMode` attribute to an appropriate setting.</span></span> <span data-ttu-id="52fc1-130">下面的示例将该属性设置为 `Kerberos`，以指定服务使用 Windows 身份验证。</span><span class="sxs-lookup"><span data-stu-id="52fc1-130">The following example set the attribute to `Kerberos` to specify that the service use Windows authentication.</span></span>  
  
5.  <span data-ttu-id="52fc1-131">添加[ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)并设置`maxClockSkew`属性中的窗体的值为`"##:##:##"`。</span><span class="sxs-lookup"><span data-stu-id="52fc1-131">Add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to a value in the form of `"##:##:##"`.</span></span> <span data-ttu-id="52fc1-132">下面的示例将其设置为 7 分钟。</span><span class="sxs-lookup"><span data-stu-id="52fc1-132">The following example sets it to 7 minutes.</span></span> <span data-ttu-id="52fc1-133">（可选） 添加[ \<localServiceSettings >](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)并设置`maxClockSkew`属性为适当的设置。</span><span class="sxs-lookup"><span data-stu-id="52fc1-133">Optionally, add a [\<localServiceSettings>](../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md) and set the `maxClockSkew` attribute to an appropriate setting.</span></span>  
  
6.  <span data-ttu-id="52fc1-134">添加一个传输元素。</span><span class="sxs-lookup"><span data-stu-id="52fc1-134">Add a transport element.</span></span> <span data-ttu-id="52fc1-135">下面的示例使用[ \<httpTransport >](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md)。</span><span class="sxs-lookup"><span data-stu-id="52fc1-135">The following example uses an [\<httpTransport>](../../../../docs/framework/configure-apps/file-schema/wcf/httptransport.md).</span></span>  
  
7.  <span data-ttu-id="52fc1-136">对于安全对话安全设置必须出现在中 bootstrap [ \<secureConversationBootstrap >](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)元素。</span><span class="sxs-lookup"><span data-stu-id="52fc1-136">For a secure conversation, the security settings must occur at the bootstrap in the [\<secureConversationBootstrap>](../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md) element.</span></span>  
  
    ```xml  
    <bindings>  
      <customBinding>  
        <binding name="MaxClockSkewBinding">  
            <textMessageEncoding />  
            <security authenticationMode="Kerberos">  
               <localClientSettings maxClockSkew="00:07:00" />  
               <localServiceSettings maxClockSkew="00:07:00" />  
               <secureConversationBootstrap>  
                  <localClientSettings maxClockSkew="00:30:00" />  
                  <localServiceSettings maxClockSkew="00:30:00" />  
               </secureConversationBootstrap>  
            </security>  
            <httpTransport />  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="52fc1-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="52fc1-137">See also</span></span>

- <xref:System.ServiceModel.Channels.LocalClientSecuritySettings>
- <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="52fc1-138">如何：使用 SecurityBindingElement 创建自定义绑定</span><span class="sxs-lookup"><span data-stu-id="52fc1-138">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
