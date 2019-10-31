---
title: GetObjectText 函数（非托管 API 参考）
description: GetObjectText 函数以 MOF 语法返回对象的文本呈现方式。
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
ms.openlocfilehash: 412e1ad503fa0e0b4f813298c0ac96ae80098c06
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102457"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="0fa79-103">GetObjectText 函数</span><span class="sxs-lookup"><span data-stu-id="0fa79-103">GetObjectText function</span></span>
<span data-ttu-id="0fa79-104">返回托管对象格式（MOF）语法中的对象的文本呈现形式。</span><span class="sxs-lookup"><span data-stu-id="0fa79-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0fa79-105">语法</span><span class="sxs-lookup"><span data-stu-id="0fa79-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="0fa79-106">参数</span><span class="sxs-lookup"><span data-stu-id="0fa79-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0fa79-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="0fa79-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0fa79-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="0fa79-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="0fa79-109">中通常为0。</span><span class="sxs-lookup"><span data-stu-id="0fa79-109">[in] Normally 0.</span></span> <span data-ttu-id="0fa79-110">如果指定 `WBEM_FLAG_NO_FLAVORS` （或0x1），则不包含传播或口味信息就包含限定符。</span><span class="sxs-lookup"><span data-stu-id="0fa79-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="0fa79-111">弄指向项 `null` 的指针。</span><span class="sxs-lookup"><span data-stu-id="0fa79-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="0fa79-112">返回时，包含对象的 MOF 语法呈现的新分配 `BSTR`。</span><span class="sxs-lookup"><span data-stu-id="0fa79-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="0fa79-113">返回值</span><span class="sxs-lookup"><span data-stu-id="0fa79-113">Return value</span></span>

<span data-ttu-id="0fa79-114">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="0fa79-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0fa79-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="0fa79-115">Constant</span></span>  |<span data-ttu-id="0fa79-116">“值”</span><span class="sxs-lookup"><span data-stu-id="0fa79-116">Value</span></span>  |<span data-ttu-id="0fa79-117">描述</span><span class="sxs-lookup"><span data-stu-id="0fa79-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="0fa79-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0fa79-118">0x80041001</span></span> | <span data-ttu-id="0fa79-119">出现一般错误。</span><span class="sxs-lookup"><span data-stu-id="0fa79-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0fa79-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0fa79-120">0x80041008</span></span> | <span data-ttu-id="0fa79-121">参数无效。</span><span class="sxs-lookup"><span data-stu-id="0fa79-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0fa79-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0fa79-122">0x80041006</span></span> | <span data-ttu-id="0fa79-123">没有足够的内存可用来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="0fa79-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0fa79-124">0</span><span class="sxs-lookup"><span data-stu-id="0fa79-124">0</span></span> | <span data-ttu-id="0fa79-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="0fa79-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0fa79-126">备注</span><span class="sxs-lookup"><span data-stu-id="0fa79-126">Remarks</span></span>

<span data-ttu-id="0fa79-127">此函数包装对[IWbemClassObject：： GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="0fa79-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="0fa79-128">返回的 MOF 文本不包含有关对象的所有信息，但只有足够的信息可供 MOF 编译器重新创建原始对象。</span><span class="sxs-lookup"><span data-stu-id="0fa79-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="0fa79-129">例如，不包含传播的限定符或父类属性。</span><span class="sxs-lookup"><span data-stu-id="0fa79-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="0fa79-130">以下算法用于重新构造方法的参数文本：</span><span class="sxs-lookup"><span data-stu-id="0fa79-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="0fa79-131">参数的标识符值顺序 resequenced。</span><span class="sxs-lookup"><span data-stu-id="0fa79-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="0fa79-132">指定为 `[in]` 和 `[out]` 的参数合并为单个参数。</span><span class="sxs-lookup"><span data-stu-id="0fa79-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="0fa79-133">调用函数时，`pstrObjectText` 必须是指向 `null` 的指针;它不能指向方法调用之前有效的字符串，因为不会释放指针。</span><span class="sxs-lookup"><span data-stu-id="0fa79-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="0fa79-134">要求</span><span class="sxs-lookup"><span data-stu-id="0fa79-134">Requirements</span></span>  
<span data-ttu-id="0fa79-135">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0fa79-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fa79-136">**标头：** WMINet_Utils .idl</span><span class="sxs-lookup"><span data-stu-id="0fa79-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0fa79-137">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0fa79-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fa79-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="0fa79-138">See also</span></span>

- [<span data-ttu-id="0fa79-139">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="0fa79-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
