---
title: "GetMethod 函数 （非托管 API 参考）"
description: "GetMethod 函数可检索有关方法的信息。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethod
helpviewer_keywords: GetMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f22a2dfa7aae411cac960cbad2017718df8057e1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="getmethod-function"></a><span data-ttu-id="7e7c1-103">GetMethod 函数</span><span class="sxs-lookup"><span data-stu-id="7e7c1-103">GetMethod function</span></span>
<span data-ttu-id="7e7c1-104">检索有关指定方法的信息。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="7e7c1-105">语法</span><span class="sxs-lookup"><span data-stu-id="7e7c1-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="7e7c1-106">参数</span><span class="sxs-lookup"><span data-stu-id="7e7c1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="7e7c1-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="7e7c1-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="7e7c1-109">[in]方法名。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-109">[in] The method name.</span></span> <span data-ttu-id="7e7c1-110">此参数不能为`null`且必须指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="7e7c1-111">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-111">[in] Reserved.</span></span> <span data-ttu-id="7e7c1-112">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="7e7c1-113">[out]指向的地址的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)描述在 paramteers 到方法的实例。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-113">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="7e7c1-114">如果设置为，则忽略此参数`null`。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="7e7c1-115">[out]指向的地址的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)描述对方法的输出参数的实例。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-115">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="7e7c1-116">如果设置为，则忽略此参数`null`。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="7e7c1-117">返回值</span><span class="sxs-lookup"><span data-stu-id="7e7c1-117">Return value</span></span>

<span data-ttu-id="7e7c1-118">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="7e7c1-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7e7c1-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="7e7c1-119">Constant</span></span>  |<span data-ttu-id="7e7c1-120">“值”</span><span class="sxs-lookup"><span data-stu-id="7e7c1-120">Value</span></span>  |<span data-ttu-id="7e7c1-121">描述</span><span class="sxs-lookup"><span data-stu-id="7e7c1-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="7e7c1-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7e7c1-122">0x80041002</span></span> | <span data-ttu-id="7e7c1-123">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7e7c1-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7e7c1-124">0x80041006</span></span> | <span data-ttu-id="7e7c1-125">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7e7c1-126">0</span><span class="sxs-lookup"><span data-stu-id="7e7c1-126">0</span></span> | <span data-ttu-id="7e7c1-127">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="7e7c1-128">备注</span><span class="sxs-lookup"><span data-stu-id="7e7c1-128">Remarks</span></span>

<span data-ttu-id="7e7c1-129">此函数包装对的调用[IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-129">This function wraps a call to the [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="7e7c1-130">可以设置 Windows 管理[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向`null`如果此方法不具有任何输入参数。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-130">Windows Management can set the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="7e7c1-131">在`ppInSignature`和`ppOutSignature`分别，为中的属性描述输入和输出参数，`IWbemClassObject`系统类的实例[_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span></span> <span data-ttu-id="7e7c1-132">中的属性`ppInsignature`命名**Param***n*，其中 *n* 是参数 （例如将方法签名中的位置作为`Param1`，`Param2`等。)。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-132">The properties in `ppInsignature` are named **Param***n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="7e7c1-133">中的属性`ppOutSignature`也称为**Param***n*，和返回值名为**ReturnValue**。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-133">The properties in `ppOutSignature` are also named **Param***n*, and the return value is named **ReturnValue**.</span></span> <span data-ttu-id="7e7c1-134">有关详细信息及示例，请参阅[IWbemClassObject::GetMethod 方法](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-134">For more information and an example, see [IWbemClassObject::GetMethod method](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="7e7c1-135">惠?</span><span class="sxs-lookup"><span data-stu-id="7e7c1-135">Requirements</span></span>  
<span data-ttu-id="7e7c1-136">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7e7c1-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7e7c1-137">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7e7c1-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7e7c1-138">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7e7c1-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e7c1-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="7e7c1-139">See also</span></span>  
[<span data-ttu-id="7e7c1-140">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="7e7c1-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
