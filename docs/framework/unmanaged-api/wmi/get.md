---
title: "Get 函数 （非托管 API 参考）"
description: "Get 函数将检索指定的属性值。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 69312030689ab1b87e3aadd040395f06e1c94ac8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="get-function"></a><span data-ttu-id="60ec2-103">Get 函数</span><span class="sxs-lookup"><span data-stu-id="60ec2-103">Get function</span></span>
<span data-ttu-id="60ec2-104">如果它存在，请检索指定的属性值。</span><span class="sxs-lookup"><span data-stu-id="60ec2-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="60ec2-105">语法</span><span class="sxs-lookup"><span data-stu-id="60ec2-105">Syntax</span></span>  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="60ec2-106">参数</span><span class="sxs-lookup"><span data-stu-id="60ec2-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="60ec2-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="60ec2-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="60ec2-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="60ec2-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="60ec2-109">[in]属性的名称。</span><span class="sxs-lookup"><span data-stu-id="60ec2-109">[in] The name of the property.</span></span>

<span data-ttu-id="60ec2-110">`lFlags`[in]保留。</span><span class="sxs-lookup"><span data-stu-id="60ec2-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="60ec2-111">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="60ec2-111">This parameter must be 0.</span></span>

<span data-ttu-id="60ec2-112">`pVal`[out]如果该函数将返回成功，包含的值的`wszName`属性。</span><span class="sxs-lookup"><span data-stu-id="60ec2-112">`pVal` [out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="60ec2-113">`pval`自变量分配的正确类型和值限定符。</span><span class="sxs-lookup"><span data-stu-id="60ec2-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

<span data-ttu-id="60ec2-114">`pvtType`[out]如果该函数将返回成功，则包含[CIM 类型的常量](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx)，该值指示属性类型。</span><span class="sxs-lookup"><span data-stu-id="60ec2-114">`pvtType` [out] If the function returns successfully, contains a [CIM-type constant](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) that indicates the property type.</span></span> <span data-ttu-id="60ec2-115">其值也可以是`null`。</span><span class="sxs-lookup"><span data-stu-id="60ec2-115">Its value can also be `null`.</span></span> 

<span data-ttu-id="60ec2-116">`plFlavor`[out]如果该函数将返回成功，则接收原点顺的属性的信息。</span><span class="sxs-lookup"><span data-stu-id="60ec2-116">`plFlavor` [out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="60ec2-117">其值可以是`null`，或定义中的以下 WBEM_FLAVOR_TYPE 常量之一*WbemCli.h*标头文件：</span><span class="sxs-lookup"><span data-stu-id="60ec2-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="60ec2-118">返回的常量</span><span class="sxs-lookup"><span data-stu-id="60ec2-118">Constant</span></span>  |<span data-ttu-id="60ec2-119">“值”</span><span class="sxs-lookup"><span data-stu-id="60ec2-119">Value</span></span>  |<span data-ttu-id="60ec2-120">描述</span><span class="sxs-lookup"><span data-stu-id="60ec2-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="60ec2-121">0x40</span><span class="sxs-lookup"><span data-stu-id="60ec2-121">0x40</span></span> | <span data-ttu-id="60ec2-122">属性是标准系统属性。</span><span class="sxs-lookup"><span data-stu-id="60ec2-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="60ec2-123">0x20</span><span class="sxs-lookup"><span data-stu-id="60ec2-123">0x20</span></span> | <span data-ttu-id="60ec2-124">类： 从父类继承属性。</span><span class="sxs-lookup"><span data-stu-id="60ec2-124">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="60ec2-125">实例： 属性，继承自的父类、 时未修改的实例。</span><span class="sxs-lookup"><span data-stu-id="60ec2-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="60ec2-126">0</span><span class="sxs-lookup"><span data-stu-id="60ec2-126">0</span></span> | <span data-ttu-id="60ec2-127">类： 属性所属的派生类。</span><span class="sxs-lookup"><span data-stu-id="60ec2-127">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="60ec2-128">实例： 实例; 修改的属性也就是说，已提供的值，或限定符已添加或修改。</span><span class="sxs-lookup"><span data-stu-id="60ec2-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="60ec2-129">返回值</span><span class="sxs-lookup"><span data-stu-id="60ec2-129">Return value</span></span>

<span data-ttu-id="60ec2-130">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="60ec2-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="60ec2-131">返回的常量</span><span class="sxs-lookup"><span data-stu-id="60ec2-131">Constant</span></span>  |<span data-ttu-id="60ec2-132">“值”</span><span class="sxs-lookup"><span data-stu-id="60ec2-132">Value</span></span>  |<span data-ttu-id="60ec2-133">描述</span><span class="sxs-lookup"><span data-stu-id="60ec2-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="60ec2-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="60ec2-134">0x80041001</span></span> | <span data-ttu-id="60ec2-135">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="60ec2-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="60ec2-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="60ec2-136">0x80041008</span></span> | <span data-ttu-id="60ec2-137">一个或多个参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="60ec2-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="60ec2-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="60ec2-138">0x80041002</span></span> | <span data-ttu-id="60ec2-139">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="60ec2-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="60ec2-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="60ec2-140">0x80041006</span></span> | <span data-ttu-id="60ec2-141">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="60ec2-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="60ec2-142">0</span><span class="sxs-lookup"><span data-stu-id="60ec2-142">0</span></span> | <span data-ttu-id="60ec2-143">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="60ec2-143">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="60ec2-144">备注</span><span class="sxs-lookup"><span data-stu-id="60ec2-144">Remarks</span></span>

<span data-ttu-id="60ec2-145">此函数包装对的调用[IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="60ec2-145">This function wraps a call to the [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="60ec2-146">`Get`函数还可以返回系统属性。</span><span class="sxs-lookup"><span data-stu-id="60ec2-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="60ec2-147">`pVal`自变量分配的正确类型和值限定符和 COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx)函数</span><span class="sxs-lookup"><span data-stu-id="60ec2-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) function</span></span>

## <a name="requirements"></a><span data-ttu-id="60ec2-148">惠?</span><span class="sxs-lookup"><span data-stu-id="60ec2-148">Requirements</span></span>  
 <span data-ttu-id="60ec2-149">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="60ec2-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60ec2-150">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="60ec2-150">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="60ec2-151">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="60ec2-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60ec2-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="60ec2-152">See also</span></span>  
[<span data-ttu-id="60ec2-153">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="60ec2-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
