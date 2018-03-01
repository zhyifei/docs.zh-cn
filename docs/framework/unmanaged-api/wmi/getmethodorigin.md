---
title: "GetMethodOrigin 函数 （非托管 API 参考）"
description: "GetMethodOrigin 函数将确定在其中声明了方法的类。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a97376b459a5d9cce9b18ff692ac4c7535a24a56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="830d6-103">GetMethodOrigin 函数</span><span class="sxs-lookup"><span data-stu-id="830d6-103">GetMethodOrigin function</span></span>
<span data-ttu-id="830d6-104">确定在其中声明了方法的类。</span><span class="sxs-lookup"><span data-stu-id="830d6-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="830d6-105">语法</span><span class="sxs-lookup"><span data-stu-id="830d6-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="830d6-106">参数</span><span class="sxs-lookup"><span data-stu-id="830d6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="830d6-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="830d6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="830d6-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="830d6-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="830d6-109">[in]针对正在请求其所属的类的对象的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="830d6-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="830d6-110">[out]接收拥有方法的类的名称。</span><span class="sxs-lookup"><span data-stu-id="830d6-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="830d6-111">返回值</span><span class="sxs-lookup"><span data-stu-id="830d6-111">Return value</span></span>

<span data-ttu-id="830d6-112">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="830d6-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="830d6-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="830d6-113">Constant</span></span>  |<span data-ttu-id="830d6-114">“值”</span><span class="sxs-lookup"><span data-stu-id="830d6-114">Value</span></span>  |<span data-ttu-id="830d6-115">描述</span><span class="sxs-lookup"><span data-stu-id="830d6-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="830d6-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="830d6-116">0x80041002</span></span> | <span data-ttu-id="830d6-117">找不到指定的方法。</span><span class="sxs-lookup"><span data-stu-id="830d6-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="830d6-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="830d6-118">0x80041008</span></span> | <span data-ttu-id="830d6-119">一个或多个参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="830d6-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="830d6-120">0</span><span class="sxs-lookup"><span data-stu-id="830d6-120">0</span></span> | <span data-ttu-id="830d6-121">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="830d6-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="830d6-122">备注</span><span class="sxs-lookup"><span data-stu-id="830d6-122">Remarks</span></span>

<span data-ttu-id="830d6-123">此函数包装对的调用[IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="830d6-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="830d6-124">类可以从一个或多个基类继承方法，因为开发人员通常需要确定在其中定义给定的方法的类。</span><span class="sxs-lookup"><span data-stu-id="830d6-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="830d6-125">`pstrClassName`参数必须指向有效`BSTR`因为这是调用该函数之前`out`参数; 此函数返回之后，会释放指针。</span><span class="sxs-lookup"><span data-stu-id="830d6-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="830d6-126">惠?</span><span class="sxs-lookup"><span data-stu-id="830d6-126">Requirements</span></span>  
<span data-ttu-id="830d6-127">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="830d6-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="830d6-128">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="830d6-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="830d6-129">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="830d6-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="830d6-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="830d6-130">See also</span></span>  
[<span data-ttu-id="830d6-131">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="830d6-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
