---
title: QualifierSet_Put 函数 （非托管 API 参考）
description: QualifierSet_Put 函数写入指定的限定符和其值。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e42cf3440bef030f5c7bec71ed1b4b875b79a61
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57378813"
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="9aea8-103">QualifierSet_Put 函数</span><span class="sxs-lookup"><span data-stu-id="9aea8-103">QualifierSet_Put function</span></span>

<span data-ttu-id="9aea8-104">写入命名限定符和值。</span><span class="sxs-lookup"><span data-stu-id="9aea8-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="9aea8-105">新限定符将覆盖具有相同名称的以前的值。</span><span class="sxs-lookup"><span data-stu-id="9aea8-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="9aea8-106">如果限定符不存在，则创建它。</span><span class="sxs-lookup"><span data-stu-id="9aea8-106">If the qualifier does not exist, it is created.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="9aea8-107">语法</span><span class="sxs-lookup"><span data-stu-id="9aea8-107">Syntax</span></span>

```cpp
HRESULT QualifierSet_Put (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
);
```

## <a name="parameters"></a><span data-ttu-id="9aea8-108">参数</span><span class="sxs-lookup"><span data-stu-id="9aea8-108">Parameters</span></span>

`vFunc`\
<span data-ttu-id="9aea8-109">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="9aea8-109">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="9aea8-110">[in]一个指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例。</span><span class="sxs-lookup"><span data-stu-id="9aea8-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`\
<span data-ttu-id="9aea8-111">[in]要写入的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="9aea8-111">[in] The name of the qualifier to write.</span></span>

`pVal`\
<span data-ttu-id="9aea8-112">[in]指向一个有效的指针`VARIANT`，其中包含要写入的限定符。</span><span class="sxs-lookup"><span data-stu-id="9aea8-112">[in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="9aea8-113">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="9aea8-113">This parameter cannot be `null`.</span></span>

`lFlavor`\
<span data-ttu-id="9aea8-114">[in]定义此限定符的所需的限定符特色信息的以下常量之一。</span><span class="sxs-lookup"><span data-stu-id="9aea8-114">[in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="9aea8-115">默认值是`WBEM_FLAVOR_OVERRIDABLE`(0)。</span><span class="sxs-lookup"><span data-stu-id="9aea8-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="9aea8-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="9aea8-116">Constant</span></span>  |<span data-ttu-id="9aea8-117">值</span><span class="sxs-lookup"><span data-stu-id="9aea8-117">Value</span></span>  |<span data-ttu-id="9aea8-118">描述</span><span class="sxs-lookup"><span data-stu-id="9aea8-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="9aea8-119">0</span><span class="sxs-lookup"><span data-stu-id="9aea8-119">0</span></span> | <span data-ttu-id="9aea8-120">可以在派生的类或实例中重写限定符。</span><span class="sxs-lookup"><span data-stu-id="9aea8-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="9aea8-121">**这是默认值。**</span><span class="sxs-lookup"><span data-stu-id="9aea8-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="9aea8-122">1</span><span class="sxs-lookup"><span data-stu-id="9aea8-122">1</span></span> | <span data-ttu-id="9aea8-123">限定符传播到实例。</span><span class="sxs-lookup"><span data-stu-id="9aea8-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="9aea8-124">2</span><span class="sxs-lookup"><span data-stu-id="9aea8-124">2</span></span> | <span data-ttu-id="9aea8-125">将限定符传播给派生类。</span><span class="sxs-lookup"><span data-stu-id="9aea8-125">The qualifier is propagated to derived classes.</span></span> |
| `WBEM_FLAVOR_NOT_OVERRIDABLE` | <span data-ttu-id="9aea8-126">0x10</span><span class="sxs-lookup"><span data-stu-id="9aea8-126">0x10</span></span> | <span data-ttu-id="9aea8-127">不能在派生类或实例中重写限定符。</span><span class="sxs-lookup"><span data-stu-id="9aea8-127">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| `WBEM_FLAVOR_AMENDED` | <span data-ttu-id="9aea8-128">0x80</span><span class="sxs-lookup"><span data-stu-id="9aea8-128">0x80</span></span> | <span data-ttu-id="9aea8-129">本地化限定符。</span><span class="sxs-lookup"><span data-stu-id="9aea8-129">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="9aea8-130">返回值</span><span class="sxs-lookup"><span data-stu-id="9aea8-130">Return value</span></span>

<span data-ttu-id="9aea8-131">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="9aea8-131">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9aea8-132">返回的常量</span><span class="sxs-lookup"><span data-stu-id="9aea8-132">Constant</span></span>  |<span data-ttu-id="9aea8-133">“值”</span><span class="sxs-lookup"><span data-stu-id="9aea8-133">Value</span></span>  |<span data-ttu-id="9aea8-134">描述</span><span class="sxs-lookup"><span data-stu-id="9aea8-134">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="9aea8-135">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="9aea8-135">0x8004101f</span></span> | <span data-ttu-id="9aea8-136">出现非法尝试指定**密钥**限定符不能为键的属性。</span><span class="sxs-lookup"><span data-stu-id="9aea8-136">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="9aea8-137">指定密钥 om c; 对象 a 定义并不能在每个实例的基础上更改。</span><span class="sxs-lookup"><span data-stu-id="9aea8-137">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9aea8-138">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9aea8-138">0x80041008</span></span> | <span data-ttu-id="9aea8-139">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="9aea8-139">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="9aea8-140">0x80041029</span><span class="sxs-lookup"><span data-stu-id="9aea8-140">0x80041029</span></span> | <span data-ttu-id="9aea8-141">`pVal`参数不是合法的限定符类型。</span><span class="sxs-lookup"><span data-stu-id="9aea8-141">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="9aea8-142">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="9aea8-142">0x8004101a</span></span> | <span data-ttu-id="9aea8-143">不能调用`QualifierSet_Put`方法对限定符因为所属对象不允许重写。</span><span class="sxs-lookup"><span data-stu-id="9aea8-143">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="9aea8-144">0</span><span class="sxs-lookup"><span data-stu-id="9aea8-144">0</span></span> | <span data-ttu-id="9aea8-145">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="9aea8-145">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="9aea8-146">备注</span><span class="sxs-lookup"><span data-stu-id="9aea8-146">Remarks</span></span>

<span data-ttu-id="9aea8-147">此函数包装对的调用[IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put)方法。</span><span class="sxs-lookup"><span data-stu-id="9aea8-147">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="9aea8-148">要求</span><span class="sxs-lookup"><span data-stu-id="9aea8-148">Requirements</span></span>

<span data-ttu-id="9aea8-149">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9aea8-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="9aea8-150">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9aea8-150">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="9aea8-151">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9aea8-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="9aea8-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="9aea8-152">See also</span></span>

- [<span data-ttu-id="9aea8-153">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="9aea8-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)