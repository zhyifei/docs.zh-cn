---
title: GetObjectText 函数 （非托管 API 参考）
description: GetObjectText 函数用 MOF 语法返回一个对象的文本呈现。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d34cb399ac0e8780c442eeb2e95cebfd0a22ca02
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59208314"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="bcdaf-103">GetObjectText 函数</span><span class="sxs-lookup"><span data-stu-id="bcdaf-103">GetObjectText function</span></span>
<span data-ttu-id="bcdaf-104">返回托管对象格式 (MOF) 语法中的对象的文本呈现。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="bcdaf-105">语法</span><span class="sxs-lookup"><span data-stu-id="bcdaf-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="bcdaf-106">参数</span><span class="sxs-lookup"><span data-stu-id="bcdaf-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="bcdaf-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="bcdaf-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="bcdaf-109">[in]通常情况下 0。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-109">[in] Normally 0.</span></span> <span data-ttu-id="bcdaf-110">如果`WBEM_FLAG_NO_FLAVORS`（或 0x1） 指定，限定符是包含但不传播或风格的信息。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="bcdaf-111">[out]一个指向`null`条目。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="bcdaf-112">返回时，新分配`BSTR`，其中包含的对象的 MOF 语法呈现。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="bcdaf-113">返回值</span><span class="sxs-lookup"><span data-stu-id="bcdaf-113">Return value</span></span>

<span data-ttu-id="bcdaf-114">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="bcdaf-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="bcdaf-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="bcdaf-115">Constant</span></span>  |<span data-ttu-id="bcdaf-116">“值”</span><span class="sxs-lookup"><span data-stu-id="bcdaf-116">Value</span></span>  |<span data-ttu-id="bcdaf-117">描述</span><span class="sxs-lookup"><span data-stu-id="bcdaf-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="bcdaf-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="bcdaf-118">0x80041001</span></span> | <span data-ttu-id="bcdaf-119">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="bcdaf-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="bcdaf-120">0x80041008</span></span> | <span data-ttu-id="bcdaf-121">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="bcdaf-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="bcdaf-122">0x80041006</span></span> | <span data-ttu-id="bcdaf-123">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="bcdaf-124">0</span><span class="sxs-lookup"><span data-stu-id="bcdaf-124">0</span></span> | <span data-ttu-id="bcdaf-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="bcdaf-126">备注</span><span class="sxs-lookup"><span data-stu-id="bcdaf-126">Remarks</span></span>

<span data-ttu-id="bcdaf-127">此函数包装对的调用[IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext)方法。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="bcdaf-128">返回的 MOF 文本不包含所有对象的信息，但仅 MOF 编译器要能够重新创建原始对象的足够信息。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="bcdaf-129">例如，没有传播的限定符或父类属性中包含。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="bcdaf-130">使用以下算法来重新构造方法的参数的文本：</span><span class="sxs-lookup"><span data-stu-id="bcdaf-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="bcdaf-131">参数被 resequenced 按其标识符值的顺序。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="bcdaf-132">指定为参数`[in]`和`[out]`合并到单个参数。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
`pstrObjectText` <span data-ttu-id="bcdaf-133">必须是指向指针`null`时调用的函数; 它必须指向是方法调用前有效，因为将释放指针的字符串。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-133">must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="bcdaf-134">要求</span><span class="sxs-lookup"><span data-stu-id="bcdaf-134">Requirements</span></span>  
<span data-ttu-id="bcdaf-135">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bcdaf-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bcdaf-136">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="bcdaf-136">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="bcdaf-137">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="bcdaf-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bcdaf-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="bcdaf-138">See also</span></span>

- [<span data-ttu-id="bcdaf-139">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="bcdaf-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
