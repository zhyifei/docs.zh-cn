---
title: 服务
ms.date: 03/30/2017
ms.assetid: 999806e1-6376-409e-b998-b0af391adfe7
ms.openlocfilehash: c59672b3b7617d9c28d99f7d534b6e7f2f2e9fbb
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196903"
---
# <a name="service"></a><span data-ttu-id="5427c-102">服务</span><span class="sxs-lookup"><span data-stu-id="5427c-102">Service</span></span>
<span data-ttu-id="5427c-103">服务</span><span class="sxs-lookup"><span data-stu-id="5427c-103">Service</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5427c-104">语法</span><span class="sxs-lookup"><span data-stu-id="5427c-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="5427c-105">方法</span><span class="sxs-lookup"><span data-stu-id="5427c-105">Methods</span></span>  
 <span data-ttu-id="5427c-106">Service 类未定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="5427c-106">The Service class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="5427c-107">属性</span><span class="sxs-lookup"><span data-stu-id="5427c-107">Properties</span></span>  
 <span data-ttu-id="5427c-108">Service 类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="5427c-108">The Service class has the following properties:</span></span>  
  
### <a name="baseaddresses"></a><span data-ttu-id="5427c-109">BaseAddresses</span><span class="sxs-lookup"><span data-stu-id="5427c-109">BaseAddresses</span></span>  
 <span data-ttu-id="5427c-110">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="5427c-110">Data type: string array</span></span>  
  
 <span data-ttu-id="5427c-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-112">服务使用的基址。</span><span class="sxs-lookup"><span data-stu-id="5427c-112">The base addresses used by the service.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="5427c-113">行为</span><span class="sxs-lookup"><span data-stu-id="5427c-113">Behaviors</span></span>  
 <span data-ttu-id="5427c-114">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="5427c-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="5427c-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-116">与此服务关联的行为。</span><span class="sxs-lookup"><span data-stu-id="5427c-116">The behaviors associated with this service.</span></span>  
  
### <a name="configurationname"></a><span data-ttu-id="5427c-117">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="5427c-117">ConfigurationName</span></span>  
 <span data-ttu-id="5427c-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5427c-118">Data type: string</span></span>  
  
 <span data-ttu-id="5427c-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-120">ServiceElement_BehaviorConfiguration</span><span class="sxs-lookup"><span data-stu-id="5427c-120">ServiceElement_BehaviorConfiguration</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="5427c-121">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="5427c-121">CounterInstanceName</span></span>  
 <span data-ttu-id="5427c-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5427c-122">Data type: string</span></span>  
  
 <span data-ttu-id="5427c-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-124">此服务的性能计数器实例的实例名称。</span><span class="sxs-lookup"><span data-stu-id="5427c-124">Instance name of the instance of the performance counters of the service.</span></span>  
  
### <a name="distinguishedname"></a><span data-ttu-id="5427c-125">DistinguishedName</span><span class="sxs-lookup"><span data-stu-id="5427c-125">DistinguishedName</span></span>  
 <span data-ttu-id="5427c-126">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5427c-126">Data type: string</span></span>  
  
 <span data-ttu-id="5427c-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-128">该地址处的服务名称。</span><span class="sxs-lookup"><span data-stu-id="5427c-128">Service name at the address.</span></span>  
  
### <a name="extensions"></a><span data-ttu-id="5427c-129">扩展</span><span class="sxs-lookup"><span data-stu-id="5427c-129">Extensions</span></span>  
 <span data-ttu-id="5427c-130">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="5427c-130">Data type: string array</span></span>  
  
 <span data-ttu-id="5427c-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-132">服务实例扩展的实例上下文。</span><span class="sxs-lookup"><span data-stu-id="5427c-132">The instance contexts for the extensions of the service instance.</span></span>  
  
### <a name="metadata"></a><span data-ttu-id="5427c-133">元数据</span><span class="sxs-lookup"><span data-stu-id="5427c-133">Metadata</span></span>  
 <span data-ttu-id="5427c-134">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="5427c-134">Data type: string array</span></span>  
  
 <span data-ttu-id="5427c-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-136">服务元数据设置。</span><span class="sxs-lookup"><span data-stu-id="5427c-136">The service metadata settings.</span></span>  
  
### <a name="name"></a><span data-ttu-id="5427c-137">name</span><span class="sxs-lookup"><span data-stu-id="5427c-137">Name</span></span>  
 <span data-ttu-id="5427c-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5427c-138">Data type: string</span></span>  
  
 <span data-ttu-id="5427c-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-140">此服务的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="5427c-140">The unique name of this service.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="5427c-141">命名空间</span><span class="sxs-lookup"><span data-stu-id="5427c-141">Namespace</span></span>  
 <span data-ttu-id="5427c-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="5427c-142">Data type: string</span></span>  
  
 <span data-ttu-id="5427c-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-144">服务的命名空间。</span><span class="sxs-lookup"><span data-stu-id="5427c-144">The namespace of the service.</span></span>  
  
### <a name="opened"></a><span data-ttu-id="5427c-145">已打开</span><span class="sxs-lookup"><span data-stu-id="5427c-145">Opened</span></span>  
 <span data-ttu-id="5427c-146">数据类型：DateTime</span><span class="sxs-lookup"><span data-stu-id="5427c-146">Data type: datetime</span></span>  
  
 <span data-ttu-id="5427c-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-148">服务打开的时间。</span><span class="sxs-lookup"><span data-stu-id="5427c-148">The time the service was opened.</span></span>  
  
### <a name="outgoingchannels"></a><span data-ttu-id="5427c-149">OutgoingChannels</span><span class="sxs-lookup"><span data-stu-id="5427c-149">OutgoingChannels</span></span>  
 <span data-ttu-id="5427c-150">数据类型：Channel array</span><span class="sxs-lookup"><span data-stu-id="5427c-150">Data type: Channel array</span></span>  
  
 <span data-ttu-id="5427c-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-152">从服务实例传出的通道。</span><span class="sxs-lookup"><span data-stu-id="5427c-152">The channels that are outgoing from the service instance.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="5427c-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="5427c-153">ProcessId</span></span>  
 <span data-ttu-id="5427c-154">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="5427c-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="5427c-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="5427c-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="5427c-156">承载服务的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="5427c-156">The process id of the process that hosts the service.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5427c-157">要求</span><span class="sxs-lookup"><span data-stu-id="5427c-157">Requirements</span></span>  
  
|<span data-ttu-id="5427c-158">MOF</span><span class="sxs-lookup"><span data-stu-id="5427c-158">MOF</span></span>|<span data-ttu-id="5427c-159">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="5427c-159">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="5427c-160">命名空间</span><span class="sxs-lookup"><span data-stu-id="5427c-160">Namespace</span></span>|<span data-ttu-id="5427c-161">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="5427c-161">Defined in root\ServiceModel</span></span>|
