---
title: GetObjectText 函数 （非托管 API 参考）
description: GetObjectText 函数返回对象的文本呈现用 MOF 语法。
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
ms.openlocfilehash: d2f0e766a3a310bdb58f7cbffd8d49404eb5e0b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459634"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="04cb9-103">GetObjectText 函数</span><span class="sxs-lookup"><span data-stu-id="04cb9-103">GetObjectText function</span></span>
<span data-ttu-id="04cb9-104">返回对象的文本呈现中的托管对象格式 (MOF) 语法。</span><span class="sxs-lookup"><span data-stu-id="04cb9-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="04cb9-105">语法</span><span class="sxs-lookup"><span data-stu-id="04cb9-105">Syntax</span></span>  
  
```  
HRESULT GetObjectText (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
); 
```  

## <a name="parameters"></a><span data-ttu-id="04cb9-106">参数</span><span class="sxs-lookup"><span data-stu-id="04cb9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="04cb9-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="04cb9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="04cb9-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="04cb9-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="04cb9-109">[in]通常 0。</span><span class="sxs-lookup"><span data-stu-id="04cb9-109">[in] Normally 0.</span></span> <span data-ttu-id="04cb9-110">如果`WBEM_FLAG_NO_FLAVORS`（或 0x1） 指定，限定符是包含不带传播或风格的信息。</span><span class="sxs-lookup"><span data-stu-id="04cb9-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

`pstrObjectText`   
<span data-ttu-id="04cb9-111">[out]指向的指针`null`条目。</span><span class="sxs-lookup"><span data-stu-id="04cb9-111">[out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="04cb9-112">返回时，新分配`BSTR`，该字符串包含对象 MOF 语法呈现。</span><span class="sxs-lookup"><span data-stu-id="04cb9-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="04cb9-113">返回值</span><span class="sxs-lookup"><span data-stu-id="04cb9-113">Return value</span></span>

<span data-ttu-id="04cb9-114">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="04cb9-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="04cb9-115">返回的常量</span><span class="sxs-lookup"><span data-stu-id="04cb9-115">Constant</span></span>  |<span data-ttu-id="04cb9-116">值</span><span class="sxs-lookup"><span data-stu-id="04cb9-116">Value</span></span>  |<span data-ttu-id="04cb9-117">描述</span><span class="sxs-lookup"><span data-stu-id="04cb9-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="04cb9-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="04cb9-118">0x80041001</span></span> | <span data-ttu-id="04cb9-119">发生了常规错误。</span><span class="sxs-lookup"><span data-stu-id="04cb9-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="04cb9-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="04cb9-120">0x80041008</span></span> | <span data-ttu-id="04cb9-121">参数不是有效的。</span><span class="sxs-lookup"><span data-stu-id="04cb9-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="04cb9-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="04cb9-122">0x80041006</span></span> | <span data-ttu-id="04cb9-123">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="04cb9-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="04cb9-124">0</span><span class="sxs-lookup"><span data-stu-id="04cb9-124">0</span></span> | <span data-ttu-id="04cb9-125">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="04cb9-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="04cb9-126">备注</span><span class="sxs-lookup"><span data-stu-id="04cb9-126">Remarks</span></span>

<span data-ttu-id="04cb9-127">此函数包装对的调用[IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="04cb9-127">This function wraps a call to the [IWbemClassObject::GetObjectText](https://msdn.microsoft.com/library/aa391448(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="04cb9-128">返回的 MOF 文本不包含所有对象的相关信息，但仅足够 MOF 编译器要能够重新创建原始对象的信息。</span><span class="sxs-lookup"><span data-stu-id="04cb9-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="04cb9-129">例如，错误报告中不包括包含任何传播的限定符或父类属性。</span><span class="sxs-lookup"><span data-stu-id="04cb9-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="04cb9-130">以下算法用于重新构造方法的参数的文本：</span><span class="sxs-lookup"><span data-stu-id="04cb9-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="04cb9-131">参数被 resequenced 按其标识符值的顺序。</span><span class="sxs-lookup"><span data-stu-id="04cb9-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="04cb9-132">指定为参数`[in]`和`[out]`合并为单个参数。</span><span class="sxs-lookup"><span data-stu-id="04cb9-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>
 
<span data-ttu-id="04cb9-133">`pstrObjectText` 必须是指向`null`函数调用时，它必须不指向是之前调用方法有效，因为将会释放指针的字符串。</span><span class="sxs-lookup"><span data-stu-id="04cb9-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="04cb9-134">要求</span><span class="sxs-lookup"><span data-stu-id="04cb9-134">Requirements</span></span>  
<span data-ttu-id="04cb9-135">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04cb9-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04cb9-136">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="04cb9-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="04cb9-137">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04cb9-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04cb9-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="04cb9-138">See also</span></span>  
[<span data-ttu-id="04cb9-139">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="04cb9-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
