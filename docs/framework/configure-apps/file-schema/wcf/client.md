---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7aa3755be97a839cb576d53852b75cfe50e39276
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/22/2019
ms.locfileid: "72773943"
---
# <a name="client"></a><span data-ttu-id="b6805-101">\<client ></span><span class="sxs-lookup"><span data-stu-id="b6805-101">\<client></span></span>
<span data-ttu-id="b6805-102">`client` 元素定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="b6805-102">The `client` element defines a list of endpoints that a client can connect to.</span></span>

<span data-ttu-id="b6805-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b6805-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b6805-104">\<system &nbsp; &nbsp;[ **>** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="b6805-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b6805-105">&nbsp; &nbsp; &nbsp; &nbsp; **\<client >**</span><span class="sxs-lookup"><span data-stu-id="b6805-105">&nbsp;&nbsp;&nbsp;&nbsp;**\<client>**</span></span>

## <a name="syntax"></a><span data-ttu-id="b6805-106">语法</span><span class="sxs-lookup"><span data-stu-id="b6805-106">Syntax</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="b6805-107">特性和元素</span><span class="sxs-lookup"><span data-stu-id="b6805-107">Attributes and Elements</span></span>
 <span data-ttu-id="b6805-108">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="b6805-108">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="b6805-109">特性</span><span class="sxs-lookup"><span data-stu-id="b6805-109">Attributes</span></span>
 <span data-ttu-id="b6805-110">None</span><span class="sxs-lookup"><span data-stu-id="b6805-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="b6805-111">子元素</span><span class="sxs-lookup"><span data-stu-id="b6805-111">Child Elements</span></span>

|<span data-ttu-id="b6805-112">元素</span><span class="sxs-lookup"><span data-stu-id="b6805-112">Element</span></span>|<span data-ttu-id="b6805-113">描述</span><span class="sxs-lookup"><span data-stu-id="b6805-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6805-114">\<endpoint ></span><span class="sxs-lookup"><span data-stu-id="b6805-114">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="b6805-115">包含终结点元素的集合，这些元素指定此客户端可以连接到的终结点。</span><span class="sxs-lookup"><span data-stu-id="b6805-115">Contains a collection of endpoint elements that specify the endpoints that this client can connect to.</span></span>|
|[<span data-ttu-id="b6805-116">\<metadata ></span><span class="sxs-lookup"><span data-stu-id="b6805-116">\<metadata></span></span>](metadata.md)|<span data-ttu-id="b6805-117">包含用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="b6805-117">Contains settings for processing metadata.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="b6805-118">父元素</span><span class="sxs-lookup"><span data-stu-id="b6805-118">Parent Elements</span></span>

|<span data-ttu-id="b6805-119">元素</span><span class="sxs-lookup"><span data-stu-id="b6805-119">Element</span></span>|<span data-ttu-id="b6805-120">描述</span><span class="sxs-lookup"><span data-stu-id="b6805-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="b6805-121">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b6805-121">\<system.serviceModel></span></span>](system-servicemodel.md)|<span data-ttu-id="b6805-122">所有 Windows Communication Foundation (WCF) 配置元素的根元素。</span><span class="sxs-lookup"><span data-stu-id="b6805-122">The root element of all Windows Communication Foundation (WCF) configuration elements.</span></span>|

## <a name="remarks"></a><span data-ttu-id="b6805-123">备注</span><span class="sxs-lookup"><span data-stu-id="b6805-123">Remarks</span></span>
 <span data-ttu-id="b6805-124">`client` 节定义客户端可以连接的终结点的列表。</span><span class="sxs-lookup"><span data-stu-id="b6805-124">The `client` section defines a list of endpoints that a client can connect to.</span></span> <span data-ttu-id="b6805-125">客户端节中列出的每个终结点都定义了它自己的绑定、行为和协定。</span><span class="sxs-lookup"><span data-stu-id="b6805-125">Each endpoint listed in the client section defines its own binding, behavior, and contract.</span></span> <span data-ttu-id="b6805-126">它由 `name` 和 `contract` 属性共同进行唯一标识。</span><span class="sxs-lookup"><span data-stu-id="b6805-126">It is uniquely identified by the combination of the `name` and `contract` attributes.</span></span> <span data-ttu-id="b6805-127">客户端代码指定要连接到该客户端实现的服务终结点的 `name`。</span><span class="sxs-lookup"><span data-stu-id="b6805-127">The client code specifies the `name` to connect to an endpoint for the service that the client implements.</span></span> <span data-ttu-id="b6805-128">如果省略 `name` 属性，则该终结点将作为其实现的协定的默认终结点。</span><span class="sxs-lookup"><span data-stu-id="b6805-128">If the `name` attribute is omitted, the endpoint acts as the default endpoint for the contract it implements.</span></span>

 <span data-ttu-id="b6805-129">此外，本节还指定了用于处理元数据的设置。</span><span class="sxs-lookup"><span data-stu-id="b6805-129">In addition, this section also specifies settings for processing metadata.</span></span>

## <a name="example"></a><span data-ttu-id="b6805-130">示例</span><span class="sxs-lookup"><span data-stu-id="b6805-130">Example</span></span>

```xml
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```

## <a name="see-also"></a><span data-ttu-id="b6805-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="b6805-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [<span data-ttu-id="b6805-132">WCF 客户端配置</span><span class="sxs-lookup"><span data-stu-id="b6805-132">WCF Client Configuration</span></span>](../../../wcf/feature-details/client-configuration.md)
- [<span data-ttu-id="b6805-133">客户端</span><span class="sxs-lookup"><span data-stu-id="b6805-133">Clients</span></span>](../../../wcf/feature-details/clients.md)
