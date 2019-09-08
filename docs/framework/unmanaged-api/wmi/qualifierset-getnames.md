---
title: QualifierSet_GetNames 函数（非托管 API 参考）
description: QualifierSet_GetNames 函数从对象或属性中检索限定符的名称。
ms.date: 11/06/2017
api_name:
- QualifierSet_GetNames
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_GetNames
helpviewer_keywords:
- QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 266462a5393c8e26aa2bc3f2ec8ab72d4410a431
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798291"
---
# <a name="qualifierset_getnames-function"></a><span data-ttu-id="e0cdb-103">QualifierSet_GetNames 函数</span><span class="sxs-lookup"><span data-stu-id="e0cdb-103">QualifierSet_GetNames function</span></span>

<span data-ttu-id="e0cdb-104">检索当前对象或属性中可用的所有限定符或特定限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e0cdb-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0cdb-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
);
```

## <a name="parameters"></a><span data-ttu-id="e0cdb-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0cdb-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e0cdb-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e0cdb-108">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="e0cdb-109">中以下标志或值之一，指定要在枚举中包含的名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="e0cdb-110">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e0cdb-110">Constant</span></span>  |<span data-ttu-id="e0cdb-111">值</span><span class="sxs-lookup"><span data-stu-id="e0cdb-111">Value</span></span>  |<span data-ttu-id="e0cdb-112">Description</span><span class="sxs-lookup"><span data-stu-id="e0cdb-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="e0cdb-113">0</span><span class="sxs-lookup"><span data-stu-id="e0cdb-113">0</span></span> | <span data-ttu-id="e0cdb-114">返回所有限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="e0cdb-115">0x10</span><span class="sxs-lookup"><span data-stu-id="e0cdb-115">0x10</span></span> | <span data-ttu-id="e0cdb-116">仅返回特定于当前属性或对象的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="e0cdb-117">对于属性：仅返回特定于属性的限定符（包括替代），而不返回从类定义传播的限定符。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="e0cdb-118">对于实例：仅返回特定于实例的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="e0cdb-119">对于类：仅返回特定于派生类的限定符。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-119">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="e0cdb-120">0x20</span><span class="sxs-lookup"><span data-stu-id="e0cdb-120">0x20</span></span> | <span data-ttu-id="e0cdb-121">仅返回从另一个对象传播的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="e0cdb-122">对于属性：仅返回从类定义传播到此属性的限定符，而不是从属性本身传播的限定符。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="e0cdb-123">对于实例：仅返回从类定义传播的限定符。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="e0cdb-124">对于类：仅返回从父类继承的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

`pstrNames`\
<span data-ttu-id="e0cdb-125">弄一个新`SAFEARRAY`的，其中包含请求的名称。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-125">[out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="e0cdb-126">数组可以有0个元素。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-126">The array can have 0 elements.</span></span> <span data-ttu-id="e0cdb-127">如果发生错误，则不会`SAFEARRAY`返回新的。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="e0cdb-128">返回值</span><span class="sxs-lookup"><span data-stu-id="e0cdb-128">Return value</span></span>

<span data-ttu-id="e0cdb-129">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="e0cdb-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e0cdb-130">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e0cdb-130">Constant</span></span>  |<span data-ttu-id="e0cdb-131">值</span><span class="sxs-lookup"><span data-stu-id="e0cdb-131">Value</span></span>  |<span data-ttu-id="e0cdb-132">描述</span><span class="sxs-lookup"><span data-stu-id="e0cdb-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e0cdb-133">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e0cdb-133">0x80041008</span></span> | <span data-ttu-id="e0cdb-134">参数无效。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e0cdb-135">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e0cdb-135">0x80041006</span></span> | <span data-ttu-id="e0cdb-136">没有足够的内存可用于开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e0cdb-137">0</span><span class="sxs-lookup"><span data-stu-id="e0cdb-137">0</span></span> | <span data-ttu-id="e0cdb-138">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-138">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="e0cdb-139">备注</span><span class="sxs-lookup"><span data-stu-id="e0cdb-139">Remarks</span></span>

<span data-ttu-id="e0cdb-140">此函数包装对[IWbemQualifierSet：： GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-140">This function wraps a call to the [IWbemQualifierSet::GetNames](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-getnames) method.</span></span>

<span data-ttu-id="e0cdb-141">检索到限定符名称后，可以通过调用[QualifierSet_Get](qualifierset-get.md)函数按名称访问每个限定符。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span>

<span data-ttu-id="e0cdb-142">如果给定的对象具有零限定符，则不是错误的，因此，中`pstrNames`的字符串数可以为0，即使该函数返回`WBEM_S_NO_ERROR`也是如此。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0cdb-143">要求</span><span class="sxs-lookup"><span data-stu-id="e0cdb-143">Requirements</span></span>

<span data-ttu-id="e0cdb-144">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0cdb-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e0cdb-145">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e0cdb-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e0cdb-146">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e0cdb-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e0cdb-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0cdb-147">See also</span></span>

- [<span data-ttu-id="e0cdb-148">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e0cdb-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
