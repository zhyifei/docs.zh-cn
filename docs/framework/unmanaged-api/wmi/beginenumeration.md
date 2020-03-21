---
title: 开始枚举函数（非托管 API 引用）
description: BeginEe枚举函数将枚举器重置为枚举的开头
ms.date: 11/06/2017
api_name:
- BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginEnumeration
helpviewer_keywords:
- BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: eac23916bd78ec3970a87566e2d2f4d79b379824
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176872"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="91c0e-103">BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="91c0e-103">BeginEnumeration function</span></span>
<span data-ttu-id="91c0e-104">将枚举器重置回枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="91c0e-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="91c0e-105">语法</span><span class="sxs-lookup"><span data-stu-id="91c0e-105">Syntax</span></span>  
  
```cpp  
HRESULT BeginEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="91c0e-106">parameters</span><span class="sxs-lookup"><span data-stu-id="91c0e-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="91c0e-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="91c0e-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="91c0e-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="91c0e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="91c0e-109">[在]控制枚举中包含的属性的[备注](#remarks)部分中描述的标志或值的位组合。</span><span class="sxs-lookup"><span data-stu-id="91c0e-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="91c0e-110">返回值</span><span class="sxs-lookup"><span data-stu-id="91c0e-110">Return value</span></span>

<span data-ttu-id="91c0e-111">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="91c0e-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="91c0e-112">一直</span><span class="sxs-lookup"><span data-stu-id="91c0e-112">Constant</span></span>  |<span data-ttu-id="91c0e-113">值</span><span class="sxs-lookup"><span data-stu-id="91c0e-113">Value</span></span>  |<span data-ttu-id="91c0e-114">说明</span><span class="sxs-lookup"><span data-stu-id="91c0e-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="91c0e-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="91c0e-115">0x80041008</span></span> | <span data-ttu-id="91c0e-116">中`lEnumFlags`的标志组合无效，或指定了无效的参数。</span><span class="sxs-lookup"><span data-stu-id="91c0e-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="91c0e-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="91c0e-117">0x8004101d</span></span> | <span data-ttu-id="91c0e-118">第二次呼叫`BeginEnumeration`是在没有干预调用[`EndEnumeration`](endenumeration.md)的情况下进行的。</span><span class="sxs-lookup"><span data-stu-id="91c0e-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="91c0e-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="91c0e-119">0x80041006</span></span> | <span data-ttu-id="91c0e-120">没有足够的内存可用于开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="91c0e-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="91c0e-121">0</span><span class="sxs-lookup"><span data-stu-id="91c0e-121">0</span></span> | <span data-ttu-id="91c0e-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="91c0e-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="91c0e-123">备注</span><span class="sxs-lookup"><span data-stu-id="91c0e-123">Remarks</span></span>

<span data-ttu-id="91c0e-124">此函数包装对[IWbemClassObject 的调用：：开始枚举](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)方法。</span><span class="sxs-lookup"><span data-stu-id="91c0e-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="91c0e-125">可在`lEnumFlags`*WbemCli.h*标头文件中定义作为参数传递的标志，也可以将它们定义为代码中的常量。</span><span class="sxs-lookup"><span data-stu-id="91c0e-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="91c0e-126">您可以将每个组中的一个标志与任何其他组的任何标志合并。</span><span class="sxs-lookup"><span data-stu-id="91c0e-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="91c0e-127">但是，来自同一组的标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="91c0e-127">However, flags from the same group are mutually exclusive.</span></span>

<span data-ttu-id="91c0e-128">**组 1**</span><span class="sxs-lookup"><span data-stu-id="91c0e-128">**Group 1**</span></span>

|<span data-ttu-id="91c0e-129">一直</span><span class="sxs-lookup"><span data-stu-id="91c0e-129">Constant</span></span>  |<span data-ttu-id="91c0e-130">值</span><span class="sxs-lookup"><span data-stu-id="91c0e-130">Value</span></span>  |<span data-ttu-id="91c0e-131">说明</span><span class="sxs-lookup"><span data-stu-id="91c0e-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="91c0e-132">0x4</span><span class="sxs-lookup"><span data-stu-id="91c0e-132">0x4</span></span> | <span data-ttu-id="91c0e-133">仅包含构成密钥的属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="91c0e-134">0x8</span><span class="sxs-lookup"><span data-stu-id="91c0e-134">0x8</span></span> | <span data-ttu-id="91c0e-135">仅包含对象引用的属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="91c0e-136">**组 2**</span><span class="sxs-lookup"><span data-stu-id="91c0e-136">**Group 2**</span></span>

<span data-ttu-id="91c0e-137">一直</span><span class="sxs-lookup"><span data-stu-id="91c0e-137">Constant</span></span>  |<span data-ttu-id="91c0e-138">值</span><span class="sxs-lookup"><span data-stu-id="91c0e-138">Value</span></span>  |<span data-ttu-id="91c0e-139">说明</span><span class="sxs-lookup"><span data-stu-id="91c0e-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="91c0e-140">0x30</span><span class="sxs-lookup"><span data-stu-id="91c0e-140">0x30</span></span> | <span data-ttu-id="91c0e-141">仅将枚举限制为系统属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="91c0e-142">0x40</span><span class="sxs-lookup"><span data-stu-id="91c0e-142">0x40</span></span> | <span data-ttu-id="91c0e-143">包括本地和传播属性，但从枚举中排除系统属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="91c0e-144">对于类：</span><span class="sxs-lookup"><span data-stu-id="91c0e-144">For classes:</span></span>

<span data-ttu-id="91c0e-145">一直</span><span class="sxs-lookup"><span data-stu-id="91c0e-145">Constant</span></span>  |<span data-ttu-id="91c0e-146">值</span><span class="sxs-lookup"><span data-stu-id="91c0e-146">Value</span></span>  |<span data-ttu-id="91c0e-147">说明</span><span class="sxs-lookup"><span data-stu-id="91c0e-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="91c0e-148">0x100</span><span class="sxs-lookup"><span data-stu-id="91c0e-148">0x100</span></span> | <span data-ttu-id="91c0e-149">将枚举限制为类定义中重写的属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="91c0e-150">0x100</span><span class="sxs-lookup"><span data-stu-id="91c0e-150">0x100</span></span> | <span data-ttu-id="91c0e-151">将枚举限制为当前类定义中重写的属性和类中定义的新属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="91c0e-152">0 x 300</span><span class="sxs-lookup"><span data-stu-id="91c0e-152">0x300</span></span> | <span data-ttu-id="91c0e-153">要针对`lEnumFlags`值应用的蒙版（而不是标志），以检查是否设置了。 `WBEM_FLAG_CLASS_OVERRIDES_ONLY` `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`</span><span class="sxs-lookup"><span data-stu-id="91c0e-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="91c0e-154">0x10</span><span class="sxs-lookup"><span data-stu-id="91c0e-154">0x10</span></span> | <span data-ttu-id="91c0e-155">将枚举限制为在类本身中定义或修改的属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="91c0e-156">0x20</span><span class="sxs-lookup"><span data-stu-id="91c0e-156">0x20</span></span> | <span data-ttu-id="91c0e-157">将枚举限制为从基类继承的属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="91c0e-158">例如：</span><span class="sxs-lookup"><span data-stu-id="91c0e-158">For instances:</span></span>

<span data-ttu-id="91c0e-159">一直</span><span class="sxs-lookup"><span data-stu-id="91c0e-159">Constant</span></span>  |<span data-ttu-id="91c0e-160">值</span><span class="sxs-lookup"><span data-stu-id="91c0e-160">Value</span></span>  |<span data-ttu-id="91c0e-161">说明</span><span class="sxs-lookup"><span data-stu-id="91c0e-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="91c0e-162">0x10</span><span class="sxs-lookup"><span data-stu-id="91c0e-162">0x10</span></span> | <span data-ttu-id="91c0e-163">将枚举限制为在类本身中定义或修改的属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="91c0e-164">0x20</span><span class="sxs-lookup"><span data-stu-id="91c0e-164">0x20</span></span> | <span data-ttu-id="91c0e-165">将枚举限制为从基类继承的属性。</span><span class="sxs-lookup"><span data-stu-id="91c0e-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="91c0e-166">要求</span><span class="sxs-lookup"><span data-stu-id="91c0e-166">Requirements</span></span>  
 <span data-ttu-id="91c0e-167">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="91c0e-167">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91c0e-168">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="91c0e-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="91c0e-169">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="91c0e-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91c0e-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91c0e-170">See also</span></span>

- [<span data-ttu-id="91c0e-171">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="91c0e-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
