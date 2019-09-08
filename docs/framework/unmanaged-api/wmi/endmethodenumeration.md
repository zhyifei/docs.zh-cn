---
title: EndMethodEnumeration 函数（非托管 API 参考）
description: EndMethodEnumeration 函数终止方法枚举序列。
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
ms.openlocfilehash: cdcf49bd748a423b1cebfba88644aa961f1c7b65
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799352"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="17bbf-103">EndMethodEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="17bbf-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="17bbf-104">终止使用对[BeginMethodEnumeration 函数](beginmethodenumeration.md)的调用启动的枚举序列。</span><span class="sxs-lookup"><span data-stu-id="17bbf-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="17bbf-105">语法</span><span class="sxs-lookup"><span data-stu-id="17bbf-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="17bbf-106">参数</span><span class="sxs-lookup"><span data-stu-id="17bbf-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="17bbf-107">中此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="17bbf-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="17bbf-108">中指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例的指针。</span><span class="sxs-lookup"><span data-stu-id="17bbf-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="17bbf-109">返回值</span><span class="sxs-lookup"><span data-stu-id="17bbf-109">Return value</span></span>

<span data-ttu-id="17bbf-110">此函数返回的以下值是在*WbemCli*头文件中定义的，也可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="17bbf-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="17bbf-111">返回的常量</span><span class="sxs-lookup"><span data-stu-id="17bbf-111">Constant</span></span>  |<span data-ttu-id="17bbf-112">值</span><span class="sxs-lookup"><span data-stu-id="17bbf-112">Value</span></span>  |<span data-ttu-id="17bbf-113">描述</span><span class="sxs-lookup"><span data-stu-id="17bbf-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="17bbf-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="17bbf-114">0x8004101d</span></span> | <span data-ttu-id="17bbf-115">发生内部错误。</span><span class="sxs-lookup"><span data-stu-id="17bbf-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="17bbf-116">0</span><span class="sxs-lookup"><span data-stu-id="17bbf-116">0</span></span> | <span data-ttu-id="17bbf-117">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="17bbf-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="17bbf-118">备注</span><span class="sxs-lookup"><span data-stu-id="17bbf-118">Remarks</span></span>

<span data-ttu-id="17bbf-119">此函数包装对[IWbemClassObject：： EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)方法的调用。</span><span class="sxs-lookup"><span data-stu-id="17bbf-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="17bbf-120">调用方使用[BeginMethodEnumeration 函数](beginmethodenumeration.md)开始枚举序列，然后调用[NextMethod 函数](nextmethod.md )，直到该方法返回`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="17bbf-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="17bbf-121">调用方可以通过调用`EndMethodEnumeration`来完成序列。</span><span class="sxs-lookup"><span data-stu-id="17bbf-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="17bbf-122">调用方可以在任何时间通过调用`EndMethodEnumeration`来提前终止枚举。</span><span class="sxs-lookup"><span data-stu-id="17bbf-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="17bbf-123">要求</span><span class="sxs-lookup"><span data-stu-id="17bbf-123">Requirements</span></span>  
 <span data-ttu-id="17bbf-124">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="17bbf-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="17bbf-125">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="17bbf-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="17bbf-126">**.NET Framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="17bbf-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="17bbf-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="17bbf-127">See also</span></span>

- [<span data-ttu-id="17bbf-128">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="17bbf-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
