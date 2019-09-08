---
title: GetNames 函数（非托管 API 参考）
description: GetNames 函数检索对象的属性的名称。
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
ms.openlocfilehash: 748767596a8f4680a2d7b63cb0579acaed5f53f8
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798515"
---
# <a name="getnames-function"></a><span data-ttu-id="4a657-103">GetNames 函数</span><span class="sxs-lookup"><span data-stu-id="4a657-103">GetNames function</span></span>
<span data-ttu-id="4a657-104">检索对象属性的子集或所有名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-104">Retrieves either a subset or all of the names of the properties of an object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4a657-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a657-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="4a657-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a657-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4a657-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="4a657-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4a657-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="4a657-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszQualifierName`  
<span data-ttu-id="4a657-109">中指向有效`LPCWSTR`的指针，它指定作为筛选器一部分进行操作的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-109">[in] A pointer to a valid `LPCWSTR` that specifies a qualifier name that operates as part of a filter.</span></span> <span data-ttu-id="4a657-110">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="4a657-110">For more information, see the [Remarks](#remarks) section.</span></span> <span data-ttu-id="4a657-111">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="4a657-111">This parameter can be `null`.</span></span> 

`lFlags`  
<span data-ttu-id="4a657-112">中位域的组合。</span><span class="sxs-lookup"><span data-stu-id="4a657-112">[in] A combination of bit fields.</span></span> <span data-ttu-id="4a657-113">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="4a657-113">For more information, see the [Remarks](#remarks) section.</span></span>

`pQualifierValue`   
<span data-ttu-id="4a657-114">中指向初始化为筛选器`VARIANT`值的有效结构的指针。</span><span class="sxs-lookup"><span data-stu-id="4a657-114">[in] A pointer to a valid `VARIANT` structure initialized to a filter value.</span></span> <span data-ttu-id="4a657-115">此参数可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="4a657-115">This parameter can be `null`.</span></span> 

`pstrNames`  
<span data-ttu-id="4a657-116">弄包含属性名称的结构。`SAFEARRAY`</span><span class="sxs-lookup"><span data-stu-id="4a657-116">[out] A `SAFEARRAY` structure that contains property names.</span></span> <span data-ttu-id="4a657-117">输入时，此参数必须始终是指向`null`的指针。</span><span class="sxs-lookup"><span data-stu-id="4a657-117">On entry, this parameter must always be a pointer to `null`.</span></span> <span data-ttu-id="4a657-118">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="4a657-118">See the [Remarks](#remarks) section for more information.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4a657-119">返回值</span><span class="sxs-lookup"><span data-stu-id="4a657-119">Return value</span></span>

<span data-ttu-id="4a657-120">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="4a657-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4a657-121">返回的常量</span><span class="sxs-lookup"><span data-stu-id="4a657-121">Constant</span></span>  |<span data-ttu-id="4a657-122">值</span><span class="sxs-lookup"><span data-stu-id="4a657-122">Value</span></span>  |<span data-ttu-id="4a657-123">描述</span><span class="sxs-lookup"><span data-stu-id="4a657-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="4a657-124">0x80041001</span><span class="sxs-lookup"><span data-stu-id="4a657-124">0x80041001</span></span> | <span data-ttu-id="4a657-125">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="4a657-125">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4a657-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4a657-126">0x80041008</span></span> | <span data-ttu-id="4a657-127">一个或多个参数无效，或者指定的标志和参数组合不正确。</span><span class="sxs-lookup"><span data-stu-id="4a657-127">One or more parameters are not valid, or an incorrect combination of flags and parameters was specified.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4a657-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4a657-128">0x80041006</span></span> | <span data-ttu-id="4a657-129">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="4a657-129">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4a657-130">0</span><span class="sxs-lookup"><span data-stu-id="4a657-130">0</span></span> | <span data-ttu-id="4a657-131">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="4a657-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="4a657-132">备注</span><span class="sxs-lookup"><span data-stu-id="4a657-132">Remarks</span></span>

<span data-ttu-id="4a657-133">此函数包装对[IWbemClassObject：： GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="4a657-133">This function wraps a call to the [IWbemClassObject::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getnames) method.</span></span>

<span data-ttu-id="4a657-134">命名返回的由标志和参数的组合来控制。</span><span class="sxs-lookup"><span data-stu-id="4a657-134">The named returned are controlled by a combination of flags and parameters.</span></span> <span data-ttu-id="4a657-135">例如，函数可以返回所有属性的名称，或者只返回密钥属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-135">For example, the function can return the names of all properties or only the names of the key properties.</span></span>  <span data-ttu-id="4a657-136">主筛选器是在`lFlags`参数中指定的，其他参数根据它的不同而不同。</span><span class="sxs-lookup"><span data-stu-id="4a657-136">The primary filter is specified in the `lFlags` parameter, and the other parameters vary depending on it.</span></span>

<span data-ttu-id="4a657-137">中`lFlags`的标志值为位域</span><span class="sxs-lookup"><span data-stu-id="4a657-137">The flag values in `lFlags` are bit fields</span></span>

<span data-ttu-id="4a657-138">可以作为`lEnumFlags`参数传递的标志是在*WbemCli*头文件中定义的位域，也可以在代码中将它们定义为常量。</span><span class="sxs-lookup"><span data-stu-id="4a657-138">The flags that can be passed as the `lEnumFlags` argument are bit fields that are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>  <span data-ttu-id="4a657-139">可以将每个组中的一个标志与任何其他组中的任何标志组合在一起。</span><span class="sxs-lookup"><span data-stu-id="4a657-139">You can combine one flag from each group with any flag from any other group.</span></span> <span data-ttu-id="4a657-140">但是，同一组中的标志互相排斥。</span><span class="sxs-lookup"><span data-stu-id="4a657-140">However, flags from the same group are mutually exclusive.</span></span> 

| <span data-ttu-id="4a657-141">组1标志</span><span class="sxs-lookup"><span data-stu-id="4a657-141">Group 1 flags</span></span> |<span data-ttu-id="4a657-142">值</span><span class="sxs-lookup"><span data-stu-id="4a657-142">Value</span></span>  |<span data-ttu-id="4a657-143">Description</span><span class="sxs-lookup"><span data-stu-id="4a657-143">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_ALWAYS` | <span data-ttu-id="4a657-144">0</span><span class="sxs-lookup"><span data-stu-id="4a657-144">0</span></span> | <span data-ttu-id="4a657-145">返回所有属性名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-145">Return all property names.</span></span> <span data-ttu-id="4a657-146">`strQualifierName`和`pQualifierVal`均未使用。</span><span class="sxs-lookup"><span data-stu-id="4a657-146">`strQualifierName` and `pQualifierVal` are unused.</span></span> |
| `WBEM_FLAG_ONLY_IF_TRUE` | <span data-ttu-id="4a657-147">1</span><span class="sxs-lookup"><span data-stu-id="4a657-147">1</span></span> | <span data-ttu-id="4a657-148">仅返回具有`strQualifierName`参数指定的名称限定符的属性。</span><span class="sxs-lookup"><span data-stu-id="4a657-148">Return only properties that have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="4a657-149">如果使用此标志，则必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="4a657-149">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_FALSE` | <span data-ttu-id="4a657-150">2</span><span class="sxs-lookup"><span data-stu-id="4a657-150">2</span></span> |  <span data-ttu-id="4a657-151">仅返回不具有`strQualifierName`参数指定的名称限定符的属性。</span><span class="sxs-lookup"><span data-stu-id="4a657-151">Return only properties that do not have a qualifier of the name specified by the `strQualifierName` parameter.</span></span> <span data-ttu-id="4a657-152">如果使用此标志，则必须指定`strQualifierName`。</span><span class="sxs-lookup"><span data-stu-id="4a657-152">If this flag is used, you must specify `strQualifierName`.</span></span> |
|`WBEM_FLAG_ONLY_IF_IDENTICAL` | <span data-ttu-id="4a657-153">3</span><span class="sxs-lookup"><span data-stu-id="4a657-153">3</span></span> | <span data-ttu-id="4a657-154">仅返回具有`wszQualifierName`参数指定的名称限定符的属性，并且其值与`pQualifierVal`结构指定的值相同。</span><span class="sxs-lookup"><span data-stu-id="4a657-154">Return only properties that have a qualifier of the name specified by the `wszQualifierName` parameter and also have a value identical to that specified by the `pQualifierVal` structure.</span></span> <span data-ttu-id="4a657-155">如果使用此标志，则必须同时`wszQualifierName`指定`pQualifierValue`和。</span><span class="sxs-lookup"><span data-stu-id="4a657-155">If this flag is used, you must specify both a `wszQualifierName` and a `pQualifierValue`.</span></span> |

| <span data-ttu-id="4a657-156">组2标志</span><span class="sxs-lookup"><span data-stu-id="4a657-156">Group 2 flags</span></span> |<span data-ttu-id="4a657-157">值</span><span class="sxs-lookup"><span data-stu-id="4a657-157">Value</span></span>  |<span data-ttu-id="4a657-158">描述</span><span class="sxs-lookup"><span data-stu-id="4a657-158">Description</span></span>  |
|---------|---------|---------|
|`WBEM_FLAG_KEYS_ONLY` | <span data-ttu-id="4a657-159">0x4</span><span class="sxs-lookup"><span data-stu-id="4a657-159">0x4</span></span> | <span data-ttu-id="4a657-160">仅返回定义键的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-160">Return only the names of properties that define the keys.</span></span> |
|`WBEM_FLAG_REFS_ONLY` | <span data-ttu-id="4a657-161">0x8</span><span class="sxs-lookup"><span data-stu-id="4a657-161">0x8</span></span> | <span data-ttu-id="4a657-162">仅返回对象引用的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-162">Return only property names that are object references.</span></span> |

| <span data-ttu-id="4a657-163">组3标志</span><span class="sxs-lookup"><span data-stu-id="4a657-163">Group 3 flags</span></span> |<span data-ttu-id="4a657-164">值</span><span class="sxs-lookup"><span data-stu-id="4a657-164">Value</span></span>  |<span data-ttu-id="4a657-165">描述</span><span class="sxs-lookup"><span data-stu-id="4a657-165">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="4a657-166">0x10</span><span class="sxs-lookup"><span data-stu-id="4a657-166">0x10</span></span> | <span data-ttu-id="4a657-167">仅返回属于派生程度最高的类的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-167">Return only property names that belong to the most derived class.</span></span> <span data-ttu-id="4a657-168">排除父类中的属性。</span><span class="sxs-lookup"><span data-stu-id="4a657-168">Exclude properties from the parent classes.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="4a657-169">0x20</span><span class="sxs-lookup"><span data-stu-id="4a657-169">0x20</span></span> | <span data-ttu-id="4a657-170">仅返回属于父类的属性名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-170">Return only property names that belong to the parent classes.</span></span> |
|`WBEM_FLAG_SYSTEM_ONLY` | <span data-ttu-id="4a657-171">0x30</span><span class="sxs-lookup"><span data-stu-id="4a657-171">0x30</span></span> | <span data-ttu-id="4a657-172">仅返回系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-172">Return only the names of system properties.</span></span> |
|`WBEM_FLAG_NONSYSTEM_ONLY` | <span data-ttu-id="4a657-173">0x40</span><span class="sxs-lookup"><span data-stu-id="4a657-173">0x40</span></span> | <span data-ttu-id="4a657-174">仅返回非系统属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4a657-174">Return only the names of non-system properties.</span></span> |

<span data-ttu-id="4a657-175">如果函数返回`WBEM_S_NO_ERROR`，则该`SAFEARRAY`函数始终分配一个新`pstrNames`的，并且始终设置为指向该函数。</span><span class="sxs-lookup"><span data-stu-id="4a657-175">The function always allocates a new `SAFEARRAY` if it returns `WBEM_S_NO_ERROR`, and `pstrNames` is always set to point to it.</span></span> <span data-ttu-id="4a657-176">如果没有属性与指定的筛选器匹配，则返回的数组可以有0个元素。</span><span class="sxs-lookup"><span data-stu-id="4a657-176">The returned array can have 0 elements if no properties match the specified filters.</span></span> <span data-ttu-id="4a657-177">如果函数返回的值`WBM_S_NO_ERROR`不是，则不返回新`SAFEARRAY`结构。</span><span class="sxs-lookup"><span data-stu-id="4a657-177">If the function returns an value other than `WBM_S_NO_ERROR`, a new `SAFEARRAY` structure is not returned.</span></span>
 
## <a name="requirements"></a><span data-ttu-id="4a657-178">要求</span><span class="sxs-lookup"><span data-stu-id="4a657-178">Requirements</span></span>  
 <span data-ttu-id="4a657-179">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a657-179">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a657-180">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4a657-180">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4a657-181">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4a657-181">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a657-182">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a657-182">See also</span></span>

- [<span data-ttu-id="4a657-183">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="4a657-183">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
