---
title: PutMethod 函数 （非托管 API 参考）
description: PutMethod 函数创建一个方法。
ms.date: 11/06/2017
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
ms.openlocfilehash: 74654cf18d87fed8ad5ce9a4cd4249d56fdb4343
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693446"
---
# <a name="putmethod-function"></a><span data-ttu-id="92e9f-103">PutMethod 函数</span><span class="sxs-lookup"><span data-stu-id="92e9f-103">PutMethod function</span></span>
<span data-ttu-id="92e9f-104">创建方法。</span><span class="sxs-lookup"><span data-stu-id="92e9f-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="92e9f-105">语法</span><span class="sxs-lookup"><span data-stu-id="92e9f-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="92e9f-106">参数</span><span class="sxs-lookup"><span data-stu-id="92e9f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="92e9f-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="92e9f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="92e9f-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="92e9f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="92e9f-109">[in]若要创建的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="92e9f-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="92e9f-110">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="92e9f-110">[in] Reserved.</span></span> <span data-ttu-id="92e9f-111">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="92e9f-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="92e9f-112">[in]指向一份[__Parameters 系统类](/windows/desktop/WmiSdk/--parameters)，其中包含`in`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="92e9f-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="92e9f-113">如果忽略此参数设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="92e9f-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="92e9f-114">[in] 指向一份[__Parameters 系统类](/windows/desktop/WmiSdk/--parameters)，其中包含`out`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="92e9f-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="92e9f-115">如果忽略此参数设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="92e9f-115">This parameter is ignored if set to `null`.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="92e9f-116">返回值</span><span class="sxs-lookup"><span data-stu-id="92e9f-116">Return value</span></span>

<span data-ttu-id="92e9f-117">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="92e9f-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="92e9f-118">返回的常量</span><span class="sxs-lookup"><span data-stu-id="92e9f-118">Constant</span></span>  |<span data-ttu-id="92e9f-119">值</span><span class="sxs-lookup"><span data-stu-id="92e9f-119">Value</span></span>  |<span data-ttu-id="92e9f-120">描述</span><span class="sxs-lookup"><span data-stu-id="92e9f-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="92e9f-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="92e9f-121">0x80041008</span></span> | <span data-ttu-id="92e9f-122">一个或多个参数是无效的。</span><span class="sxs-lookup"><span data-stu-id="92e9f-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="92e9f-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="92e9f-123">0x80041043</span></span> | <span data-ttu-id="92e9f-124">`[in, out]`方法参数中指定*pInSignature*并*pOutSignature*对象具有不同的限定符。</span><span class="sxs-lookup"><span data-stu-id="92e9f-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="92e9f-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="92e9f-125">0x80041036</span></span> | <span data-ttu-id="92e9f-126">方法参数缺少的规范**ID**限定符。</span><span class="sxs-lookup"><span data-stu-id="92e9f-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="92e9f-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="92e9f-127">0x80041038</span></span> | <span data-ttu-id="92e9f-128">分配到方法参数的 ID 序列不是连续或不在 0 时不启动。</span><span class="sxs-lookup"><span data-stu-id="92e9f-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="92e9f-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="92e9f-129">0x80041039</span></span> | <span data-ttu-id="92e9f-130">一种方法的返回值具有**ID**限定符。</span><span class="sxs-lookup"><span data-stu-id="92e9f-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="92e9f-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="92e9f-131">0x80041034</span></span> | <span data-ttu-id="92e9f-132">尝试重用现有的父类，方法名称和签名不匹配。</span><span class="sxs-lookup"><span data-stu-id="92e9f-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="92e9f-133">0</span><span class="sxs-lookup"><span data-stu-id="92e9f-133">0</span></span> | <span data-ttu-id="92e9f-134">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="92e9f-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="92e9f-135">备注</span><span class="sxs-lookup"><span data-stu-id="92e9f-135">Remarks</span></span>

<span data-ttu-id="92e9f-136">此函数包装对的调用[IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)方法。</span><span class="sxs-lookup"><span data-stu-id="92e9f-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="92e9f-137">当此方法调用时才支持`ptr`是 CIM 类定义。</span><span class="sxs-lookup"><span data-stu-id="92e9f-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="92e9f-138">方法操作不能从[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向 CIM 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="92e9f-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="92e9f-139">用户无法创建方法名称的开头或下划线结尾。</span><span class="sxs-lookup"><span data-stu-id="92e9f-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="92e9f-140">这被保留给系统类和属性。</span><span class="sxs-lookup"><span data-stu-id="92e9f-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="92e9f-141">对于方法，请`in`并`out`参数为中的属性，请参见[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)对象。</span><span class="sxs-lookup"><span data-stu-id="92e9f-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="92e9f-142">`[in/out]`参数可通过将相同属性添加到指向这两个对象定义`pInSignature`和`pOutSignature`参数。</span><span class="sxs-lookup"><span data-stu-id="92e9f-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="92e9f-143">在这种情况下，属性共用同一个**ID**限定符的值。</span><span class="sxs-lookup"><span data-stu-id="92e9f-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="92e9f-144">在每个属性[__Parameters](/windows/desktop/WmiSdk/--parameters)不是类对象`ReturnValue`必须具有**ID**限定符、 从零开始的数字值，用于标识参数的显示的顺序。</span><span class="sxs-lookup"><span data-stu-id="92e9f-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="92e9f-145">没有两个参数可以具有相同**ID**值，但未**ID**可以跳过值。</span><span class="sxs-lookup"><span data-stu-id="92e9f-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="92e9f-146">如果任何一种情况发生，`PutMethod`函数返回`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`。</span><span class="sxs-lookup"><span data-stu-id="92e9f-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="92e9f-147">示例</span><span class="sxs-lookup"><span data-stu-id="92e9f-147">Example</span></span>

<span data-ttu-id="92e9f-148">有关示例，请参阅[IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)方法。</span><span class="sxs-lookup"><span data-stu-id="92e9f-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="92e9f-149">要求</span><span class="sxs-lookup"><span data-stu-id="92e9f-149">Requirements</span></span>  
 <span data-ttu-id="92e9f-150">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="92e9f-150">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92e9f-151">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="92e9f-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="92e9f-152">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="92e9f-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92e9f-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="92e9f-153">See also</span></span>
- [<span data-ttu-id="92e9f-154">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="92e9f-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
