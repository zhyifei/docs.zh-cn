---
title: <transactedBatching>
ms.date: 03/30/2017
ms.assetid: 2f790a0d-8f03-4b86-81b5-ce1bc1a6c575
ms.openlocfilehash: 12369f1053638583a3864fab396869d0e7045732
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918667"
---
# <a name="transactedbatching"></a><span data-ttu-id="d7610-101">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="d7610-101">\<transactedBatching></span></span>

<span data-ttu-id="d7610-102">指定接收操作是否支持事务批处理。</span><span class="sxs-lookup"><span data-stu-id="d7610-102">Specifies whether transaction batching is supported for receive operations.</span></span>

<span data-ttu-id="d7610-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d7610-103">\<system.ServiceModel></span></span>\
<span data-ttu-id="d7610-104">\<行为 > </span><span class="sxs-lookup"><span data-stu-id="d7610-104">\<behaviors></span></span>\
<span data-ttu-id="d7610-105">\<endpointBehaviors > </span><span class="sxs-lookup"><span data-stu-id="d7610-105">\<endpointBehaviors></span></span>\
<span data-ttu-id="d7610-106">\<行为 > </span><span class="sxs-lookup"><span data-stu-id="d7610-106">\<behavior></span></span>\
<span data-ttu-id="d7610-107">\<transactedBatching ></span><span class="sxs-lookup"><span data-stu-id="d7610-107">\<transactedBatching></span></span>

## <a name="syntax"></a><span data-ttu-id="d7610-108">语法</span><span class="sxs-lookup"><span data-stu-id="d7610-108">Syntax</span></span>

```xml
<transactedBatching maxBatchSize="Integer" />
```

## <a name="attributes-and-elements"></a><span data-ttu-id="d7610-109">特性和元素</span><span class="sxs-lookup"><span data-stu-id="d7610-109">Attributes and Elements</span></span>

<span data-ttu-id="d7610-110">下列各节描述了特性、子元素和父元素。</span><span class="sxs-lookup"><span data-stu-id="d7610-110">The following sections describe attributes, child elements, and parent elements.</span></span>

### <a name="attributes"></a><span data-ttu-id="d7610-111">特性</span><span class="sxs-lookup"><span data-stu-id="d7610-111">Attributes</span></span>

|<span data-ttu-id="d7610-112">特性</span><span class="sxs-lookup"><span data-stu-id="d7610-112">Attribute</span></span>|<span data-ttu-id="d7610-113">描述</span><span class="sxs-lookup"><span data-stu-id="d7610-113">Description</span></span>|
|---------------|-----------------|
|`maxBatchSize`|<span data-ttu-id="d7610-114">一个整数，指定可一起成批归入到一个事务中的最大接收操作数。</span><span class="sxs-lookup"><span data-stu-id="d7610-114">An integer that specifies the maximum number of receive operations that can be batched together in one transaction.</span></span> <span data-ttu-id="d7610-115">默认值为 0。</span><span class="sxs-lookup"><span data-stu-id="d7610-115">The default is 0.</span></span>|

### <a name="child-elements"></a><span data-ttu-id="d7610-116">子元素</span><span class="sxs-lookup"><span data-stu-id="d7610-116">Child Elements</span></span>

<span data-ttu-id="d7610-117">无。</span><span class="sxs-lookup"><span data-stu-id="d7610-117">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="d7610-118">父元素</span><span class="sxs-lookup"><span data-stu-id="d7610-118">Parent Elements</span></span>

|<span data-ttu-id="d7610-119">元素</span><span class="sxs-lookup"><span data-stu-id="d7610-119">Element</span></span>|<span data-ttu-id="d7610-120">描述</span><span class="sxs-lookup"><span data-stu-id="d7610-120">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="d7610-121">\<behavior></span><span class="sxs-lookup"><span data-stu-id="d7610-121">\<behavior></span></span>](behavior-of-endpointbehaviors.md)|<span data-ttu-id="d7610-122">指定终结点行为。</span><span class="sxs-lookup"><span data-stu-id="d7610-122">Specifies an endpoint behavior.</span></span>|

## <a name="remarks"></a><span data-ttu-id="d7610-123">备注</span><span class="sxs-lookup"><span data-stu-id="d7610-123">Remarks</span></span>

<span data-ttu-id="d7610-124">采用事务批处理配置的传输尝试将若干接收操作成批归入到一个事务中。</span><span class="sxs-lookup"><span data-stu-id="d7610-124">A transport that is configured with transaction batching attempts to batch several receive operations into one transaction.</span></span> <span data-ttu-id="d7610-125">这样做可以避免因创建事务以及在每个接收操作中提交事务所产生的相对较高的成本。</span><span class="sxs-lookup"><span data-stu-id="d7610-125">By doing so, the relatively high cost of creating a transaction and committing it in every receive operation is avoided.</span></span>

## <a name="example"></a><span data-ttu-id="d7610-126">示例</span><span class="sxs-lookup"><span data-stu-id="d7610-126">Example</span></span>

<span data-ttu-id="d7610-127">下面的示例演示如何将事务处理批处理行为添加到配置文件中的服务。</span><span class="sxs-lookup"><span data-stu-id="d7610-127">The following example shows how to add the transacted batching behavior to a service in a configuration file.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="d7610-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7610-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.TransactedBatchingElement>
- <xref:System.ServiceModel.Description.TransactedBatchingBehavior>
