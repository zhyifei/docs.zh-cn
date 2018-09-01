---
title: 下一步函数 （非托管 API 参考）
description: 下一步函数 retireves 枚举中的下一个属性。
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d470ccf9384695aa38a50c2c062c1b660fea96
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43388609"
---
# <a name="next-function"></a><span data-ttu-id="f5ab7-103">下一个函数</span><span class="sxs-lookup"><span data-stu-id="f5ab7-103">Next function</span></span>
<span data-ttu-id="f5ab7-104">检索到的调用开始枚举中的下一步属性[BeginEnumeration](beginenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-104">Retrieves the next property in an enumeration that begins with a call to [BeginEnumeration](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="f5ab7-105">语法</span><span class="sxs-lookup"><span data-stu-id="f5ab7-105">Syntax</span></span>  
  
```  
HRESULT Next (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor     
); 
```  

## <a name="parameters"></a><span data-ttu-id="f5ab7-106">参数</span><span class="sxs-lookup"><span data-stu-id="f5ab7-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f5ab7-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f5ab7-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f5ab7-109">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-109">[in] Reserved.</span></span> <span data-ttu-id="f5ab7-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-110">This parameter must be 0.</span></span>

`pstrName`  
<span data-ttu-id="f5ab7-111">[out]一个新`BSTR`，其中包含属性名称。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-111">[out] A new `BSTR` that contains the property name.</span></span> <span data-ttu-id="f5ab7-112">可以将此参数设置为`null`如果名称不需要。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-112">You can set this parameter to `null` if the name is not required.</span></span>

`pVal`  
<span data-ttu-id="f5ab7-113">[out]一个`VARIANT`填充的属性的值。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-113">[out] A `VARIANT` filled with the value of the property.</span></span> <span data-ttu-id="f5ab7-114">可以将此参数设置为`null`如果不需要值。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-114">You can set this parameter to `null` if the value is not required.</span></span> <span data-ttu-id="f5ab7-115">如果该函数将返回错误代码，`VARIANT`传递给`pVal`左侧不被修改。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-115">If the function returns an error code, the `VARIANT` passed to `pVal` is left unmodified.</span></span> 

`pvtType`  
<span data-ttu-id="f5ab7-116">[out]一个指向`CIMTYPE`变量 (`LONG`属性的类型放置)。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-116">[out] A pointer to a `CIMTYPE` variable (a `LONG` into which the type of the property is placed).</span></span> <span data-ttu-id="f5ab7-117">此属性的值可以是`VT_NULL_VARIANT`，在这种情况下有必要以确定该属性的实际类型。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-117">The value of this property can be a `VT_NULL_VARIANT`, in which case it is necessary to determine the actual type of the property.</span></span> <span data-ttu-id="f5ab7-118">此参数也可以是`null`。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-118">This parameter can also be `null`.</span></span> 

`plFlavor`  
<span data-ttu-id="f5ab7-119">[out]`null`，或接收信息来源的属性的值。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-119">[out] `null`, or a value that receives information on the origin of the property.</span></span> <span data-ttu-id="f5ab7-120">请参阅 [备注] 有关可能的值。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-120">See the [Remarks] section for possible values.</span></span> 

## <a name="return-value"></a><span data-ttu-id="f5ab7-121">返回值</span><span class="sxs-lookup"><span data-stu-id="f5ab7-121">Return value</span></span>

<span data-ttu-id="f5ab7-122">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="f5ab7-122">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f5ab7-123">返回的常量</span><span class="sxs-lookup"><span data-stu-id="f5ab7-123">Constant</span></span>  |<span data-ttu-id="f5ab7-124">“值”</span><span class="sxs-lookup"><span data-stu-id="f5ab7-124">Value</span></span>  |<span data-ttu-id="f5ab7-125">描述</span><span class="sxs-lookup"><span data-stu-id="f5ab7-125">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="f5ab7-126">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f5ab7-126">0x80041001</span></span> | <span data-ttu-id="f5ab7-127">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-127">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f5ab7-128">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f5ab7-128">0x80041008</span></span> | <span data-ttu-id="f5ab7-129">参数无效。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-129">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="f5ab7-130">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f5ab7-130">0x8004101d</span></span> | <span data-ttu-id="f5ab7-131">出现不需要调用[ `BeginEnumeration` ](beginenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-131">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f5ab7-132">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f5ab7-132">0x80041006</span></span> | <span data-ttu-id="f5ab7-133">没有足够的内存，可开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-133">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="f5ab7-134">0x80041015</span><span class="sxs-lookup"><span data-stu-id="f5ab7-134">0x80041015</span></span> | <span data-ttu-id="f5ab7-135">远程过程调用介于这两个的当前进程和失败的 Windows 管理。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-135">The remote procedure call betweeen the current process and Windows Management failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f5ab7-136">0</span><span class="sxs-lookup"><span data-stu-id="f5ab7-136">0</span></span> | <span data-ttu-id="f5ab7-137">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-137">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="f5ab7-138">0x40005</span><span class="sxs-lookup"><span data-stu-id="f5ab7-138">0x40005</span></span> | <span data-ttu-id="f5ab7-139">枚举中没有更多属性。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-139">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f5ab7-140">备注</span><span class="sxs-lookup"><span data-stu-id="f5ab7-140">Remarks</span></span>

<span data-ttu-id="f5ab7-141">此函数包装对的调用[IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next)方法。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-141">This function wraps a call to the [IWbemClassObject::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) method.</span></span>

<span data-ttu-id="f5ab7-142">此方法也会返回系统属性。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-142">This method also returns system properties.</span></span>

<span data-ttu-id="f5ab7-143">如果该属性的基础类型的对象路径、 日期或时间或另一种特殊类型，则返回的类型不包含足够的信息。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-143">If the underlying type of the property is an object path, a date or time, or another special type, then the returned type does not contain enough information.</span></span> <span data-ttu-id="f5ab7-144">调用方必须检查`CIMTYPE`来确定属性是否是对象引用、 日期或时间或另一种特殊类型的指定属性。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-144">The caller must examine the `CIMTYPE` for the specified property to determine if the property is an object reference, a date or time, or another special type.</span></span>

<span data-ttu-id="f5ab7-145">如果`plFlavor`不是`null`，则`LONG`值接收围绕原点的属性的信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f5ab7-145">If `plFlavor` is not `null`, the `LONG` value receives information about the origin of the property, as follows:</span></span>

|<span data-ttu-id="f5ab7-146">返回的常量</span><span class="sxs-lookup"><span data-stu-id="f5ab7-146">Constant</span></span>  |<span data-ttu-id="f5ab7-147">“值”</span><span class="sxs-lookup"><span data-stu-id="f5ab7-147">Value</span></span>  |<span data-ttu-id="f5ab7-148">描述</span><span class="sxs-lookup"><span data-stu-id="f5ab7-148">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="f5ab7-149">0x40</span><span class="sxs-lookup"><span data-stu-id="f5ab7-149">0x40</span></span> | <span data-ttu-id="f5ab7-150">该属性是标准系统属性。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-150">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="f5ab7-151">0x20</span><span class="sxs-lookup"><span data-stu-id="f5ab7-151">0x20</span></span> | <span data-ttu-id="f5ab7-152">类： 该属性从父类继承。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-152">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="f5ab7-153">实例： 属性，继承自的父类，而未修改的实例。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-153">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="f5ab7-154">0</span><span class="sxs-lookup"><span data-stu-id="f5ab7-154">0</span></span> | <span data-ttu-id="f5ab7-155">类： 属性属于派生类。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-155">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="f5ab7-156">实例： 实例; 修改属性也就是说，却提供了值，或限定符已添加或修改。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-156">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="requirements"></a><span data-ttu-id="f5ab7-157">要求</span><span class="sxs-lookup"><span data-stu-id="f5ab7-157">Requirements</span></span>  
 <span data-ttu-id="f5ab7-158">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f5ab7-158">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f5ab7-159">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f5ab7-159">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f5ab7-160">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f5ab7-160">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5ab7-161">请参阅</span><span class="sxs-lookup"><span data-stu-id="f5ab7-161">See also</span></span>  
[<span data-ttu-id="f5ab7-162">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="f5ab7-162">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
