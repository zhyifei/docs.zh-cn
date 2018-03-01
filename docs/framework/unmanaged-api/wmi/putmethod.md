---
title: "PutMethod 函数 （非托管 API 参考）"
description: "PutMethod 函数创建一个方法。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- PutMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- PutMethod
helpviewer_keywords:
- PutMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7e97ffcf44a738234f67d9736382c46c42e5b61e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="putmethod-function"></a><span data-ttu-id="84037-103">PutMethod 函数</span><span class="sxs-lookup"><span data-stu-id="84037-103">PutMethod function</span></span>
<span data-ttu-id="84037-104">创建一个方法。</span><span class="sxs-lookup"><span data-stu-id="84037-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="84037-105">语法</span><span class="sxs-lookup"><span data-stu-id="84037-105">Syntax</span></span>  
  
```  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="84037-106">参数</span><span class="sxs-lookup"><span data-stu-id="84037-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="84037-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="84037-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="84037-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="84037-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="84037-109">[in]要创建的方法名称。</span><span class="sxs-lookup"><span data-stu-id="84037-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="84037-110">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="84037-110">[in] Reserved.</span></span> <span data-ttu-id="84037-111">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="84037-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="84037-112">[in]指向一份[__Parameters 系统类](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)包含`in`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="84037-112">[in] A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="84037-113">如果忽略此参数设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="84037-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="84037-114">[in] 指向一份[__Parameters 系统类](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)包含`out`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="84037-114">[in]  A pointer to a copy of the [__Parameters system class](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="84037-115">如果忽略此参数设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="84037-115">This parameter is ignored if set to `null`.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="84037-116">返回值</span><span class="sxs-lookup"><span data-stu-id="84037-116">Return value</span></span>

<span data-ttu-id="84037-117">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="84037-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="84037-118">返回的常量</span><span class="sxs-lookup"><span data-stu-id="84037-118">Constant</span></span>  |<span data-ttu-id="84037-119">“值”</span><span class="sxs-lookup"><span data-stu-id="84037-119">Value</span></span>  |<span data-ttu-id="84037-120">描述</span><span class="sxs-lookup"><span data-stu-id="84037-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="84037-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="84037-121">0x80041008</span></span> | <span data-ttu-id="84037-122">一个或多个参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="84037-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="84037-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="84037-123">0x80041043</span></span> | <span data-ttu-id="84037-124">`[in, out]`方法参数中同时指定*pInSignature*和*pOutSignature*对象具有不同的限定符。</span><span class="sxs-lookup"><span data-stu-id="84037-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="84037-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="84037-125">0x80041036</span></span> | <span data-ttu-id="84037-126">方法参数缺少的规范**ID**限定符。</span><span class="sxs-lookup"><span data-stu-id="84037-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="84037-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="84037-127">0x80041038</span></span> | <span data-ttu-id="84037-128">分配给方法参数 ID 系列不连续，或不在 0 时不启动。</span><span class="sxs-lookup"><span data-stu-id="84037-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="84037-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="84037-129">0x80041039</span></span> | <span data-ttu-id="84037-130">一种方法的返回值具有**ID**限定符。</span><span class="sxs-lookup"><span data-stu-id="84037-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="84037-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="84037-131">0x80041034</span></span> | <span data-ttu-id="84037-132">尝试重用现有方法的父类、 名称和签名不匹配。</span><span class="sxs-lookup"><span data-stu-id="84037-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="84037-133">0</span><span class="sxs-lookup"><span data-stu-id="84037-133">0</span></span> | <span data-ttu-id="84037-134">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="84037-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="84037-135">备注</span><span class="sxs-lookup"><span data-stu-id="84037-135">Remarks</span></span>

<span data-ttu-id="84037-136">此函数包装对的调用[IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="84037-136">This function wraps a call to the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="84037-137">如果仅支持此方法调用`ptr`是 CIM 类定义。</span><span class="sxs-lookup"><span data-stu-id="84037-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="84037-138">方法操作不能从[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396)指向 CIM 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="84037-138">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) pointers that point to CIM instances.</span></span>

<span data-ttu-id="84037-139">用户无法创建方法的开头或结尾下划线开头的名称。</span><span class="sxs-lookup"><span data-stu-id="84037-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="84037-140">这被保留供系统类和属性。</span><span class="sxs-lookup"><span data-stu-id="84037-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="84037-141">对于方法，`in`和`out`参数为中的属性，请参见[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396)对象。</span><span class="sxs-lookup"><span data-stu-id="84037-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx?f=255&MSPPError=-2147217396) objects.</span></span>

<span data-ttu-id="84037-142">`[in/out]`参数可以通过将相同的属性添加到指向这两个对象定义`pInSignature`和`pOutSignature`参数。</span><span class="sxs-lookup"><span data-stu-id="84037-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="84037-143">在这种情况下，属性共用同一个**ID**限定符值。</span><span class="sxs-lookup"><span data-stu-id="84037-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="84037-144">每个属性[__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx)以外类对象`ReturnValue`必须具有**ID**限定符，标识参数的顺序的从零开始的数字值。</span><span class="sxs-lookup"><span data-stu-id="84037-144">Each property in a [__Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="84037-145">没有两个参数可以具有相同**ID**值，但没有**ID**可以跳过值。</span><span class="sxs-lookup"><span data-stu-id="84037-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="84037-146">如果任何一种情况发生，`PutMethod`函数返回`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`。</span><span class="sxs-lookup"><span data-stu-id="84037-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="84037-147">示例</span><span class="sxs-lookup"><span data-stu-id="84037-147">Example</span></span>

<span data-ttu-id="84037-148">有关示例，请参阅[IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="84037-148">For an example, see the [IWbemClassObject::PutMethod](https://msdn.microsoft.com/library/aa391456(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="84037-149">惠?</span><span class="sxs-lookup"><span data-stu-id="84037-149">Requirements</span></span>  
 <span data-ttu-id="84037-150">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84037-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84037-151">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="84037-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="84037-152">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="84037-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84037-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="84037-153">See also</span></span>  
[<span data-ttu-id="84037-154">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="84037-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
