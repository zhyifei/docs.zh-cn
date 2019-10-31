---
title: Get 函数（非托管 API 参考）
description: Get 函数检索指定的属性值。
ms.date: 11/06/2017
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
ms.openlocfilehash: 60f29b91000fd3c07efea88dcc319eb283a4af78
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120325"
---
# <a name="get-function"></a><span data-ttu-id="4464f-103">Get 函数</span><span class="sxs-lookup"><span data-stu-id="4464f-103">Get function</span></span>

<span data-ttu-id="4464f-104">检索指定的属性值（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="4464f-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4464f-105">语法</span><span class="sxs-lookup"><span data-stu-id="4464f-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="4464f-106">参数</span><span class="sxs-lookup"><span data-stu-id="4464f-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="4464f-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="4464f-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="4464f-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="4464f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="4464f-109">中属性的名称。</span><span class="sxs-lookup"><span data-stu-id="4464f-109">[in] The name of the property.</span></span>

`lFlags`\
<span data-ttu-id="4464f-110">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="4464f-110">[in] Reserved.</span></span> <span data-ttu-id="4464f-111">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="4464f-111">This parameter must be 0.</span></span>

`pVal`\
<span data-ttu-id="4464f-112">弄如果函数成功返回，则包含 `wszName` 属性的值。</span><span class="sxs-lookup"><span data-stu-id="4464f-112">[out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="4464f-113">为限定符的 `pval` 参数分配了正确的类型和值。</span><span class="sxs-lookup"><span data-stu-id="4464f-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

`pvtType`\
<span data-ttu-id="4464f-114">弄如果该函数成功返回，则包含一个指示该属性类型的[CIM 类型常量](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration)。</span><span class="sxs-lookup"><span data-stu-id="4464f-114">[out] If the function returns successfully, contains a [CIM-type constant](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) that indicates the property type.</span></span> <span data-ttu-id="4464f-115">还可以 `null`其值。</span><span class="sxs-lookup"><span data-stu-id="4464f-115">Its value can also be `null`.</span></span> 

`plFlavor`\
<span data-ttu-id="4464f-116">弄如果函数成功返回，则接收有关属性的源的信息。</span><span class="sxs-lookup"><span data-stu-id="4464f-116">[out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="4464f-117">它的值可以是 `null`或*WbemCli*头文件中定义的以下 WBEM_FLAVOR_TYPE 常数之一：</span><span class="sxs-lookup"><span data-stu-id="4464f-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="4464f-118">返回的常量</span><span class="sxs-lookup"><span data-stu-id="4464f-118">Constant</span></span>  |<span data-ttu-id="4464f-119">“值”</span><span class="sxs-lookup"><span data-stu-id="4464f-119">Value</span></span>  |<span data-ttu-id="4464f-120">描述</span><span class="sxs-lookup"><span data-stu-id="4464f-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="4464f-121">0x40</span><span class="sxs-lookup"><span data-stu-id="4464f-121">0x40</span></span> | <span data-ttu-id="4464f-122">属性为标准系统属性。</span><span class="sxs-lookup"><span data-stu-id="4464f-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="4464f-123">0x20</span><span class="sxs-lookup"><span data-stu-id="4464f-123">0x20</span></span> | <span data-ttu-id="4464f-124">对于类：属性是从父类继承的。</span><span class="sxs-lookup"><span data-stu-id="4464f-124">For a class: The property is inherited from the parent class.</span></span> <br> <span data-ttu-id="4464f-125">对于实例：从父类继承的属性未被实例修改。</span><span class="sxs-lookup"><span data-stu-id="4464f-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="4464f-126">0</span><span class="sxs-lookup"><span data-stu-id="4464f-126">0</span></span> | <span data-ttu-id="4464f-127">对于类：属性属于派生类。</span><span class="sxs-lookup"><span data-stu-id="4464f-127">For a class: The property belongs to the derived class.</span></span> <br> <span data-ttu-id="4464f-128">对于实例：属性由实例进行修改;也就是说，提供了一个值，或者添加或修改了限定符。</span><span class="sxs-lookup"><span data-stu-id="4464f-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="4464f-129">返回值</span><span class="sxs-lookup"><span data-stu-id="4464f-129">Return value</span></span>

<span data-ttu-id="4464f-130">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="4464f-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4464f-131">返回的常量</span><span class="sxs-lookup"><span data-stu-id="4464f-131">Constant</span></span>  |<span data-ttu-id="4464f-132">“值”</span><span class="sxs-lookup"><span data-stu-id="4464f-132">Value</span></span>  |<span data-ttu-id="4464f-133">描述</span><span class="sxs-lookup"><span data-stu-id="4464f-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="4464f-134">0x80041001</span><span class="sxs-lookup"><span data-stu-id="4464f-134">0x80041001</span></span> | <span data-ttu-id="4464f-135">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="4464f-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4464f-136">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4464f-136">0x80041008</span></span> | <span data-ttu-id="4464f-137">一个或多个参数无效。</span><span class="sxs-lookup"><span data-stu-id="4464f-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="4464f-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="4464f-138">0x80041002</span></span> | <span data-ttu-id="4464f-139">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="4464f-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="4464f-140">0x80041006</span><span class="sxs-lookup"><span data-stu-id="4464f-140">0x80041006</span></span> | <span data-ttu-id="4464f-141">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="4464f-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="4464f-142">0</span><span class="sxs-lookup"><span data-stu-id="4464f-142">0</span></span> | <span data-ttu-id="4464f-143">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="4464f-143">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="4464f-144">备注</span><span class="sxs-lookup"><span data-stu-id="4464f-144">Remarks</span></span>

<span data-ttu-id="4464f-145">此函数包装对[IWbemClassObject：： Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="4464f-145">This function wraps a call to the [IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) method.</span></span>

<span data-ttu-id="4464f-146">`Get` 函数还可以返回系统属性。</span><span class="sxs-lookup"><span data-stu-id="4464f-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="4464f-147">为限定符和 COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)函数分配了正确的类型和值的 `pVal` 参数</span><span class="sxs-lookup"><span data-stu-id="4464f-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit) function</span></span>

## <a name="requirements"></a><span data-ttu-id="4464f-148">要求</span><span class="sxs-lookup"><span data-stu-id="4464f-148">Requirements</span></span>

 <span data-ttu-id="4464f-149">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4464f-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="4464f-150">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="4464f-150">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="4464f-151">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4464f-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4464f-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="4464f-152">See also</span></span>

- [<span data-ttu-id="4464f-153">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="4464f-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
