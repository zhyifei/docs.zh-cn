---
title: GetMethodQualifierSet 函数（非托管 API 参考）
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
ms.openlocfilehash: 86a7788736c3c12cfcfd405de88dfadfb14c1eca
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798525"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="88ef7-103">GetMethodQualifierSet 函数</span><span class="sxs-lookup"><span data-stu-id="88ef7-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="88ef7-104">检索特定方法的限定符集。</span><span class="sxs-lookup"><span data-stu-id="88ef7-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="88ef7-105">语法</span><span class="sxs-lookup"><span data-stu-id="88ef7-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="88ef7-106">参数</span><span class="sxs-lookup"><span data-stu-id="88ef7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="88ef7-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="88ef7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="88ef7-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="88ef7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="88ef7-109">中方法名称。</span><span class="sxs-lookup"><span data-stu-id="88ef7-109">[in] The method  name.</span></span> <span data-ttu-id="88ef7-110">`wszMethod`必须指向有效`LPCWSTR`的。</span><span class="sxs-lookup"><span data-stu-id="88ef7-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="88ef7-111">弄接收接口指针，该指针允许访问方法的限定符。</span><span class="sxs-lookup"><span data-stu-id="88ef7-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="88ef7-112">`ppQualSet` 不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="88ef7-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="88ef7-113">如果发生错误，则不会返回新的对象，并且将指针设置为指向`null`。</span><span class="sxs-lookup"><span data-stu-id="88ef7-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="88ef7-114">返回值</span><span class="sxs-lookup"><span data-stu-id="88ef7-114">Return value</span></span>

<span data-ttu-id="88ef7-115">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="88ef7-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="88ef7-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="88ef7-116">Constant</span></span>  |<span data-ttu-id="88ef7-117">值</span><span class="sxs-lookup"><span data-stu-id="88ef7-117">Value</span></span>  |<span data-ttu-id="88ef7-118">描述</span><span class="sxs-lookup"><span data-stu-id="88ef7-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="88ef7-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="88ef7-119">0x80041002</span></span> | <span data-ttu-id="88ef7-120">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="88ef7-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="88ef7-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="88ef7-121">0x80041008</span></span> | <span data-ttu-id="88ef7-122">参数为`null`。</span><span class="sxs-lookup"><span data-stu-id="88ef7-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="88ef7-123">0</span><span class="sxs-lookup"><span data-stu-id="88ef7-123">0</span></span> | <span data-ttu-id="88ef7-124">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="88ef7-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="88ef7-125">备注</span><span class="sxs-lookup"><span data-stu-id="88ef7-125">Remarks</span></span>

<span data-ttu-id="88ef7-126">此函数包装对[IWbemClassObject：： GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="88ef7-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="88ef7-127">仅当当前对象为 CIM 类定义时，才支持调用此函数。</span><span class="sxs-lookup"><span data-stu-id="88ef7-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="88ef7-128">方法操作不可用于指向 CIM 实例的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)指针。</span><span class="sxs-lookup"><span data-stu-id="88ef7-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="88ef7-129">由于每个方法都可以有自己的限定符，因此， [IWbemQualifierSet 指针](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)使调用方可以添加、编辑或删除这些限定符。</span><span class="sxs-lookup"><span data-stu-id="88ef7-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="88ef7-130">要求</span><span class="sxs-lookup"><span data-stu-id="88ef7-130">Requirements</span></span>

<span data-ttu-id="88ef7-131">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="88ef7-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="88ef7-132">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="88ef7-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="88ef7-133">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="88ef7-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="88ef7-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="88ef7-134">See also</span></span>

- [<span data-ttu-id="88ef7-135">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="88ef7-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
