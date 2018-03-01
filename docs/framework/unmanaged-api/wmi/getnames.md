---
title: "GetNames 函数 （非托管 API 参考）"
description: "GetNames 函数检索的对象的属性的名称。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
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
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80284900c318a3776168b781ce2e0e5e4a68f96d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getnames-function"></a><span data-ttu-id="09d1a-103">GetNames 函数</span><span class="sxs-lookup"><span data-stu-id="09d1a-103">GetNames function</span></span>
<span data-ttu-id="09d1a-104">检索的子集或所有对象的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="09d1a-105">语法</span><span class="sxs-lookup"><span data-stu-id="09d1a-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="09d1a-106">参数</span><span class="sxs-lookup"><span data-stu-id="09d1a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="09d1a-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="09d1a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="09d1a-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="09d1a-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="09d1a-109">[in]指向一个有效的指针`LPCWSTR`指定筛选器的一部分运行的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="09d1a-110">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="09d1a-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="09d1a-111">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="09d1a-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="09d1a-112">[in]位域的组合。</span><span class="sxs-lookup"><span data-stu-id="09d1a-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="09d1a-113">有关详细信息，请参阅[备注](#remarks)部分。</span><span class="sxs-lookup"><span data-stu-id="09d1a-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="09d1a-114">[in]指向一个有效的指针`VARIANT`结构初始化为筛选器值。</span><span class="sxs-lookup"><span data-stu-id="09d1a-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="09d1a-115">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="09d1a-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="09d1a-116">[out]A`SAFEARRAY`结构，其中包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="09d1a-117">在进入时，此参数必须始终为指向的指针`null`。</span><span class="sxs-lookup"><span data-stu-id="09d1a-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="09d1a-118">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="09d1a-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="09d1a-119">返回值</span><span class="sxs-lookup"><span data-stu-id="09d1a-119">Return value</span></span>

<span data-ttu-id="09d1a-120">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="09d1a-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="09d1a-121">返回的常量</span><span class="sxs-lookup"><span data-stu-id="09d1a-121">Constant</span></span>  |<span data-ttu-id="09d1a-122">“值”</span><span class="sxs-lookup"><span data-stu-id="09d1a-122">Value</span></span>  |<span data-ttu-id="09d1a-123">描述</span><span class="sxs-lookup"><span data-stu-id="09d1a-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="09d1a-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="09d1a-124">0x80041001</span></span> | <span data-ttu-id="09d1a-125">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="09d1a-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="09d1a-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="09d1a-126">0x80041008</span></span> | <span data-ttu-id="09d1a-127">一个或多个参数是无效，或未指定的标志和参数的正确组合。</span><span class="sxs-lookup"><span data-stu-id="09d1a-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="09d1a-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="09d1a-128">0x80041006</span></span> | <span data-ttu-id="09d1a-129">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="09d1a-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="09d1a-130">0</span><span class="sxs-lookup"><span data-stu-id="09d1a-130">0</span></span> | <span data-ttu-id="09d1a-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="09d1a-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="09d1a-132">备注</span><span class="sxs-lookup"><span data-stu-id="09d1a-132">Remarks</span></span>

