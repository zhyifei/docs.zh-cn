---
title: "QualifierSet_BeginEnumeration 函数 （非托管 API 参考）"
description: "QualifierSet_BeginEnumeration 函数将重置枚举器对象的限定符。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_BeginEnumeration
helpviewer_keywords: QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 440dde03f4ed138a33eb6f817723d7c5c74f6d46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="762b7-103">QualifierSet_BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="762b7-103">QualifierSet_BeginEnumeration function</span></span>
<span data-ttu-id="762b7-104">将枚举数对象的限定符重置为枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="762b7-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="762b7-105">语法</span><span class="sxs-lookup"><span data-stu-id="762b7-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="762b7-106">参数</span><span class="sxs-lookup"><span data-stu-id="762b7-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="762b7-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="762b7-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="762b7-108">[in]指向的指针[IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="762b7-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="762b7-109">[in]标志或中所述的值的按位组合[备注](#remarks)部分，用于指定要包含在枚举中的限定符。</span><span class="sxs-lookup"><span data-stu-id="762b7-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="762b7-110">返回值</span><span class="sxs-lookup"><span data-stu-id="762b7-110">Return value</span></span>

<span data-ttu-id="762b7-111">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="762b7-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="762b7-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="762b7-112">Constant</span></span>  |<span data-ttu-id="762b7-113">“值”</span><span class="sxs-lookup"><span data-stu-id="762b7-113">Value</span></span>  |<span data-ttu-id="762b7-114">描述</span><span class="sxs-lookup"><span data-stu-id="762b7-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="762b7-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="762b7-115">0x80041008</span></span> | <span data-ttu-id="762b7-116">`lFlags`参数无效。</span><span class="sxs-lookup"><span data-stu-id="762b7-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="762b7-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="762b7-117">0x8004101d</span></span> | <span data-ttu-id="762b7-118">第二个调用`QualifierSet_BeginEnumeration`而无需对的干预调用进行[ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="762b7-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="762b7-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="762b7-119">0x80041006</span></span> | <span data-ttu-id="762b7-120">没有足够的内存，可开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="762b7-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="762b7-121">0</span><span class="sxs-lookup"><span data-stu-id="762b7-121">0</span></span> | <span data-ttu-id="762b7-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="762b7-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="762b7-123">备注</span><span class="sxs-lookup"><span data-stu-id="762b7-123">Remarks</span></span>

<span data-ttu-id="762b7-124">此函数包装对的调用[IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="762b7-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="762b7-125">若要枚举所有对象上的限定符，此方法必须调用之前首次调用[QualifierSet_Next](qualifierset-next.md)。</span><span class="sxs-lookup"><span data-stu-id="762b7-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="762b7-126">在其中枚举限定符的顺序被保证是固定为给定的枚举。</span><span class="sxs-lookup"><span data-stu-id="762b7-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="762b7-127">可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中。</span><span class="sxs-lookup"><span data-stu-id="762b7-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>   

|<span data-ttu-id="762b7-128">返回的常量</span><span class="sxs-lookup"><span data-stu-id="762b7-128">Constant</span></span>  |<span data-ttu-id="762b7-129">“值”</span><span class="sxs-lookup"><span data-stu-id="762b7-129">Value</span></span>  |<span data-ttu-id="762b7-130">描述</span><span class="sxs-lookup"><span data-stu-id="762b7-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="762b7-131">0</span><span class="sxs-lookup"><span data-stu-id="762b7-131">0</span></span> | <span data-ttu-id="762b7-132">返回所有限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="762b7-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="762b7-133">0x10</span><span class="sxs-lookup"><span data-stu-id="762b7-133">0x10</span></span> | <span data-ttu-id="762b7-134">返回特定于当前的属性或对象的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="762b7-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="762b7-135">属性： 返回仅限定符特定的属性 （包括替代），并不这些限定符传播从类定义。</span><span class="sxs-lookup"><span data-stu-id="762b7-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="762b7-136">实例： 返回仅特定于实例的限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="762b7-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="762b7-137">类： 回到派生类 beiong 特定仅限定符。</span><span class="sxs-lookup"><span data-stu-id="762b7-137">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="762b7-138">0x20</span><span class="sxs-lookup"><span data-stu-id="762b7-138">0x20</span></span> | <span data-ttu-id="762b7-139">返回名称的列是限定符传播的另一个对象。</span><span class="sxs-lookup"><span data-stu-id="762b7-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="762b7-140">属性： 返回仅限定符传播到此属性从类定义中，而不从本身的属性。</span><span class="sxs-lookup"><span data-stu-id="762b7-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="762b7-141">实例： 从类定义返回仅这些限定符传播。</span><span class="sxs-lookup"><span data-stu-id="762b7-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="762b7-142">类： 返回仅这些限定符名称从父类继承。</span><span class="sxs-lookup"><span data-stu-id="762b7-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="762b7-143">惠?</span><span class="sxs-lookup"><span data-stu-id="762b7-143">Requirements</span></span>  
 <span data-ttu-id="762b7-144">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="762b7-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="762b7-145">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="762b7-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="762b7-146">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="762b7-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="762b7-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="762b7-147">See also</span></span>  
[<span data-ttu-id="762b7-148">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="762b7-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
