---
title: <mexHttpsBinding>
ms.date: 03/30/2017
ms.assetid: f2ed3774-78b9-4a15-b79b-655f1ad68b86
ms.openlocfilehash: 924d68dd828622b74c5e424a695f80874391b453
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430337"
---
# <a name="mexhttpsbinding"></a><span data-ttu-id="48714-101">\<mexHttpsBinding></span><span class="sxs-lookup"><span data-stu-id="48714-101">\<mexHttpsBinding></span></span>
<span data-ttu-id="48714-102">指定用于通过 HTTPS 进行的 WS-MetadataExchange (WS-MEX) 消息交换的绑定的设置。</span><span class="sxs-lookup"><span data-stu-id="48714-102">Specifies the settings for a binding used for the WS-MetadataExchange (WS-MEX) message exchange over HTTPS.</span></span>  
  
<span data-ttu-id="48714-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="48714-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="48714-104">&nbsp;&nbsp;[ **\<system.serviceModel>** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="48714-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="48714-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<bindings>** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="48714-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="48714-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<mexHttpsBinding>**</span><span class="sxs-lookup"><span data-stu-id="48714-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<mexHttpsBinding>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48714-107">语法</span><span class="sxs-lookup"><span data-stu-id="48714-107">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="48714-108">特性和元素</span><span class="sxs-lookup"><span data-stu-id="48714-108">Attributes and Elements</span></span>  
 <span data-ttu-id="48714-109">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="48714-109">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="48714-110">特性</span><span class="sxs-lookup"><span data-stu-id="48714-110">Attributes</span></span>  
  
|<span data-ttu-id="48714-111">特性</span><span class="sxs-lookup"><span data-stu-id="48714-111">Attribute</span></span>|<span data-ttu-id="48714-112">描述</span><span class="sxs-lookup"><span data-stu-id="48714-112">Description</span></span>|  
|---------------|-----------------|  
|`closeTimeout`|<span data-ttu-id="48714-113">一个 <xref:System.TimeSpan> 值，指定为完成关闭操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="48714-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="48714-114">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="48714-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48714-115">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="48714-115">The default is 00:01:00.</span></span>|  
|`name`|<span data-ttu-id="48714-116">一个包含绑定的配置名称的字符串。</span><span class="sxs-lookup"><span data-stu-id="48714-116">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="48714-117">因为此值用作绑定的标识，所以它应该是唯一的。</span><span class="sxs-lookup"><span data-stu-id="48714-117">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="48714-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span><span class="sxs-lookup"><span data-stu-id="48714-118">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="48714-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span><span class="sxs-lookup"><span data-stu-id="48714-119">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|`openTimeout`|<span data-ttu-id="48714-120">一个 <xref:System.TimeSpan> 值，指定为完成打开操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="48714-120">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="48714-121">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="48714-121">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48714-122">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="48714-122">The default is 00:01:00.</span></span>|  
|`receiveTimeout`|<span data-ttu-id="48714-123">一个 <xref:System.TimeSpan> 值，指定为完成接收操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="48714-123">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="48714-124">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="48714-124">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48714-125">默认值为 00:10:00。</span><span class="sxs-lookup"><span data-stu-id="48714-125">The default is 00:10:00.</span></span>|  
|`sendTimeout`|<span data-ttu-id="48714-126">一个 <xref:System.TimeSpan> 值，指定为完成发送操作提供的时间间隔。</span><span class="sxs-lookup"><span data-stu-id="48714-126">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="48714-127">此值应大于或等于 <xref:System.TimeSpan.Zero>。</span><span class="sxs-lookup"><span data-stu-id="48714-127">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="48714-128">默认值为 00:01:00。</span><span class="sxs-lookup"><span data-stu-id="48714-128">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="48714-129">子元素</span><span class="sxs-lookup"><span data-stu-id="48714-129">Child Elements</span></span>  
 <span data-ttu-id="48714-130">无。</span><span class="sxs-lookup"><span data-stu-id="48714-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="48714-131">父元素</span><span class="sxs-lookup"><span data-stu-id="48714-131">Parent Elements</span></span>  
  
|<span data-ttu-id="48714-132">元素</span><span class="sxs-lookup"><span data-stu-id="48714-132">Element</span></span>|<span data-ttu-id="48714-133">描述</span><span class="sxs-lookup"><span data-stu-id="48714-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="48714-134">\<bindings></span><span class="sxs-lookup"><span data-stu-id="48714-134">\<bindings></span></span>](bindings.md)|<span data-ttu-id="48714-135">此元素包含标准绑定和自定义绑定的集合。</span><span class="sxs-lookup"><span data-stu-id="48714-135">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48714-136">备注</span><span class="sxs-lookup"><span data-stu-id="48714-136">Remarks</span></span>  
 <span data-ttu-id="48714-137">此绑定实质上是支持使用证书的传输级安全性的 `WSHttpBinding` 绑定。</span><span class="sxs-lookup"><span data-stu-id="48714-137">This binding is essentially a `WSHttpBinding` binding that supports transport-level security using certificates.</span></span> <span data-ttu-id="48714-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span><span class="sxs-lookup"><span data-stu-id="48714-138">For more information about configuring and using such a metadata endpoint, see [How to: Configure a Custom WS-Metadata Exchange Binding](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md), [How to: Retrieve Metadata Over a non-MEX Binding](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md), and the sample [Custom Secure Metadata Endpoint](../../../wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48714-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="48714-139">See also</span></span>

- <xref:System.ServiceModel.Description.MetadataExchangeBindings.CreateMexHttpsBinding%2A>
- <xref:System.ServiceModel.Configuration.MexHttpsBindingElement>
- [<span data-ttu-id="48714-140">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="48714-140">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
- [<span data-ttu-id="48714-141">通过自定义绑定发布和检索元数据</span><span class="sxs-lookup"><span data-stu-id="48714-141">Publishing and Retrieving Metadata Over a Custom Binding</span></span>](../../../wcf/extending/publishing-and-retrieving-metadata-over-a-custom-binding.md)
- [<span data-ttu-id="48714-142">如何：配置自定义 WS-Metadata Exchange 绑定</span><span class="sxs-lookup"><span data-stu-id="48714-142">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>](../../../wcf/extending/how-to-configure-a-custom-ws-metadata-exchange-binding.md)
- [<span data-ttu-id="48714-143">如何：通过非 MEX 绑定检索元数据</span><span class="sxs-lookup"><span data-stu-id="48714-143">How to: Retrieve Metadata Over a non-MEX Binding</span></span>](../../../wcf/extending/how-to-retrieve-metadata-over-a-non-mex-binding.md)
- [<span data-ttu-id="48714-144">自定义元数据终结点</span><span class="sxs-lookup"><span data-stu-id="48714-144">Custom Secure Metadata Endpoint</span></span>](../../../wcf/samples/custom-secure-metadata-endpoint.md)
- [<span data-ttu-id="48714-145">元数据</span><span class="sxs-lookup"><span data-stu-id="48714-145">Metadata</span></span>](../../../wcf/feature-details/metadata.md)
- [<span data-ttu-id="48714-146">绑定</span><span class="sxs-lookup"><span data-stu-id="48714-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="48714-147">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="48714-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="48714-148">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="48714-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="48714-149">\<binding></span><span class="sxs-lookup"><span data-stu-id="48714-149">\<binding></span></span>](bindings.md)
