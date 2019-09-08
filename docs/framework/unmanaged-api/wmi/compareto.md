---
title: CompareTo 函数（非托管 API 参考）
description: CompareTo 函数将对象与另一个 WMI 对象进行比较。
ms.date: 11/06/2017
api_name:
- CompareTo
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CompareTo
helpviewer_keywords:
- CompareTo function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ec42dff333422e247a11b4a3a5b9aed9bd316fa
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798771"
---
# <a name="compareto-function"></a><span data-ttu-id="e09be-103">CompareTo 函数</span><span class="sxs-lookup"><span data-stu-id="e09be-103">CompareTo function</span></span>

<span data-ttu-id="e09be-104">将对象与另一个 Windows 管理对象进行比较。</span><span class="sxs-lookup"><span data-stu-id="e09be-104">Compares an object to another Windows management object.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e09be-105">语法</span><span class="sxs-lookup"><span data-stu-id="e09be-105">Syntax</span></span>

```cpp
HRESULT CompareTo (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo
);
```

## <a name="parameters"></a><span data-ttu-id="e09be-106">参数</span><span class="sxs-lookup"><span data-stu-id="e09be-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="e09be-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="e09be-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="e09be-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="e09be-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`flags`\
<span data-ttu-id="e09be-109">中标志的按位组合，用于指定要考虑比较的对象特征。</span><span class="sxs-lookup"><span data-stu-id="e09be-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="e09be-110">有关详细信息，请参阅 "[备注](#remarks)" 部分。</span><span class="sxs-lookup"><span data-stu-id="e09be-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`\
<span data-ttu-id="e09be-111">中用于比较的对象。</span><span class="sxs-lookup"><span data-stu-id="e09be-111">[in] The object for comparison.</span></span> <span data-ttu-id="e09be-112">`pCompareTo`必须是有效的[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例;不能为`null`。</span><span class="sxs-lookup"><span data-stu-id="e09be-112">`pCompareTo` must be a valid [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="e09be-113">返回值</span><span class="sxs-lookup"><span data-stu-id="e09be-113">Return value</span></span>

<span data-ttu-id="e09be-114">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="e09be-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e09be-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e09be-115">Constant</span></span>  |<span data-ttu-id="e09be-116">值</span><span class="sxs-lookup"><span data-stu-id="e09be-116">Value</span></span>  |<span data-ttu-id="e09be-117">描述</span><span class="sxs-lookup"><span data-stu-id="e09be-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="e09be-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="e09be-118">0x80041001</span></span> | <span data-ttu-id="e09be-119">发生了未指定的错误。</span><span class="sxs-lookup"><span data-stu-id="e09be-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e09be-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e09be-120">0x80041008</span></span> | <span data-ttu-id="e09be-121">参数无效。</span><span class="sxs-lookup"><span data-stu-id="e09be-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="e09be-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="e09be-122">0x8004101d</span></span> | <span data-ttu-id="e09be-123">对的第二`BeginEnumeration`次调用没有干预[`EndEnumeration`](endenumeration.md)调用。</span><span class="sxs-lookup"><span data-stu-id="e09be-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e09be-124">0</span><span class="sxs-lookup"><span data-stu-id="e09be-124">0</span></span> | <span data-ttu-id="e09be-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e09be-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="e09be-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="e09be-126">0x40003</span></span> | <span data-ttu-id="e09be-127">对象不同。</span><span class="sxs-lookup"><span data-stu-id="e09be-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="e09be-128">0</span><span class="sxs-lookup"><span data-stu-id="e09be-128">0</span></span> | <span data-ttu-id="e09be-129">根据比较标志，对象是相同的。</span><span class="sxs-lookup"><span data-stu-id="e09be-129">The objects are the same based on the comparison flags.</span></span> |

## <a name="remarks"></a><span data-ttu-id="e09be-130">备注</span><span class="sxs-lookup"><span data-stu-id="e09be-130">Remarks</span></span>

<span data-ttu-id="e09be-131">此函数包装对[IWbemClassObject：： CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="e09be-131">This function wraps a call to the [IWbemClassObject::CompareTo](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-compareto) method.</span></span>

<span data-ttu-id="e09be-132">可以作为`lEnumFlags`参数传递的标志在*WbemCli*头文件中定义，也可以在代码中将它们定义为常量。</span><span class="sxs-lookup"><span data-stu-id="e09be-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="e09be-133">您可以通过指定下列标志的按位组合来指定比较中涉及的各个特征：</span><span class="sxs-lookup"><span data-stu-id="e09be-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="e09be-134">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e09be-134">Constant</span></span>  |<span data-ttu-id="e09be-135">值</span><span class="sxs-lookup"><span data-stu-id="e09be-135">Value</span></span>  |<span data-ttu-id="e09be-136">描述</span><span class="sxs-lookup"><span data-stu-id="e09be-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="e09be-137">2</span><span class="sxs-lookup"><span data-stu-id="e09be-137">2</span></span> | <span data-ttu-id="e09be-138">忽略源（服务器及其所属的命名空间）。</span><span class="sxs-lookup"><span data-stu-id="e09be-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="e09be-139">1</span><span class="sxs-lookup"><span data-stu-id="e09be-139">1</span></span> | <span data-ttu-id="e09be-140">忽略所有限定符（包括**密钥**和**动态**）</span><span class="sxs-lookup"><span data-stu-id="e09be-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="e09be-141">4</span><span class="sxs-lookup"><span data-stu-id="e09be-141">4</span></span> | <span data-ttu-id="e09be-142">忽略属性的默认值。</span><span class="sxs-lookup"><span data-stu-id="e09be-142">Ignore default values of properties.</span></span> <span data-ttu-id="e09be-143">此标志仅适用于对类进行比较。</span><span class="sxs-lookup"><span data-stu-id="e09be-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="e09be-144">0x20</span><span class="sxs-lookup"><span data-stu-id="e09be-144">0x20</span></span> | <span data-ttu-id="e09be-145">忽略限定符的风格。</span><span class="sxs-lookup"><span data-stu-id="e09be-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="e09be-146">此标志仍会考虑限定符，但会忽略风格差别，如传播规则和替代限制。</span><span class="sxs-lookup"><span data-stu-id="e09be-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="e09be-147">0x10</span><span class="sxs-lookup"><span data-stu-id="e09be-147">0x10</span></span> | <span data-ttu-id="e09be-148">比较字符串值时忽略大小写。</span><span class="sxs-lookup"><span data-stu-id="e09be-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="e09be-149">这同时适用于字符串和限定符值。</span><span class="sxs-lookup"><span data-stu-id="e09be-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="e09be-150">不管是否设置了此标志，属性和限定符名称的比较始终区分大小写。</span><span class="sxs-lookup"><span data-stu-id="e09be-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="e09be-151">0x8</span><span class="sxs-lookup"><span data-stu-id="e09be-151">0x8</span></span> | <span data-ttu-id="e09be-152">假设要比较的对象是同一个类的实例。</span><span class="sxs-lookup"><span data-stu-id="e09be-152">Assume that the objects being compared are instances of the same class.</span></span> <span data-ttu-id="e09be-153">因此，此标志仅比较与实例相关的信息。</span><span class="sxs-lookup"><span data-stu-id="e09be-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="e09be-154">使用此标志优化性能。</span><span class="sxs-lookup"><span data-stu-id="e09be-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="e09be-155">如果对象不属于同一类，则结果是不确定的。</span><span class="sxs-lookup"><span data-stu-id="e09be-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="e09be-156">也可以按如下所示指定单个复合标志：</span><span class="sxs-lookup"><span data-stu-id="e09be-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="e09be-157">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e09be-157">Constant</span></span>  |<span data-ttu-id="e09be-158">值</span><span class="sxs-lookup"><span data-stu-id="e09be-158">Value</span></span>  |<span data-ttu-id="e09be-159">Description</span><span class="sxs-lookup"><span data-stu-id="e09be-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="e09be-160">0</span><span class="sxs-lookup"><span data-stu-id="e09be-160">0</span></span> | <span data-ttu-id="e09be-161">考虑比较中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="e09be-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="e09be-162">要求</span><span class="sxs-lookup"><span data-stu-id="e09be-162">Requirements</span></span>

<span data-ttu-id="e09be-163">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e09be-163">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="e09be-164">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e09be-164">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="e09be-165">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e09be-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="e09be-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="e09be-166">See also</span></span>

- [<span data-ttu-id="e09be-167">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e09be-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
