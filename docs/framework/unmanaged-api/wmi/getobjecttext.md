---
title: 获取对象文本功能（非托管 API 引用）
description: GetObjectText 函数在 MOF 语法中返回对象的文本呈现。
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6881125760e0f1dc38e6b01917d5829edc95e3ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176781"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="35b16-103">GetObjectText 函数</span><span class="sxs-lookup"><span data-stu-id="35b16-103">GetObjectText function</span></span>
<span data-ttu-id="35b16-104">在托管对象格式 （MOF） 语法中返回对象的文本呈现。</span><span class="sxs-lookup"><span data-stu-id="35b16-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="35b16-105">语法</span><span class="sxs-lookup"><span data-stu-id="35b16-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="35b16-106">parameters</span><span class="sxs-lookup"><span data-stu-id="35b16-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="35b16-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="35b16-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="35b16-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="35b16-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="35b16-109">[在]通常为 0。</span><span class="sxs-lookup"><span data-stu-id="35b16-109">[in] Normally 0.</span></span> <span data-ttu-id="35b16-110">如果`WBEM_FLAG_NO_FLAVORS`指定 （或 0x1），则包含限定符而不包含传播或风味信息。</span><span class="sxs-lookup"><span data-stu-id="35b16-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="35b16-111">`pstrObjectText`[出]指向上条目的`null`指针。</span><span class="sxs-lookup"><span data-stu-id="35b16-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="35b16-112">返回时，包含对象的`BSTR`MOF 语法呈现的新分配。</span><span class="sxs-lookup"><span data-stu-id="35b16-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="35b16-113">返回值</span><span class="sxs-lookup"><span data-stu-id="35b16-113">Return value</span></span>

<span data-ttu-id="35b16-114">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="35b16-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="35b16-115">一直</span><span class="sxs-lookup"><span data-stu-id="35b16-115">Constant</span></span>  |<span data-ttu-id="35b16-116">值</span><span class="sxs-lookup"><span data-stu-id="35b16-116">Value</span></span>  |<span data-ttu-id="35b16-117">说明</span><span class="sxs-lookup"><span data-stu-id="35b16-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="35b16-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="35b16-118">0x80041001</span></span> | <span data-ttu-id="35b16-119">出现了一个普遍的失败。</span><span class="sxs-lookup"><span data-stu-id="35b16-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="35b16-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="35b16-120">0x80041008</span></span> | <span data-ttu-id="35b16-121">参数无效。</span><span class="sxs-lookup"><span data-stu-id="35b16-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="35b16-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="35b16-122">0x80041006</span></span> | <span data-ttu-id="35b16-123">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="35b16-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="35b16-124">0</span><span class="sxs-lookup"><span data-stu-id="35b16-124">0</span></span> | <span data-ttu-id="35b16-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="35b16-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="35b16-126">备注</span><span class="sxs-lookup"><span data-stu-id="35b16-126">Remarks</span></span>

<span data-ttu-id="35b16-127">此函数将调用包起来到[IWbem ClassObject：：getObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)方法。</span><span class="sxs-lookup"><span data-stu-id="35b16-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="35b16-128">返回的 MOF 文本不包含有关对象的所有信息，但仅包含足够的信息，以便 MOF 编译器能够重新创建原始对象。</span><span class="sxs-lookup"><span data-stu-id="35b16-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="35b16-129">例如，不包含传播的限定符或父类属性。</span><span class="sxs-lookup"><span data-stu-id="35b16-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="35b16-130">以下算法用于重建方法参数的文本：</span><span class="sxs-lookup"><span data-stu-id="35b16-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="35b16-131">参数按其标识符值的顺序重新排序。</span><span class="sxs-lookup"><span data-stu-id="35b16-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="35b16-132">指定为`[in]`并`[out]`组合到单个参数的参数。</span><span class="sxs-lookup"><span data-stu-id="35b16-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="35b16-133">`pstrObjectText`调用函数时必须指向`null`的 指针;它不得指向方法调用之前有效的字符串，因为指针不会被处理。</span><span class="sxs-lookup"><span data-stu-id="35b16-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="35b16-134">要求</span><span class="sxs-lookup"><span data-stu-id="35b16-134">Requirements</span></span>  
<span data-ttu-id="35b16-135">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="35b16-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35b16-136">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="35b16-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="35b16-137">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="35b16-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35b16-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35b16-138">See also</span></span>

- [<span data-ttu-id="35b16-139">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="35b16-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
