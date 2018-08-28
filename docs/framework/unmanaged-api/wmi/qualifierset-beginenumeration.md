---
title: QualifierSet_BeginEnumeration 函数 （非托管 API 参考）
description: QualifierSet_BeginEnumeration 函数重置对象的限定符的枚举的器。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d20701237501834c611c4e498c39597cf275176
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2018
ms.locfileid: "43001458"
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="8429f-103">QualifierSet_BeginEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="8429f-103">QualifierSet_BeginEnumeration function</span></span>
<span data-ttu-id="8429f-104">将一个对象的限定符的枚举数重置为枚举的开头。</span><span class="sxs-lookup"><span data-stu-id="8429f-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8429f-105">语法</span><span class="sxs-lookup"><span data-stu-id="8429f-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="8429f-106">参数</span><span class="sxs-lookup"><span data-stu-id="8429f-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="8429f-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="8429f-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="8429f-108">[in]一个指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例。</span><span class="sxs-lookup"><span data-stu-id="8429f-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="8429f-109">[in]值中所述的标志的按位组合[备注](#remarks)节指定要包括在枚举中的限定符。</span><span class="sxs-lookup"><span data-stu-id="8429f-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="8429f-110">返回值</span><span class="sxs-lookup"><span data-stu-id="8429f-110">Return value</span></span>

<span data-ttu-id="8429f-111">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="8429f-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8429f-112">返回的常量</span><span class="sxs-lookup"><span data-stu-id="8429f-112">Constant</span></span>  |<span data-ttu-id="8429f-113">“值”</span><span class="sxs-lookup"><span data-stu-id="8429f-113">Value</span></span>  |<span data-ttu-id="8429f-114">描述</span><span class="sxs-lookup"><span data-stu-id="8429f-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8429f-115">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8429f-115">0x80041008</span></span> | <span data-ttu-id="8429f-116">`lFlags`参数无效。</span><span class="sxs-lookup"><span data-stu-id="8429f-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="8429f-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="8429f-117">0x8004101d</span></span> | <span data-ttu-id="8429f-118">第二次调用`QualifierSet_BeginEnumeration`而无需对的干预调用进行[ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="8429f-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8429f-119">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8429f-119">0x80041006</span></span> | <span data-ttu-id="8429f-120">没有足够的内存，可开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="8429f-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8429f-121">0</span><span class="sxs-lookup"><span data-stu-id="8429f-121">0</span></span> | <span data-ttu-id="8429f-122">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="8429f-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8429f-123">备注</span><span class="sxs-lookup"><span data-stu-id="8429f-123">Remarks</span></span>

<span data-ttu-id="8429f-124">此函数包装对的调用[IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration)方法。</span><span class="sxs-lookup"><span data-stu-id="8429f-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-beginenumeration) method.</span></span>

<span data-ttu-id="8429f-125">若要枚举所有对象上的限定符，调用此方法必须在首次调用前[QualifierSet_Next](qualifierset-next.md)。</span><span class="sxs-lookup"><span data-stu-id="8429f-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="8429f-126">保证在其中枚举了限定符的顺序是固定的给定的枚举。</span><span class="sxs-lookup"><span data-stu-id="8429f-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="8429f-127">可以作为传递的标志`lEnumFlags`中定义参数*WbemCli.h*标头文件，也可以在定义它们为常量在代码中。</span><span class="sxs-lookup"><span data-stu-id="8429f-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>   

|<span data-ttu-id="8429f-128">返回的常量</span><span class="sxs-lookup"><span data-stu-id="8429f-128">Constant</span></span>  |<span data-ttu-id="8429f-129">“值”</span><span class="sxs-lookup"><span data-stu-id="8429f-129">Value</span></span>  |<span data-ttu-id="8429f-130">描述</span><span class="sxs-lookup"><span data-stu-id="8429f-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="8429f-131">0</span><span class="sxs-lookup"><span data-stu-id="8429f-131">0</span></span> | <span data-ttu-id="8429f-132">返回所有限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="8429f-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="8429f-133">0x10</span><span class="sxs-lookup"><span data-stu-id="8429f-133">0x10</span></span> | <span data-ttu-id="8429f-134">返回限定符的名称特定于当前的属性或对象。</span><span class="sxs-lookup"><span data-stu-id="8429f-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="8429f-135">属性： 返回仅限定符特定属性 （包括重写），并不是这些限定符传播从类定义。</span><span class="sxs-lookup"><span data-stu-id="8429f-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="8429f-136">实例： 返回仅特定于实例的限定符名称。</span><span class="sxs-lookup"><span data-stu-id="8429f-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="8429f-137">类： 回到派生类 beiong 特定仅限定符。</span><span class="sxs-lookup"><span data-stu-id="8429f-137">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="8429f-138">0x20</span><span class="sxs-lookup"><span data-stu-id="8429f-138">0x20</span></span> | <span data-ttu-id="8429f-139">返回名称的列是限定符传播从另一个对象。</span><span class="sxs-lookup"><span data-stu-id="8429f-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="8429f-140">属性： 返回仅限定符传播给此属性从类定义中，而不从该属性本身。</span><span class="sxs-lookup"><span data-stu-id="8429f-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="8429f-141">实例： 从类定义返回仅这些限定符传播。</span><span class="sxs-lookup"><span data-stu-id="8429f-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="8429f-142">类： 返回从父类继承仅这些限定符名称。</span><span class="sxs-lookup"><span data-stu-id="8429f-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="8429f-143">要求</span><span class="sxs-lookup"><span data-stu-id="8429f-143">Requirements</span></span>  
 <span data-ttu-id="8429f-144">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8429f-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8429f-145">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8429f-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8429f-146">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8429f-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8429f-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="8429f-147">See also</span></span>  
[<span data-ttu-id="8429f-148">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="8429f-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
