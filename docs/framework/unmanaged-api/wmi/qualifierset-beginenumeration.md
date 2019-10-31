---
title: QualifierSet_BeginEnumeration 函数（非托管 API 参考）
description: QualifierSet_BeginEnumeration 函数重置对象限定符的枚举器。
ms.date: 11/06/2017
api_name:
- QualifierSet_BeginEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_BeginEnumeration
helpviewer_keywords:
- QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 79edbd876fc9992f088b9adb159e005c735a72cb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127329"
---
# <a name="qualifierset_beginenumeration-function"></a><span data-ttu-id="0a10d-103">QualifierSet_BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="0a10d-103">QualifierSet_BeginEnumeration function</span></span>

<span data-ttu-id="0a10d-104">将对象限定符的枚举器重置到枚举的起始处。</span><span class="sxs-lookup"><span data-stu-id="0a10d-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="0a10d-105">语法</span><span class="sxs-lookup"><span data-stu-id="0a10d-105">Syntax</span></span>

```cpp
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags
);
```

## <a name="parameters"></a><span data-ttu-id="0a10d-106">参数</span><span class="sxs-lookup"><span data-stu-id="0a10d-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="0a10d-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="0a10d-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="0a10d-108">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="0a10d-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`\
<span data-ttu-id="0a10d-109">中"[备注](#remarks)" 部分中描述的标志或值的按位组合，用于指定要包括在枚举中的限定符。</span><span class="sxs-lookup"><span data-stu-id="0a10d-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="0a10d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0a10d-110">Return value</span></span>

<span data-ttu-id="0a10d-111">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="0a10d-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0a10d-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="0a10d-112">Constant</span></span>  |<span data-ttu-id="0a10d-113">“值”</span><span class="sxs-lookup"><span data-stu-id="0a10d-113">Value</span></span>  |<span data-ttu-id="0a10d-114">描述</span><span class="sxs-lookup"><span data-stu-id="0a10d-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0a10d-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0a10d-115">0x80041008</span></span> | <span data-ttu-id="0a10d-116">`lFlags` 参数无效。</span><span class="sxs-lookup"><span data-stu-id="0a10d-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="0a10d-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="0a10d-117">0x8004101d</span></span> | <span data-ttu-id="0a10d-118">对 `QualifierSet_BeginEnumeration` 进行了第二次调用，无需对[`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md)进行干预。</span><span class="sxs-lookup"><span data-stu-id="0a10d-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0a10d-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0a10d-119">0x80041006</span></span> | <span data-ttu-id="0a10d-120">没有足够的内存可用于开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="0a10d-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0a10d-121">0</span><span class="sxs-lookup"><span data-stu-id="0a10d-121">0</span></span> | <span data-ttu-id="0a10d-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="0a10d-122">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="0a10d-123">备注</span><span class="sxs-lookup"><span data-stu-id="0a10d-123">Remarks</span></span>

<span data-ttu-id="0a10d-124">此函数包装对[IWbemQualifierSet：： endenumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="0a10d-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="0a10d-125">若要枚举对象的所有限定符，必须在首次调用[QualifierSet_Next](qualifierset-next.md)之前调用此方法。</span><span class="sxs-lookup"><span data-stu-id="0a10d-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="0a10d-126">为给定枚举保证限定符的枚举顺序是固定的。</span><span class="sxs-lookup"><span data-stu-id="0a10d-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="0a10d-127">可以作为 `lEnumFlags` 参数传递的标志在*WbemCli*头文件中定义，也可以在代码中将它们定义为常量。</span><span class="sxs-lookup"><span data-stu-id="0a10d-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>

|<span data-ttu-id="0a10d-128">返回的常量</span><span class="sxs-lookup"><span data-stu-id="0a10d-128">Constant</span></span>  |<span data-ttu-id="0a10d-129">“值”</span><span class="sxs-lookup"><span data-stu-id="0a10d-129">Value</span></span>  |<span data-ttu-id="0a10d-130">描述</span><span class="sxs-lookup"><span data-stu-id="0a10d-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="0a10d-131">0</span><span class="sxs-lookup"><span data-stu-id="0a10d-131">0</span></span> | <span data-ttu-id="0a10d-132">返回所有限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="0a10d-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="0a10d-133">0x10</span><span class="sxs-lookup"><span data-stu-id="0a10d-133">0x10</span></span> | <span data-ttu-id="0a10d-134">仅返回特定于当前属性或对象的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="0a10d-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="0a10d-135">对于属性：仅返回特定于属性的限定符（包括替代），而不返回从类定义传播的限定符。</span><span class="sxs-lookup"><span data-stu-id="0a10d-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="0a10d-136">对于实例：仅返回特定于实例的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="0a10d-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="0a10d-137">对于类：仅返回特定于要派生的类的限定符。</span><span class="sxs-lookup"><span data-stu-id="0a10d-137">For a class: Return only qualifiers specific to the class being derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="0a10d-138">0x20</span><span class="sxs-lookup"><span data-stu-id="0a10d-138">0x20</span></span> | <span data-ttu-id="0a10d-139">仅返回从另一个对象传播的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="0a10d-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="0a10d-140">对于属性：返回从类定义传播到此属性的限定符，而不是从属性本身传播到此属性。</span><span class="sxs-lookup"><span data-stu-id="0a10d-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="0a10d-141">对于实例：仅返回从类定义传播的限定符。</span><span class="sxs-lookup"><span data-stu-id="0a10d-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="0a10d-142">对于类：仅返回从父类继承的那些限定符名称。</span><span class="sxs-lookup"><span data-stu-id="0a10d-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="0a10d-143">要求</span><span class="sxs-lookup"><span data-stu-id="0a10d-143">Requirements</span></span>

<span data-ttu-id="0a10d-144">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0a10d-144">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="0a10d-145">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="0a10d-145">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="0a10d-146">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0a10d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0a10d-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a10d-147">See also</span></span>

- [<span data-ttu-id="0a10d-148">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="0a10d-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
