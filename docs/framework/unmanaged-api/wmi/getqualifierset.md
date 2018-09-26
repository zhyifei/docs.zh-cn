---
title: GetQualifierSet 函数 （非托管 API 参考）
description: GetQualifierSet 函数可检索为类或实例设置的限定符。
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 635dc7605af00f2662a9f9553adefafcd25f9452
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/26/2018
ms.locfileid: "47198756"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="0b1a1-103">GetQualifierSet 函数</span><span class="sxs-lookup"><span data-stu-id="0b1a1-103">GetQualifierSet function</span></span>
<span data-ttu-id="0b1a1-104">检索类实例或类定义的限定符集。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0b1a1-105">语法</span><span class="sxs-lookup"><span data-stu-id="0b1a1-105">Syntax</span></span>  
  
```  
HRESULT GetQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a><span data-ttu-id="0b1a1-106">参数</span><span class="sxs-lookup"><span data-stu-id="0b1a1-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0b1a1-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0b1a1-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="0b1a1-109">[out]接收允许对类对象的限定符访问的接口指针。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="0b1a1-110">`ppQualSet` 不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="0b1a1-111">如果发生错误，未返回一个新的对象，并且指针保持不变。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span> 

## <a name="return-value"></a><span data-ttu-id="0b1a1-112">返回值</span><span class="sxs-lookup"><span data-stu-id="0b1a1-112">Return value</span></span>

<span data-ttu-id="0b1a1-113">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="0b1a1-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0b1a1-114">返回的常量</span><span class="sxs-lookup"><span data-stu-id="0b1a1-114">Constant</span></span>  |<span data-ttu-id="0b1a1-115">“值”</span><span class="sxs-lookup"><span data-stu-id="0b1a1-115">Value</span></span>  |<span data-ttu-id="0b1a1-116">描述</span><span class="sxs-lookup"><span data-stu-id="0b1a1-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="0b1a1-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="0b1a1-117">0x80041001</span></span> | <span data-ttu-id="0b1a1-118">已存在时的常见错误。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="0b1a1-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0b1a1-119">0x80041002</span></span> | <span data-ttu-id="0b1a1-120">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0b1a1-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0b1a1-121">0x80041006</span></span> | <span data-ttu-id="0b1a1-122">没有足够的内存是可用于完成该操作。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="0b1a1-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="0b1a1-123">0x80041008</span></span> | <span data-ttu-id="0b1a1-124">参数是`null`。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0b1a1-125">0</span><span class="sxs-lookup"><span data-stu-id="0b1a1-125">0</span></span> | <span data-ttu-id="0b1a1-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0b1a1-127">备注</span><span class="sxs-lookup"><span data-stu-id="0b1a1-127">Remarks</span></span>

<span data-ttu-id="0b1a1-128">此函数包装对的调用[IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)方法。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span> 

<span data-ttu-id="0b1a1-129">[IWbemQualifierSet 指针](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)允许调用方添加、 编辑或删除这些限定符。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="0b1a1-130">此类添加、 编辑或已删除的限定符应用于整个实例或类定义。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="0b1a1-131">要求</span><span class="sxs-lookup"><span data-stu-id="0b1a1-131">Requirements</span></span>  
<span data-ttu-id="0b1a1-132">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0b1a1-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0b1a1-133">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0b1a1-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0b1a1-134">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0b1a1-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b1a1-135">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b1a1-135">See also</span></span>  
[<span data-ttu-id="0b1a1-136">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="0b1a1-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
