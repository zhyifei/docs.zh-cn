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
ms.openlocfilehash: 0e1fc8d9d8c135f9eea8b9451b884ef3b7ba4704
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54694134"
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="fb83c-103">QualifierSet_Put 函数</span><span class="sxs-lookup"><span data-stu-id="fb83c-103">QualifierSet_Put function</span></span>
<span data-ttu-id="fb83c-104">写入命名限定符和值。</span><span class="sxs-lookup"><span data-stu-id="fb83c-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="fb83c-105">新限定符将覆盖具有相同名称的以前的值。</span><span class="sxs-lookup"><span data-stu-id="fb83c-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="fb83c-106">如果限定符不存在，则创建它。</span><span class="sxs-lookup"><span data-stu-id="fb83c-106">If the qualifier does not exist, it is created.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fb83c-107">语法</span><span class="sxs-lookup"><span data-stu-id="fb83c-107">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="fb83c-108">参数</span><span class="sxs-lookup"><span data-stu-id="fb83c-108">Parameters</span></span>

`vFunc`   
<span data-ttu-id="fb83c-109">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="fb83c-109">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="fb83c-110">[in]一个指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例。</span><span class="sxs-lookup"><span data-stu-id="fb83c-110">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`wszName`   
<span data-ttu-id="fb83c-111">[in]要写入的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="fb83c-111">[in] The name of the qualifier to write.</span></span>

<span data-ttu-id="fb83c-112">`pVal` [in]指向一个有效的指针`VARIANT`，其中包含要写入的限定符。</span><span class="sxs-lookup"><span data-stu-id="fb83c-112">`pVal` [in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="fb83c-113">此参数不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="fb83c-113">This parameter cannot be `null`.</span></span>

<span data-ttu-id="fb83c-114">`lFlavor` [in]定义此限定符的所需的限定符特色信息的以下常量之一。</span><span class="sxs-lookup"><span data-stu-id="fb83c-114">`lFlavor` [in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="fb83c-115">默认值是`WBEM_FLAVOR_OVERRIDABLE`(0)。</span><span class="sxs-lookup"><span data-stu-id="fb83c-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="fb83c-116">返回的常量</span><span class="sxs-lookup"><span data-stu-id="fb83c-116">Constant</span></span>  |<span data-ttu-id="fb83c-117">值</span><span class="sxs-lookup"><span data-stu-id="fb83c-117">Value</span></span>  |<span data-ttu-id="fb83c-118">描述</span><span class="sxs-lookup"><span data-stu-id="fb83c-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="fb83c-119">0</span><span class="sxs-lookup"><span data-stu-id="fb83c-119">0</span></span> | <span data-ttu-id="fb83c-120">可以在派生的类或实例中重写限定符。</span><span class="sxs-lookup"><span data-stu-id="fb83c-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="fb83c-121">**这是默认值。**</span><span class="sxs-lookup"><span data-stu-id="fb83c-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="fb83c-122">1</span><span class="sxs-lookup"><span data-stu-id="fb83c-122">1</span></span> | <span data-ttu-id="fb83c-123">限定符传播到实例。</span><span class="sxs-lookup"><span data-stu-id="fb83c-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="fb83c-124">2</span><span class="sxs-lookup"><span data-stu-id="fb83c-124">2</span></span> | <span data-ttu-id="fb83c-125">将限定符传播给派生类。</span><span class="sxs-lookup"><span data-stu-id="fb83c-125">The qualifier is propagated to derived classes.</span></span> |
| <span data-ttu-id="fb83c-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span><span class="sxs-lookup"><span data-stu-id="fb83c-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span></span> | <span data-ttu-id="fb83c-127">0x10</span><span class="sxs-lookup"><span data-stu-id="fb83c-127">0x10</span></span> | <span data-ttu-id="fb83c-128">不能在派生类或实例中重写限定符。</span><span class="sxs-lookup"><span data-stu-id="fb83c-128">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| <span data-ttu-id="fb83c-129">\`WBEM_FLAVOR_AMENDED</span><span class="sxs-lookup"><span data-stu-id="fb83c-129">\`WBEM_FLAVOR_AMENDED</span></span> | <span data-ttu-id="fb83c-130">0x80</span><span class="sxs-lookup"><span data-stu-id="fb83c-130">0x80</span></span> | <span data-ttu-id="fb83c-131">本地化限定符。</span><span class="sxs-lookup"><span data-stu-id="fb83c-131">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="fb83c-132">返回值</span><span class="sxs-lookup"><span data-stu-id="fb83c-132">Return value</span></span>

<span data-ttu-id="fb83c-133">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="fb83c-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fb83c-134">返回的常量</span><span class="sxs-lookup"><span data-stu-id="fb83c-134">Constant</span></span>  |<span data-ttu-id="fb83c-135">值</span><span class="sxs-lookup"><span data-stu-id="fb83c-135">Value</span></span>  |<span data-ttu-id="fb83c-136">描述</span><span class="sxs-lookup"><span data-stu-id="fb83c-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="fb83c-137">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="fb83c-137">0x8004101f</span></span> | <span data-ttu-id="fb83c-138">出现非法尝试指定**密钥**限定符不能为键的属性。</span><span class="sxs-lookup"><span data-stu-id="fb83c-138">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="fb83c-139">指定密钥 om c; 对象 a 定义并不能在每个实例的基础上更改。</span><span class="sxs-lookup"><span data-stu-id="fb83c-139">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fb83c-140">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fb83c-140">0x80041008</span></span> | <span data-ttu-id="fb83c-141">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="fb83c-141">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="fb83c-142">0x80041029</span><span class="sxs-lookup"><span data-stu-id="fb83c-142">0x80041029</span></span> | <span data-ttu-id="fb83c-143">`pVal`参数不是合法的限定符类型。</span><span class="sxs-lookup"><span data-stu-id="fb83c-143">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="fb83c-144">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="fb83c-144">0x8004101a</span></span> | <span data-ttu-id="fb83c-145">不能调用`QualifierSet_Put`方法对限定符因为所属对象不允许重写。</span><span class="sxs-lookup"><span data-stu-id="fb83c-145">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="fb83c-146">0</span><span class="sxs-lookup"><span data-stu-id="fb83c-146">0</span></span> | <span data-ttu-id="fb83c-147">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="fb83c-147">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fb83c-148">备注</span><span class="sxs-lookup"><span data-stu-id="fb83c-148">Remarks</span></span>

<span data-ttu-id="fb83c-149">此函数包装对的调用[IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put)方法。</span><span class="sxs-lookup"><span data-stu-id="fb83c-149">This function wraps a call to the [IWbemQualifierSet::Put](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-put) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb83c-150">要求</span><span class="sxs-lookup"><span data-stu-id="fb83c-150">Requirements</span></span>  
 <span data-ttu-id="fb83c-151">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fb83c-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb83c-152">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fb83c-152">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fb83c-153">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fb83c-153">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb83c-154">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb83c-154">See also</span></span>
- [<span data-ttu-id="fb83c-155">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="fb83c-155">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
