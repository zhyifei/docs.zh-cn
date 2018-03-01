---
title: "GetMethodQualifierSet 函数 （非托管 API 参考）"
description: "GetMethodQualifierSet 函数检索方法的限定符集。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2999bef31576cf2bc025868260c2b1782a9b69f9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="61bb3-103">GetMethodQualifierSet 函数</span><span class="sxs-lookup"><span data-stu-id="61bb3-103">GetMethodQualifierSet function</span></span>
<span data-ttu-id="61bb3-104">检索为特定方法设置的限定符。</span><span class="sxs-lookup"><span data-stu-id="61bb3-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="61bb3-105">语法</span><span class="sxs-lookup"><span data-stu-id="61bb3-105">Syntax</span></span>  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="61bb3-106">参数</span><span class="sxs-lookup"><span data-stu-id="61bb3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="61bb3-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="61bb3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="61bb3-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="61bb3-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethod`  
<span data-ttu-id="61bb3-109">[in]方法名。</span><span class="sxs-lookup"><span data-stu-id="61bb3-109">[in] The method  name.</span></span> <span data-ttu-id="61bb3-110">`wszMethod`必须指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="61bb3-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span> 

`ppQualSet`  
<span data-ttu-id="61bb3-111">[out]接收的接口指针，它允许访问的方法的限定符。</span><span class="sxs-lookup"><span data-stu-id="61bb3-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="61bb3-112">`ppQualSet` 不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="61bb3-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="61bb3-113">如果出现错误，则不返回一个新对象，并且指针设置为指向`null`。</span><span class="sxs-lookup"><span data-stu-id="61bb3-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="61bb3-114">返回值</span><span class="sxs-lookup"><span data-stu-id="61bb3-114">Return value</span></span>

<span data-ttu-id="61bb3-115">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="61bb3-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="61bb3-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="61bb3-116">Constant</span></span>  |<span data-ttu-id="61bb3-117">“值”</span><span class="sxs-lookup"><span data-stu-id="61bb3-117">Value</span></span>  |<span data-ttu-id="61bb3-118">描述</span><span class="sxs-lookup"><span data-stu-id="61bb3-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="61bb3-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="61bb3-119">0x80041002</span></span> | <span data-ttu-id="61bb3-120">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="61bb3-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="61bb3-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="61bb3-121">0x80041008</span></span> | <span data-ttu-id="61bb3-122">参数是`null`。</span><span class="sxs-lookup"><span data-stu-id="61bb3-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="61bb3-123">0</span><span class="sxs-lookup"><span data-stu-id="61bb3-123">0</span></span> | <span data-ttu-id="61bb3-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="61bb3-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="61bb3-125">备注</span><span class="sxs-lookup"><span data-stu-id="61bb3-125">Remarks</span></span>

<span data-ttu-id="61bb3-126">此函数包装对的调用[IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="61bb3-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](https://msdn.microsoft.com/library/aa391446(v=vs.85).aspx) method.</span></span> 

<span data-ttu-id="61bb3-127">仅当当前对象是 CIM 类定义，被支持对此函数的调用。</span><span class="sxs-lookup"><span data-stu-id="61bb3-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="61bb3-128">方法操作不可用于[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters 指向 CIM 实例。</span><span class="sxs-lookup"><span data-stu-id="61bb3-128">Method manipulation is not available for [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) ponters that point to CIM instances.</span></span>

<span data-ttu-id="61bb3-129">因为每个方法可能具有其自己的限定符， [IWbemQualifierSet 指针](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)允许调用方添加、 编辑或删除这些限定符。</span><span class="sxs-lookup"><span data-stu-id="61bb3-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="61bb3-130">惠?</span><span class="sxs-lookup"><span data-stu-id="61bb3-130">Requirements</span></span>  
<span data-ttu-id="61bb3-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61bb3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61bb3-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="61bb3-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="61bb3-133">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="61bb3-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61bb3-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="61bb3-134">See also</span></span>  
[<span data-ttu-id="61bb3-135">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="61bb3-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
