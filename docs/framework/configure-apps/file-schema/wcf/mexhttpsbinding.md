---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 2bd34de1417db45ba4dfd3bfdc9519b055ed695d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55276713"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="0b732-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="0b732-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="0b732-102">指定用于通过 HTTPS 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="0b732-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
 <span data-ttu-id="0b732-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0b732-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="0b732-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0b732-104">\<bindings></span></span>  
<span data-ttu-id="0b732-105">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="0b732-105">\<mexHttpsBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b732-106">语法</span><span class="sxs-lookup"><span data-stu-id="0b732-106">Syntax</span></span>  
  
```xml  
<mexHttpsBinding>
  <binding closeTimeout="TimeSpan"
            name="string"
            openTimeout="TimeSpan"
            receiveTimeout="TimeSpan"
            sendTimeout="TimeSpan">
  </binding>
</mexHttpsBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0b732-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="0b732-107">Attributes and Elements</span></span>  
 <span data-ttu-id="0b732-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="0b732-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0b732-109">特性</span><span class="sxs-lookup"><span data-stu-id="0b732-109">Attributes</span></span>  
  
|<span data-ttu-id="0b732-110">特性</span><span class="sxs-lookup"><span data-stu-id="0b732-110">Attribute</span></span>|<span data-ttu-id="0b732-111">描述</span><span class="sxs-lookup"><span data-stu-id="0b732-111">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="0b732-112">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0b732-112">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="0b732-113">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0b732-113">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b732-114">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="0b732-114">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="0b732-115">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="0b732-115">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="0b732-116">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0b732-116">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="0b732-117">每个绑定都具有 `name` 和 `namespace` 属性，它们共同在服务的元数据中唯一标识每个绑定。</span><span class="sxs-lookup"><span data-stu-id="0b732-117">Each binding has a `name` and `namespace` attribute that together uniquely identify it in the metadata of the service.</span></span> <span data-ttu-id="0b732-118">此外，在同一类型的绑定中，此名称是唯一的。</span><span class="sxs-lookup"><span data-stu-id="0b732-118">In addition, this name is unique among bindings of the same type.</span></span> <span data-ttu-id="0b732-119">从 [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)] 开始，不要求绑定和行为具有名称。</span><span class="sxs-lookup"><span data-stu-id="0b732-119">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="0b732-120">有关默认配置以及无名称绑定和行为的详细信息，请参阅[Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="0b732-120">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="0b732-121">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0b732-121">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="0b732-122">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0b732-122">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b732-123">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="0b732-123">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="0b732-124">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0b732-124">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="0b732-125">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0b732-125">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b732-126">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="0b732-126">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="0b732-127">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="0b732-127">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="0b732-128">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="0b732-128">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="0b732-129">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="0b732-129">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0b732-130">子元素</span><span class="sxs-lookup"><span data-stu-id="0b732-130">Child Elements</span></span>  
 <span data-ttu-id="0b732-131">无。</span><span class="sxs-lookup"><span data-stu-id="0b732-131">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0b732-132">父元素</span><span class="sxs-lookup"><span data-stu-id="0b732-132">Parent Elements</span></span>  
  
|<span data-ttu-id="0b732-133">元素</span><span class="sxs-lookup"><span data-stu-id="0b732-133">Element</span></span>|<span data-ttu-id="0b732-134">描述</span><span class="sxs-lookup"><span data-stu-id="0b732-134">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0b732-135">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0b732-135">\<bindings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|<span data-ttu-id="0b732-136">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="0b732-136">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0b732-137">备注</span><span class="sxs-lookup"><span data-stu-id="0b732-137">Remarks</span></span>  
 <span data-ttu-id="0b732-138">此绑定实质上是支持使用证书的传输级安全性的 `WSHttpBinding` 绑定。</span><span class="sxs-lookup"><span data-stu-id="0b732-138">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="0b732-139">有关配置和使用此类的元数据终结点的详细信息，请参阅[如何：配置自定义 Ws-metadata Exchange 绑定](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)，[如何：检索元数据通过非 MEX 绑定](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)，示例和示例[自定义安全元数据终结点](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="0b732-139">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b732-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b732-140">See also</span></span>
- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="0b732-141">如何：发布使用配置文件服务的元数据</span><span class="sxs-lookup"><span data-stu-id="0b732-141">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="0b732-142">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="0b732-142">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../../../docs/framework/wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="0b732-143">如何：配置自定义 Ws-metadata Exchange 绑定</span><span class="sxs-lookup"><span data-stu-id="0b732-143">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="0b732-144">如何：检索元数据通过非 MEX 绑定</span><span class="sxs-lookup"><span data-stu-id="0b732-144">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../../../docs/framework/wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="0b732-145">自定义元数据终结点</span><span class="sxs-lookup"><span data-stu-id="0b732-145">Custom Secure Metadata Endpoint</span></span>](../../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="0b732-146">元数据</span><span class="sxs-lookup"><span data-stu-id="0b732-146">Metadata</span></span>](../../../../../docs/framework/wcf/feature-details/metadata.md)
- [<span data-ttu-id="0b732-147">绑定</span><span class="sxs-lookup"><span data-stu-id="0b732-147">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0b732-148">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="0b732-148">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0b732-149">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="0b732-149">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0b732-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="0b732-150">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
