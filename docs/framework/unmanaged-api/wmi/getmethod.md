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
ms.openlocfilehash: 48986f5ff1cbbb45840ec1a059aa86711848d717
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102593"
---
# <a name="getmethod-function"></a><span data-ttu-id="aba38-103">GetMethod 函数</span><span class="sxs-lookup"><span data-stu-id="aba38-103">GetMethod function</span></span>

<span data-ttu-id="aba38-104">检索有关指定方法的信息。</span><span class="sxs-lookup"><span data-stu-id="aba38-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="aba38-105">语法</span><span class="sxs-lookup"><span data-stu-id="aba38-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="aba38-106">参数</span><span class="sxs-lookup"><span data-stu-id="aba38-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="aba38-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="aba38-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="aba38-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="aba38-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="aba38-109">中方法名称。</span><span class="sxs-lookup"><span data-stu-id="aba38-109">[in] The method name.</span></span> <span data-ttu-id="aba38-110">此参数不能 `null` 并且必须指向有效的 `LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="aba38-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`\
<span data-ttu-id="aba38-111">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="aba38-111">[in] Reserved.</span></span> <span data-ttu-id="aba38-112">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="aba38-112">This parameter must be 0.</span></span>

`ppInSignature`\
<span data-ttu-id="aba38-113">弄一个指针，指向用于描述方法的 in 参数的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的地址。</span><span class="sxs-lookup"><span data-stu-id="aba38-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in parameters to the method.</span></span> <span data-ttu-id="aba38-114">如果将此参数设置为 `null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="aba38-114">This parameter is ignored if it is set to `null`.</span></span>

`ppOutSignature`\
<span data-ttu-id="aba38-115">弄一个指针，指向用于描述方法的 out 参数的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的地址。</span><span class="sxs-lookup"><span data-stu-id="aba38-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="aba38-116">如果将此参数设置为 `null`，则忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="aba38-116">This parameter is ignored if it is set to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="aba38-117">返回值</span><span class="sxs-lookup"><span data-stu-id="aba38-117">Return value</span></span>

<span data-ttu-id="aba38-118">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="aba38-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="aba38-119">返回的常量</span><span class="sxs-lookup"><span data-stu-id="aba38-119">Constant</span></span>  |<span data-ttu-id="aba38-120">“值”</span><span class="sxs-lookup"><span data-stu-id="aba38-120">Value</span></span>  |<span data-ttu-id="aba38-121">描述</span><span class="sxs-lookup"><span data-stu-id="aba38-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="aba38-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="aba38-122">0x80041002</span></span> | <span data-ttu-id="aba38-123">找不到指定的属性。</span><span class="sxs-lookup"><span data-stu-id="aba38-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="aba38-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="aba38-124">0x80041006</span></span> | <span data-ttu-id="aba38-125">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="aba38-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="aba38-126">0</span><span class="sxs-lookup"><span data-stu-id="aba38-126">0</span></span> | <span data-ttu-id="aba38-127">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="aba38-127">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="aba38-128">备注</span><span class="sxs-lookup"><span data-stu-id="aba38-128">Remarks</span></span>

<span data-ttu-id="aba38-129">此函数包装对[IWbemClassObject：： GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="aba38-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="aba38-130">如果该方法在参数中没有，Windows Management 可以将[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针设置为 `null`。</span><span class="sxs-lookup"><span data-stu-id="aba38-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="aba38-131">在 `ppInSignature` 和 `ppOutSignature` 分别说明 in 和 out 参数，作为 system 类[_Parameters](/windows/desktop/WmiSdk/--parameters)的 `IWbemClassObject` 实例中的属性。</span><span class="sxs-lookup"><span data-stu-id="aba38-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="aba38-132">`ppInSignature` 中的属性名为 `Param`*n*，其中*n*是参数在方法签名中的位置（如 `Param1`、`Param2`，等等）。</span><span class="sxs-lookup"><span data-stu-id="aba38-132">The properties in `ppInSignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="aba38-133">`ppOutSignature` 中的属性也称为 `Param`*n*，返回值为 `ReturnValue`。</span><span class="sxs-lookup"><span data-stu-id="aba38-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="aba38-134">有关详细信息和示例，请参阅[IWbemClassObject：： GetMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod)。</span><span class="sxs-lookup"><span data-stu-id="aba38-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="aba38-135">要求</span><span class="sxs-lookup"><span data-stu-id="aba38-135">Requirements</span></span>

<span data-ttu-id="aba38-136">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aba38-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="aba38-137">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="aba38-137">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="aba38-138">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="aba38-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="aba38-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="aba38-139">See also</span></span>

- [<span data-ttu-id="aba38-140">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="aba38-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
