---
title: GetNames 函数 （非托管 API 参考）
description: GetNames 函数检索的对象的属性的名称。
ms.date: 11/06/2017
api_name:
- GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetNames
helpviewer_keywords:
- GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f664edf29e5d2f9ec4e523aa7f7b204cf999e01b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61724078"
---
# <a name="getnames-function"></a><span data-ttu-id="44e6d-103">GetNames 函数</span><span class="sxs-lookup"><span data-stu-id="44e6d-103">GetNames function</span></span>
<span data-ttu-id="44e6d-104">检索对象属性的子集或所有名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="44e6d-105">语法</span><span class="sxs-lookup"><span data-stu-id="44e6d-105">Syntax</span></span>  
  
```  
HRESULT GetNames (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="44e6d-106">参数</span><span class="sxs-lookup"><span data-stu-id="44e6d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="44e6d-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="44e6d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="44e6d-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="44e6d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="44e6d-109">[in]指向一个有效的指针`LPCWSTR`，指定作为筛选器的一部分进行操作的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="44e6d-110">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="44e6d-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="44e6d-111">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="44e6d-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="44e6d-112">[in]位域的组合。</span><span class="sxs-lookup"><span data-stu-id="44e6d-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="44e6d-113">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="44e6d-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="44e6d-114">[in]指向一个有效的指针`VARIANT`结构初始化为一个筛选器值。</span><span class="sxs-lookup"><span data-stu-id="44e6d-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="44e6d-115">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="44e6d-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="44e6d-116">[out]一个`SAFEARRAY`结构，其中包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="44e6d-117">在进入时，此参数必须始终为一个指向`null`。</span><span class="sxs-lookup"><span data-stu-id="44e6d-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="44e6d-118">请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="44e6d-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="44e6d-119">返回值</span><span class="sxs-lookup"><span data-stu-id="44e6d-119">Return value</span></span>

<span data-ttu-id="44e6d-120">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="44e6d-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="44e6d-121">返回的常量</span><span class="sxs-lookup"><span data-stu-id="44e6d-121">Constant</span></span>  |<span data-ttu-id="44e6d-122">“值”</span><span class="sxs-lookup"><span data-stu-id="44e6d-122">Value</span></span>  |<span data-ttu-id="44e6d-123">描述</span><span class="sxs-lookup"><span data-stu-id="44e6d-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="44e6d-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="44e6d-124">0x80041001</span></span> | <span data-ttu-id="44e6d-125">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="44e6d-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="44e6d-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="44e6d-126">0x80041008</span></span> | <span data-ttu-id="44e6d-127">一个或多个参数无效，或者指定了不正确的标志和参数组合。</span><span class="sxs-lookup"><span data-stu-id="44e6d-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="44e6d-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="44e6d-128">0x80041006</span></span> | <span data-ttu-id="44e6d-129">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="44e6d-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="44e6d-130">0</span><span class="sxs-lookup"><span data-stu-id="44e6d-130">0</span></span> | <span data-ttu-id="44e6d-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="44e6d-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="44e6d-132">备注</span><span class="sxs-lookup"><span data-stu-id="44e6d-132">Remarks</span></span>

<span data-ttu-id="44e6d-133">此函数包装对的调用[IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)方法。</span><span class="sxs-lookup"><span data-stu-id="44e6d-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="44e6d-134">由组合的标志和参数控制返回的命名。</span><span class="sxs-lookup"><span data-stu-id="44e6d-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="44e6d-135">例如，该函数可以返回所有属性的名称或键属性的名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="44e6d-136">中指定主要筛选器`lFlags`参数，并使用其他参数不同，具体取决于它。</span><span class="sxs-lookup"><span data-stu-id="44e6d-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="44e6d-137">中的标志值`lFlags`是位域</span><span class="sxs-lookup"><span data-stu-id="44e6d-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="44e6d-138">可以作为传递的标志`lEnumFlags`自变量是在中定义的位域*WbemCli.h*标头文件，也可以在定义它们为常量在代码中。</span><span class="sxs-lookup"><span data-stu-id="44e6d-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="44e6d-139">可以结合任何其他组中的任何标志每个组中的一个标志。</span><span class="sxs-lookup"><span data-stu-id="44e6d-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="44e6d-140">但是，在同一组中的标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="44e6d-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="44e6d-141">组 1 标志</span><span class="sxs-lookup"><span data-stu-id="44e6d-141">Group 1 flags</span></span> |<span data-ttu-id="44e6d-142">“值”</span><span class="sxs-lookup"><span data-stu-id="44e6d-142">Value</span></span>  |<span data-ttu-id="44e6d-143">Description</span><span class="sxs-lookup"><span data-stu-id="44e6d-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="44e6d-144">0</span><span class="sxs-lookup"><span data-stu-id="44e6d-144">0</span></span> | <span data-ttu-id="44e6d-145">返回所有属性名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-145">Return all property names.</span></span> <span data-ttu-id="44e6d-146">`strQualifierName` 和`pQualifierVal`未使用。</span><span class="sxs-lookup"><span data-stu-id="44e6d-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="44e6d-147">1</span><span class="sxs-lookup"><span data-stu-id="44e6d-147">1</span></span> | <span data-ttu-id="44e6d-148">返回具有指定的名称的限定符的唯一属性`strQualifierName`参数。</span><span class="sxs-lookup"><span data-stu-id="44e6d-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="44e6d-149">如果使用此标志，则必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="44e6d-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="44e6d-150">2</span><span class="sxs-lookup"><span data-stu-id="44e6d-150">2</span></span> |  <span data-ttu-id="44e6d-151">返回不具有指定的名称的限定符的唯一属性`strQualifierName`参数。</span><span class="sxs-lookup"><span data-stu-id="44e6d-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="44e6d-152">如果使用此标志，则必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="44e6d-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="44e6d-153">3</span><span class="sxs-lookup"><span data-stu-id="44e6d-153">3</span></span> | <span data-ttu-id="44e6d-154">返回具有指定的名称的限定符的属性`wszQualifierName`参数和也有值与指定的相同`pQualifierVal`结构。</span><span class="sxs-lookup"><span data-stu-id="44e6d-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="44e6d-155">如果使用此标志，则必须指定这两`wszQualifierName`和一个`pQualifierValue`。</span><span class="sxs-lookup"><span data-stu-id="44e6d-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="44e6d-156">组 2 标志</span><span class="sxs-lookup"><span data-stu-id="44e6d-156">Group 2 flags</span></span> |<span data-ttu-id="44e6d-157">“值”</span><span class="sxs-lookup"><span data-stu-id="44e6d-157">Value</span></span>  |<span data-ttu-id="44e6d-158">描述</span><span class="sxs-lookup"><span data-stu-id="44e6d-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="44e6d-159">0x4</span><span class="sxs-lookup"><span data-stu-id="44e6d-159">0x4</span></span> | <span data-ttu-id="44e6d-160">返回定义的键的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="44e6d-161">0x8</span><span class="sxs-lookup"><span data-stu-id="44e6d-161">0x8</span></span> | <span data-ttu-id="44e6d-162">返回唯一属性名称的对象引用。</span><span class="sxs-lookup"><span data-stu-id="44e6d-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="44e6d-163">组 3 标志</span><span class="sxs-lookup"><span data-stu-id="44e6d-163">Group 3 flags</span></span> |<span data-ttu-id="44e6d-164">“值”</span><span class="sxs-lookup"><span data-stu-id="44e6d-164">Value</span></span>  |<span data-ttu-id="44e6d-165">描述</span><span class="sxs-lookup"><span data-stu-id="44e6d-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="44e6d-166">0x10</span><span class="sxs-lookup"><span data-stu-id="44e6d-166">0x10</span></span> | <span data-ttu-id="44e6d-167">返回属于派生程度最高的类的属性名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="44e6d-168">从父类中排除的属性。</span><span class="sxs-lookup"><span data-stu-id="44e6d-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="44e6d-169">0x20</span><span class="sxs-lookup"><span data-stu-id="44e6d-169">0x20</span></span> | <span data-ttu-id="44e6d-170">返回属于父类的属性名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="44e6d-171">0x30</span><span class="sxs-lookup"><span data-stu-id="44e6d-171">0x30</span></span> | <span data-ttu-id="44e6d-172">返回系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="44e6d-173">0x40</span><span class="sxs-lookup"><span data-stu-id="44e6d-173">0x40</span></span> | <span data-ttu-id="44e6d-174">返回仅非系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="44e6d-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="44e6d-175">该函数始终会分配一个新`SAFEARRAY`如果它返回`WBEM_S_NO_ERROR`，和`pstrNames`始终设置为指向它。</span><span class="sxs-lookup"><span data-stu-id="44e6d-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="44e6d-176">如果没有属性与指定筛选器匹配，则返回的数组可以有 0 个元素。</span><span class="sxs-lookup"><span data-stu-id="44e6d-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="44e6d-177">如果该函数将返回一个值，而不`WBM_S_NO_ERROR`，新`SAFEARRAY`结构，则不返回。</span><span class="sxs-lookup"><span data-stu-id="44e6d-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="44e6d-178">要求</span><span class="sxs-lookup"><span data-stu-id="44e6d-178">Requirements</span></span>  
 <span data-ttu-id="44e6d-179">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44e6d-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e6d-180">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="44e6d-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="44e6d-181">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="44e6d-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e6d-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="44e6d-182">See also</span></span>

- [<span data-ttu-id="44e6d-183">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="44e6d-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
