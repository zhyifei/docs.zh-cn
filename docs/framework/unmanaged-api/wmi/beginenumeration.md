---
title: "BeginEnumeration 函数 （非托管 API 参考）"
description: "BeginEnumeration 函数将枚举器重置到开头枚举"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginEnumeration
helpviewer_keywords: BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12a742774bff22030bdfaaa34e431059e016a4bf
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="987e6-103">BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="987e6-103">BeginEnumeration function</span></span>
<span data-ttu-id="987e6-104">将枚举数重置回枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="987e6-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="987e6-105">语法</span><span class="sxs-lookup"><span data-stu-id="987e6-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="987e6-106">参数</span><span class="sxs-lookup"><span data-stu-id="987e6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="987e6-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="987e6-107">[in] This parameter is unused.</span></span>

<span data-ttu-id="987e6-108">`ptr`[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="987e6-108">`ptr` [in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="987e6-109">[in]标志或中所述的值的按位组合[备注](#remarks)控制包含在枚举中的属性的部分。</span><span class="sxs-lookup"><span data-stu-id="987e6-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="987e6-110">返回值</span><span class="sxs-lookup"><span data-stu-id="987e6-110">Return value</span></span>

<span data-ttu-id="987e6-111">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="987e6-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="987e6-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="987e6-112">Constant</span></span>  |<span data-ttu-id="987e6-113">值</span><span class="sxs-lookup"><span data-stu-id="987e6-113">Value</span></span>  |<span data-ttu-id="987e6-114">描述</span><span class="sxs-lookup"><span data-stu-id="987e6-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="987e6-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="987e6-115">0x80041008</span></span> | <span data-ttu-id="987e6-116">中的标志的组合`lEnumFlags`无效，或者无效指定的参数。</span><span class="sxs-lookup"><span data-stu-id="987e6-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="987e6-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="987e6-117">0x8004101d</span></span> | <span data-ttu-id="987e6-118">第二个调用`BeginEnumeration`而无需对的干预调用进行[ `EndEnumeration` ](endenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="987e6-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="987e6-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="987e6-119">0x80041006</span></span> | <span data-ttu-id="987e6-120">没有足够的内存，可开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="987e6-121">0</span><span class="sxs-lookup"><span data-stu-id="987e6-121">0</span></span> | <span data-ttu-id="987e6-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="987e6-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="987e6-123">备注</span><span class="sxs-lookup"><span data-stu-id="987e6-123">Remarks</span></span>

<span data-ttu-id="987e6-124">此函数包装对的调用[IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="987e6-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) method.</span></span>

<span data-ttu-id="987e6-125">可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。</span><span class="sxs-lookup"><span data-stu-id="987e6-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="987e6-126">你可以组合使用任何其他组的任何标志每个组中的一个标志。</span><span class="sxs-lookup"><span data-stu-id="987e6-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="987e6-127">但是，同一组中的标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="987e6-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="987e6-128">**组 1**</span><span class="sxs-lookup"><span data-stu-id="987e6-128">**Group 1**</span></span>

|<span data-ttu-id="987e6-129">返回的常量</span><span class="sxs-lookup"><span data-stu-id="987e6-129">Constant</span></span>  |<span data-ttu-id="987e6-130">值</span><span class="sxs-lookup"><span data-stu-id="987e6-130">Value</span></span>  |<span data-ttu-id="987e6-131">描述</span><span class="sxs-lookup"><span data-stu-id="987e6-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="987e6-132">0x4</span><span class="sxs-lookup"><span data-stu-id="987e6-132">0x4</span></span> | <span data-ttu-id="987e6-133">包括构成仅密钥的属性。</span><span class="sxs-lookup"><span data-stu-id="987e6-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="987e6-134">0x8</span><span class="sxs-lookup"><span data-stu-id="987e6-134">0x8</span></span> | <span data-ttu-id="987e6-135">包括仅对象引用的属性。</span><span class="sxs-lookup"><span data-stu-id="987e6-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="987e6-136">**组 2**</span><span class="sxs-lookup"><span data-stu-id="987e6-136">**Group 2**</span></span>

<span data-ttu-id="987e6-137">返回的常量</span><span class="sxs-lookup"><span data-stu-id="987e6-137">Constant</span></span>  |<span data-ttu-id="987e6-138">值</span><span class="sxs-lookup"><span data-stu-id="987e6-138">Value</span></span>  |<span data-ttu-id="987e6-139">描述</span><span class="sxs-lookup"><span data-stu-id="987e6-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="987e6-140">0x30</span><span class="sxs-lookup"><span data-stu-id="987e6-140">0x30</span></span> | <span data-ttu-id="987e6-141">限制对系统属性仅枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="987e6-142">0x40</span><span class="sxs-lookup"><span data-stu-id="987e6-142">0x40</span></span> | <span data-ttu-id="987e6-143">包括本地和传播属性，但枚举中排除系统属性。</span><span class="sxs-lookup"><span data-stu-id="987e6-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="987e6-144">对于类：</span><span class="sxs-lookup"><span data-stu-id="987e6-144">For classes:</span></span>

<span data-ttu-id="987e6-145">返回的常量</span><span class="sxs-lookup"><span data-stu-id="987e6-145">Constant</span></span>  |<span data-ttu-id="987e6-146">值</span><span class="sxs-lookup"><span data-stu-id="987e6-146">Value</span></span>  |<span data-ttu-id="987e6-147">描述</span><span class="sxs-lookup"><span data-stu-id="987e6-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="987e6-148">0x100</span><span class="sxs-lookup"><span data-stu-id="987e6-148">0x100</span></span> | <span data-ttu-id="987e6-149">限制对属性重写的类定义中枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="987e6-150">0x100</span><span class="sxs-lookup"><span data-stu-id="987e6-150">0x100</span></span> | <span data-ttu-id="987e6-151">限制到当前的类定义中重写的属性和新属性的类中定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="987e6-152">0x300</span><span class="sxs-lookup"><span data-stu-id="987e6-152">0x300</span></span> | <span data-ttu-id="987e6-153">一个掩码 （而不是一个标志） 用于针对`lEnumFlags`要检查如果任一值`WBEM_FLAG_CLASS_OVERRIDES_ONLY`或`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`设置。</span><span class="sxs-lookup"><span data-stu-id="987e6-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="987e6-154">0x10</span><span class="sxs-lookup"><span data-stu-id="987e6-154">0x10</span></span> | <span data-ttu-id="987e6-155">限制到属性定义或修改在类本身中枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="987e6-156">0x20</span><span class="sxs-lookup"><span data-stu-id="987e6-156">0x20</span></span> | <span data-ttu-id="987e6-157">限制从基类继承的属性对枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="987e6-158">实例：</span><span class="sxs-lookup"><span data-stu-id="987e6-158">For instances:</span></span>

<span data-ttu-id="987e6-159">返回的常量</span><span class="sxs-lookup"><span data-stu-id="987e6-159">Constant</span></span>  |<span data-ttu-id="987e6-160">值</span><span class="sxs-lookup"><span data-stu-id="987e6-160">Value</span></span>  |<span data-ttu-id="987e6-161">描述</span><span class="sxs-lookup"><span data-stu-id="987e6-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="987e6-162">0x10</span><span class="sxs-lookup"><span data-stu-id="987e6-162">0x10</span></span> | <span data-ttu-id="987e6-163">限制到属性定义或修改在类本身中枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="987e6-164">0x20</span><span class="sxs-lookup"><span data-stu-id="987e6-164">0x20</span></span> | <span data-ttu-id="987e6-165">限制从基类继承的属性对枚举。</span><span class="sxs-lookup"><span data-stu-id="987e6-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |


## <a name="requirements"></a><span data-ttu-id="987e6-166">要求</span><span class="sxs-lookup"><span data-stu-id="987e6-166">Requirements</span></span>  
 <span data-ttu-id="987e6-167">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="987e6-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="987e6-168">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="987e6-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="987e6-169">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="987e6-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987e6-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="987e6-170">See also</span></span>  
[<span data-ttu-id="987e6-171">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="987e6-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
