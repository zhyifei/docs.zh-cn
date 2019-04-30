---
title: 服务
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991440"
---
# <a name="service"></a><span data-ttu-id="5f04b-102">服务</span><span class="sxs-lookup"><span data-stu-id="5f04b-102">Service</span></span>
<span data-ttu-id="5f04b-103">服务</span><span class="sxs-lookup"><span data-stu-id="5f04b-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f04b-104">语法</span><span class="sxs-lookup"><span data-stu-id="5f04b-104">Syntax</span></span>  
  
```csharp
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
  
## <a name="methods"></a><span data-ttu-id="5f04b-105">方法</span><span class="sxs-lookup"><span data-stu-id="5f04b-105">Methods</span></span>  
 <span data-ttu-id="5f04b-106">Service 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="5f04b-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5f04b-107">属性</span><span class="sxs-lookup"><span data-stu-id="5f04b-107">Properties</span></span>  
 <span data-ttu-id="5f04b-108">Service 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="5f04b-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="5f04b-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="5f04b-109">BaseAddresses</span></span>  
 <span data-ttu-id="5f04b-110">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="5f04b-110">Data type: string array</span></span>  
  
 <span data-ttu-id="5f04b-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-112">服务使用的基址。</span><span class="sxs-lookup"><span data-stu-id="5f04b-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="5f04b-113">Behaviors</span><span class="sxs-lookup"><span data-stu-id="5f04b-113">Behaviors</span></span>  
 <span data-ttu-id="5f04b-114">数据类型：行为数组</span><span class="sxs-lookup"><span data-stu-id="5f04b-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="5f04b-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-116">与此服务关联的行为。</span><span class="sxs-lookup"><span data-stu-id="5f04b-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="5f04b-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="5f04b-117">ConfigurationName</span></span>  
 <span data-ttu-id="5f04b-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5f04b-118">Data type: string</span></span>  
  
 <span data-ttu-id="5f04b-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="5f04b-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="5f04b-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="5f04b-121">CounterInstanceName</span></span>  
 <span data-ttu-id="5f04b-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5f04b-122">Data type: string</span></span>  
  
 <span data-ttu-id="5f04b-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-124">此服务的性能计数器实例的实例名称。</span><span class="sxs-lookup"><span data-stu-id="5f04b-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="5f04b-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="5f04b-125">DistinguishedName</span></span>  
 <span data-ttu-id="5f04b-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5f04b-126">Data type: string</span></span>  
  
 <span data-ttu-id="5f04b-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-128">该地址处的服务名称。</span><span class="sxs-lookup"><span data-stu-id="5f04b-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="5f04b-129">Extensions</span><span class="sxs-lookup"><span data-stu-id="5f04b-129">Extensions</span></span>  
 <span data-ttu-id="5f04b-130">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="5f04b-130">Data type: string array</span></span>  
  
 <span data-ttu-id="5f04b-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-132">服务实例扩展的实例上下文。</span><span class="sxs-lookup"><span data-stu-id="5f04b-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="5f04b-133">元数据</span><span class="sxs-lookup"><span data-stu-id="5f04b-133">Metadata</span></span>  
 <span data-ttu-id="5f04b-134">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="5f04b-134">Data type: string array</span></span>  
  
 <span data-ttu-id="5f04b-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-136">服务元数据设置。</span><span class="sxs-lookup"><span data-stu-id="5f04b-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="5f04b-137">名称</span><span class="sxs-lookup"><span data-stu-id="5f04b-137">Name</span></span>  
 <span data-ttu-id="5f04b-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5f04b-138">Data type: string</span></span>  
  
 <span data-ttu-id="5f04b-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-140">此服务的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="5f04b-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="5f04b-141">命名空间</span><span class="sxs-lookup"><span data-stu-id="5f04b-141">Namespace</span></span>  
 <span data-ttu-id="5f04b-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5f04b-142">Data type: string</span></span>  
  
 <span data-ttu-id="5f04b-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-144">服务的命名空间。</span><span class="sxs-lookup"><span data-stu-id="5f04b-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="5f04b-145">已打开</span><span class="sxs-lookup"><span data-stu-id="5f04b-145">Opened</span></span>  
 <span data-ttu-id="5f04b-146">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="5f04b-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="5f04b-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-148">服务打开的时间。</span><span class="sxs-lookup"><span data-stu-id="5f04b-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="5f04b-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="5f04b-149">OutgoingChannels</span></span>  
 <span data-ttu-id="5f04b-150">数据类型：通道阵列分区</span><span class="sxs-lookup"><span data-stu-id="5f04b-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="5f04b-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-152">从服务实例传出的通道。</span><span class="sxs-lookup"><span data-stu-id="5f04b-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="5f04b-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="5f04b-153">ProcessId</span></span>  
 <span data-ttu-id="5f04b-154">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="5f04b-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="5f04b-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5f04b-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5f04b-156">承载服务的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="5f04b-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f04b-157">要求</span><span class="sxs-lookup"><span data-stu-id="5f04b-157">Requirements</span></span>  
  
|<span data-ttu-id="5f04b-158">MOF</span><span class="sxs-lookup"><span data-stu-id="5f04b-158">MOF</span></span>|<span data-ttu-id="5f04b-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="5f04b-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5f04b-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="5f04b-160">Namespace</span></span>|<span data-ttu-id="5f04b-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="5f04b-161">Defined in root\ServiceModel</span></span>|
