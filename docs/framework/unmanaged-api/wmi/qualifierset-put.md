---
title: "QualifierSet_Put 函数 （非托管 API 参考）"
description: "QualifierSet_Put 函数写入命名的限定符，并将其值。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Put
helpviewer_keywords: QualifierSet_Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7fdb6759d4e39ad9ab6bd6da2c2a0e2abfbe5d56
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="9b033-103">QualifierSet_Put 函数</span><span class="sxs-lookup"><span data-stu-id="9b033-103">QualifierSet_Put function</span></span>
<span data-ttu-id="9b033-104">写入命名的限定符和值。</span><span class="sxs-lookup"><span data-stu-id="9b033-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="9b033-105">新限定符将覆盖具有相同名称的以前的值。</span><span class="sxs-lookup"><span data-stu-id="9b033-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="9b033-106">如果限定符不存在，则创建它。</span><span class="sxs-lookup"><span data-stu-id="9b033-106">If the qualifier does not exist, it is created.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9b033-107">语法</span><span class="sxs-lookup"><span data-stu-id="9b033-107">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="9b033-108">参数</span><span class="sxs-lookup"><span data-stu-id="9b033-108">Parameters</span></span>

`vFunc`   
<span data-ttu-id="9b033-109">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="9b033-109">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="9b033-110">[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="9b033-110">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="9b033-111">[in]要写入的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="9b033-111">[in] The name of the qualifier to write.</span></span>

<span data-ttu-id="9b033-112">`pVal`[in]指向一个有效的指针`VARIANT`，其中包含要写入的限定符。</span><span class="sxs-lookup"><span data-stu-id="9b033-112">`pVal` [in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="9b033-113">此参数不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="9b033-113">This parameter cannot be `null`.</span></span>

<span data-ttu-id="9b033-114">`lFlavor`[in]定义此限定符的所需的限定符特色信息的以下常量之一。</span><span class="sxs-lookup"><span data-stu-id="9b033-114">`lFlavor` [in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="9b033-115">默认值是`WBEM_FLAVOR_OVERRIDABLE`(0)。</span><span class="sxs-lookup"><span data-stu-id="9b033-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="9b033-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="9b033-116">Constant</span></span>  |<span data-ttu-id="9b033-117">值</span><span class="sxs-lookup"><span data-stu-id="9b033-117">Value</span></span>  |<span data-ttu-id="9b033-118">描述</span><span class="sxs-lookup"><span data-stu-id="9b033-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="9b033-119">0</span><span class="sxs-lookup"><span data-stu-id="9b033-119">0</span></span> | <span data-ttu-id="9b033-120">可以在派生的类或实例中重写限定符。</span><span class="sxs-lookup"><span data-stu-id="9b033-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="9b033-121">**这是默认值。**</span><span class="sxs-lookup"><span data-stu-id="9b033-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="9b033-122">1</span><span class="sxs-lookup"><span data-stu-id="9b033-122">1</span></span> | <span data-ttu-id="9b033-123">限定符传播到实例。</span><span class="sxs-lookup"><span data-stu-id="9b033-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="9b033-124">2</span><span class="sxs-lookup"><span data-stu-id="9b033-124">2</span></span> | <span data-ttu-id="9b033-125">将限定符传播给派生类中。</span><span class="sxs-lookup"><span data-stu-id="9b033-125">The qualifier is propagated to derived classes.</span></span> |
| <span data-ttu-id="9b033-126">WBEM_FLAVOR_NOT_OVERRIDABLE</span><span class="sxs-lookup"><span data-stu-id="9b033-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span></span> | <span data-ttu-id="9b033-127">0x10</span><span class="sxs-lookup"><span data-stu-id="9b033-127">0x10</span></span> | <span data-ttu-id="9b033-128">不能在派生类或实例中重写限定符。</span><span class="sxs-lookup"><span data-stu-id="9b033-128">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| <span data-ttu-id="9b033-129">WBEM_FLAVOR_AMENDED</span><span class="sxs-lookup"><span data-stu-id="9b033-129">\`WBEM_FLAVOR_AMENDED</span></span> | <span data-ttu-id="9b033-130">0x80</span><span class="sxs-lookup"><span data-stu-id="9b033-130">0x80</span></span> | <span data-ttu-id="9b033-131">限定符进行了本地化。</span><span class="sxs-lookup"><span data-stu-id="9b033-131">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="9b033-132">返回值</span><span class="sxs-lookup"><span data-stu-id="9b033-132">Return value</span></span>

<span data-ttu-id="9b033-133">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="9b033-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9b033-134">返回的常量</span><span class="sxs-lookup"><span data-stu-id="9b033-134">Constant</span></span>  |<span data-ttu-id="9b033-135">值</span><span class="sxs-lookup"><span data-stu-id="9b033-135">Value</span></span>  |<span data-ttu-id="9b033-136">描述</span><span class="sxs-lookup"><span data-stu-id="9b033-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="9b033-137">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="9b033-137">0x8004101f</span></span> | <span data-ttu-id="9b033-138">没有非法尝试指定**密钥**限定符不能为键的属性上。</span><span class="sxs-lookup"><span data-stu-id="9b033-138">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="9b033-139">密钥指定 om c; 海量定义对象，不能修改基于每个实例。</span><span class="sxs-lookup"><span data-stu-id="9b033-139">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9b033-140">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9b033-140">0x80041008</span></span> | <span data-ttu-id="9b033-141">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="9b033-141">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="9b033-142">0x80041029</span><span class="sxs-lookup"><span data-stu-id="9b033-142">0x80041029</span></span> | <span data-ttu-id="9b033-143">`pVal`参数不是合法的限定符类型。</span><span class="sxs-lookup"><span data-stu-id="9b033-143">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="9b033-144">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="9b033-144">0x8004101a</span></span> | <span data-ttu-id="9b033-145">不能调用`QualifierSet_Put`方法对限定符因为所属的对象不允许重写。</span><span class="sxs-lookup"><span data-stu-id="9b033-145">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9b033-146">0</span><span class="sxs-lookup"><span data-stu-id="9b033-146">0</span></span> | <span data-ttu-id="9b033-147">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="9b033-147">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9b033-148">备注</span><span class="sxs-lookup"><span data-stu-id="9b033-148">Remarks</span></span>

<span data-ttu-id="9b033-149">此函数包装对的调用[IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="9b033-149">This function wraps a call to the [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b033-150">要求</span><span class="sxs-lookup"><span data-stu-id="9b033-150">Requirements</span></span>  
 <span data-ttu-id="9b033-151">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b033-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b033-152">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9b033-152">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9b033-153">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b033-153">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b033-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="9b033-154">See also</span></span>  
[<span data-ttu-id="9b033-155">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="9b033-155">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
