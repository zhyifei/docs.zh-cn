---
title: QualifierSet_Next函数（非托管 API 引用）
description: QualifierSet_Next函数在枚举中检索下一个限定符。
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
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174870"
---
# <a name="qualifierset_next-function"></a><span data-ttu-id="9b7a7-103">QualifierSet_Next 函数</span><span class="sxs-lookup"><span data-stu-id="9b7a7-103">QualifierSet_Next function</span></span>
<span data-ttu-id="9b7a7-104">检索枚举中的下一个限定符，该枚举以调用 [QualifierSet_BeginEnumeration ](qualifierset-beginenumeration.md) 函数开始。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9b7a7-105">语法</span><span class="sxs-lookup"><span data-stu-id="9b7a7-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="9b7a7-106">parameters</span><span class="sxs-lookup"><span data-stu-id="9b7a7-106">Parameters</span></span>

<span data-ttu-id="9b7a7-107">`vFunc`[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-107">`vFunc` [in] This parameter is unused.</span></span>

<span data-ttu-id="9b7a7-108">`ptr`[在]指向[IWbem 限定符集实例的](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)指针。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-108">`ptr` [in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

<span data-ttu-id="9b7a7-109">`lFlags`[在]保留。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-109">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="9b7a7-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-110">This parameter must be 0.</span></span>

<span data-ttu-id="9b7a7-111">`pstrName`[出]限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-111">`pstrName` [out] The name of the qualifier.</span></span> <span data-ttu-id="9b7a7-112">如果`null`忽略 此 参数，则忽略此参数。否则，`pstrName`不应指向有效`BSTR`或发生内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="9b7a7-113">如果不是 null，则函数在返回`BSTR``WBEM_S_NO_ERROR`时始终分配一个新的。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

<span data-ttu-id="9b7a7-114">`pVal`[出]成功时，限定符的值。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-114">`pVal` [out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="9b7a7-115">如果函数失败，`VARIANT`则 不修改`pVal`指向 的 。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="9b7a7-116">如果此参数为`null`，则忽略该参数。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-116">If this parameter is `null`, the parameter is ignored.</span></span>

<span data-ttu-id="9b7a7-117">`plFlavor`[出]指向接收限定符味道的 LONG 的指针。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-117">`plFlavor` [out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="9b7a7-118">如果不需要风味信息，则此参数可以是`null`。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-118">If flavor information is not desired, this parameter can be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="9b7a7-119">返回值</span><span class="sxs-lookup"><span data-stu-id="9b7a7-119">Return value</span></span>

<span data-ttu-id="9b7a7-120">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="9b7a7-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9b7a7-121">一直</span><span class="sxs-lookup"><span data-stu-id="9b7a7-121">Constant</span></span>  |<span data-ttu-id="9b7a7-122">值</span><span class="sxs-lookup"><span data-stu-id="9b7a7-122">Value</span></span>  |<span data-ttu-id="9b7a7-123">说明</span><span class="sxs-lookup"><span data-stu-id="9b7a7-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9b7a7-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9b7a7-124">0x80041008</span></span> | <span data-ttu-id="9b7a7-125">参数无效。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="9b7a7-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="9b7a7-126">0x8004101d</span></span> | <span data-ttu-id="9b7a7-127">呼叫者未呼叫[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="9b7a7-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="9b7a7-128">0x80041006</span></span> | <span data-ttu-id="9b7a7-129">没有足够的内存可用于开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="9b7a7-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="9b7a7-130">0x40005</span></span> | <span data-ttu-id="9b7a7-131">枚举中不再保留限定符。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9b7a7-132">0</span><span class="sxs-lookup"><span data-stu-id="9b7a7-132">0</span></span> | <span data-ttu-id="9b7a7-133">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9b7a7-134">备注</span><span class="sxs-lookup"><span data-stu-id="9b7a7-134">Remarks</span></span>

<span data-ttu-id="9b7a7-135">此函数包装对[IWbem 限定符集的调用：：下一个](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)方法。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="9b7a7-136">重复调用函数`QualifierSet_Next`以枚举所有限定符，直到函数返回`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="9b7a7-137">要提前终止枚举，请调用[QualifierSet_EndEnumeration](qualifierset-endenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="9b7a7-138">枚举期间返回的限定符的顺序未定义。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="9b7a7-139">要求</span><span class="sxs-lookup"><span data-stu-id="9b7a7-139">Requirements</span></span>  
 <span data-ttu-id="9b7a7-140">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9b7a7-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9b7a7-141">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9b7a7-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9b7a7-142">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9b7a7-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9b7a7-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9b7a7-143">See also</span></span>

- [<span data-ttu-id="9b7a7-144">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="9b7a7-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
