---
title: PutMethod 函数（非托管 API 参考）
description: PutMethod 函数将创建方法。
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
ms.openlocfilehash: 1d409507de593cf198fe87340eece6820eaefc63
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127332"
---
# <a name="putmethod-function"></a><span data-ttu-id="c8727-103">PutMethod 函数</span><span class="sxs-lookup"><span data-stu-id="c8727-103">PutMethod function</span></span>
<span data-ttu-id="c8727-104">创建方法。</span><span class="sxs-lookup"><span data-stu-id="c8727-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="c8727-105">语法</span><span class="sxs-lookup"><span data-stu-id="c8727-105">Syntax</span></span>  
  
```cpp  
HRESULT PutMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*  ptr, 
   [in] LPCWSTR            wszName,
   [in] LONG               lFlags,
   [in] IWbemClassObject*  pInSignature,
   [in] IWbemClassObject*  pOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="c8727-106">参数</span><span class="sxs-lookup"><span data-stu-id="c8727-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="c8727-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="c8727-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="c8727-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="c8727-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="c8727-109">中要创建的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="c8727-109">[in] The name of the method to create.</span></span> 

`lFlags`  
<span data-ttu-id="c8727-110">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="c8727-110">[in] Reserved.</span></span> <span data-ttu-id="c8727-111">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="c8727-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="c8727-112">中一个指针，指向包含方法 `in` 参数的[__Parameters 系统类](/windows/desktop/WmiSdk/--parameters)的副本。</span><span class="sxs-lookup"><span data-stu-id="c8727-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="c8727-113">如果设置为 `null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="c8727-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="c8727-114">中 一个指针，指向包含方法 `out` 参数的[__Parameters 系统类](/windows/desktop/WmiSdk/--parameters)的副本。</span><span class="sxs-lookup"><span data-stu-id="c8727-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="c8727-115">如果设置为 `null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="c8727-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c8727-116">返回值</span><span class="sxs-lookup"><span data-stu-id="c8727-116">Return value</span></span>

<span data-ttu-id="c8727-117">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="c8727-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c8727-118">返回的常量</span><span class="sxs-lookup"><span data-stu-id="c8727-118">Constant</span></span>  |<span data-ttu-id="c8727-119">“值”</span><span class="sxs-lookup"><span data-stu-id="c8727-119">Value</span></span>  |<span data-ttu-id="c8727-120">描述</span><span class="sxs-lookup"><span data-stu-id="c8727-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c8727-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c8727-121">0x80041008</span></span> | <span data-ttu-id="c8727-122">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="c8727-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="c8727-123">0x80041043</span><span class="sxs-lookup"><span data-stu-id="c8727-123">0x80041043</span></span> | <span data-ttu-id="c8727-124">*PInSignature*和*pOutSignature*对象中指定的 `[in, out]` 方法参数具有不同的限定符。</span><span class="sxs-lookup"><span data-stu-id="c8727-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="c8727-125">0x80041036</span><span class="sxs-lookup"><span data-stu-id="c8727-125">0x80041036</span></span> | <span data-ttu-id="c8727-126">方法参数缺少**ID**限定符的规范。</span><span class="sxs-lookup"><span data-stu-id="c8727-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="c8727-127">0x80041038</span><span class="sxs-lookup"><span data-stu-id="c8727-127">0x80041038</span></span> | <span data-ttu-id="c8727-128">分配给方法参数的 ID 序列不是连续的，或者不是从0开始。</span><span class="sxs-lookup"><span data-stu-id="c8727-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="c8727-129">0x80041039</span><span class="sxs-lookup"><span data-stu-id="c8727-129">0x80041039</span></span> | <span data-ttu-id="c8727-130">方法的返回值具有**ID**限定符。</span><span class="sxs-lookup"><span data-stu-id="c8727-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="c8727-131">0x80041034</span><span class="sxs-lookup"><span data-stu-id="c8727-131">0x80041034</span></span> | <span data-ttu-id="c8727-132">尝试重用父类的现有方法名称，且签名不匹配。</span><span class="sxs-lookup"><span data-stu-id="c8727-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="c8727-133">0</span><span class="sxs-lookup"><span data-stu-id="c8727-133">0</span></span> | <span data-ttu-id="c8727-134">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="c8727-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="c8727-135">备注</span><span class="sxs-lookup"><span data-stu-id="c8727-135">Remarks</span></span>

<span data-ttu-id="c8727-136">此函数包装对[IWbemClassObject：:P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="c8727-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="c8727-137">仅当 `ptr` 为 CIM 类定义时，才支持此方法调用。</span><span class="sxs-lookup"><span data-stu-id="c8727-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="c8727-138">指向 CIM 实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针不提供方法操作。</span><span class="sxs-lookup"><span data-stu-id="c8727-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="c8727-139">用户无法创建名称以下划线开头或结尾的方法。</span><span class="sxs-lookup"><span data-stu-id="c8727-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="c8727-140">此为系统类和属性保留。</span><span class="sxs-lookup"><span data-stu-id="c8727-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="c8727-141">对于方法，`in` 和 `out` 参数被描述为[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)对象中的属性。</span><span class="sxs-lookup"><span data-stu-id="c8727-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="c8727-142">可以通过将同一属性添加到 `pInSignature` 和 `pOutSignature` 参数指向的两个对象来定义 `[in/out]` 参数。</span><span class="sxs-lookup"><span data-stu-id="c8727-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="c8727-143">在这种情况下，属性共享相同的**ID**限定符值。</span><span class="sxs-lookup"><span data-stu-id="c8727-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="c8727-144">除 `ReturnValue` 以外的[__Parameters](/windows/desktop/WmiSdk/--parameters)类对象中的每个属性都必须有一个**ID**限定符（一个标识参数出现顺序的从零开始的数值）。</span><span class="sxs-lookup"><span data-stu-id="c8727-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="c8727-145">不能有两个参数具有相同的**id**值，也不能跳过任何**id**值。</span><span class="sxs-lookup"><span data-stu-id="c8727-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="c8727-146">如果发生上述任一情况，`PutMethod` 函数将返回 `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`。</span><span class="sxs-lookup"><span data-stu-id="c8727-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="c8727-147">示例</span><span class="sxs-lookup"><span data-stu-id="c8727-147">Example</span></span>

<span data-ttu-id="c8727-148">有关示例，请参阅[IWbemClassObject：:P utmethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)方法。</span><span class="sxs-lookup"><span data-stu-id="c8727-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c8727-149">要求</span><span class="sxs-lookup"><span data-stu-id="c8727-149">Requirements</span></span>  
 <span data-ttu-id="c8727-150">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c8727-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8727-151">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="c8727-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="c8727-152">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c8727-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8727-153">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8727-153">See also</span></span>

- [<span data-ttu-id="c8727-154">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="c8727-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
