---
title: GetMethod 函数 （非托管 API 参考）
description: GetMethod 函数可检索有关方法的信息。
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 65b8cb74a028892a3494e818f2b523f75e8766a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460442"
---
# <a name="getmethod-function"></a><span data-ttu-id="e6ee5-103">GetMethod 函数</span><span class="sxs-lookup"><span data-stu-id="e6ee5-103">GetMethod function</span></span>
<span data-ttu-id="e6ee5-104">检索有关指定方法的信息。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e6ee5-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6ee5-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="e6ee5-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6ee5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e6ee5-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e6ee5-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="e6ee5-109">[in]方法名。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-109">[in] The method name.</span></span> <span data-ttu-id="e6ee5-110">此参数不能为`null`且必须指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="e6ee5-111">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-111">[in] Reserved.</span></span> <span data-ttu-id="e6ee5-112">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="e6ee5-113">[out]指向的地址的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)描述在 paramteers 到方法的实例。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-113">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="e6ee5-114">如果设置为，则忽略此参数`null`。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="e6ee5-115">[out]指向的地址的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)描述对方法的输出参数的实例。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-115">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="e6ee5-116">如果设置为，则忽略此参数`null`。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="e6ee5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="e6ee5-117">Return value</span></span>

<span data-ttu-id="e6ee5-118">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="e6ee5-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e6ee5-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e6ee5-119">Constant</span></span>  |<span data-ttu-id="e6ee5-120">值</span><span class="sxs-lookup"><span data-stu-id="e6ee5-120">Value</span></span>  |<span data-ttu-id="e6ee5-121">描述</span><span class="sxs-lookup"><span data-stu-id="e6ee5-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e6ee5-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e6ee5-122">0x80041002</span></span> | <span data-ttu-id="e6ee5-123">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e6ee5-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e6ee5-124">0x80041006</span></span> | <span data-ttu-id="e6ee5-125">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e6ee5-126">0</span><span class="sxs-lookup"><span data-stu-id="e6ee5-126">0</span></span> | <span data-ttu-id="e6ee5-127">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e6ee5-128">备注</span><span class="sxs-lookup"><span data-stu-id="e6ee5-128">Remarks</span></span>

<span data-ttu-id="e6ee5-129">此函数包装对的调用[IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-129">This function wraps a call to the [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="e6ee5-130">可以设置 Windows 管理[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向`null`如果此方法不具有任何输入参数。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-130">Windows Management can set the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="e6ee5-131">在`ppInSignature`和`ppOutSignature`分别，为中的属性描述输入和输出参数，`IWbemClassObject`系统类的实例[_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span></span> <span data-ttu-id="e6ee5-132">中的属性`ppInsignature`名为 **Param * * * n*，其中*n*是方法签名中的参数位置 (如`Param1`，`Param2`等。)。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-132">The properties in `ppInsignature` are named **Param***n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="e6ee5-133">中的属性`ppOutSignature`也名为 **Param * * * n*，和返回值名为**ReturnValue**。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-133">The properties in `ppOutSignature` are also named **Param***n*, and the return value is named **ReturnValue**.</span></span> <span data-ttu-id="e6ee5-134">有关详细信息及示例，请参阅[IWbemClassObject::GetMethod 方法](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx)。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-134">For more information and an example, see [IWbemClassObject::GetMethod method](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="e6ee5-135">要求</span><span class="sxs-lookup"><span data-stu-id="e6ee5-135">Requirements</span></span>  
<span data-ttu-id="e6ee5-136">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6ee5-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6ee5-137">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e6ee5-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e6ee5-138">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e6ee5-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6ee5-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6ee5-139">See also</span></span>  
[<span data-ttu-id="e6ee5-140">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e6ee5-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
