---
title: QualifierSet_Next 函数 （非托管 API 参考）
description: QualifierSet_Next 函数检索枚举中的下一步限定符。
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
ms.openlocfilehash: e8b96957467b0acb100f7eea137b3294a60e208a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000189"
---
# <a name="qualifiersetnext-function"></a><span data-ttu-id="e0ebb-103">QualifierSet_Next 函数</span><span class="sxs-lookup"><span data-stu-id="e0ebb-103">QualifierSet_Next function</span></span>
<span data-ttu-id="e0ebb-104">检索枚举中的下一个限定符，该枚举以调用 [QualifierSet_BeginEnumeration ](qualifierset-beginenumeration.md) 函数开始。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-104">Retrieves the next qualifier in an enumeration that started with a call to the [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) function.</span></span>   

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e0ebb-105">语法</span><span class="sxs-lookup"><span data-stu-id="e0ebb-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Next (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,        
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor                 
); 
```  

## <a name="parameters"></a><span data-ttu-id="e0ebb-106">参数</span><span class="sxs-lookup"><span data-stu-id="e0ebb-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="e0ebb-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="e0ebb-108">[in]一个指向[IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)实例。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-108">[in] A pointer to an [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) instance.</span></span>

`lFlags`   
<span data-ttu-id="e0ebb-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-109">[in] Reserved.</span></span> <span data-ttu-id="e0ebb-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-110">This parameter must be 0.</span></span>

`pstrName`   
<span data-ttu-id="e0ebb-111">[out]限定符的名称。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-111">[out] The name of the qualifier.</span></span> <span data-ttu-id="e0ebb-112">如果`null`，此参数是被忽略; 否则为`pstrName`应不指向有效`BSTR`或发生内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-112">If `null`, this parameter is ignored; otherwise, `pstrName` should not point to a valid `BSTR` or a memory leak occurs.</span></span> <span data-ttu-id="e0ebb-113">如果不为 null，该函数始终会分配一个新`BSTR`其返回`WBEM_S_NO_ERROR`。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-113">If not null, the function always allocates a new `BSTR` when it returns `WBEM_S_NO_ERROR`.</span></span>

`pVal`   
<span data-ttu-id="e0ebb-114">[out]成功后，限定符的值。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-114">[out] When successful, the value for the qualifier.</span></span> <span data-ttu-id="e0ebb-115">如果函数失败，`VARIANT`指向的`pVal`则不会修改。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-115">If the function fails, the `VARIANT` pointed to by `pVal` is not modified.</span></span> <span data-ttu-id="e0ebb-116">如果此参数为`null`，将忽略此参数。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-116">If this parameter is `null`, the parameter is ignored.</span></span>

`plFlavor`   
<span data-ttu-id="e0ebb-117">[out]为接收限定符特色信息的长整型指针。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-117">[out] A pointer to a LONG that receives the qualifier flavor.</span></span> <span data-ttu-id="e0ebb-118">如果不想风格的信息，此参数可以是`null`。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-118">If flavor information is not desired, this parameter can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="e0ebb-119">返回值</span><span class="sxs-lookup"><span data-stu-id="e0ebb-119">Return value</span></span>

<span data-ttu-id="e0ebb-120">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="e0ebb-120">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e0ebb-121">返回的常量</span><span class="sxs-lookup"><span data-stu-id="e0ebb-121">Constant</span></span>  |<span data-ttu-id="e0ebb-122">“值”</span><span class="sxs-lookup"><span data-stu-id="e0ebb-122">Value</span></span>  |<span data-ttu-id="e0ebb-123">描述</span><span class="sxs-lookup"><span data-stu-id="e0ebb-123">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e0ebb-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e0ebb-124">0x80041008</span></span> | <span data-ttu-id="e0ebb-125">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-125">A parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="e0ebb-126">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="e0ebb-126">0x8004101d</span></span> | <span data-ttu-id="e0ebb-127">调用方未调用[QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-127">The caller did not call [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e0ebb-128">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e0ebb-128">0x80041006</span></span> | <span data-ttu-id="e0ebb-129">没有足够的内存，可开始新的枚举。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-129">Not enough memory is available to begin a new enumeration.</span></span> |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="e0ebb-130">0x40005</span><span class="sxs-lookup"><span data-stu-id="e0ebb-130">0x40005</span></span> | <span data-ttu-id="e0ebb-131">没有更多限定符会保留在枚举。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-131">No more qualifiers are left in the enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e0ebb-132">0</span><span class="sxs-lookup"><span data-stu-id="e0ebb-132">0</span></span> | <span data-ttu-id="e0ebb-133">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-133">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e0ebb-134">备注</span><span class="sxs-lookup"><span data-stu-id="e0ebb-134">Remarks</span></span>

<span data-ttu-id="e0ebb-135">此函数包装对的调用[IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)方法。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-135">This function wraps a call to the [IWbemQualifierSet::Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next) method.</span></span>

<span data-ttu-id="e0ebb-136">在调用`QualifierSet_Next`函数重复合用来枚举函数返回之前所有的限定符`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-136">You call the `QualifierSet_Next` function repeatedly to enumerate all the qualifiers until the function return `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="e0ebb-137">若要终止枚举早期，调用[QualifierSet_EndEnumeration](qualifierset-endenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-137">To terminate the enumeration early, call the [QualifierSet_EndEnumeration](qualifierset-endenumeration.md) function.</span></span>

<span data-ttu-id="e0ebb-138">在枚举期间返回的限定符的顺序是未定义。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-138">The order of the qualifiers returned during the enumeration is undefined.</span></span>

## <a name="requirements"></a><span data-ttu-id="e0ebb-139">要求</span><span class="sxs-lookup"><span data-stu-id="e0ebb-139">Requirements</span></span>  
 <span data-ttu-id="e0ebb-140">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0ebb-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0ebb-141">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e0ebb-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e0ebb-142">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e0ebb-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0ebb-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ebb-143">See also</span></span>

- [<span data-ttu-id="e0ebb-144">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e0ebb-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
