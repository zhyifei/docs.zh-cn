---
title: GetPropertyQualifierSet 函数 （非托管 API 参考）
description: GetPropertyQualifierSet 函数可检索为属性设置的限定符。
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d2951733211737f06cd737b20bd1537277be1be1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461472"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="ea95d-103">GetPropertyQualifierSet 函数</span><span class="sxs-lookup"><span data-stu-id="ea95d-103">GetPropertyQualifierSet function</span></span>
<span data-ttu-id="ea95d-104">检索为特定的属性设置的限定符。</span><span class="sxs-lookup"><span data-stu-id="ea95d-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="ea95d-105">语法</span><span class="sxs-lookup"><span data-stu-id="ea95d-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="ea95d-106">参数</span><span class="sxs-lookup"><span data-stu-id="ea95d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ea95d-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="ea95d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ea95d-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="ea95d-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="ea95d-109">[in]属性名称。</span><span class="sxs-lookup"><span data-stu-id="ea95d-109">[in] The property  name.</span></span> <span data-ttu-id="ea95d-110">`wszProperty` 必须指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="ea95d-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="ea95d-111">[out]接收的接口指针，它允许访问的属性的限定符。</span><span class="sxs-lookup"><span data-stu-id="ea95d-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="ea95d-112">`ppQualSet` 不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="ea95d-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="ea95d-113">如果出现错误，则不返回一个新对象，并且指针设置为指向`null`。</span><span class="sxs-lookup"><span data-stu-id="ea95d-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="ea95d-114">返回值</span><span class="sxs-lookup"><span data-stu-id="ea95d-114">Return value</span></span>

<span data-ttu-id="ea95d-115">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="ea95d-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ea95d-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="ea95d-116">Constant</span></span>  |<span data-ttu-id="ea95d-117">值</span><span class="sxs-lookup"><span data-stu-id="ea95d-117">Value</span></span>  |<span data-ttu-id="ea95d-118">描述</span><span class="sxs-lookup"><span data-stu-id="ea95d-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ea95d-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ea95d-119">0x80041001</span></span> | <span data-ttu-id="ea95d-120">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="ea95d-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="ea95d-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ea95d-121">0x80041002</span></span> | <span data-ttu-id="ea95d-122">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="ea95d-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ea95d-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ea95d-123">0x80041006</span></span> | <span data-ttu-id="ea95d-124">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="ea95d-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ea95d-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ea95d-125">0x80041008</span></span> | <span data-ttu-id="ea95d-126">参数是`null`。</span><span class="sxs-lookup"><span data-stu-id="ea95d-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="ea95d-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="ea95d-127">0x80041030</span></span> | <span data-ttu-id="ea95d-128">该函数尝试获取限定符的系统属性。</span><span class="sxs-lookup"><span data-stu-id="ea95d-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ea95d-129">0</span><span class="sxs-lookup"><span data-stu-id="ea95d-129">0</span></span> | <span data-ttu-id="ea95d-130">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="ea95d-130">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ea95d-131">备注</span><span class="sxs-lookup"><span data-stu-id="ea95d-131">Remarks</span></span>

<span data-ttu-id="ea95d-132">此函数包装对的调用[IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="ea95d-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](https://msdn.microsoft.com/library/aa391450(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="ea95d-133">仅当当前对象是 CIM 类定义，被支持对此函数的调用。</span><span class="sxs-lookup"><span data-stu-id="ea95d-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="ea95d-134">方法操作不可用于[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters 指向 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="ea95d-134">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="ea95d-135">因为每个方法可能具有其自己的限定符， [IWbemQualifierSet 指针](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)允许调用方添加、 编辑或删除这些限定符。</span><span class="sxs-lookup"><span data-stu-id="ea95d-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="ea95d-136">由于系统属性具有不到限定符，该函数将返回`WBEM_E_SYSTEM_PROPERTY`如果你尝试获取[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)系统属性的指针。</span><span class="sxs-lookup"><span data-stu-id="ea95d-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="ea95d-137">要求</span><span class="sxs-lookup"><span data-stu-id="ea95d-137">Requirements</span></span>  
<span data-ttu-id="ea95d-138">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ea95d-138">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea95d-139">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ea95d-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ea95d-140">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea95d-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea95d-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="ea95d-141">See also</span></span>  
[<span data-ttu-id="ea95d-142">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="ea95d-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
