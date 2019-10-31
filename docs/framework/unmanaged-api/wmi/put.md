---
title: Put 函数（非托管 API 参考）
description: Put 函数为命名属性分配一个新值。
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
ms.openlocfilehash: f1bb8aa09a269e3b8fd23f393d63a275d308a77c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127406"
---
# <a name="put-function"></a><span data-ttu-id="e96a7-103">Put 函数</span><span class="sxs-lookup"><span data-stu-id="e96a7-103">Put function</span></span>

<span data-ttu-id="e96a7-104">将命名属性设置为新值。</span><span class="sxs-lookup"><span data-stu-id="e96a7-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e96a7-105">语法</span><span class="sxs-lookup"><span data-stu-id="e96a7-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="e96a7-106">参数</span><span class="sxs-lookup"><span data-stu-id="e96a7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e96a7-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="e96a7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e96a7-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="e96a7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="e96a7-109">中属性的名称。</span><span class="sxs-lookup"><span data-stu-id="e96a7-109">[in] The name of the property.</span></span> <span data-ttu-id="e96a7-110">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e96a7-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="e96a7-111">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="e96a7-111">[in] Reserved.</span></span> <span data-ttu-id="e96a7-112">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="e96a7-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="e96a7-113">中指向有效 `VARIANT` 的指针，它将成为新的属性值。</span><span class="sxs-lookup"><span data-stu-id="e96a7-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="e96a7-114">如果 `pVal` `null` 或指向类型 `VT_NULL`的 `VARIANT`，则将属性设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="e96a7-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="e96a7-115">中`pVal`指向的 `VARIANT` 的类型。</span><span class="sxs-lookup"><span data-stu-id="e96a7-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="e96a7-116">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="e96a7-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="e96a7-117">返回值</span><span class="sxs-lookup"><span data-stu-id="e96a7-117">Return value</span></span>

<span data-ttu-id="e96a7-118">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="e96a7-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e96a7-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e96a7-119">Constant</span></span>  |<span data-ttu-id="e96a7-120">“值”</span><span class="sxs-lookup"><span data-stu-id="e96a7-120">Value</span></span>  |<span data-ttu-id="e96a7-121">描述</span><span class="sxs-lookup"><span data-stu-id="e96a7-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e96a7-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e96a7-122">0x80041001</span></span> | <span data-ttu-id="e96a7-123">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="e96a7-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e96a7-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e96a7-124">0x80041008</span></span> | <span data-ttu-id="e96a7-125">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="e96a7-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="e96a7-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="e96a7-126">0x8004102a</span></span> | <span data-ttu-id="e96a7-127">无法识别属性类型。</span><span class="sxs-lookup"><span data-stu-id="e96a7-127">The property type is not recognized.</span></span> <span data-ttu-id="e96a7-128">如果类已经存在，则会在创建类实例时返回此值。</span><span class="sxs-lookup"><span data-stu-id="e96a7-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e96a7-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e96a7-129">0x80041006</span></span> | <span data-ttu-id="e96a7-130">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e96a7-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="e96a7-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="e96a7-131">0x80041005</span></span> | <span data-ttu-id="e96a7-132">对于实例：指示 `pVal` 指向属性的错误类型的 `VARIANT`。</span><span class="sxs-lookup"><span data-stu-id="e96a7-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="e96a7-133">对于类定义：父类中已存在该属性，而新的 COM 类型不同于旧的 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="e96a7-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e96a7-134">0</span><span class="sxs-lookup"><span data-stu-id="e96a7-134">0</span></span> | <span data-ttu-id="e96a7-135">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e96a7-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e96a7-136">备注</span><span class="sxs-lookup"><span data-stu-id="e96a7-136">Remarks</span></span>

<span data-ttu-id="e96a7-137">此函数包装对[IWbemClassObject：:P](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)的工作方式方法的调用。</span><span class="sxs-lookup"><span data-stu-id="e96a7-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="e96a7-138">此函数始终使用新的属性值覆盖当前属性值。</span><span class="sxs-lookup"><span data-stu-id="e96a7-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="e96a7-139">如果[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向某个类定义，`Put` 将创建或更新该属性值。</span><span class="sxs-lookup"><span data-stu-id="e96a7-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="e96a7-140">当[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向 CIM 实例时，`Put` 仅更新属性值;`Put` 无法创建属性值。</span><span class="sxs-lookup"><span data-stu-id="e96a7-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="e96a7-141">只有在创建类的过程中不能留空时，`__CLASS` 系统属性才能写入。</span><span class="sxs-lookup"><span data-stu-id="e96a7-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="e96a7-142">所有其他系统属性都是只读的。</span><span class="sxs-lookup"><span data-stu-id="e96a7-142">All other system properties are read-only.</span></span>

<span data-ttu-id="e96a7-143">用户不能创建名称以下划线开头或结尾的属性（"_"）。</span><span class="sxs-lookup"><span data-stu-id="e96a7-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="e96a7-144">此为系统类和属性保留。</span><span class="sxs-lookup"><span data-stu-id="e96a7-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="e96a7-145">如果父类中存在由 `Put` 函数设置的属性，则除非属性类型与父类类型不匹配，否则将更改属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="e96a7-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="e96a7-146">如果该属性不存在并且不是类型不匹配，则会创建该属性。</span><span class="sxs-lookup"><span data-stu-id="e96a7-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="e96a7-147">仅当在 CIM 类定义中创建新属性并且 `pVal` `null` 或指向类型 `VT_NULL`的 `VARIANT` 时，才使用 `vtType` 参数。</span><span class="sxs-lookup"><span data-stu-id="e96a7-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="e96a7-148">在这种情况下，`vType` 参数指定属性的 CIM 类型。</span><span class="sxs-lookup"><span data-stu-id="e96a7-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="e96a7-149">在其他所有情况下，`vtType` 必须为0。</span><span class="sxs-lookup"><span data-stu-id="e96a7-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="e96a7-150">如果基础对象是实例，则 `vtType` 也必须为0（即使 `Val` 是 `null`），因为该属性的类型是固定的且无法更改。</span><span class="sxs-lookup"><span data-stu-id="e96a7-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="e96a7-151">示例</span><span class="sxs-lookup"><span data-stu-id="e96a7-151">Example</span></span>

<span data-ttu-id="e96a7-152">有关示例，请参阅[IWbemClassObject：:P](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)工作不上方法。</span><span class="sxs-lookup"><span data-stu-id="e96a7-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="e96a7-153">要求</span><span class="sxs-lookup"><span data-stu-id="e96a7-153">Requirements</span></span>

<span data-ttu-id="e96a7-154">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e96a7-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e96a7-155">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="e96a7-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e96a7-156">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e96a7-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e96a7-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="e96a7-157">See also</span></span>

- [<span data-ttu-id="e96a7-158">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e96a7-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
