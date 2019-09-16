---
title: GetMethod 函数（非托管 API 参考）
description: GetMethod 函数检索有关方法的信息。
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b9cc185bf8cccb8ed3c24e28954afd86464602d7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798562"
---
# <a name="getmethod-function"></a><span data-ttu-id="e6abb-103">GetMethod 函数</span><span class="sxs-lookup"><span data-stu-id="e6abb-103">GetMethod function</span></span>

<span data-ttu-id="e6abb-104">检索有关指定方法的信息。</span><span class="sxs-lookup"><span data-stu-id="e6abb-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e6abb-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6abb-105">Syntax</span></span>

```cpp
HRESULT GetMethod (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```

## <a name="parameters"></a><span data-ttu-id="e6abb-106">参数</span><span class="sxs-lookup"><span data-stu-id="e6abb-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e6abb-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="e6abb-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e6abb-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="e6abb-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="e6abb-109">中方法名称。</span><span class="sxs-lookup"><span data-stu-id="e6abb-109">[in] The method name.</span></span> <span data-ttu-id="e6abb-110">此参数不能`null`为，且必须指向有效`LPCWSTR`的。</span><span class="sxs-lookup"><span data-stu-id="e6abb-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="e6abb-111">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="e6abb-111">[in] Reserved.</span></span> <span data-ttu-id="e6abb-112">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="e6abb-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="e6abb-113">弄一个指针，指向用于描述方法的 in 参数的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的地址。</span><span class="sxs-lookup"><span data-stu-id="e6abb-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="e6abb-114">如果将此参数设置为`null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="e6abb-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="e6abb-115">弄一个指针，指向用于描述方法的 out 参数的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的地址。</span><span class="sxs-lookup"><span data-stu-id="e6abb-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="e6abb-116">如果将此参数设置为`null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="e6abb-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e6abb-117">返回值</span><span class="sxs-lookup"><span data-stu-id="e6abb-117">Return value</span></span>

<span data-ttu-id="e6abb-118">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="e6abb-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e6abb-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e6abb-119">Constant</span></span>  |<span data-ttu-id="e6abb-120">值</span><span class="sxs-lookup"><span data-stu-id="e6abb-120">Value</span></span>  |<span data-ttu-id="e6abb-121">描述</span><span class="sxs-lookup"><span data-stu-id="e6abb-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e6abb-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e6abb-122">0x80041002</span></span> | <span data-ttu-id="e6abb-123">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="e6abb-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e6abb-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e6abb-124">0x80041006</span></span> | <span data-ttu-id="e6abb-125">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="e6abb-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e6abb-126">0</span><span class="sxs-lookup"><span data-stu-id="e6abb-126">0</span></span> | <span data-ttu-id="e6abb-127">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e6abb-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e6abb-128">备注</span><span class="sxs-lookup"><span data-stu-id="e6abb-128">Remarks</span></span>

<span data-ttu-id="e6abb-129">此函数包装对[IWbemClassObject：： GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="e6abb-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="e6abb-130">如果该方法在参数中没有，  Windows Management 可以将 [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) 指针设置为`null`。</span><span class="sxs-lookup"><span data-stu-id="e6abb-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="e6abb-131">在`ppInSignature` `IWbemClassObject`和`ppOutSignature`中，分别介绍了 in 和 out 参数，作为 system 类[_Parameters](/windows/desktop/WmiSdk/--parameters)的实例中的属性。</span><span class="sxs-lookup"><span data-stu-id="e6abb-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="e6abb-132">中`ppInSignature`的属性名为`Param` *n*，其中*n*是参数在方法签名中的位置（例如`Param1`、 `Param2`等）。</span><span class="sxs-lookup"><span data-stu-id="e6abb-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="e6abb-133">中`ppOutSignature`的属性也命名为`Param` *n* `ReturnValue`，返回值为。</span><span class="sxs-lookup"><span data-stu-id="e6abb-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="e6abb-134">有关详细信息和示例，请参阅[IWbemClassObject：： GetMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)。</span><span class="sxs-lookup"><span data-stu-id="e6abb-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="e6abb-135">要求</span><span class="sxs-lookup"><span data-stu-id="e6abb-135">Requirements</span></span>

<span data-ttu-id="e6abb-136">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6abb-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e6abb-137">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e6abb-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e6abb-138">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e6abb-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e6abb-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="e6abb-139">See also</span></span>

- [<span data-ttu-id="e6abb-140">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e6abb-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
