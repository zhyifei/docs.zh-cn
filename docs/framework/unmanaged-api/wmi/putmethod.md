---
title: PutMethod 函数（非托管 API 引用）
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
ms.openlocfilehash: 93347b7290211b5d62829604678261fdf4da1ec3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174909"
---
# <a name="putmethod-function"></a><span data-ttu-id="6465d-103">PutMethod 函数</span><span class="sxs-lookup"><span data-stu-id="6465d-103">PutMethod function</span></span>
<span data-ttu-id="6465d-104">创建方法。</span><span class="sxs-lookup"><span data-stu-id="6465d-104">Creates a method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="6465d-105">语法</span><span class="sxs-lookup"><span data-stu-id="6465d-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="6465d-106">parameters</span><span class="sxs-lookup"><span data-stu-id="6465d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="6465d-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="6465d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="6465d-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="6465d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="6465d-109">[在]要创建的方法的名称。</span><span class="sxs-lookup"><span data-stu-id="6465d-109">[in] The name of the method to create.</span></span>

`lFlags`  
<span data-ttu-id="6465d-110">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="6465d-110">[in] Reserved.</span></span> <span data-ttu-id="6465d-111">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="6465d-111">This parameter must be 0.</span></span>

`pSignatureIn`  
<span data-ttu-id="6465d-112">[在]指向包含方法参数[的__Parameters系统类](/windows/desktop/WmiSdk/--parameters)`in`副本的指针。</span><span class="sxs-lookup"><span data-stu-id="6465d-112">[in] A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `in` parameters for the method.</span></span> <span data-ttu-id="6465d-113">如果设置为`null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="6465d-113">This parameter is ignored if set to `null`.</span></span>  

`pSignatureOut`  
<span data-ttu-id="6465d-114">[在] 指向包含方法参数[的__Parameters系统类](/windows/desktop/WmiSdk/--parameters)`out`副本的指针。</span><span class="sxs-lookup"><span data-stu-id="6465d-114">[in]  A pointer to a copy of the [__Parameters system class](/windows/desktop/WmiSdk/--parameters) that contains the `out` parameters for the method.</span></span> <span data-ttu-id="6465d-115">如果设置为`null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="6465d-115">This parameter is ignored if set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="6465d-116">返回值</span><span class="sxs-lookup"><span data-stu-id="6465d-116">Return value</span></span>

<span data-ttu-id="6465d-117">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="6465d-117">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="6465d-118">一直</span><span class="sxs-lookup"><span data-stu-id="6465d-118">Constant</span></span>  |<span data-ttu-id="6465d-119">值</span><span class="sxs-lookup"><span data-stu-id="6465d-119">Value</span></span>  |<span data-ttu-id="6465d-120">说明</span><span class="sxs-lookup"><span data-stu-id="6465d-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="6465d-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="6465d-121">0x80041008</span></span> | <span data-ttu-id="6465d-122">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="6465d-122">One or more parameters are not valid.</span></span> |
| `WBEM_E_INVALID_DUPLICATE_PARAMETER` | <span data-ttu-id="6465d-123">0 x80041043</span><span class="sxs-lookup"><span data-stu-id="6465d-123">0x80041043</span></span> | <span data-ttu-id="6465d-124">在`[in, out]` *pInSignature*和*pOutSignature*对象中指定的方法参数具有不同的限定符。</span><span class="sxs-lookup"><span data-stu-id="6465d-124">The `[in, out]` method parameter specified in both the *pInSignature* and *pOutSignature* objects have different qualifiers.</span></span>
| `WBEM_E_MISSING_PARAMETER_ID` | <span data-ttu-id="6465d-125">0 x80041036</span><span class="sxs-lookup"><span data-stu-id="6465d-125">0x80041036</span></span> | <span data-ttu-id="6465d-126">缺少**ID**限定符的规范的方法参数。</span><span class="sxs-lookup"><span data-stu-id="6465d-126">A method parameter is missing the specification of the **ID** qualifier.</span></span> |
| `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS` | <span data-ttu-id="6465d-127">0 x80041038</span><span class="sxs-lookup"><span data-stu-id="6465d-127">0x80041038</span></span> | <span data-ttu-id="6465d-128">分配给方法参数的 ID 系列不是连续的，也不是从 0 开始的。</span><span class="sxs-lookup"><span data-stu-id="6465d-128">The ID series that is assigned to the method parameters is not consecutive or does not start at 0.</span></span> |
| `WBEM_E_PARAMETER_ID_ON_RETVAL` | <span data-ttu-id="6465d-129">0 x80041039</span><span class="sxs-lookup"><span data-stu-id="6465d-129">0x80041039</span></span> | <span data-ttu-id="6465d-130">方法的返回值具有**ID**限定符。</span><span class="sxs-lookup"><span data-stu-id="6465d-130">The return value for a method has an **ID** qualifier.</span></span> |
| `WBEM_E_PROPAGATED_METHOD` | <span data-ttu-id="6465d-131">0 x80041034</span><span class="sxs-lookup"><span data-stu-id="6465d-131">0x80041034</span></span> | <span data-ttu-id="6465d-132">尝试从父类重用现有方法名称，并且签名不匹配。</span><span class="sxs-lookup"><span data-stu-id="6465d-132">An attempt was made to reuse an existing method name from a parent class, and the signatures did not match.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="6465d-133">0</span><span class="sxs-lookup"><span data-stu-id="6465d-133">0</span></span> | <span data-ttu-id="6465d-134">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="6465d-134">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="6465d-135">备注</span><span class="sxs-lookup"><span data-stu-id="6465d-135">Remarks</span></span>

