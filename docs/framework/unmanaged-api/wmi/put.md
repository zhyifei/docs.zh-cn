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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5aa629c2d07fb25db035cd80aba3c74413070e6e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798396"
---
# <a name="put-function"></a><span data-ttu-id="10fee-103">Put 函数</span><span class="sxs-lookup"><span data-stu-id="10fee-103">Put function</span></span>

<span data-ttu-id="10fee-104">将命名属性设置为新值。</span><span class="sxs-lookup"><span data-stu-id="10fee-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="10fee-105">语法</span><span class="sxs-lookup"><span data-stu-id="10fee-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="10fee-106">参数</span><span class="sxs-lookup"><span data-stu-id="10fee-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="10fee-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="10fee-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="10fee-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="10fee-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="10fee-109">中属性的名称。</span><span class="sxs-lookup"><span data-stu-id="10fee-109">[in] The name of the property.</span></span> <span data-ttu-id="10fee-110">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="10fee-110">This parameter cannot be `null`.</span></span>

`lFlags`\
<span data-ttu-id="10fee-111">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="10fee-111">[in] Reserved.</span></span> <span data-ttu-id="10fee-112">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="10fee-112">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="10fee-113">中指向作为新属性值`VARIANT`的有效的指针。</span><span class="sxs-lookup"><span data-stu-id="10fee-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="10fee-114">如果`pVal`为`null`或指向`null`类型`VARIANT` 的，则将`VT_NULL`属性设置为。</span><span class="sxs-lookup"><span data-stu-id="10fee-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span>

`vtType`\
<span data-ttu-id="10fee-115">中`VARIANT` 指向`pVal`的的类型。</span><span class="sxs-lookup"><span data-stu-id="10fee-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="10fee-116">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="10fee-116">See the [Remarks](#remarks) section for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="10fee-117">返回值</span><span class="sxs-lookup"><span data-stu-id="10fee-117">Return value</span></span>

<span data-ttu-id="10fee-118">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="10fee-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="10fee-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="10fee-119">Constant</span></span>  |<span data-ttu-id="10fee-120">值</span><span class="sxs-lookup"><span data-stu-id="10fee-120">Value</span></span>  |<span data-ttu-id="10fee-121">描述</span><span class="sxs-lookup"><span data-stu-id="10fee-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="10fee-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="10fee-122">0x80041001</span></span> | <span data-ttu-id="10fee-123">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="10fee-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="10fee-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="10fee-124">0x80041008</span></span> | <span data-ttu-id="10fee-125">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="10fee-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="10fee-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="10fee-126">0x8004102a</span></span> | <span data-ttu-id="10fee-127">无法识别属性类型。</span><span class="sxs-lookup"><span data-stu-id="10fee-127">The property type is not recognized.</span></span> <span data-ttu-id="10fee-128">如果类已经存在，则会在创建类实例时返回此值。</span><span class="sxs-lookup"><span data-stu-id="10fee-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="10fee-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="10fee-129">0x80041006</span></span> | <span data-ttu-id="10fee-130">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="10fee-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="10fee-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="10fee-131">0x80041005</span></span> | <span data-ttu-id="10fee-132">对于实例：指示指向属性的不正确类型的。 `VARIANT` `pVal`</span><span class="sxs-lookup"><span data-stu-id="10fee-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="10fee-133">对于类定义：父类中已存在该属性，而新的 COM 类型不同于旧的 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="10fee-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="10fee-134">0</span><span class="sxs-lookup"><span data-stu-id="10fee-134">0</span></span> | <span data-ttu-id="10fee-135">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="10fee-135">The function call was successful.</span></span> |

## <a name="remarks"></a><span data-ttu-id="10fee-136">备注</span><span class="sxs-lookup"><span data-stu-id="10fee-136">Remarks</span></span>

<span data-ttu-id="10fee-137">此函数包装对[IWbemClassObject：:P](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)的工作方式方法的调用。</span><span class="sxs-lookup"><span data-stu-id="10fee-137">This function wraps a call to the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

<span data-ttu-id="10fee-138">此函数始终使用新的属性值覆盖当前属性值。</span><span class="sxs-lookup"><span data-stu-id="10fee-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="10fee-139">如果[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向某个类定义， `Put`则会创建或更新该属性值。</span><span class="sxs-lookup"><span data-stu-id="10fee-139">If the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="10fee-140">当[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向 CIM 实例时， `Put`仅更新属性值;`Put`无法创建属性值。</span><span class="sxs-lookup"><span data-stu-id="10fee-140">When [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="10fee-141">`__CLASS`系统属性只有在创建类的过程中不能为空时才可以写入。</span><span class="sxs-lookup"><span data-stu-id="10fee-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="10fee-142">所有其他系统属性都是只读的。</span><span class="sxs-lookup"><span data-stu-id="10fee-142">All other system properties are read-only.</span></span>

<span data-ttu-id="10fee-143">用户不能创建名称以下划线开头或结尾的属性（"_"）。</span><span class="sxs-lookup"><span data-stu-id="10fee-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="10fee-144">此为系统类和属性保留。</span><span class="sxs-lookup"><span data-stu-id="10fee-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="10fee-145">如果父类中存在由`Put`函数设置的属性，则除非属性类型与父类类型不匹配，否则将更改属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="10fee-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="10fee-146">如果该属性不存在并且不是类型不匹配，则会创建该属性。</span><span class="sxs-lookup"><span data-stu-id="10fee-146">If the property does not exist and it is not a type mismatch, the property is created.</span></span>

<span data-ttu-id="10fee-147">`VARIANT` `pVal` `null`仅当在 CIM 类定义中创建新属性并且或指向类型`VT_NULL`的时，才使用参数。`vtType`</span><span class="sxs-lookup"><span data-stu-id="10fee-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="10fee-148">在这种情况下`vType` ，参数指定属性的 CIM 类型。</span><span class="sxs-lookup"><span data-stu-id="10fee-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="10fee-149">在其他所有情况下`vtType` ，必须为0。</span><span class="sxs-lookup"><span data-stu-id="10fee-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="10fee-150">`vtType`如果基础对象是实例，则必须为0（即使`Val`为`null`），因为属性的类型是固定的且无法更改。</span><span class="sxs-lookup"><span data-stu-id="10fee-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>

## <a name="example"></a><span data-ttu-id="10fee-151">示例</span><span class="sxs-lookup"><span data-stu-id="10fee-151">Example</span></span>

<span data-ttu-id="10fee-152">有关示例，请参阅[IWbemClassObject：:P](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put)工作不上方法。</span><span class="sxs-lookup"><span data-stu-id="10fee-152">For an example, see the [IWbemClassObject::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="10fee-153">要求</span><span class="sxs-lookup"><span data-stu-id="10fee-153">Requirements</span></span>

<span data-ttu-id="10fee-154">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="10fee-154">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="10fee-155">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="10fee-155">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="10fee-156">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="10fee-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="10fee-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="10fee-157">See also</span></span>

- [<span data-ttu-id="10fee-158">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="10fee-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
