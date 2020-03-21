---
title: 结束方法枚举函数（非托管 API 引用）
description: EndMethodEee）计数函数终止方法枚举序列。
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
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175000"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="e6393-103">EndMethodEnumeration 函数</span><span class="sxs-lookup"><span data-stu-id="e6393-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="e6393-104">终止以调用[BeginMethodEee 计算函数](beginmethodenumeration.md)开始的枚举序列。</span><span class="sxs-lookup"><span data-stu-id="e6393-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e6393-105">语法</span><span class="sxs-lookup"><span data-stu-id="e6393-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="e6393-106">parameters</span><span class="sxs-lookup"><span data-stu-id="e6393-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e6393-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="e6393-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e6393-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="e6393-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="e6393-109">返回值</span><span class="sxs-lookup"><span data-stu-id="e6393-109">Return value</span></span>

<span data-ttu-id="e6393-110">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="e6393-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e6393-111">一直</span><span class="sxs-lookup"><span data-stu-id="e6393-111">Constant</span></span>  |<span data-ttu-id="e6393-112">值</span><span class="sxs-lookup"><span data-stu-id="e6393-112">Value</span></span>  |<span data-ttu-id="e6393-113">说明</span><span class="sxs-lookup"><span data-stu-id="e6393-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="e6393-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="e6393-114">0x8004101d</span></span> | <span data-ttu-id="e6393-115">发生了内部错误。</span><span class="sxs-lookup"><span data-stu-id="e6393-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e6393-116">0</span><span class="sxs-lookup"><span data-stu-id="e6393-116">0</span></span> | <span data-ttu-id="e6393-117">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="e6393-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e6393-118">备注</span><span class="sxs-lookup"><span data-stu-id="e6393-118">Remarks</span></span>

<span data-ttu-id="e6393-119">此函数将调用包起来到[IWbemClassObject：：结束方法枚举](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration)方法。</span><span class="sxs-lookup"><span data-stu-id="e6393-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="e6393-120">调用方使用[BeginMethodEee 枚举函数](beginmethodenumeration.md)开始枚举序列，然后调用[NextMethod 函数](nextmethod.md )，直到`WBEM_S_NO_MORE_DATA`方法返回 。</span><span class="sxs-lookup"><span data-stu-id="e6393-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="e6393-121">调用方通过调用`EndMethodEnumeration`完成序列。</span><span class="sxs-lookup"><span data-stu-id="e6393-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="e6393-122">调用方可能通过随时调用`EndMethodEnumeration`来提前终止枚举。</span><span class="sxs-lookup"><span data-stu-id="e6393-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6393-123">要求</span><span class="sxs-lookup"><span data-stu-id="e6393-123">Requirements</span></span>  
 <span data-ttu-id="e6393-124">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e6393-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6393-125">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e6393-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e6393-126">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e6393-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6393-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6393-127">See also</span></span>

- [<span data-ttu-id="e6393-128">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="e6393-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
