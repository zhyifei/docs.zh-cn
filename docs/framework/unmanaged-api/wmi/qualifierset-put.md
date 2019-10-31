---
title: QualifierSet_Put 函数（非托管 API 参考）
description: QualifierSet_Put 函数写入指定的限定符及其值。
ms.date: 11/06/2017
api_name:
- QualifierSet_Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Put
helpviewer_keywords:
- QualifierSet_Put function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: a35025c6d16455a51b7b22d822ba77337ddd894a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120237"
---
# <a name="qualifierset_put-function"></a><span data-ttu-id="08b89-103">QualifierSet_Put 函数</span><span class="sxs-lookup"><span data-stu-id="08b89-103">QualifierSet_Put function</span></span>

<span data-ttu-id="08b89-104">写入命名限定符和值。</span><span class="sxs-lookup"><span data-stu-id="08b89-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="08b89-105">新限定符覆盖相同名称的以前的值。</span><span class="sxs-lookup"><span data-stu-id="08b89-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="08b89-106">如果限定符不存在，则创建它。</span><span class="sxs-lookup"><span data-stu-id="08b89-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="08b89-107">语法</span><span class="sxs-lookup"><span data-stu-id="08b89-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="08b89-108">参数</span><span class="sxs-lookup"><span data-stu-id="08b89-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="08b89-109">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="08b89-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="08b89-110">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="08b89-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="08b89-111">中要写入的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="08b89-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="08b89-112">中指向包含要写入的限定符的有效 `VARIANT` 的指针。</span><span class="sxs-lookup"><span data-stu-id="08b89-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="08b89-113">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="08b89-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="08b89-114">中以下常量之一，定义此限定符所需的限定符风格。</span><span class="sxs-lookup"><span data-stu-id="08b89-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="08b89-115">默认值为 `WBEM_FLAVOR_OVERRIDABLE` （0）。</span><span class="sxs-lookup"><span data-stu-id="08b89-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="08b89-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="08b89-116">Constant</span></span>  |<span data-ttu-id="08b89-117">“值”</span><span class="sxs-lookup"><span data-stu-id="08b89-117">Value</span></span>  |<span data-ttu-id="08b89-118">描述</span><span class="sxs-lookup"><span data-stu-id="08b89-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="08b89-119">0</span><span class="sxs-lookup"><span data-stu-id="08b89-119">0</span></span> | <span data-ttu-id="08b89-120">限定符可以在派生类或实例中重写。</span><span class="sxs-lookup"><span data-stu-id="08b89-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="08b89-121">**这是默认值。**</span><span class="sxs-lookup"><span data-stu-id="08b89-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="08b89-122">1</span><span class="sxs-lookup"><span data-stu-id="08b89-122">1</span></span> | <span data-ttu-id="08b89-123">限定符传播到实例。</span><span class="sxs-lookup"><span data-stu-id="08b89-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="08b89-124">2</span><span class="sxs-lookup"><span data-stu-id="08b89-124">2</span></span> | <span data-ttu-id="08b89-125">限定符传播到派生类。</span><span class="sxs-lookup"><span data-stu-id="08b89-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="08b89-126">0x10</span><span class="sxs-lookup"><span data-stu-id="08b89-126">0x10</span></span> | <span data-ttu-id="08b89-127">不能在派生类或实例中重写限定符。</span><span class="sxs-lookup"><span data-stu-id="08b89-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="08b89-128">0x80</span><span class="sxs-lookup"><span data-stu-id="08b89-128">0x80</span></span> | <span data-ttu-id="08b89-129">限定符已本地化。</span><span class="sxs-lookup"><span data-stu-id="08b89-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="08b89-130">返回值</span><span class="sxs-lookup"><span data-stu-id="08b89-130">Return value</span></span>

<span data-ttu-id="08b89-131">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="08b89-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="08b89-132">返回的常量</span><span class="sxs-lookup"><span data-stu-id="08b89-132">Constant</span></span>  |<span data-ttu-id="08b89-133">“值”</span><span class="sxs-lookup"><span data-stu-id="08b89-133">Value</span></span>  |<span data-ttu-id="08b89-134">描述</span><span class="sxs-lookup"><span data-stu-id="08b89-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="08b89-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="08b89-135">0x8004101f</span></span> | <span data-ttu-id="08b89-136">尝试在不能是键的属性上指定**密钥**限定符。</span><span class="sxs-lookup"><span data-stu-id="08b89-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="08b89-137">键在对象的类定义中指定，不能基于每个实例进行更改。</span><span class="sxs-lookup"><span data-stu-id="08b89-137">The keys are specified in the class definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="08b89-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="08b89-138">0x80041008</span></span> | <span data-ttu-id="08b89-139">参数无效。</span><span class="sxs-lookup"><span data-stu-id="08b89-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="08b89-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="08b89-140">0x80041029</span></span> | <span data-ttu-id="08b89-141">`pVal` 参数不是合法的限定符类型。</span><span class="sxs-lookup"><span data-stu-id="08b89-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="08b89-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="08b89-142">0x8004101a</span></span> | <span data-ttu-id="08b89-143">不能对限定符调用 `QualifierSet_Put` 方法，因为所属对象不允许替代。</span><span class="sxs-lookup"><span data-stu-id="08b89-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="08b89-144">0</span><span class="sxs-lookup"><span data-stu-id="08b89-144">0</span></span> | <span data-ttu-id="08b89-145">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="08b89-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="08b89-146">备注</span><span class="sxs-lookup"><span data-stu-id="08b89-146">Remarks</span></span>

<span data-ttu-id="08b89-147">此函数包装对[IWbemQualifierSet：:P](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put)的工作方式方法的调用。</span><span class="sxs-lookup"><span data-stu-id="08b89-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="08b89-148">要求</span><span class="sxs-lookup"><span data-stu-id="08b89-148">Requirements</span></span>

<span data-ttu-id="08b89-149">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="08b89-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="08b89-150">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="08b89-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="08b89-151">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="08b89-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="08b89-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="08b89-152">See also</span></span>

- [<span data-ttu-id="08b89-153">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="08b89-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
