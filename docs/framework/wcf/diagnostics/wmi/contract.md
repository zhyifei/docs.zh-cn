---
title: Contract1
ms.date: 03/30/2017
ms.assetid: aa00f6b3-7e1f-4213-841a-206463fca20b
ms.openlocfilehash: 12e9cbf5232ebbad33ccc4fdca33233997d27357
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50194665"
---
# <a name="contract"></a><span data-ttu-id="ee246-102">协定</span><span class="sxs-lookup"><span data-stu-id="ee246-102">Contract</span></span>
<span data-ttu-id="ee246-103">协定</span><span class="sxs-lookup"><span data-stu-id="ee246-103">Contract</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee246-104">语法</span><span class="sxs-lookup"><span data-stu-id="ee246-104">Syntax</span></span>  
  
```csharp
class Contract  
{  
  sint32 AppDomainId;  
  Behavior Behaviors[];  
  string Name;  
  string Namespace;  
  Operation Operations[];  
  sint32 ProcessId;  
  Contract ref;  
  string SessionMode;  
  string Type;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="ee246-105">方法</span><span class="sxs-lookup"><span data-stu-id="ee246-105">Methods</span></span>  
 <span data-ttu-id="ee246-106">Contract 类不定义任何方法。</span><span class="sxs-lookup"><span data-stu-id="ee246-106">The Contract class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="ee246-107">属性</span><span class="sxs-lookup"><span data-stu-id="ee246-107">Properties</span></span>  
 <span data-ttu-id="ee246-108">Contract 类具有下列属性：</span><span class="sxs-lookup"><span data-stu-id="ee246-108">The Contract class has the following properties:</span></span>  
  
### <a name="appdomainid"></a><span data-ttu-id="ee246-109">AppDomainId</span><span class="sxs-lookup"><span data-stu-id="ee246-109">AppDomainId</span></span>  
 <span data-ttu-id="ee246-110">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="ee246-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="ee246-111">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-112">承载协定的 appdomain 的 appdomain ID。</span><span class="sxs-lookup"><span data-stu-id="ee246-112">The appdomain id of the appdomain that hosts the contract.</span></span>  
  
### <a name="behaviors"></a><span data-ttu-id="ee246-113">行为</span><span class="sxs-lookup"><span data-stu-id="ee246-113">Behaviors</span></span>  
 <span data-ttu-id="ee246-114">数据类型：Behavior array</span><span class="sxs-lookup"><span data-stu-id="ee246-114">Data type: Behavior array</span></span>  
  
 <span data-ttu-id="ee246-115">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-116">与此协定关联的行为。</span><span class="sxs-lookup"><span data-stu-id="ee246-116">The behaviors associated with this contract.</span></span>  
  
### <a name="name"></a><span data-ttu-id="ee246-117">name</span><span class="sxs-lookup"><span data-stu-id="ee246-117">Name</span></span>  
 <span data-ttu-id="ee246-118">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ee246-118">Data type: string</span></span>  
  
 <span data-ttu-id="ee246-119">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-120">WSDL 中协定的名称。</span><span class="sxs-lookup"><span data-stu-id="ee246-120">The name of the contract in WSDL.</span></span>  
  
### <a name="namespace"></a><span data-ttu-id="ee246-121">命名空间</span><span class="sxs-lookup"><span data-stu-id="ee246-121">Namespace</span></span>  
 <span data-ttu-id="ee246-122">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ee246-122">Data type: string</span></span>  
  
 <span data-ttu-id="ee246-123">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-124">WSDL 中 `portType` 元素的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ee246-124">The namespace of the `portType` element in WSDL.</span></span>  
  
### <a name="operations"></a><span data-ttu-id="ee246-125">操作</span><span class="sxs-lookup"><span data-stu-id="ee246-125">Operations</span></span>  
 <span data-ttu-id="ee246-126">数据类型：操作数组</span><span class="sxs-lookup"><span data-stu-id="ee246-126">Data type: Operation array</span></span>  
  
 <span data-ttu-id="ee246-127">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-128">此协定的操作。</span><span class="sxs-lookup"><span data-stu-id="ee246-128">The operations of this contract.</span></span>  
  
### <a name="processid"></a><span data-ttu-id="ee246-129">ProcessId</span><span class="sxs-lookup"><span data-stu-id="ee246-129">ProcessId</span></span>  
 <span data-ttu-id="ee246-130">数据类型：sint32</span><span class="sxs-lookup"><span data-stu-id="ee246-130">Data type: sint32</span></span>  
  
 <span data-ttu-id="ee246-131">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-131">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-132">承载此协定的进程的进程 ID。</span><span class="sxs-lookup"><span data-stu-id="ee246-132">The process Id of the process that hosts the contract.</span></span>  
  
### <a name="ref"></a><span data-ttu-id="ee246-133">ref</span><span class="sxs-lookup"><span data-stu-id="ee246-133">ref</span></span>  
 <span data-ttu-id="ee246-134">数据类型：Contract</span><span class="sxs-lookup"><span data-stu-id="ee246-134">Data type: Contract</span></span>  
  
 <span data-ttu-id="ee246-135">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-135">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-136">协定为双工协定时的回调类型。</span><span class="sxs-lookup"><span data-stu-id="ee246-136">The type of callback when the contract is a duplex contract.</span></span>  
  
### <a name="sessionmode"></a><span data-ttu-id="ee246-137">SessionMode</span><span class="sxs-lookup"><span data-stu-id="ee246-137">SessionMode</span></span>  
 <span data-ttu-id="ee246-138">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ee246-138">Data type: string</span></span>  
  
 <span data-ttu-id="ee246-139">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-139">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-140">指示协定是否要求与此协定关联的绑定来使用通道会话。</span><span class="sxs-lookup"><span data-stu-id="ee246-140">Indicates whether the contract requires the binding associated with this contract to use channel sessions.</span></span>  
  
### <a name="type"></a><span data-ttu-id="ee246-141">类型</span><span class="sxs-lookup"><span data-stu-id="ee246-141">Type</span></span>  
 <span data-ttu-id="ee246-142">数据类型：String</span><span class="sxs-lookup"><span data-stu-id="ee246-142">Data type: string</span></span>  
  
 <span data-ttu-id="ee246-143">访问类型：只读</span><span class="sxs-lookup"><span data-stu-id="ee246-143">Access type: Read-only</span></span>  
  
 <span data-ttu-id="ee246-144">协定的类型。</span><span class="sxs-lookup"><span data-stu-id="ee246-144">The type of the contract.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ee246-145">要求</span><span class="sxs-lookup"><span data-stu-id="ee246-145">Requirements</span></span>  
  
|<span data-ttu-id="ee246-146">MOF</span><span class="sxs-lookup"><span data-stu-id="ee246-146">MOF</span></span>|<span data-ttu-id="ee246-147">已在 Servicemodel.mof 中声明。</span><span class="sxs-lookup"><span data-stu-id="ee246-147">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="ee246-148">命名空间</span><span class="sxs-lookup"><span data-stu-id="ee246-148">Namespace</span></span>|<span data-ttu-id="ee246-149">已在 root\ServiceModel 中定义</span><span class="sxs-lookup"><span data-stu-id="ee246-149">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="ee246-150">请参阅</span><span class="sxs-lookup"><span data-stu-id="ee246-150">See Also</span></span>  
 <xref:System.ServiceModel.Description.ContractDescription>