<span data-ttu-id="6465d-136">此函数包装对[IWbemClassObject：:PutMethod 方法的](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)调用。</span><span class="sxs-lookup"><span data-stu-id="6465d-136">This function wraps a call to the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

<span data-ttu-id="6465d-137">仅当是 CIM 类定义`ptr`时，才支持此方法调用。</span><span class="sxs-lookup"><span data-stu-id="6465d-137">This method call is only supported if `ptr` is a CIM class definition.</span></span> <span data-ttu-id="6465d-138">方法操作从指向 CIM 实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针中不可用。</span><span class="sxs-lookup"><span data-stu-id="6465d-138">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="6465d-139">用户无法创建名称以下划线开头或结尾的方法。</span><span class="sxs-lookup"><span data-stu-id="6465d-139">Users cannot create methods with names that begin or end with an underscore.</span></span> <span data-ttu-id="6465d-140">这是为系统类和属性保留的。</span><span class="sxs-lookup"><span data-stu-id="6465d-140">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="6465d-141">对于方法，`in`和`out`参数被描述为[IWbemClassObject 对象](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)中的属性。</span><span class="sxs-lookup"><span data-stu-id="6465d-141">For a method, the `in` and `out` parameters are described as properties in [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) objects.</span></span>

<span data-ttu-id="6465d-142">`[in/out]`可以通过将相同的属性添加到 和`pInSignature``pOutSignature`参数指向的两个对象来定义参数。</span><span class="sxs-lookup"><span data-stu-id="6465d-142">An `[in/out]` parameter can be defined by adding the same property to both objects pointed to by the `pInSignature` and `pOutSignature` parameters.</span></span> <span data-ttu-id="6465d-143">在这种情况下，属性共享相同的**ID**限定符值。</span><span class="sxs-lookup"><span data-stu-id="6465d-143">In this case, the properties share the same **ID** qualifier value.</span></span>

<span data-ttu-id="6465d-144">[__Parameters](/windows/desktop/WmiSdk/--parameters)类对象中的每个属性除必须具有`ReturnValue`**ID**限定符外，该限定符是标识参数显示顺序的零基数值。</span><span class="sxs-lookup"><span data-stu-id="6465d-144">Each property in a [__Parameters](/windows/desktop/WmiSdk/--parameters) class object other than `ReturnValue` must have an **ID** qualifier, a zero-based numeric value that identifies the order in which the parameters appear.</span></span> <span data-ttu-id="6465d-145">没有两个参数可以具有相同的**ID**值，并且不能跳过**ID**值。</span><span class="sxs-lookup"><span data-stu-id="6465d-145">No two parameters can have the same **ID** value, and no **ID** value can be skipped.</span></span> <span data-ttu-id="6465d-146">如果发生任一条件，`PutMethod`则函数`WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`将返回 。</span><span class="sxs-lookup"><span data-stu-id="6465d-146">If either condition occurs, the `PutMethod` function returns `WBEM_E_NONCONSECUTIVE_PARAMETER_IDS`.</span></span>

## <a name="example"></a><span data-ttu-id="6465d-147">示例</span><span class="sxs-lookup"><span data-stu-id="6465d-147">Example</span></span>

<span data-ttu-id="6465d-148">例如，请参阅[IWbemClassObject：:PutMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod)。</span><span class="sxs-lookup"><span data-stu-id="6465d-148">For an example, see the [IWbemClassObject::PutMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-putmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="6465d-149">要求</span><span class="sxs-lookup"><span data-stu-id="6465d-149">Requirements</span></span>  
 <span data-ttu-id="6465d-150">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6465d-150">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6465d-151">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="6465d-151">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="6465d-152">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="6465d-152">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6465d-153">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6465d-153">See also</span></span>

- [<span data-ttu-id="6465d-154">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="6465d-154">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