<span data-ttu-id="09d1a-133">此函数包装对的调用[IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="09d1a-133">This function wraps a call to the [IWbemClassObject::GetNames](https://msdn.microsoft.com/library/aa391447(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="09d1a-134">由标志和参数的组合控制返回的命名。</span><span class="sxs-lookup"><span data-stu-id="09d1a-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="09d1a-135">例如，函数可以返回所有属性的名称或键属性的名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="09d1a-136">中指定主筛选器`lFlags`参数，并使用其他参数不同，具体取决于它。</span><span class="sxs-lookup"><span data-stu-id="09d1a-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="09d1a-137">中的标志值`lFlags`是位域</span><span class="sxs-lookup"><span data-stu-id="09d1a-137">The flag values in `lFlags` are bit fields</span></span>


<span data-ttu-id="09d1a-138">可以作为传递的标志`lEnumFlags`自变量是在中定义的位域*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。</span><span class="sxs-lookup"><span data-stu-id="09d1a-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="09d1a-139">你可以组合使用任何其他组的任何标志每个组中的一个标志。</span><span class="sxs-lookup"><span data-stu-id="09d1a-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="09d1a-140">但是，同一组中的标志是互斥的。</span><span class="sxs-lookup"><span data-stu-id="09d1a-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="09d1a-141">组 1 标志</span><span class="sxs-lookup"><span data-stu-id="09d1a-141">Group 1 flags</span></span> |<span data-ttu-id="09d1a-142">“值”</span><span class="sxs-lookup"><span data-stu-id="09d1a-142">Value</span></span>  |<span data-ttu-id="09d1a-143">描述</span><span class="sxs-lookup"><span data-stu-id="09d1a-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="09d1a-144">0</span><span class="sxs-lookup"><span data-stu-id="09d1a-144">0</span></span> | <span data-ttu-id="09d1a-145">返回所有属性名。</span><span class="sxs-lookup"><span data-stu-id="09d1a-145">Return all property names.</span></span> <span data-ttu-id="09d1a-146">`strQualifierName`和`pQualifierVal`未使用。</span><span class="sxs-lookup"><span data-stu-id="09d1a-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="09d1a-147">1</span><span class="sxs-lookup"><span data-stu-id="09d1a-147">1</span></span> | <span data-ttu-id="09d1a-148">返回具有指定的名称的限定符的唯一属性`strQualifierName`参数。</span><span class="sxs-lookup"><span data-stu-id="09d1a-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="09d1a-149">如果使用此标志，你必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="09d1a-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="09d1a-150">2</span><span class="sxs-lookup"><span data-stu-id="09d1a-150">2</span></span> |  <span data-ttu-id="09d1a-151">返回不具有指定的名称的限定符的唯一属性`strQualifierName`参数。</span><span class="sxs-lookup"><span data-stu-id="09d1a-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="09d1a-152">如果使用此标志，你必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="09d1a-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="09d1a-153">3</span><span class="sxs-lookup"><span data-stu-id="09d1a-153">3</span></span> | <span data-ttu-id="09d1a-154">返回具有指定的名称的限定符的属性`wszQualifierName`参数和也有等于指定的值`pQualifierVal`结构。</span><span class="sxs-lookup"><span data-stu-id="09d1a-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="09d1a-155">如果使用此标志，则必须将同时指定`wszQualifierName`和`pQualifierValue`。</span><span class="sxs-lookup"><span data-stu-id="09d1a-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="09d1a-156">组 2 标志</span><span class="sxs-lookup"><span data-stu-id="09d1a-156">Group 2 flags</span></span> |<span data-ttu-id="09d1a-157">“值”</span><span class="sxs-lookup"><span data-stu-id="09d1a-157">Value</span></span>  |<span data-ttu-id="09d1a-158">描述</span><span class="sxs-lookup"><span data-stu-id="09d1a-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="09d1a-159">0x4</span><span class="sxs-lookup"><span data-stu-id="09d1a-159">0x4</span></span> | <span data-ttu-id="09d1a-160">返回仅定义的键的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="09d1a-161">0x8</span><span class="sxs-lookup"><span data-stu-id="09d1a-161">0x8</span></span> | <span data-ttu-id="09d1a-162">返回唯一属性的名称是对象的引用。</span><span class="sxs-lookup"><span data-stu-id="09d1a-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="09d1a-163">组 3 标志</span><span class="sxs-lookup"><span data-stu-id="09d1a-163">Group 3 flags</span></span> |<span data-ttu-id="09d1a-164">“值”</span><span class="sxs-lookup"><span data-stu-id="09d1a-164">Value</span></span>  |<span data-ttu-id="09d1a-165">描述</span><span class="sxs-lookup"><span data-stu-id="09d1a-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="09d1a-166">0x10</span><span class="sxs-lookup"><span data-stu-id="09d1a-166">0x10</span></span> | <span data-ttu-id="09d1a-167">返回属于派生程度最高的类添加的属性名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="09d1a-168">从父类中排除属性。</span><span class="sxs-lookup"><span data-stu-id="09d1a-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="09d1a-169">0x20</span><span class="sxs-lookup"><span data-stu-id="09d1a-169">0x20</span></span> | <span data-ttu-id="09d1a-170">返回属于父类添加的属性名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="09d1a-171">0x30</span><span class="sxs-lookup"><span data-stu-id="09d1a-171">0x30</span></span> | <span data-ttu-id="09d1a-172">返回系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="09d1a-173">0x40</span><span class="sxs-lookup"><span data-stu-id="09d1a-173">0x40</span></span> | <span data-ttu-id="09d1a-174">返回仅非系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="09d1a-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="09d1a-175">函数始终分配一个新`SAFEARRAY`如果它返回`WBEM_S_NO_ERROR`，和`pstrNames`始终设置为指向它。</span><span class="sxs-lookup"><span data-stu-id="09d1a-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="09d1a-176">如果没有属性与指定筛选器匹配，则返回的数组可以有 0 个元素。</span><span class="sxs-lookup"><span data-stu-id="09d1a-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="09d1a-177">如果该函数返回值以外`WBM_S_NO_ERROR`，新`SAFEARRAY`结构，则不返回。</span><span class="sxs-lookup"><span data-stu-id="09d1a-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="09d1a-178">惠?</span><span class="sxs-lookup"><span data-stu-id="09d1a-178">Requirements</span></span>  
 <span data-ttu-id="09d1a-179">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="09d1a-179">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09d1a-180">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="09d1a-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="09d1a-181">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="09d1a-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d1a-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="09d1a-182">See also</span></span>  
[<span data-ttu-id="09d1a-183">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="09d1a-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
