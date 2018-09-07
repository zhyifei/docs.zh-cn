---
title: EndMethodEnumeration 函数 （非托管 API 参考）
description: EndMethodEnumeration 函数终止方法将枚举序列。
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 42ee188c2a622d0bed2985e56e49997d2934686f
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078494"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="abbfe-103">EndMethodEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="abbfe-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="abbfe-104">终止通过调用开始枚举序列[BeginMethodEnumeration 函数](beginmethodenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="abbfe-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="abbfe-105">语法</span><span class="sxs-lookup"><span data-stu-id="abbfe-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="abbfe-106">参数</span><span class="sxs-lookup"><span data-stu-id="abbfe-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="abbfe-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="abbfe-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="abbfe-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="abbfe-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="abbfe-109">返回值</span><span class="sxs-lookup"><span data-stu-id="abbfe-109">Return value</span></span>

<span data-ttu-id="abbfe-110">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="abbfe-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="abbfe-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="abbfe-111">Constant</span></span>  |<span data-ttu-id="abbfe-112">“值”</span><span class="sxs-lookup"><span data-stu-id="abbfe-112">Value</span></span>  |<span data-ttu-id="abbfe-113">描述</span><span class="sxs-lookup"><span data-stu-id="abbfe-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="abbfe-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="abbfe-114">0x8004101d</span></span> | <span data-ttu-id="abbfe-115">出现内部错误。</span><span class="sxs-lookup"><span data-stu-id="abbfe-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="abbfe-116">0</span><span class="sxs-lookup"><span data-stu-id="abbfe-116">0</span></span> | <span data-ttu-id="abbfe-117">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="abbfe-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="abbfe-118">备注</span><span class="sxs-lookup"><span data-stu-id="abbfe-118">Remarks</span></span>

<span data-ttu-id="abbfe-119">此函数包装对的调用[IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)方法。</span><span class="sxs-lookup"><span data-stu-id="abbfe-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="abbfe-120">枚举序列使用调用方开始[BeginMethodEnumeration 函数](beginmethodenumeration.md)，然后调用[NextMethod 函数](nextmethod.md )直到该方法返回`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="abbfe-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="abbfe-121">调用方可以选择通过调用完成序列`EndMethodEnumeration`。</span><span class="sxs-lookup"><span data-stu-id="abbfe-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="abbfe-122">调用方可能会提前终止枚举，通过调用`EndMethodEnumeration`在任何时间。</span><span class="sxs-lookup"><span data-stu-id="abbfe-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="abbfe-123">要求</span><span class="sxs-lookup"><span data-stu-id="abbfe-123">Requirements</span></span>  
 <span data-ttu-id="abbfe-124">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="abbfe-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abbfe-125">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="abbfe-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="abbfe-126">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="abbfe-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abbfe-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="abbfe-127">See also</span></span>  
[<span data-ttu-id="abbfe-128">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="abbfe-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
