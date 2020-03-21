---
title: 获取名称功能（非托管 API 引用）
description: GetNames 函数检索对象属性的名称。
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
ms.openlocfilehash: 449f0ce9c291d4bbcad4947214e56ff46f55beed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174948"
---
# <a name="getnames-function"></a><span data-ttu-id="7b116-103">GetNames 函数</span><span class="sxs-lookup"><span data-stu-id="7b116-103">GetNames function</span></span>
<span data-ttu-id="7b116-104">检索对象属性的子集或所有名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-104">Retrieves either a subset or all of the names of the properties of an object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7b116-105">语法</span><span class="sxs-lookup"><span data-stu-id="7b116-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNames (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszQualifierName,
   [in] LONG                lFlags,
   [in] VARIANT*            pQualifierValue,
   [out] SAFEARRAY (BSTR)** pstrNames
);
```  

## <a name="parameters"></a><span data-ttu-id="7b116-106">parameters</span><span class="sxs-lookup"><span data-stu-id="7b116-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7b116-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="7b116-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7b116-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="7b116-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="7b116-109">[在]指向有效的`LPCWSTR`指针，用于指定作为筛选器一部分运行的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="7b116-110">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="7b116-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="7b116-111">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="7b116-111">This parameter can be `null`.</span></span>

`lFlags`  
<span data-ttu-id="7b116-112">[在]位字段的组合。</span><span class="sxs-lookup"><span data-stu-id="7b116-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="7b116-113">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="7b116-113">For more information, see the [Remarks](#remarks) section.</span></span>

<span data-ttu-id="7b116-114">`pQualifierValue`[在]指向初始化到筛选器`VARIANT`值的有效结构的指针。</span><span class="sxs-lookup"><span data-stu-id="7b116-114">`pQualifierValue` [in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="7b116-115">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="7b116-115">This parameter can be `null`.</span></span>

`pstrNames`  
<span data-ttu-id="7b116-116">[出]包含`SAFEARRAY`属性名称的结构。</span><span class="sxs-lookup"><span data-stu-id="7b116-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="7b116-117">在输入时，此参数必须始终是指向`null`的指针。</span><span class="sxs-lookup"><span data-stu-id="7b116-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="7b116-118">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="7b116-118">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="7b116-119">返回值</span><span class="sxs-lookup"><span data-stu-id="7b116-119">Return value</span></span>

<span data-ttu-id="7b116-120">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="7b116-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7b116-121">一直</span><span class="sxs-lookup"><span data-stu-id="7b116-121">Constant</span></span>  |<span data-ttu-id="7b116-122">值</span><span class="sxs-lookup"><span data-stu-id="7b116-122">Value</span></span>  |<span data-ttu-id="7b116-123">说明</span><span class="sxs-lookup"><span data-stu-id="7b116-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="7b116-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7b116-124">0x80041001</span></span> | <span data-ttu-id="7b116-125">出现了一个普遍的失败。</span><span class="sxs-lookup"><span data-stu-id="7b116-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7b116-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7b116-126">0x80041008</span></span> | <span data-ttu-id="7b116-127">一个或多个参数无效，或指定了不正确的标志和参数组合。</span><span class="sxs-lookup"><span data-stu-id="7b116-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7b116-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7b116-128">0x80041006</span></span> | <span data-ttu-id="7b116-129">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="7b116-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7b116-130">0</span><span class="sxs-lookup"><span data-stu-id="7b116-130">0</span></span> | <span data-ttu-id="7b116-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="7b116-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7b116-132">备注</span><span class="sxs-lookup"><span data-stu-id="7b116-132">Remarks</span></span>

<span data-ttu-id="7b116-133">此函数包装对[IWbem ClassObject 的调用：：getNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)方法。</span><span class="sxs-lookup"><span data-stu-id="7b116-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="7b116-134">返回的命名由标志和参数的组合控制。</span><span class="sxs-lookup"><span data-stu-id="7b116-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="7b116-135">例如，函数可以返回所有属性的名称，也可以仅返回键属性的名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="7b116-136">主筛选器在`lFlags`参数中指定，其他参数因它而异。</span><span class="sxs-lookup"><span data-stu-id="7b116-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="7b116-137">中`lFlags`的标志值是位字段</span><span class="sxs-lookup"><span data-stu-id="7b116-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="7b116-138">可以作为`lEnumFlags`参数传递的标志是在*WbemCli.h*标头文件中定义的位字段，也可以将它们定义为代码中的常量。</span><span class="sxs-lookup"><span data-stu-id="7b116-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="7b116-139">您可以将每个组中的一个标志与任何其他组的任何标志合并。</span><span class="sxs-lookup"><span data-stu-id="7b116-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="7b116-140">但是，来自同一组的标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="7b116-140">However, flags from the same group are mutually exclusive.</span></span>

| <span data-ttu-id="7b116-141">组 1 标志</span><span class="sxs-lookup"><span data-stu-id="7b116-141">Group 1 flags</span></span> |<span data-ttu-id="7b116-142">值</span><span class="sxs-lookup"><span data-stu-id="7b116-142">Value</span></span>  |<span data-ttu-id="7b116-143">说明</span><span class="sxs-lookup"><span data-stu-id="7b116-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="7b116-144">0</span><span class="sxs-lookup"><span data-stu-id="7b116-144">0</span></span> | <span data-ttu-id="7b116-145">返回所有属性名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-145">Return all property names.</span></span> <span data-ttu-id="7b116-146">`strQualifierName`未`pQualifierVal`使用。</span><span class="sxs-lookup"><span data-stu-id="7b116-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="7b116-147">1</span><span class="sxs-lookup"><span data-stu-id="7b116-147">1</span></span> | <span data-ttu-id="7b116-148">仅返回具有`strQualifierName`参数指定名称限定符的属性。</span><span class="sxs-lookup"><span data-stu-id="7b116-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7b116-149">如果使用此标志，则必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="7b116-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="7b116-150">2</span><span class="sxs-lookup"><span data-stu-id="7b116-150">2</span></span> |  <span data-ttu-id="7b116-151">仅返回没有`strQualifierName`参数指定名称限定符的属性。</span><span class="sxs-lookup"><span data-stu-id="7b116-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="7b116-152">如果使用此标志，则必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="7b116-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="7b116-153">3</span><span class="sxs-lookup"><span data-stu-id="7b116-153">3</span></span> | <span data-ttu-id="7b116-154">仅返回具有`wszQualifierName`参数指定名称限定符且值与`pQualifierVal`结构指定的值相同的属性。</span><span class="sxs-lookup"><span data-stu-id="7b116-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="7b116-155">如果使用此标志，则必须同时指定 a`wszQualifierName`和 。 `pQualifierValue`</span><span class="sxs-lookup"><span data-stu-id="7b116-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="7b116-156">组 2 标志</span><span class="sxs-lookup"><span data-stu-id="7b116-156">Group 2 flags</span></span> |<span data-ttu-id="7b116-157">值</span><span class="sxs-lookup"><span data-stu-id="7b116-157">Value</span></span>  |<span data-ttu-id="7b116-158">说明</span><span class="sxs-lookup"><span data-stu-id="7b116-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="7b116-159">0x4</span><span class="sxs-lookup"><span data-stu-id="7b116-159">0x4</span></span> | <span data-ttu-id="7b116-160">仅返回定义键的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="7b116-161">0x8</span><span class="sxs-lookup"><span data-stu-id="7b116-161">0x8</span></span> | <span data-ttu-id="7b116-162">仅返回作为对象引用的属性名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="7b116-163">组 3 标志</span><span class="sxs-lookup"><span data-stu-id="7b116-163">Group 3 flags</span></span> |<span data-ttu-id="7b116-164">值</span><span class="sxs-lookup"><span data-stu-id="7b116-164">Value</span></span>  |<span data-ttu-id="7b116-165">说明</span><span class="sxs-lookup"><span data-stu-id="7b116-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7b116-166">0x10</span><span class="sxs-lookup"><span data-stu-id="7b116-166">0x10</span></span> | <span data-ttu-id="7b116-167">仅返回属于最派生类的属性名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="7b116-168">从父类中排除属性。</span><span class="sxs-lookup"><span data-stu-id="7b116-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="7b116-169">0x20</span><span class="sxs-lookup"><span data-stu-id="7b116-169">0x20</span></span> | <span data-ttu-id="7b116-170">仅返回属于父类的属性名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="7b116-171">0x30</span><span class="sxs-lookup"><span data-stu-id="7b116-171">0x30</span></span> | <span data-ttu-id="7b116-172">仅返回系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="7b116-173">0x40</span><span class="sxs-lookup"><span data-stu-id="7b116-173">0x40</span></span> | <span data-ttu-id="7b116-174">仅返回非系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="7b116-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="7b116-175">如果函数返回`SAFEARRAY``WBEM_S_NO_ERROR`，则始终分配新函数，并且`pstrNames`始终设置为指向它。</span><span class="sxs-lookup"><span data-stu-id="7b116-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="7b116-176">如果没有与指定筛选器匹配的属性，则返回的数组可以具有 0 个元素。</span><span class="sxs-lookup"><span data-stu-id="7b116-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="7b116-177">如果函数返回的值，`WBM_S_NO_ERROR`则不返回新`SAFEARRAY`结构。</span><span class="sxs-lookup"><span data-stu-id="7b116-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b116-178">要求</span><span class="sxs-lookup"><span data-stu-id="7b116-178">Requirements</span></span>  
 <span data-ttu-id="7b116-179">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b116-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b116-180">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7b116-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7b116-181">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7b116-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7b116-182">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b116-182">See also</span></span>

- [<span data-ttu-id="7b116-183">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="7b116-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
