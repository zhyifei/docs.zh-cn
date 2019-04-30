---
title: 终结点
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 4562481e8b0b18c0ea0d9df0af3427ffe6419821
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61963600"
---
# <a name="endpoint"></a><span data-ttu-id="ad9bb-102">终结点</span><span class="sxs-lookup"><span data-stu-id="ad9bb-102">Endpoint</span></span>
<span data-ttu-id="ad9bb-103">终结点</span><span class="sxs-lookup"><span data-stu-id="ad9bb-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad9bb-104">语法</span><span class="sxs-lookup"><span data-stu-id="ad9bb-104">Syntax</span></span>  
  
```csharp
class Endpoint  
{  
  string Address;  
  string AddressHeaders[];  
  string AddressIdentity;  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  Binding Binding;  
  string ContractName;  
  string CounterInstanceName;  
  string ListenUri;  
  string Name;  
  sint32 ProcessId;  
  Contract ref;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ad9bb-105">方法</span><span class="sxs-lookup"><span data-stu-id="ad9bb-105">Methods</span></span>  
 <span data-ttu-id="ad9bb-106">该终结点类定义以下方法。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="ad9bb-107">方法</span><span class="sxs-lookup"><span data-stu-id="ad9bb-107">Method</span></span>|<span data-ttu-id="ad9bb-108">描述</span><span class="sxs-lookup"><span data-stu-id="ad9bb-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ad9bb-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="ad9bb-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="ad9bb-110">检索操作性能计数器实例名称</span><span class="sxs-lookup"><span data-stu-id="ad9bb-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="ad9bb-111">属性</span><span class="sxs-lookup"><span data-stu-id="ad9bb-111">Properties</span></span>  
 <span data-ttu-id="ad9bb-112">该终结点类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="ad9bb-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="ad9bb-113">Address</span><span class="sxs-lookup"><span data-stu-id="ad9bb-113">Address</span></span>  
 <span data-ttu-id="ad9bb-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ad9bb-114">Data type: string</span></span>  
  
 <span data-ttu-id="ad9bb-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-116">一个包含终结点地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="ad9bb-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="ad9bb-117">AddressHeaders</span></span>  
 <span data-ttu-id="ad9bb-118">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="ad9bb-118">Data type: string array</span></span>  
  
 <span data-ttu-id="ad9bb-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-120">附加到此终结点的地址头的集合。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="ad9bb-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="ad9bb-121">AddressIdentity</span></span>  
 <span data-ttu-id="ad9bb-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ad9bb-122">Data type: string</span></span>  
  
 <span data-ttu-id="ad9bb-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-124">终结点的标识。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="ad9bb-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="ad9bb-125">AppDomainId</span></span>  
 <span data-ttu-id="ad9bb-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="ad9bb-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="ad9bb-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-128">承载终结点的 AppDomain 的 AppDomain ID。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="ad9bb-129">Behaviors</span><span class="sxs-lookup"><span data-stu-id="ad9bb-129">Behaviors</span></span>  
 <span data-ttu-id="ad9bb-130">数据类型：行为数组</span><span class="sxs-lookup"><span data-stu-id="ad9bb-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="ad9bb-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-132">此终结点所实现的行为的集合。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="ad9bb-133">绑定</span><span class="sxs-lookup"><span data-stu-id="ad9bb-133">Binding</span></span>  
 <span data-ttu-id="ad9bb-134">数据类型：绑定</span><span class="sxs-lookup"><span data-stu-id="ad9bb-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="ad9bb-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-136">此终结点所使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="ad9bb-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="ad9bb-137">ContractName</span></span>  
 <span data-ttu-id="ad9bb-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ad9bb-138">Data type: string</span></span>  
  
 <span data-ttu-id="ad9bb-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-140">一个字符串，指定此终结点公开了哪个协定。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="ad9bb-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="ad9bb-141">CounterInstanceName</span></span>  
 <span data-ttu-id="ad9bb-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ad9bb-142">Data type: string</span></span>  
  
 <span data-ttu-id="ad9bb-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-144">该终结点的性能计数器的实例名称。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="ad9bb-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="ad9bb-145">ListenUri</span></span>  
 <span data-ttu-id="ad9bb-146">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ad9bb-146">Data type: string</span></span>  
  
 <span data-ttu-id="ad9bb-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-148">终结点在其上侦听的 Uri。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="ad9bb-149">名称</span><span class="sxs-lookup"><span data-stu-id="ad9bb-149">Name</span></span>  
 <span data-ttu-id="ad9bb-150">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ad9bb-150">Data type: string</span></span>  
  
 <span data-ttu-id="ad9bb-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-152">此终结点的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="ad9bb-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="ad9bb-153">ProcessId</span></span>  
 <span data-ttu-id="ad9bb-154">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="ad9bb-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="ad9bb-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-156">承载该终结点的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ad9bb-157">ref</span><span class="sxs-lookup"><span data-stu-id="ad9bb-157">ref</span></span>  
 <span data-ttu-id="ad9bb-158">数据类型：协定</span><span class="sxs-lookup"><span data-stu-id="ad9bb-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="ad9bb-159">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ad9bb-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ad9bb-160">此终结点公开的协定。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad9bb-161">要求</span><span class="sxs-lookup"><span data-stu-id="ad9bb-161">Requirements</span></span>  
  
|<span data-ttu-id="ad9bb-162">MOF</span><span class="sxs-lookup"><span data-stu-id="ad9bb-162">MOF</span></span>|<span data-ttu-id="ad9bb-163">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ad9bb-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ad9bb-164">命名空间</span><span class="sxs-lookup"><span data-stu-id="ad9bb-164">Namespace</span></span>|<span data-ttu-id="ad9bb-165">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ad9bb-165">Defined in root\ServiceModel</span></span>|
