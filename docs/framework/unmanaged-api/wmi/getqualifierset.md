---
title: 获取限定符集功能（非托管 API 引用）
description: GetQualifierSet 函数检索类或实例的限定符集。
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
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176768"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="28ebc-103">GetQualifierSet 函数</span><span class="sxs-lookup"><span data-stu-id="28ebc-103">GetQualifierSet function</span></span>
<span data-ttu-id="28ebc-104">检索类实例或类定义的限定符集。</span><span class="sxs-lookup"><span data-stu-id="28ebc-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="28ebc-105">语法</span><span class="sxs-lookup"><span data-stu-id="28ebc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="28ebc-106">parameters</span><span class="sxs-lookup"><span data-stu-id="28ebc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="28ebc-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="28ebc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="28ebc-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="28ebc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="28ebc-109">[出]接收允许访问类对象的限定符的接口指针。</span><span class="sxs-lookup"><span data-stu-id="28ebc-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="28ebc-110">`ppQualSet` 不能为 `null`。</span><span class="sxs-lookup"><span data-stu-id="28ebc-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="28ebc-111">如果发生错误，则不返回新对象，并且指针未修改。</span><span class="sxs-lookup"><span data-stu-id="28ebc-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="28ebc-112">返回值</span><span class="sxs-lookup"><span data-stu-id="28ebc-112">Return value</span></span>

<span data-ttu-id="28ebc-113">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="28ebc-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="28ebc-114">一直</span><span class="sxs-lookup"><span data-stu-id="28ebc-114">Constant</span></span>  |<span data-ttu-id="28ebc-115">值</span><span class="sxs-lookup"><span data-stu-id="28ebc-115">Value</span></span>  |<span data-ttu-id="28ebc-116">说明</span><span class="sxs-lookup"><span data-stu-id="28ebc-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="28ebc-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="28ebc-117">0x80041001</span></span> | <span data-ttu-id="28ebc-118">出现了一个普遍的失败。</span><span class="sxs-lookup"><span data-stu-id="28ebc-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="28ebc-119">0 x80041002</span><span class="sxs-lookup"><span data-stu-id="28ebc-119">0x80041002</span></span> | <span data-ttu-id="28ebc-120">指定的方法不存在。</span><span class="sxs-lookup"><span data-stu-id="28ebc-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="28ebc-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="28ebc-121">0x80041006</span></span> | <span data-ttu-id="28ebc-122">没有足够的可用内存来完成该操作。</span><span class="sxs-lookup"><span data-stu-id="28ebc-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="28ebc-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="28ebc-123">0x80041008</span></span> | <span data-ttu-id="28ebc-124">参数为`null`。</span><span class="sxs-lookup"><span data-stu-id="28ebc-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="28ebc-125">0</span><span class="sxs-lookup"><span data-stu-id="28ebc-125">0</span></span> | <span data-ttu-id="28ebc-126">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="28ebc-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="28ebc-127">备注</span><span class="sxs-lookup"><span data-stu-id="28ebc-127">Remarks</span></span>

<span data-ttu-id="28ebc-128">此函数包装对[IWbem ClassObject 的调用：：getQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset)方法。</span><span class="sxs-lookup"><span data-stu-id="28ebc-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="28ebc-129">[IWbemQualifierSet 指针](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)允许调用方添加、编辑或删除这些限定符。</span><span class="sxs-lookup"><span data-stu-id="28ebc-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="28ebc-130">此类添加、编辑或删除的限定符适用于整个实例或类定义。</span><span class="sxs-lookup"><span data-stu-id="28ebc-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="28ebc-131">要求</span><span class="sxs-lookup"><span data-stu-id="28ebc-131">Requirements</span></span>  
<span data-ttu-id="28ebc-132">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="28ebc-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28ebc-133">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="28ebc-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="28ebc-134">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="28ebc-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="28ebc-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28ebc-135">See also</span></span>

- [<span data-ttu-id="28ebc-136">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="28ebc-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
