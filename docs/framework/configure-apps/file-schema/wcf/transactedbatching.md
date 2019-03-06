---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 43415d9eac5e61f42006aecb3248dec9811eb3e6
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57366447"
---
# <a name="transactedbatching"></a><span data-ttu-id="c45ec-101">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="c45ec-101">\<transactedBatching></span></span>

<span data-ttu-id="c45ec-102">指定接收操作是否支持事务批处理。</span><span class="sxs-lookup"><span data-stu-id="c45ec-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="c45ec-103">\<system.ServiceModel>\\</span><span class="sxs-lookup"><span data-stu-id="c45ec-103">\<system.ServiceModel>\\</span></span>
<span data-ttu-id="c45ec-104">\<behaviors>\\</span><span class="sxs-lookup"><span data-stu-id="c45ec-104">\<behaviors>\\</span></span>
<span data-ttu-id="c45ec-105">\<endpointBehaviors>\\</span><span class="sxs-lookup"><span data-stu-id="c45ec-105">\<endpointBehaviors>\\</span></span>
<span data-ttu-id="c45ec-106">\<behavior>\\</span><span class="sxs-lookup"><span data-stu-id="c45ec-106">\<behavior>\\</span></span>
<span data-ttu-id="c45ec-107">\<transactedBatching></span><span class="sxs-lookup"><span data-stu-id="c45ec-107">\<transactedBatching></span></span>

## <a name="syntax"></a><span data-ttu-id="c45ec-108">语法</span><span class="sxs-lookup"><span data-stu-id="c45ec-108">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="c45ec-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="c45ec-109">Attributes and Elements</span></span>

<span data-ttu-id="c45ec-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="c45ec-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="c45ec-111">特性</span><span class="sxs-lookup"><span data-stu-id="c45ec-111">Attributes</span></span>

|<span data-ttu-id="c45ec-112">特性</span><span class="sxs-lookup"><span data-stu-id="c45ec-112">Attribute</span></span>|<span data-ttu-id="c45ec-113">描述</span><span class="sxs-lookup"><span data-stu-id="c45ec-113">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="c45ec-114">一个整数，指定可一起成批归入到一个事务中的最大接收操作数。</span><span class="sxs-lookup"><span data-stu-id="c45ec-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="c45ec-115">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="c45ec-115">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="c45ec-116">子元素</span><span class="sxs-lookup"><span data-stu-id="c45ec-116">Child Elements</span></span>

<span data-ttu-id="c45ec-117">无。</span><span class="sxs-lookup"><span data-stu-id="c45ec-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="c45ec-118">父元素</span><span class="sxs-lookup"><span data-stu-id="c45ec-118">Parent Elements</span></span>

|<span data-ttu-id="c45ec-119">元素</span><span class="sxs-lookup"><span data-stu-id="c45ec-119">Element</span></span>|<span data-ttu-id="c45ec-120">描述</span><span class="sxs-lookup"><span data-stu-id="c45ec-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="c45ec-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="c45ec-121">\<behavior></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|<span data-ttu-id="c45ec-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="c45ec-122">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="c45ec-123">备注</span><span class="sxs-lookup"><span data-stu-id="c45ec-123">Remarks</span></span>

<span data-ttu-id="c45ec-124">采用事务批处理配置的传输尝试将若干接收操作成批归入到一个事务中。</span><span class="sxs-lookup"><span data-stu-id="c45ec-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="c45ec-125">这样做可以避免因创建事务以及在每个接收操作中提交事务所产生的相对较高的成本。</span><span class="sxs-lookup"><span data-stu-id="c45ec-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="c45ec-126">示例</span><span class="sxs-lookup"><span data-stu-id="c45ec-126">Example</span></span>

<span data-ttu-id="c45ec-127">下面的示例演示如何将事务处理批处理行为添加到配置文件中的服务。</span><span class="sxs-lookup"><span data-stu-id="c45ec-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

```xml
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- Define NetMsmqEndpoint -->
      <endpoint address="net.msmq://localhost/private/ServiceModelSamples"
                binding="netMsmqBinding"
                contract="Microsoft.ServiceModel.Samples.IQueueCalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <behaviors>
    <endpointBehaviors>
      <behavior name="endpointBehavior">
        <transactedBatching maxBatchSize="10" />
      </behavior>
    </endpointBehaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="true" />
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```

## <a name="see-also"></a><span data-ttu-id="c45ec-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="c45ec-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
