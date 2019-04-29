---
title: BeginEnumeration 函数 （非托管 API 参考）
description: BeginEnumeration 函数将一个枚举数重置为枚举的开头
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4221dbea2b5ad98f889e04eb8a9b6d992b59066e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61767450"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="24c85-103">BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="24c85-103">BeginEnumeration function</span></span>
<span data-ttu-id="24c85-104">将枚举数重置到枚举的起点。</span><span class="sxs-lookup"><span data-stu-id="24c85-104">Resets an enumerator back to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="24c85-105">语法</span><span class="sxs-lookup"><span data-stu-id="24c85-105">Syntax</span></span>  
  
```  
HRESULT BeginEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="24c85-106">参数</span><span class="sxs-lookup"><span data-stu-id="24c85-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="24c85-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="24c85-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="24c85-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="24c85-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`\
<span data-ttu-id="24c85-109">[in]值中所述的标志的按位组合[备注](#remarks)部分，用于控制在枚举中包含的属性。</span><span class="sxs-lookup"><span data-stu-id="24c85-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that controls the properties included in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="24c85-110">返回值</span><span class="sxs-lookup"><span data-stu-id="24c85-110">Return value</span></span>

<span data-ttu-id="24c85-111">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="24c85-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="24c85-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="24c85-112">Constant</span></span>  |<span data-ttu-id="24c85-113">“值”</span><span class="sxs-lookup"><span data-stu-id="24c85-113">Value</span></span>  |<span data-ttu-id="24c85-114">描述</span><span class="sxs-lookup"><span data-stu-id="24c85-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="24c85-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="24c85-115">0x80041008</span></span> | <span data-ttu-id="24c85-116">中的标志的组合`lEnumFlags`无效，或一个无效的指定的参数。</span><span class="sxs-lookup"><span data-stu-id="24c85-116">The combination of flags in `lEnumFlags` is invalid, or an invalid argument was specified.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="24c85-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="24c85-117">0x8004101d</span></span> | <span data-ttu-id="24c85-118">第二次调用`BeginEnumeration`而无需对的干预调用进行[ `EndEnumeration` ](endenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="24c85-118">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="24c85-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="24c85-119">0x80041006</span></span> | <span data-ttu-id="24c85-120">没有足够的内存，可开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="24c85-121">0</span><span class="sxs-lookup"><span data-stu-id="24c85-121">0</span></span> | <span data-ttu-id="24c85-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="24c85-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="24c85-123">备注</span><span class="sxs-lookup"><span data-stu-id="24c85-123">Remarks</span></span>

<span data-ttu-id="24c85-124">此函数包装对的调用[IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)方法。</span><span class="sxs-lookup"><span data-stu-id="24c85-124">This function wraps a call to the [IWbemClassObject::BeginEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="24c85-125">可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，也可以在定义它们为常量在代码中。</span><span class="sxs-lookup"><span data-stu-id="24c85-125">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="24c85-126">可以结合任何其他组中的任何标志每个组中的一个标志。</span><span class="sxs-lookup"><span data-stu-id="24c85-126">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="24c85-127">但是，在同一组中的标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="24c85-127">However, flags from the same group are mutually exclusive.</span></span> 

<span data-ttu-id="24c85-128">**组 1**</span><span class="sxs-lookup"><span data-stu-id="24c85-128">**Group 1**</span></span>

|<span data-ttu-id="24c85-129">返回的常量</span><span class="sxs-lookup"><span data-stu-id="24c85-129">Constant</span></span>  |<span data-ttu-id="24c85-130">“值”</span><span class="sxs-lookup"><span data-stu-id="24c85-130">Value</span></span>  |<span data-ttu-id="24c85-131">描述</span><span class="sxs-lookup"><span data-stu-id="24c85-131">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="24c85-132">0x4</span><span class="sxs-lookup"><span data-stu-id="24c85-132">0x4</span></span> | <span data-ttu-id="24c85-133">包含构成仅密钥的属性。</span><span class="sxs-lookup"><span data-stu-id="24c85-133">Include properties that constitute the key only.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="24c85-134">0x8</span><span class="sxs-lookup"><span data-stu-id="24c85-134">0x8</span></span> | <span data-ttu-id="24c85-135">包括仅限对象引用的属性。</span><span class="sxs-lookup"><span data-stu-id="24c85-135">Include properties that are object references only.</span></span> |

<span data-ttu-id="24c85-136">**组 2**</span><span class="sxs-lookup"><span data-stu-id="24c85-136">**Group 2**</span></span>

<span data-ttu-id="24c85-137">返回的常量</span><span class="sxs-lookup"><span data-stu-id="24c85-137">Constant</span></span>  |<span data-ttu-id="24c85-138">“值”</span><span class="sxs-lookup"><span data-stu-id="24c85-138">Value</span></span>  |<span data-ttu-id="24c85-139">描述</span><span class="sxs-lookup"><span data-stu-id="24c85-139">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="24c85-140">0x30</span><span class="sxs-lookup"><span data-stu-id="24c85-140">0x30</span></span> | <span data-ttu-id="24c85-141">限制为仅系统属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-141">Limit the enumeration to system properties only.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="24c85-142">0x40</span><span class="sxs-lookup"><span data-stu-id="24c85-142">0x40</span></span> | <span data-ttu-id="24c85-143">包括本地和传播属性但不枚举中的系统属性。</span><span class="sxs-lookup"><span data-stu-id="24c85-143">Include local and propagated properties but exclude system properties from the enumeration.</span></span> |

<span data-ttu-id="24c85-144">对于类：</span><span class="sxs-lookup"><span data-stu-id="24c85-144">For classes:</span></span>

<span data-ttu-id="24c85-145">返回的常量</span><span class="sxs-lookup"><span data-stu-id="24c85-145">Constant</span></span>  |<span data-ttu-id="24c85-146">“值”</span><span class="sxs-lookup"><span data-stu-id="24c85-146">Value</span></span>  |<span data-ttu-id="24c85-147">描述</span><span class="sxs-lookup"><span data-stu-id="24c85-147">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_CLASS_OVERRIDES_ONLY` | <span data-ttu-id="24c85-148">0x100</span><span class="sxs-lookup"><span data-stu-id="24c85-148">0x100</span></span> | <span data-ttu-id="24c85-149">限制到类定义中被重写的属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-149">Limit the enumeration to properties overridden in the class definition.</span></span> |
|`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` | <span data-ttu-id="24c85-150">0x100</span><span class="sxs-lookup"><span data-stu-id="24c85-150">0x100</span></span> | <span data-ttu-id="24c85-151">限制到当前的类定义中被重写的属性和新的类中定义的属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-151">Limit the enumeration to properties overridden in the current class definition and to new properties defined in the class.</span></span> |
| `WBEM_MASK_CLASS_CONDITION` | <span data-ttu-id="24c85-152">0x300</span><span class="sxs-lookup"><span data-stu-id="24c85-152">0x300</span></span> | <span data-ttu-id="24c85-153">一个屏蔽 （而不是标记） 以应用针对`lEnumFlags`值以检查如果任一`WBEM_FLAG_CLASS_OVERRIDES_ONLY`或`WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES`设置。</span><span class="sxs-lookup"><span data-stu-id="24c85-153">A mask (rather than a flag) to apply against a `lEnumFlags` value to check if either `WBEM_FLAG_CLASS_OVERRIDES_ONLY` or `WBEM_FLAG_CLASS_LOCAL_AND_OVERRIDES` is set.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="24c85-154">0x10</span><span class="sxs-lookup"><span data-stu-id="24c85-154">0x10</span></span> | <span data-ttu-id="24c85-155">限制到定义的或在类本身中修改属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-155">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="24c85-156">0x20</span><span class="sxs-lookup"><span data-stu-id="24c85-156">0x20</span></span> | <span data-ttu-id="24c85-157">限制对从基类继承的属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-157">Limit the enumeration to properties that are inherited from base classes.</span></span> |

<span data-ttu-id="24c85-158">实例：</span><span class="sxs-lookup"><span data-stu-id="24c85-158">For instances:</span></span>

<span data-ttu-id="24c85-159">返回的常量</span><span class="sxs-lookup"><span data-stu-id="24c85-159">Constant</span></span>  |<span data-ttu-id="24c85-160">“值”</span><span class="sxs-lookup"><span data-stu-id="24c85-160">Value</span></span>  |<span data-ttu-id="24c85-161">描述</span><span class="sxs-lookup"><span data-stu-id="24c85-161">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="24c85-162">0x10</span><span class="sxs-lookup"><span data-stu-id="24c85-162">0x10</span></span> | <span data-ttu-id="24c85-163">限制到定义的或在类本身中修改属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-163">Limit the enumeration to properties that are defined or modified in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="24c85-164">0x20</span><span class="sxs-lookup"><span data-stu-id="24c85-164">0x20</span></span> | <span data-ttu-id="24c85-165">限制对从基类继承的属性的枚举。</span><span class="sxs-lookup"><span data-stu-id="24c85-165">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="24c85-166">要求</span><span class="sxs-lookup"><span data-stu-id="24c85-166">Requirements</span></span>  
 <span data-ttu-id="24c85-167">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24c85-167">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24c85-168">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="24c85-168">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="24c85-169">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="24c85-169">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24c85-170">请参阅</span><span class="sxs-lookup"><span data-stu-id="24c85-170">See also</span></span>

- [<span data-ttu-id="24c85-171">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="24c85-171">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)