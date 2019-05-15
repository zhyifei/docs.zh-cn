---
title: Put 的函数 （非托管 API 参考）
description: Put 函数将新值分配给命名的属性。
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fba929e5a1a1e4c2b69e15bf6c855211e25a67a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636625"
---
# <a name="put-function"></a><span data-ttu-id="507f5-103">Put 的函数</span><span class="sxs-lookup"><span data-stu-id="507f5-103">Put function</span></span>

<span data-ttu-id="507f5-104">将命名属性设置为新值。</span><span class="sxs-lookup"><span data-stu-id="507f5-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="507f5-105">语法</span><span class="sxs-lookup"><span data-stu-id="507f5-105">Syntax</span></span>

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a><span data-ttu-id="507f5-106">参数</span><span class="sxs-lookup"><span data-stu-id="507f5-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="507f5-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="507f5-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="507f5-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="507f5-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="507f5-109">[in]属性的名称。</span><span class="sxs-lookup"><span data-stu-id="507f5-109">[in] The name of the property.</span></span> <span data-ttu-id="507f5-110">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="507f5-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="507f5-111">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="507f5-111">[in] Reserved.</span></span> <span data-ttu-id="507f5-112">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="507f5-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="507f5-113">[in]指向一个有效的指针`VARIANT`该按钮将变为新的属性值。</span><span class="sxs-lookup"><span data-stu-id="507f5-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="507f5-114">如果`pVal`是`null`或指向`VARIANT`类型的`VT_NULL`，该属性设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="507f5-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="507f5-115">[in]类型`VARIANT`指向的`pVal`。</span><span class="sxs-lookup"><span data-stu-id="507f5-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="507f5-116">请参阅[备注](#remarks)部分，了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="507f5-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="507f5-117">返回值</span><span class="sxs-lookup"><span data-stu-id="507f5-117">Return value</span></span>

<span data-ttu-id="507f5-118">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="507f5-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="507f5-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="507f5-119">Constant</span></span>  |<span data-ttu-id="507f5-120">值</span><span class="sxs-lookup"><span data-stu-id="507f5-120">Value</span></span>  |<span data-ttu-id="507f5-121">描述</span><span class="sxs-lookup"><span data-stu-id="507f5-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="507f5-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="507f5-122">0x80041001</span></span> | <span data-ttu-id="507f5-123">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="507f5-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="507f5-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="507f5-124">0x80041008</span></span> | <span data-ttu-id="507f5-125">一个或多个参数是无效的。</span><span class="sxs-lookup"><span data-stu-id="507f5-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="507f5-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="507f5-126">0x8004102a</span></span> | <span data-ttu-id="507f5-127">未识别属性类型。</span><span class="sxs-lookup"><span data-stu-id="507f5-127">The property type is not recognized.</span></span> <span data-ttu-id="507f5-128">创建类实例，如果该类已存在时返回此值。</span><span class="sxs-lookup"><span data-stu-id="507f5-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="507f5-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="507f5-129">0x80041006</span></span> | <span data-ttu-id="507f5-130">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="507f5-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="507f5-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="507f5-131">0x80041005</span></span> | <span data-ttu-id="507f5-132">实例：指示`pVal`指向`VARIANT`属性类型不正确。</span><span class="sxs-lookup"><span data-stu-id="507f5-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="507f5-133">查找类定义：属性已存在的父类、 中和新的 COM 类型都不同于旧的 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="507f5-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="507f5-134">0</span><span class="sxs-lookup"><span data-stu-id="507f5-134">0</span></span> | <span data-ttu-id="507f5-135">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="507f5-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="507f5-136">备注</span><span class="sxs-lookup"><span data-stu-id="507f5-136">Remarks</span></span>

<span data-ttu-id="507f5-137">此函数包装对的调用[IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)方法。</span><span class="sxs-lookup"><span data-stu-id="507f5-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="507f5-138">此函数始终覆盖使用新的当前属性值。</span><span class="sxs-lookup"><span data-stu-id="507f5-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="507f5-139">如果[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向的类定义，`Put`创建或更新的属性值。</span><span class="sxs-lookup"><span data-stu-id="507f5-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="507f5-140">当[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向 CIM 的实例，`Put`更新属性值; 仅`Put`不能创建一个属性值。</span><span class="sxs-lookup"><span data-stu-id="507f5-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="507f5-141">`__CLASS`系统属性才是可写类创建过程时它可能不为空。</span><span class="sxs-lookup"><span data-stu-id="507f5-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="507f5-142">所有其他系统属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="507f5-142">All other system properties are read-only.</span></span>

<span data-ttu-id="507f5-143">用户不能具有名称的开头或结尾下划线 ("_") 创建属性。</span><span class="sxs-lookup"><span data-stu-id="507f5-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="507f5-144">这被保留给系统类和属性。</span><span class="sxs-lookup"><span data-stu-id="507f5-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="507f5-145">如果该属性设置的`Put`父类中存在的函数，除非属性类型与父类类型不匹配，将更改属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="507f5-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="507f5-146">如果该属性不存在，它不是类型不匹配，则创建属性。</span><span class="sxs-lookup"><span data-stu-id="507f5-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="507f5-147">使用`vtType`参数仅在 CIM 类定义中创建新的属性时，`pVal`是`null`或指向`VARIANT`类型的`VT_NULL`。</span><span class="sxs-lookup"><span data-stu-id="507f5-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="507f5-148">在这种情况下，`vType`参数指定的属性的 CIM 类型。</span><span class="sxs-lookup"><span data-stu-id="507f5-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="507f5-149">在所有其他情况下，`vtType`必须为 0。</span><span class="sxs-lookup"><span data-stu-id="507f5-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="507f5-150">`vtType` 如果基础对象实例也必须为 0 (即使`Val`是`null`) 由于属性类型固定的不能更改。</span><span class="sxs-lookup"><span data-stu-id="507f5-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="507f5-151">示例</span><span class="sxs-lookup"><span data-stu-id="507f5-151">Example</span></span>

<span data-ttu-id="507f5-152">有关示例，请参阅[IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)方法。</span><span class="sxs-lookup"><span data-stu-id="507f5-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="507f5-153">要求</span><span class="sxs-lookup"><span data-stu-id="507f5-153">Requirements</span></span>

<span data-ttu-id="507f5-154">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="507f5-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="507f5-155">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="507f5-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="507f5-156">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="507f5-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="507f5-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="507f5-157">See also</span></span>

- [<span data-ttu-id="507f5-158">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="507f5-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
