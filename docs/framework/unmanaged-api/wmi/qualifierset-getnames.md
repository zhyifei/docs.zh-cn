---
title: QualifierSet_GetNames 函数 （非托管 API 参考）
description: QualifierSet_GetNames 函数从某个对象或属性检索的限定符的名称。
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 84059c5e5542e13b1d4fc4efcfc4c7f418db391e
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43877932"
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="7931f-103">QualifierSet_GetNames 函数</span><span class="sxs-lookup"><span data-stu-id="7931f-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="7931f-104">检索所有的限定符或某些来自当前对象或属性的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="7931f-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7931f-105">语法</span><span class="sxs-lookup"><span data-stu-id="7931f-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="7931f-106">参数</span><span class="sxs-lookup"><span data-stu-id="7931f-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="7931f-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="7931f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="7931f-108">[in]一个指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例。</span><span class="sxs-lookup"><span data-stu-id="7931f-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="7931f-109">[in]以下标志或值，该值指定要在枚举中包括哪些名称之一。</span><span class="sxs-lookup"><span data-stu-id="7931f-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="7931f-110">返回的常量</span><span class="sxs-lookup"><span data-stu-id="7931f-110">Constant</span></span>  |<span data-ttu-id="7931f-111">“值”</span><span class="sxs-lookup"><span data-stu-id="7931f-111">Value</span></span>  |<span data-ttu-id="7931f-112">描述</span><span class="sxs-lookup"><span data-stu-id="7931f-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="7931f-113">0</span><span class="sxs-lookup"><span data-stu-id="7931f-113">0</span></span> | <span data-ttu-id="7931f-114">返回所有限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="7931f-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="7931f-115">0x10</span><span class="sxs-lookup"><span data-stu-id="7931f-115">0x10</span></span> | <span data-ttu-id="7931f-116">返回限定符的名称特定于当前的属性或对象。</span><span class="sxs-lookup"><span data-stu-id="7931f-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="7931f-117">属性： 返回仅限定符特定属性 （包括重写），并不是这些限定符传播从类定义。</span><span class="sxs-lookup"><span data-stu-id="7931f-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="7931f-118">实例： 返回仅特定于实例的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="7931f-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="7931f-119">类： 回到派生类 beiong 特定仅限定符。</span><span class="sxs-lookup"><span data-stu-id="7931f-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="7931f-120">0x20</span><span class="sxs-lookup"><span data-stu-id="7931f-120">0x20</span></span> | <span data-ttu-id="7931f-121">返回名称的列是限定符传播从另一个对象。</span><span class="sxs-lookup"><span data-stu-id="7931f-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="7931f-122">属性： 返回仅限定符传播给此属性从类定义中，而不从该属性本身。</span><span class="sxs-lookup"><span data-stu-id="7931f-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="7931f-123">实例： 从类定义返回仅这些限定符传播。</span><span class="sxs-lookup"><span data-stu-id="7931f-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="7931f-124">类： 返回从父类继承仅这些限定符名称。</span><span class="sxs-lookup"><span data-stu-id="7931f-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="7931f-125">`pstrNames` [out]一个新`SAFEARRAY`，其中包含请求的名称。</span><span class="sxs-lookup"><span data-stu-id="7931f-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="7931f-126">该数组可以具有 0 个元素。</span><span class="sxs-lookup"><span data-stu-id="7931f-126">The array can have 0 elements.</span></span> <span data-ttu-id="7931f-127">如果发生错误，新`SAFEARRAY`不会返回。</span><span class="sxs-lookup"><span data-stu-id="7931f-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="7931f-128">返回值</span><span class="sxs-lookup"><span data-stu-id="7931f-128">Return value</span></span>

<span data-ttu-id="7931f-129">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="7931f-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7931f-130">返回的常量</span><span class="sxs-lookup"><span data-stu-id="7931f-130">Constant</span></span>  |<span data-ttu-id="7931f-131">“值”</span><span class="sxs-lookup"><span data-stu-id="7931f-131">Value</span></span>  |<span data-ttu-id="7931f-132">描述</span><span class="sxs-lookup"><span data-stu-id="7931f-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7931f-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7931f-133">0x80041008</span></span> | <span data-ttu-id="7931f-134">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="7931f-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7931f-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7931f-135">0x80041006</span></span> | <span data-ttu-id="7931f-136">没有足够的内存，可开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="7931f-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7931f-137">0</span><span class="sxs-lookup"><span data-stu-id="7931f-137">0</span></span> | <span data-ttu-id="7931f-138">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="7931f-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7931f-139">备注</span><span class="sxs-lookup"><span data-stu-id="7931f-139">Remarks</span></span>

<span data-ttu-id="7931f-140">此函数包装对的调用[IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames)方法。</span><span class="sxs-lookup"><span data-stu-id="7931f-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="7931f-141">已检索到的限定符名称后, 您可以访问每个限定符的名称通过调用[QualifierSet_Get](qualifierset-get.md)函数。</span><span class="sxs-lookup"><span data-stu-id="7931f-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="7931f-142">它不是给定的对象具有零个限定符，因此错误中的字符串数`pstrNames`返回时可为 0，即使该函数将返回`WBEM_S_NO_ERROR`。</span><span class="sxs-lookup"><span data-stu-id="7931f-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="7931f-143">要求</span><span class="sxs-lookup"><span data-stu-id="7931f-143">Requirements</span></span>  
 <span data-ttu-id="7931f-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7931f-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7931f-145">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7931f-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7931f-146">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7931f-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7931f-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="7931f-147">See also</span></span>  
[<span data-ttu-id="7931f-148">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="7931f-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
