---
title: "服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f7b631ede7bd011a92003dc5f6083c1c427d990e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="service"></a><span data-ttu-id="d882e-102">服务</span><span class="sxs-lookup"><span data-stu-id="d882e-102">Service</span></span>
<span data-ttu-id="d882e-103">服务</span><span class="sxs-lookup"><span data-stu-id="d882e-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d882e-104">语法</span><span class="sxs-lookup"><span data-stu-id="d882e-104">Syntax</span></span>  
  
```  
class Service  
{  
  string BaseAddresses[];  
  Behavior Behaviors[];  
  string ConfigurationName;  
  string CounterInstanceName;  
  string DistinguishedName;  
  string Extensions[];  
  string Metadata[];  
  string Name;  
  string Namespace;  
  datetime Opened;  
  Channel OutgoingChannels[];  
  sint32 ProcessId;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="d882e-105">方法</span><span class="sxs-lookup"><span data-stu-id="d882e-105">Methods</span></span>  
 <span data-ttu-id="d882e-106">Service 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="d882e-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="d882e-107">属性</span><span class="sxs-lookup"><span data-stu-id="d882e-107">Properties</span></span>  
 <span data-ttu-id="d882e-108">Service 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="d882e-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="d882e-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="d882e-109">BaseAddresses</span></span>  
 <span data-ttu-id="d882e-110">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="d882e-110">Data type: string array</span></span>  
  
 <span data-ttu-id="d882e-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-112">服务使用的基址。</span><span class="sxs-lookup"><span data-stu-id="d882e-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="d882e-113">行为</span><span class="sxs-lookup"><span data-stu-id="d882e-113">Behaviors</span></span>  
 <span data-ttu-id="d882e-114">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="d882e-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="d882e-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-116">与此服务关联的行为。</span><span class="sxs-lookup"><span data-stu-id="d882e-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="d882e-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="d882e-117">ConfigurationName</span></span>  
 <span data-ttu-id="d882e-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d882e-118">Data type: string</span></span>  
  
 <span data-ttu-id="d882e-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="d882e-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="d882e-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d882e-121">CounterInstanceName</span></span>  
 <span data-ttu-id="d882e-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d882e-122">Data type: string</span></span>  
  
 <span data-ttu-id="d882e-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-124">此服务的性能计数器实例的实例名称。</span><span class="sxs-lookup"><span data-stu-id="d882e-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="d882e-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="d882e-125">DistinguishedName</span></span>  
 <span data-ttu-id="d882e-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d882e-126">Data type: string</span></span>  
  
 <span data-ttu-id="d882e-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-128">该地址处的服务名称。</span><span class="sxs-lookup"><span data-stu-id="d882e-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="d882e-129">扩展</span><span class="sxs-lookup"><span data-stu-id="d882e-129">Extensions</span></span>  
 <span data-ttu-id="d882e-130">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="d882e-130">Data type: string array</span></span>  
  
 <span data-ttu-id="d882e-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-132">服务实例扩展的实例上下文。</span><span class="sxs-lookup"><span data-stu-id="d882e-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="d882e-133">元数据</span><span class="sxs-lookup"><span data-stu-id="d882e-133">Metadata</span></span>  
 <span data-ttu-id="d882e-134">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="d882e-134">Data type: string array</span></span>  
  
 <span data-ttu-id="d882e-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-136">服务元数据设置。</span><span class="sxs-lookup"><span data-stu-id="d882e-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d882e-137">name</span><span class="sxs-lookup"><span data-stu-id="d882e-137">Name</span></span>  
 <span data-ttu-id="d882e-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d882e-138">Data type: string</span></span>  
  
 <span data-ttu-id="d882e-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-140">此服务的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d882e-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="d882e-141">命名空间</span><span class="sxs-lookup"><span data-stu-id="d882e-141">Namespace</span></span>  
 <span data-ttu-id="d882e-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d882e-142">Data type: string</span></span>  
  
 <span data-ttu-id="d882e-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-144">服务的命名空间。</span><span class="sxs-lookup"><span data-stu-id="d882e-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="d882e-145">已打开</span><span class="sxs-lookup"><span data-stu-id="d882e-145">Opened</span></span>  
 <span data-ttu-id="d882e-146">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="d882e-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="d882e-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-148">服务打开的时间。</span><span class="sxs-lookup"><span data-stu-id="d882e-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="d882e-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="d882e-149">OutgoingChannels</span></span>  
 <span data-ttu-id="d882e-150">数据类型：Channel array</span><span class="sxs-lookup"><span data-stu-id="d882e-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="d882e-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-152">从服务实例传出的通道。</span><span class="sxs-lookup"><span data-stu-id="d882e-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="d882e-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="d882e-153">ProcessId</span></span>  
 <span data-ttu-id="d882e-154">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="d882e-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="d882e-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d882e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d882e-156">承载服务的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="d882e-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d882e-157">惠?</span><span class="sxs-lookup"><span data-stu-id="d882e-157">Requirements</span></span>  
  
|<span data-ttu-id="d882e-158">MOF</span><span class="sxs-lookup"><span data-stu-id="d882e-158">MOF</span></span>|<span data-ttu-id="d882e-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="d882e-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d882e-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="d882e-160">Namespace</span></span>|<span data-ttu-id="d882e-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="d882e-161">Defined in root\ServiceModel</span></span>|
