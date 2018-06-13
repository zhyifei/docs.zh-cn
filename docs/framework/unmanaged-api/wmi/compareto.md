---
title: CompareTo 函数 （非托管 API 参考）
description: CompareTo 函数比较到另一个 WMI 对象的对象。
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
ms.openlocfilehash: db4431da90842f4f96a0f09a2f28dc473d956ee3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460403"
---
# <a name="compareto-function"></a><span data-ttu-id="f4b35-103">CompareTo 函数</span><span class="sxs-lookup"><span data-stu-id="f4b35-103">CompareTo function</span></span>
<span data-ttu-id="f4b35-104">比较对象和另一个 Windows 管理对象。</span><span class="sxs-lookup"><span data-stu-id="f4b35-104">Compares an object to another Windows management object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="f4b35-105">语法</span><span class="sxs-lookup"><span data-stu-id="f4b35-105">Syntax</span></span>  
  
```
HRESULT CompareTo (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              flags,
   [in] IWbemClassObject* pCompareTo 
); 
```  

## <a name="parameters"></a><span data-ttu-id="f4b35-106">参数</span><span class="sxs-lookup"><span data-stu-id="f4b35-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f4b35-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="f4b35-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f4b35-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="f4b35-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`flags`  
<span data-ttu-id="f4b35-109">[in]指定要考虑进行比较的对象特征的标志的按位组合。</span><span class="sxs-lookup"><span data-stu-id="f4b35-109">[in] A bitwise combination of the flags that specify the object characteristics to consider for the comparison.</span></span> <span data-ttu-id="f4b35-110">请参阅[备注](#remarks)部分以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="f4b35-110">See the [Remarks](#remarks) section for more information.</span></span>

`pCompareTo`  

<span data-ttu-id="f4b35-111">[in]用于比较的对象。</span><span class="sxs-lookup"><span data-stu-id="f4b35-111">[in] The object for comparison.</span></span> <span data-ttu-id="f4b35-112">`pcompareTo` 必须为有效[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例; 它不能是`null`。</span><span class="sxs-lookup"><span data-stu-id="f4b35-112">`pcompareTo` must be a valid [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance; it cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="f4b35-113">返回值</span><span class="sxs-lookup"><span data-stu-id="f4b35-113">Return value</span></span>

<span data-ttu-id="f4b35-114">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="f4b35-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f4b35-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="f4b35-115">Constant</span></span>  |<span data-ttu-id="f4b35-116">值</span><span class="sxs-lookup"><span data-stu-id="f4b35-116">Value</span></span>  |<span data-ttu-id="f4b35-117">描述</span><span class="sxs-lookup"><span data-stu-id="f4b35-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="f4b35-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f4b35-118">0x80041001</span></span> | <span data-ttu-id="f4b35-119">发生未知的错误。</span><span class="sxs-lookup"><span data-stu-id="f4b35-119">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f4b35-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f4b35-120">0x80041008</span></span> | <span data-ttu-id="f4b35-121">参数无效。</span><span class="sxs-lookup"><span data-stu-id="f4b35-121">A parameter is invalid.</span></span> |
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="f4b35-122">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="f4b35-122">0x8004101d</span></span> | <span data-ttu-id="f4b35-123">第二个调用`BeginEnumeration`而无需对的干预调用进行[ `EndEnumeration` ](endenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b35-123">A second call to `BeginEnumeration` was made without an intervening call to [`EndEnumeration`](endenumeration.md).</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="f4b35-124">0</span><span class="sxs-lookup"><span data-stu-id="f4b35-124">0</span></span> | <span data-ttu-id="f4b35-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="f4b35-125">The function call was successful.</span></span>  |
| `WBEM_S_DIFFERENT` | <span data-ttu-id="f4b35-126">0x40003</span><span class="sxs-lookup"><span data-stu-id="f4b35-126">0x40003</span></span> | <span data-ttu-id="f4b35-127">对象有不同。</span><span class="sxs-lookup"><span data-stu-id="f4b35-127">The objects are different.</span></span> |
| `WBEM_S_SAME` | <span data-ttu-id="f4b35-128">0</span><span class="sxs-lookup"><span data-stu-id="f4b35-128">0</span></span> | <span data-ttu-id="f4b35-129">对象相同的基于比较标志。</span><span class="sxs-lookup"><span data-stu-id="f4b35-129">The objects are the same based on the comparison flags.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="f4b35-130">备注</span><span class="sxs-lookup"><span data-stu-id="f4b35-130">Remarks</span></span>

<span data-ttu-id="f4b35-131">此函数包装对的调用[IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="f4b35-131">This function wraps a call to the [IWbemClassObject::CompareTo](https://msdn.microsoft.com/library/aa391437(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="f4b35-132">可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。</span><span class="sxs-lookup"><span data-stu-id="f4b35-132">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span> <span data-ttu-id="f4b35-133">通过指定以下标志的按位组合，可以指定在比较中涉及的各个特征：</span><span class="sxs-lookup"><span data-stu-id="f4b35-133">You can specify the individual characteristics involved in the comparison by specifying a bitwise combination of the following flags:</span></span>

|<span data-ttu-id="f4b35-134">返回的常量</span><span class="sxs-lookup"><span data-stu-id="f4b35-134">Constant</span></span>  |<span data-ttu-id="f4b35-135">值</span><span class="sxs-lookup"><span data-stu-id="f4b35-135">Value</span></span>  |<span data-ttu-id="f4b35-136">描述</span><span class="sxs-lookup"><span data-stu-id="f4b35-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_IGNORE_OBJECT_SOURCE` | <span data-ttu-id="f4b35-137">2</span><span class="sxs-lookup"><span data-stu-id="f4b35-137">2</span></span> | <span data-ttu-id="f4b35-138">忽略源 （服务器和它们的命名空间）。</span><span class="sxs-lookup"><span data-stu-id="f4b35-138">Ignore the source (the server and the namespace they came from).</span></span> |
| `WBEM_FLAG_IGNORE_QUALIFIERS` | <span data-ttu-id="f4b35-139">1</span><span class="sxs-lookup"><span data-stu-id="f4b35-139">1</span></span> | <span data-ttu-id="f4b35-140">忽略所有的限定符 (包括**密钥**和**动态**)</span><span class="sxs-lookup"><span data-stu-id="f4b35-140">Ignore all qualifiers (including **Key** and **Dynamic**)</span></span> |
| `WBEM_FLAG_IGNORE_DEFAULT_VALUES` | <span data-ttu-id="f4b35-141">4</span><span class="sxs-lookup"><span data-stu-id="f4b35-141">4</span></span> | <span data-ttu-id="f4b35-142">忽略属性的默认的值。</span><span class="sxs-lookup"><span data-stu-id="f4b35-142">Ignore default values of properties.</span></span> <span data-ttu-id="f4b35-143">此标志只适用于的类的比较。</span><span class="sxs-lookup"><span data-stu-id="f4b35-143">This flag only applies to comparison of classes.</span></span> |
| `WBEM_FLAG_IGNORE_FLAVOR` | <span data-ttu-id="f4b35-144">0x20</span><span class="sxs-lookup"><span data-stu-id="f4b35-144">0x20</span></span> | <span data-ttu-id="f4b35-145">忽略的限定符特色信息。</span><span class="sxs-lookup"><span data-stu-id="f4b35-145">Ignore qualifier flavors.</span></span> <span data-ttu-id="f4b35-146">此标志仍将限定符考虑在内，但会忽略风格差别如传播规则和重写限制。</span><span class="sxs-lookup"><span data-stu-id="f4b35-146">This flag still takes qualifiers into account, but ignores flavor distinctions such as propagation rules and override restrictions.</span></span> |
| `WBEM_FLAG_IGNORE_CASE` | <span data-ttu-id="f4b35-147">0x10</span><span class="sxs-lookup"><span data-stu-id="f4b35-147">0x10</span></span> | <span data-ttu-id="f4b35-148">忽略大小写的比较字符串值。</span><span class="sxs-lookup"><span data-stu-id="f4b35-148">Ignore case in comparing string values.</span></span> <span data-ttu-id="f4b35-149">这同时适用于字符串和限定符值。</span><span class="sxs-lookup"><span data-stu-id="f4b35-149">This applies both to strings and qualifier values.</span></span> <span data-ttu-id="f4b35-150">属性和限定符的名称比较始终是区分大小写，无论是否设置此标志。</span><span class="sxs-lookup"><span data-stu-id="f4b35-150">The comparison of property and qualifier names is always case-sensitive regardless of whether this flag is set.</span></span> |
| `WBEM_FLAG_IGNORE_CLASS` | <span data-ttu-id="f4b35-151">0x8</span><span class="sxs-lookup"><span data-stu-id="f4b35-151">0x8</span></span> | <span data-ttu-id="f4b35-152">假定要比较的对象都是同一个类的 instanes。</span><span class="sxs-lookup"><span data-stu-id="f4b35-152">Assume that the objects being compared are instanes of the same class.</span></span> <span data-ttu-id="f4b35-153">因此，此标志将实例相关信息进行比较。</span><span class="sxs-lookup"><span data-stu-id="f4b35-153">Consequently, this flag compares instance-related information only.</span></span> <span data-ttu-id="f4b35-154">使用此标志来优化性能。</span><span class="sxs-lookup"><span data-stu-id="f4b35-154">Use this flags to optimize performance.</span></span> <span data-ttu-id="f4b35-155">如果这些对象不属于相同，则结果是类的未定义。</span><span class="sxs-lookup"><span data-stu-id="f4b35-155">If the objects are not of the same class, the results are undefined.</span></span> |

<span data-ttu-id="f4b35-156">或者，你可以指定单个复合标志，如下所示：</span><span class="sxs-lookup"><span data-stu-id="f4b35-156">Or you can specify a single composite flag as follows:</span></span>

|<span data-ttu-id="f4b35-157">返回的常量</span><span class="sxs-lookup"><span data-stu-id="f4b35-157">Constant</span></span>  |<span data-ttu-id="f4b35-158">值</span><span class="sxs-lookup"><span data-stu-id="f4b35-158">Value</span></span>  |<span data-ttu-id="f4b35-159">描述</span><span class="sxs-lookup"><span data-stu-id="f4b35-159">Description</span></span>  |
|---------|---------|---------|
|`WBEM_COMPARISON_INCLUDE_ALL` | <span data-ttu-id="f4b35-160">0</span><span class="sxs-lookup"><span data-stu-id="f4b35-160">0</span></span> | <span data-ttu-id="f4b35-161">请考虑在比较中的所有功能。</span><span class="sxs-lookup"><span data-stu-id="f4b35-161">Consider all features in the comparison.</span></span> |

## <a name="requirements"></a><span data-ttu-id="f4b35-162">要求</span><span class="sxs-lookup"><span data-stu-id="f4b35-162">Requirements</span></span>  
 <span data-ttu-id="f4b35-163">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f4b35-163">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4b35-164">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="f4b35-164">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f4b35-165">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f4b35-165">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4b35-166">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4b35-166">See also</span></span>  
[<span data-ttu-id="f4b35-167">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="f4b35-167">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
