---
title: Delete 函数（非托管 API 参考）
description: Delete 函数从 CIM 类定义中删除指定的属性及其所有限定符。
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1bf9bd5d93d1affee649588138456269411d280
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798667"
---
# <a name="delete-function"></a><span data-ttu-id="7b6d7-103">Delete 函数</span><span class="sxs-lookup"><span data-stu-id="7b6d7-103">Delete function</span></span>

<span data-ttu-id="7b6d7-104">从 CIM 类定义中删除指定的属性及其所有限定符。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="7b6d7-105">语法</span><span class="sxs-lookup"><span data-stu-id="7b6d7-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="7b6d7-106">参数</span><span class="sxs-lookup"><span data-stu-id="7b6d7-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="7b6d7-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="7b6d7-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="7b6d7-109">中要删除的属性的名称。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="7b6d7-110">`wszName`必须是指向有效`LPCWSTR`的的指针。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="7b6d7-111">返回值</span><span class="sxs-lookup"><span data-stu-id="7b6d7-111">Return value</span></span>

<span data-ttu-id="7b6d7-112">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="7b6d7-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7b6d7-113">返回的常量</span><span class="sxs-lookup"><span data-stu-id="7b6d7-113">Constant</span></span>  |<span data-ttu-id="7b6d7-114">值</span><span class="sxs-lookup"><span data-stu-id="7b6d7-114">Value</span></span>  |<span data-ttu-id="7b6d7-115">描述</span><span class="sxs-lookup"><span data-stu-id="7b6d7-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="7b6d7-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="7b6d7-116">0x80041001</span></span> | <span data-ttu-id="7b6d7-117">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="7b6d7-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="7b6d7-118">0x80041016</span></span> | <span data-ttu-id="7b6d7-119">不能删除该属性。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="7b6d7-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="7b6d7-120">0x80041008</span></span> | <span data-ttu-id="7b6d7-121">`wszName` 无效。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="7b6d7-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="7b6d7-122">0x80041002</span></span> | <span data-ttu-id="7b6d7-123">指定的属性不存在。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="7b6d7-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="7b6d7-124">0x80041006</span></span> | <span data-ttu-id="7b6d7-125">没有足够的内存来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="7b6d7-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="7b6d7-126">0x8004101c</span></span> | <span data-ttu-id="7b6d7-127">属性继承自基类。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="7b6d7-128">属性为系统属性。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="7b6d7-129">0</span><span class="sxs-lookup"><span data-stu-id="7b6d7-129">0</span></span> | <span data-ttu-id="7b6d7-130">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="7b6d7-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="7b6d7-131">0x80041030</span></span> | <span data-ttu-id="7b6d7-132">函数删除了当前类的替代默认值。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="7b6d7-133">父类中此属性的默认值已重新激活。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="7b6d7-134">备注</span><span class="sxs-lookup"><span data-stu-id="7b6d7-134">Remarks</span></span>

<span data-ttu-id="7b6d7-135">此函数包装对[IWbemClassObject：:D e)](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="7b6d7-136">要求</span><span class="sxs-lookup"><span data-stu-id="7b6d7-136">Requirements</span></span>

<span data-ttu-id="7b6d7-137">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b6d7-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7b6d7-138">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7b6d7-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="7b6d7-139">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7b6d7-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7b6d7-140">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b6d7-140">See also</span></span>

- [<span data-ttu-id="7b6d7-141">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="7b6d7-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
