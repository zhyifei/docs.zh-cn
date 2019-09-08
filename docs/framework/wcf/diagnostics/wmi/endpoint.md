---
title: 终结点
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 03c401358839671d750985b95b1aada599931aad
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795909"
---
# <a name="endpoint"></a><span data-ttu-id="7b68d-102">终结点</span><span class="sxs-lookup"><span data-stu-id="7b68d-102">Endpoint</span></span>
<span data-ttu-id="7b68d-103">终结点</span><span class="sxs-lookup"><span data-stu-id="7b68d-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b68d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b68d-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="7b68d-105">方法</span><span class="sxs-lookup"><span data-stu-id="7b68d-105">Methods</span></span>  
 <span data-ttu-id="7b68d-106">该终结点类定义以下方法。</span><span class="sxs-lookup"><span data-stu-id="7b68d-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="7b68d-107">方法</span><span class="sxs-lookup"><span data-stu-id="7b68d-107">Method</span></span>|<span data-ttu-id="7b68d-108">描述</span><span class="sxs-lookup"><span data-stu-id="7b68d-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7b68d-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="7b68d-109">GetOperationCounterInstanceName</span></span>](getoperationcounterinstancename.md)|<span data-ttu-id="7b68d-110">检索操作性能计数器实例名称</span><span class="sxs-lookup"><span data-stu-id="7b68d-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="7b68d-111">属性</span><span class="sxs-lookup"><span data-stu-id="7b68d-111">Properties</span></span>  
 <span data-ttu-id="7b68d-112">该终结点类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="7b68d-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="7b68d-113">Address</span><span class="sxs-lookup"><span data-stu-id="7b68d-113">Address</span></span>  
 <span data-ttu-id="7b68d-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="7b68d-114">Data type: string</span></span>  
  
 <span data-ttu-id="7b68d-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-116">一个包含终结点地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="7b68d-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="7b68d-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="7b68d-117">AddressHeaders</span></span>  
 <span data-ttu-id="7b68d-118">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="7b68d-118">Data type: string array</span></span>  
  
 <span data-ttu-id="7b68d-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-120">附加到此终结点的地址头的集合。</span><span class="sxs-lookup"><span data-stu-id="7b68d-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="7b68d-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="7b68d-121">AddressIdentity</span></span>  
 <span data-ttu-id="7b68d-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="7b68d-122">Data type: string</span></span>  
  
 <span data-ttu-id="7b68d-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-124">终结点的标识。</span><span class="sxs-lookup"><span data-stu-id="7b68d-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="7b68d-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="7b68d-125">AppDomainId</span></span>  
 <span data-ttu-id="7b68d-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="7b68d-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="7b68d-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-128">承载终结点的 AppDomain 的 AppDomain ID。</span><span class="sxs-lookup"><span data-stu-id="7b68d-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="7b68d-129">Behaviors</span><span class="sxs-lookup"><span data-stu-id="7b68d-129">Behaviors</span></span>  
 <span data-ttu-id="7b68d-130">数据类型：行为数组</span><span class="sxs-lookup"><span data-stu-id="7b68d-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="7b68d-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-132">此终结点所实现的行为的集合。</span><span class="sxs-lookup"><span data-stu-id="7b68d-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="7b68d-133">绑定</span><span class="sxs-lookup"><span data-stu-id="7b68d-133">Binding</span></span>  
 <span data-ttu-id="7b68d-134">数据类型：绑定</span><span class="sxs-lookup"><span data-stu-id="7b68d-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="7b68d-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-136">此终结点所使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="7b68d-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="7b68d-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="7b68d-137">ContractName</span></span>  
 <span data-ttu-id="7b68d-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="7b68d-138">Data type: string</span></span>  
  
 <span data-ttu-id="7b68d-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-140">一个字符串，指定此终结点公开了哪个协定。</span><span class="sxs-lookup"><span data-stu-id="7b68d-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="7b68d-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="7b68d-141">CounterInstanceName</span></span>  
 <span data-ttu-id="7b68d-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="7b68d-142">Data type: string</span></span>  
  
 <span data-ttu-id="7b68d-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-144">该终结点的性能计数器的实例名称。</span><span class="sxs-lookup"><span data-stu-id="7b68d-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="7b68d-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="7b68d-145">ListenUri</span></span>  
 <span data-ttu-id="7b68d-146">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="7b68d-146">Data type: string</span></span>  
  
 <span data-ttu-id="7b68d-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-148">终结点在其上侦听的 Uri。</span><span class="sxs-lookup"><span data-stu-id="7b68d-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="7b68d-149">name</span><span class="sxs-lookup"><span data-stu-id="7b68d-149">Name</span></span>  
 <span data-ttu-id="7b68d-150">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="7b68d-150">Data type: string</span></span>  
  
 <span data-ttu-id="7b68d-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-152">此终结点的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="7b68d-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="7b68d-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="7b68d-153">ProcessId</span></span>  
 <span data-ttu-id="7b68d-154">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="7b68d-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="7b68d-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-156">承载该终结点的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="7b68d-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="7b68d-157">ref</span><span class="sxs-lookup"><span data-stu-id="7b68d-157">ref</span></span>  
 <span data-ttu-id="7b68d-158">数据类型：协定</span><span class="sxs-lookup"><span data-stu-id="7b68d-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="7b68d-159">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="7b68d-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="7b68d-160">此终结点公开的协定。</span><span class="sxs-lookup"><span data-stu-id="7b68d-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b68d-161">要求</span><span class="sxs-lookup"><span data-stu-id="7b68d-161">Requirements</span></span>  
  
|<span data-ttu-id="7b68d-162">MOF</span><span class="sxs-lookup"><span data-stu-id="7b68d-162">MOF</span></span>|<span data-ttu-id="7b68d-163">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="7b68d-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="7b68d-164">命名空间</span><span class="sxs-lookup"><span data-stu-id="7b68d-164">Namespace</span></span>|<span data-ttu-id="7b68d-165">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="7b68d-165">Defined in root\ServiceModel</span></span>|
