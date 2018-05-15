---
title: Put 的函数 （非托管 API 参考）
description: Put 函数将新值分配给指定的属性。
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
ms.openlocfilehash: 9f3ffe27bef6583b733fc04f2f25903d545daa74
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="put-function"></a><span data-ttu-id="a2dd4-103">Put 的函数</span><span class="sxs-lookup"><span data-stu-id="a2dd4-103">Put function</span></span>
<span data-ttu-id="a2dd4-104">将指定的属性设置为新值。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-104">Sets a named property to a new value.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="a2dd4-105">语法</span><span class="sxs-lookup"><span data-stu-id="a2dd4-105">Syntax</span></span>  
  
```  
HRESULT Put (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
); 
```  

## <a name="parameters"></a><span data-ttu-id="a2dd4-106">参数</span><span class="sxs-lookup"><span data-stu-id="a2dd4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="a2dd4-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="a2dd4-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="a2dd4-109">[in]属性的名称。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-109">[in] The name of the property.</span></span> <span data-ttu-id="a2dd4-110">此参数不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-110">This parameter cannot be `null`.</span></span>

`lFlags`  
<span data-ttu-id="a2dd4-111">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-111">[in] Reserved.</span></span> <span data-ttu-id="a2dd4-112">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-112">This parameter must be 0.</span></span>

`pVal`   
<span data-ttu-id="a2dd4-113">[in]指向一个有效的指针`VARIANT`该按钮将变为新的属性值。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-113">[in] A pointer to a valid `VARIANT` that becomes the new property value.</span></span> <span data-ttu-id="a2dd4-114">如果`pVal`是`null`或指向`VARIANT`类型的`VT_NULL`，该属性设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-114">If `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`, the property is set to `null`.</span></span> 

