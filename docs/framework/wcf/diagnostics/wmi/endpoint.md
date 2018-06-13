---
title: 终结点
ms.date: 03/30/2017
ms.assetid: fe63370d-81a1-40f3-97c2-59cb357c78d2
ms.openlocfilehash: 5d597e9e029cec3552c94b47a64dfbf36d933e67
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487641"
---
# <a name="endpoint"></a><span data-ttu-id="d0b0e-102">终结点</span><span class="sxs-lookup"><span data-stu-id="d0b0e-102">Endpoint</span></span>
<span data-ttu-id="d0b0e-103">终结点</span><span class="sxs-lookup"><span data-stu-id="d0b0e-103">Endpoint</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0b0e-104">语法</span><span class="sxs-lookup"><span data-stu-id="d0b0e-104">Syntax</span></span>  
  
```  
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
  
## <a name="methods"></a><span data-ttu-id="d0b0e-105">方法</span><span class="sxs-lookup"><span data-stu-id="d0b0e-105">Methods</span></span>  
 <span data-ttu-id="d0b0e-106">该终结点类定义以下方法。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-106">The Endpoint class defines the following method.</span></span>  
  
|<span data-ttu-id="d0b0e-107">方法</span><span class="sxs-lookup"><span data-stu-id="d0b0e-107">Method</span></span>|<span data-ttu-id="d0b0e-108">描述</span><span class="sxs-lookup"><span data-stu-id="d0b0e-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0b0e-109">GetOperationCounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d0b0e-109">GetOperationCounterInstanceName</span></span>](../../../../../docs/framework/wcf/diagnostics/wmi/getoperationcounterinstancename.md)|<span data-ttu-id="d0b0e-110">检索操作性能计数器实例名称</span><span class="sxs-lookup"><span data-stu-id="d0b0e-110">Retrieves the operation performance counter instance name</span></span>|  
  
## <a name="properties"></a><span data-ttu-id="d0b0e-111">属性</span><span class="sxs-lookup"><span data-stu-id="d0b0e-111">Properties</span></span>  
 <span data-ttu-id="d0b0e-112">该终结点类具有以下属性：</span><span class="sxs-lookup"><span data-stu-id="d0b0e-112">The Endpoint class has the following properties:</span></span>  
  
### <a name="address"></a><span data-ttu-id="d0b0e-113">Address</span><span class="sxs-lookup"><span data-stu-id="d0b0e-113">Address</span></span>  
 <span data-ttu-id="d0b0e-114">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d0b0e-114">Data type: string</span></span>  
  
 <span data-ttu-id="d0b0e-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-116">一个包含终结点地址的 URI。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-116">A URI that contains the address of the endpoint.</span></span>  
  
### <a name="addressheaders"></a><span data-ttu-id="d0b0e-117">AddressHeaders</span><span class="sxs-lookup"><span data-stu-id="d0b0e-117">AddressHeaders</span></span>  
 <span data-ttu-id="d0b0e-118">数据类型：String array</span><span class="sxs-lookup"><span data-stu-id="d0b0e-118">Data type: string array</span></span>  
  
 <span data-ttu-id="d0b0e-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-120">附加到此终结点的地址头的集合。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-120">The collection of address headers attached to this endpoint.</span></span>  
  
### <a name="addressidentity"></a><span data-ttu-id="d0b0e-121">AddressIdentity</span><span class="sxs-lookup"><span data-stu-id="d0b0e-121">AddressIdentity</span></span>  
 <span data-ttu-id="d0b0e-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d0b0e-122">Data type: string</span></span>  
  
 <span data-ttu-id="d0b0e-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-124">终结点的标识。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-124">The identity of the endpoint.</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="d0b0e-125">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="d0b0e-125">AppDomainId</span></span>  
 <span data-ttu-id="d0b0e-126">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="d0b0e-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="d0b0e-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-128">承载终结点的 AppDomain 的 AppDomain ID。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-128">The appdomain id of the appdomain that hosts the endpoint.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="d0b0e-129">行为</span><span class="sxs-lookup"><span data-stu-id="d0b0e-129">Behaviors</span></span>  
 <span data-ttu-id="d0b0e-130">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="d0b0e-130">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="d0b0e-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-132">此终结点所实现的行为的集合。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-132">The collection of behaviors implemented by this endpoint.</span></span>  
  
### <a name="binding"></a><span data-ttu-id="d0b0e-133">绑定</span><span class="sxs-lookup"><span data-stu-id="d0b0e-133">Binding</span></span>  
 <span data-ttu-id="d0b0e-134">数据类型：绑定</span><span class="sxs-lookup"><span data-stu-id="d0b0e-134">Data type: Binding</span></span>  
  
 <span data-ttu-id="d0b0e-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-136">此终结点所使用的绑定。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-136">The binding used by this endpoint.</span></span>  
  
### <a name="contractname"></a><span data-ttu-id="d0b0e-137">ContractName</span><span class="sxs-lookup"><span data-stu-id="d0b0e-137">ContractName</span></span>  
 <span data-ttu-id="d0b0e-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d0b0e-138">Data type: string</span></span>  
  
 <span data-ttu-id="d0b0e-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-140">一个字符串，指定此终结点公开了哪个协定。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-140">A string that specifies which contract this endpoint is exposing.</span></span>  
  
### <a name="counterinstancename"></a><span data-ttu-id="d0b0e-141">CounterInstanceName</span><span class="sxs-lookup"><span data-stu-id="d0b0e-141">CounterInstanceName</span></span>  
 <span data-ttu-id="d0b0e-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d0b0e-142">Data type: string</span></span>  
  
 <span data-ttu-id="d0b0e-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-144">该终结点的性能计数器的实例名称。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-144">The name of the instance of performance counters of the endpoint.</span></span>  
  
### <a name="listenuri"></a><span data-ttu-id="d0b0e-145">ListenUri</span><span class="sxs-lookup"><span data-stu-id="d0b0e-145">ListenUri</span></span>  
 <span data-ttu-id="d0b0e-146">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d0b0e-146">Data type: string</span></span>  
  
 <span data-ttu-id="d0b0e-147">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-147">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-148">终结点在其上侦听的 Uri。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-148">The Uri the endpoint listens on.</span></span>  
  
### <a name="name"></a><span data-ttu-id="d0b0e-149">名称</span><span class="sxs-lookup"><span data-stu-id="d0b0e-149">Name</span></span>  
 <span data-ttu-id="d0b0e-150">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="d0b0e-150">Data type: string</span></span>  
  
 <span data-ttu-id="d0b0e-151">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-151">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-152">此终结点的唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-152">The unique name of this endpoint.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="d0b0e-153">ProcessId</span><span class="sxs-lookup"><span data-stu-id="d0b0e-153">ProcessId</span></span>  
 <span data-ttu-id="d0b0e-154">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="d0b0e-154">Data type: sint32</span></span>  
  
 <span data-ttu-id="d0b0e-155">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-155">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-156">承载该终结点的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-156">The process Id of the process that hosts the endpoint.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="d0b0e-157">ref</span><span class="sxs-lookup"><span data-stu-id="d0b0e-157">ref</span></span>  
 <span data-ttu-id="d0b0e-158">数据类型：Contract</span><span class="sxs-lookup"><span data-stu-id="d0b0e-158">Data type: Contract</span></span>  
  
 <span data-ttu-id="d0b0e-159">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="d0b0e-159">Access type: Read-only</span></span>  
  
 <span data-ttu-id="d0b0e-160">此终结点公开的协定。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-160">The contract this endpoint is exposing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0b0e-161">要求</span><span class="sxs-lookup"><span data-stu-id="d0b0e-161">Requirements</span></span>  
  
|<span data-ttu-id="d0b0e-162">MOF</span><span class="sxs-lookup"><span data-stu-id="d0b0e-162">MOF</span></span>|<span data-ttu-id="d0b0e-163">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="d0b0e-163">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="d0b0e-164">命名空间</span><span class="sxs-lookup"><span data-stu-id="d0b0e-164">Namespace</span></span>|<span data-ttu-id="d0b0e-165">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="d0b0e-165">Defined in root\ServiceModel</span></span>|
