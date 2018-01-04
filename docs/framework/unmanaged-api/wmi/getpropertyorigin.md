---
title: "GetPropertyOrigin 函数 （Unmnaged API 参考）"
description: "GetPropertyOrigin 函数将确定所声明的属性的类。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyOrigin
helpviewer_keywords: GetPropertyOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0a79bfc62ad776cb2bfab2c143d19761d64358bf
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="a070a-103">GetPropertyOrigin 函数</span><span class="sxs-lookup"><span data-stu-id="a070a-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="a070a-104">确定所声明的属性的类。</span><span class="sxs-lookup"><span data-stu-id="a070a-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="a070a-105">语法</span><span class="sxs-lookup"><span data-stu-id="a070a-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="a070a-106">参数</span><span class="sxs-lookup"><span data-stu-id="a070a-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a070a-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="a070a-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a070a-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="a070a-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="a070a-109">[in]正在请求其所属的类的对象的属性名称。</span><span class="sxs-lookup"><span data-stu-id="a070a-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="a070a-110">[out]接收拥有的属性类的名称。</span><span class="sxs-lookup"><span data-stu-id="a070a-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="a070a-111">返回值</span><span class="sxs-lookup"><span data-stu-id="a070a-111">Return value</span></span>

<span data-ttu-id="a070a-112">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="a070a-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a070a-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="a070a-113">Constant</span></span>  |<span data-ttu-id="a070a-114">“值”</span><span class="sxs-lookup"><span data-stu-id="a070a-114">Value</span></span>  |<span data-ttu-id="a070a-115">描述</span><span class="sxs-lookup"><span data-stu-id="a070a-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="a070a-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a070a-116">0x80041001</span></span> | <span data-ttu-id="a070a-117">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="a070a-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="a070a-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="a070a-118">0x80041002</span></span> | <span data-ttu-id="a070a-119">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="a070a-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a070a-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a070a-120">0x80041008</span></span> | <span data-ttu-id="a070a-121">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="a070a-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a070a-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a070a-122">0x80041006</span></span> | <span data-ttu-id="a070a-123">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="a070a-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a070a-124">0</span><span class="sxs-lookup"><span data-stu-id="a070a-124">0</span></span> | <span data-ttu-id="a070a-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="a070a-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="a070a-126">备注</span><span class="sxs-lookup"><span data-stu-id="a070a-126">Remarks</span></span>

<span data-ttu-id="a070a-127">此函数包装对的调用[IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="a070a-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a070a-128">类可以从一个或多个基类继承属性，因为开发人员通常需要确定在其中定义给定的方法的属性。</span><span class="sxs-lookup"><span data-stu-id="a070a-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="a070a-129">`pstrClassName`参数必须指向有效`BSTR`因为这是调用该函数之前`out`参数; 此函数返回之后，会释放指针。</span><span class="sxs-lookup"><span data-stu-id="a070a-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="a070a-130">惠?</span><span class="sxs-lookup"><span data-stu-id="a070a-130">Requirements</span></span>  
<span data-ttu-id="a070a-131">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a070a-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a070a-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a070a-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a070a-133">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a070a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a070a-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="a070a-134">See also</span></span>  
[<span data-ttu-id="a070a-135">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="a070a-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