`vtType`  
<span data-ttu-id="a2dd4-115">[in]一种`VARIANT`指向`pVal`。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-115">[in] The type of `VARIANT` pointed to by `pVal`.</span></span> <span data-ttu-id="a2dd4-116">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-116">See the [Remarks](#remarks) section for more information.</span></span>
 

## <a name="return-value"></a><span data-ttu-id="a2dd4-117">返回值</span><span class="sxs-lookup"><span data-stu-id="a2dd4-117">Return value</span></span>

<span data-ttu-id="a2dd4-118">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="a2dd4-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="a2dd4-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="a2dd4-119">Constant</span></span>  |<span data-ttu-id="a2dd4-120">值</span><span class="sxs-lookup"><span data-stu-id="a2dd4-120">Value</span></span>  |<span data-ttu-id="a2dd4-121">描述</span><span class="sxs-lookup"><span data-stu-id="a2dd4-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="a2dd4-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="a2dd4-122">0x80041001</span></span> | <span data-ttu-id="a2dd4-123">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-123">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="a2dd4-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="a2dd4-124">0x80041008</span></span> | <span data-ttu-id="a2dd4-125">一个或多个参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-125">One or more parameters are not valid.</span></span> |
|`WBEM_E_INVALID_PROPERTY_TYPE` | <span data-ttu-id="a2dd4-126">0x8004102a</span><span class="sxs-lookup"><span data-stu-id="a2dd4-126">0x8004102a</span></span> | <span data-ttu-id="a2dd4-127">无法识别属性类型。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-127">The property type is not recognized.</span></span> <span data-ttu-id="a2dd4-128">创建类实例，如果该类已存在时，则返回此值。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-128">This value is returned when creating class instances if the class already exists.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="a2dd4-129">0x80041006</span><span class="sxs-lookup"><span data-stu-id="a2dd4-129">0x80041006</span></span> | <span data-ttu-id="a2dd4-130">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-130">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="a2dd4-131">0x80041005</span><span class="sxs-lookup"><span data-stu-id="a2dd4-131">0x80041005</span></span> | <span data-ttu-id="a2dd4-132">实例： 指示`pVal`指向`VARIANT`属性类型不正确。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-132">For instances: Indicates that `pVal` points to a `VARIANT` of an incorrect type for the property.</span></span> <br/> <span data-ttu-id="a2dd4-133">类定义： 的父类、 中已存在的属性和新的 COM 类型是否不同于旧的 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-133">For class definitions: The property already exists in the parent class, and the new COM type is different from the old COM type.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="a2dd4-134">0</span><span class="sxs-lookup"><span data-stu-id="a2dd4-134">0</span></span> | <span data-ttu-id="a2dd4-135">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-135">The function call was successful.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="a2dd4-136">备注</span><span class="sxs-lookup"><span data-stu-id="a2dd4-136">Remarks</span></span>

<span data-ttu-id="a2dd4-137">此函数包装对的调用[IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-137">This function wraps a call to the [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="a2dd4-138">此函数始终会用一个新覆盖当前的属性值。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-138">This function always overwrites the current property value with a new one.</span></span> <span data-ttu-id="a2dd4-139">如果[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向类定义，`Put`创建或更新的属性值。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-139">If the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) points to a class definition, `Put` creates or updates the property value.</span></span> <span data-ttu-id="a2dd4-140">当[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)指向 CIM 的实例，`Put`更新属性值仅;`Put`无法创建属性值。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-140">When [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) points to a CIM instance, `Put` updates the property value only; `Put` cannot create a property value.</span></span>

<span data-ttu-id="a2dd4-141">`__CLASS`系统属性时才是可写类在创建期间，它可能不能留空。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-141">The `__CLASS` system property is only writable during class creation, when it may not be left blank.</span></span> <span data-ttu-id="a2dd4-142">所有其他系统属性是只读的。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-142">All other system properties are read-only.</span></span>

<span data-ttu-id="a2dd4-143">用户无法创建属性的开头或结尾下划线 (_) 开头的名称。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-143">A user cannot create properties with names that begin or end with an underscore ("_").</span></span> <span data-ttu-id="a2dd4-144">这被保留供系统类和属性。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-144">This is reserved for system classes and properties.</span></span>

<span data-ttu-id="a2dd4-145">如果该属性设置的`Put`父类中存在的函数，除非该属性类型与父类类型不匹配，则更改属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-145">If the property set by the `Put` function exists in the parent class, the default value of the property is changed unless the property type does not match the parent class type.</span></span> <span data-ttu-id="a2dd4-146">如果属性不存在，并且它不是类型不匹配，则该属性为 ceated。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-146">If the property does not exist and it is not a type mismatch, the property is ceated.</span></span>

<span data-ttu-id="a2dd4-147">使用`vtType`参数仅在 CIM 类定义中创建新属性时和`pVal`是`null`或指向`VARIANT`类型的`VT_NULL`。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-147">Use the `vtType` parameter only when creating new properties in a CIM class definition and `pVal` is `null` or points to a `VARIANT` of type `VT_NULL`.</span></span> <span data-ttu-id="a2dd4-148">在这种情况下，`vType`参数指定的属性的 CIM 类型。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-148">In this case, the `vType` parameter specifies the CIM type of the property.</span></span> <span data-ttu-id="a2dd4-149">在每个其他情况下，`vtType`必须为 0。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-149">In every other case, `vtType` must be 0.</span></span> <span data-ttu-id="a2dd4-150">`vtType` 如果基础对象为实例也必须为 0 (即使`Val`是`null`) 因为属性的类型固定的不能更改。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-150">`vtType` must also be 0 if the underlying object is an instance (even if `Val` is `null`) because the type of the property is fixed and cannot be changed.</span></span>   

## <a name="example"></a><span data-ttu-id="a2dd4-151">示例</span><span class="sxs-lookup"><span data-stu-id="a2dd4-151">Example</span></span>

<span data-ttu-id="a2dd4-152">有关示例，请参阅[IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-152">For an example, see the [IWbemClassObject::Put](https://msdn.microsoft.com/library/aa391455(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="a2dd4-153">要求</span><span class="sxs-lookup"><span data-stu-id="a2dd4-153">Requirements</span></span>  
 <span data-ttu-id="a2dd4-154">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a2dd4-154">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2dd4-155">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="a2dd4-155">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="a2dd4-156">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="a2dd4-156">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2dd4-157">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2dd4-157">See also</span></span>  
[<span data-ttu-id="a2dd4-158">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="a2dd4-158">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
