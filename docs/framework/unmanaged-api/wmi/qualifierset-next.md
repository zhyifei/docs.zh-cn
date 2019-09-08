---
title: QualifierSet_Next 函数（非托管 API 参考）
description: QualifierSet_Next 函数检索枚举中的下一个限定符。
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f97a19f236b87a7f4c5b2014aca6ee4abd338c63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798284"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="db57d-103">QualifierSet_Next 函数</span><span class="sxs-lookup"><span data-stu-id="db57d-103">QualifierSet_Next function</span></span>
<span data-ttu-id="db57d-104">检索枚举中的下一个限定符，该枚举以调用 [QualifierSet_BeginEnumeration ](qualifierset-beginenumeration.md) 函数开始。</span><span class="sxs-lookup"><span data-stu-id="db57d-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="db57d-105">语法</span><span class="sxs-lookup"><span data-stu-id="db57d-105">Syntax</span></span>  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="db57d-106">参数</span><span class="sxs-lookup"><span data-stu-id="db57d-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="db57d-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="db57d-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="db57d-108">中指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="db57d-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="db57d-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="db57d-109">[in] Reserved.</span></span> <span data-ttu-id="db57d-110">此参数必须为0。</span><span class="sxs-lookup"><span data-stu-id="db57d-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="db57d-111">弄限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="db57d-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="db57d-112">如果`null`为，则忽略此参数; 否则`pstrName` ，将不会指向有效`BSTR`或内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="db57d-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="db57d-113">如果不为 null，则当函数返回`BSTR` `WBEM_S_NO_ERROR`时，它将始终分配一个新的。</span><span class="sxs-lookup"><span data-stu-id="db57d-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="db57d-114">弄如果成功，则为限定符的值。</span><span class="sxs-lookup"><span data-stu-id="db57d-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="db57d-115">如果函数失败， `VARIANT`则不会修改指向的。 `pVal`</span><span class="sxs-lookup"><span data-stu-id="db57d-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="db57d-116">如果此参数为`null`，则忽略参数。</span><span class="sxs-lookup"><span data-stu-id="db57d-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="db57d-117">弄指向接收限定符风格的长时间的指针。</span><span class="sxs-lookup"><span data-stu-id="db57d-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="db57d-118">如果不需要口味信息，此参数可以为`null`。</span><span class="sxs-lookup"><span data-stu-id="db57d-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="db57d-119">返回值</span><span class="sxs-lookup"><span data-stu-id="db57d-119">Return value</span></span>

<span data-ttu-id="db57d-120">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="db57d-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="db57d-121">返回的常量</span><span class="sxs-lookup"><span data-stu-id="db57d-121">Constant</span></span>  |<span data-ttu-id="db57d-122">值</span><span class="sxs-lookup"><span data-stu-id="db57d-122">Value</span></span>  |<span data-ttu-id="db57d-123">描述</span><span class="sxs-lookup"><span data-stu-id="db57d-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="db57d-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="db57d-124">0x80041008</span></span> | <span data-ttu-id="db57d-125">参数无效。</span><span class="sxs-lookup"><span data-stu-id="db57d-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="db57d-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="db57d-126">0x8004101d</span></span> | <span data-ttu-id="db57d-127">调用方未调用[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="db57d-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="db57d-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="db57d-128">0x80041006</span></span> | <span data-ttu-id="db57d-129">没有足够的内存可用于开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="db57d-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="db57d-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="db57d-130">0x40005</span></span> | <span data-ttu-id="db57d-131">枚举中没有剩余限定符。</span><span class="sxs-lookup"><span data-stu-id="db57d-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="db57d-132">0</span><span class="sxs-lookup"><span data-stu-id="db57d-132">0</span></span> | <span data-ttu-id="db57d-133">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="db57d-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="db57d-134">备注</span><span class="sxs-lookup"><span data-stu-id="db57d-134">Remarks</span></span>

<span data-ttu-id="db57d-135">此函数包装对[IWbemQualifierSet：： Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="db57d-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="db57d-136">重复调用`QualifierSet_Next`函数以枚举所有限定符，直到函数返回`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="db57d-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="db57d-137">若要提前终止枚举，请调用[QualifierSet_EndEnumeration](qualifierset-endenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="db57d-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="db57d-138">枚举过程中返回的限定符的顺序是不确定的。</span><span class="sxs-lookup"><span data-stu-id="db57d-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="db57d-139">要求</span><span class="sxs-lookup"><span data-stu-id="db57d-139">Requirements</span></span>  
 <span data-ttu-id="db57d-140">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db57d-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db57d-141">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="db57d-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="db57d-142">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="db57d-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db57d-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="db57d-143">See also</span></span>

- [<span data-ttu-id="db57d-144">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="db57d-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
