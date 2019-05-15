---
title: GetMethodQualifierSet 函数 （非托管 API 参考）
description: GetMethodQualifierSet 函数检索方法的限定符集。
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 329dcf66c5178a16d0f278c258f6f80f5a1b3e8d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636754"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="d6111-103">GetMethodQualifierSet 函数</span><span class="sxs-lookup"><span data-stu-id="d6111-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="d6111-104">检索特定方法的限定符集。</span><span class="sxs-lookup"><span data-stu-id="d6111-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="d6111-105">语法</span><span class="sxs-lookup"><span data-stu-id="d6111-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="d6111-106">参数</span><span class="sxs-lookup"><span data-stu-id="d6111-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="d6111-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="d6111-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="d6111-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="d6111-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="d6111-109">[in]方法名称。</span><span class="sxs-lookup"><span data-stu-id="d6111-109">[in] The method  name.</span></span> <span data-ttu-id="d6111-110">`wszMethod` 必须指向有效`LPCWSTR`。</span><span class="sxs-lookup"><span data-stu-id="d6111-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="d6111-111">[out]接收允许的方法的限定符访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="d6111-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="d6111-112">`ppQualSet` 不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d6111-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="d6111-113">如果发生错误，未返回一个新的对象，并将指针设置为指向`null`。</span><span class="sxs-lookup"><span data-stu-id="d6111-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="d6111-114">返回值</span><span class="sxs-lookup"><span data-stu-id="d6111-114">Return value</span></span>

<span data-ttu-id="d6111-115">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="d6111-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="d6111-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="d6111-116">Constant</span></span>  |<span data-ttu-id="d6111-117">值</span><span class="sxs-lookup"><span data-stu-id="d6111-117">Value</span></span>  |<span data-ttu-id="d6111-118">描述</span><span class="sxs-lookup"><span data-stu-id="d6111-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="d6111-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="d6111-119">0x80041002</span></span> | <span data-ttu-id="d6111-120">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="d6111-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="d6111-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="d6111-121">0x80041008</span></span> | <span data-ttu-id="d6111-122">参数是`null`。</span><span class="sxs-lookup"><span data-stu-id="d6111-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="d6111-123">0</span><span class="sxs-lookup"><span data-stu-id="d6111-123">0</span></span> | <span data-ttu-id="d6111-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="d6111-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="d6111-125">备注</span><span class="sxs-lookup"><span data-stu-id="d6111-125">Remarks</span></span>

<span data-ttu-id="d6111-126">此函数包装对的调用[IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset)方法。</span><span class="sxs-lookup"><span data-stu-id="d6111-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="d6111-127">当前对象是 CIM 类定义时，才支持对此函数的调用。</span><span class="sxs-lookup"><span data-stu-id="d6111-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="d6111-128">方法操作不适用于[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指向 CIM 实例的指针。</span><span class="sxs-lookup"><span data-stu-id="d6111-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="d6111-129">因为每个方法可能具有其自己的限定符[IWbemQualifierSet 指针](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)允许调用方添加、 编辑或删除这些限定符。</span><span class="sxs-lookup"><span data-stu-id="d6111-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="d6111-130">要求</span><span class="sxs-lookup"><span data-stu-id="d6111-130">Requirements</span></span>

<span data-ttu-id="d6111-131">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6111-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="d6111-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="d6111-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="d6111-133">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="d6111-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d6111-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="d6111-134">See also</span></span>

- [<span data-ttu-id="d6111-135">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d6111-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
