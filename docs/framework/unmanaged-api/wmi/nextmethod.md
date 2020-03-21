---
title: NextMethod 函数（非托管 API 引用）
description: NextMethod 函数检索枚举中的下一个方法。
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174922"
---
# <a name="nextmethod-function"></a><span data-ttu-id="00a47-103">NextMethod 函数</span><span class="sxs-lookup"><span data-stu-id="00a47-103">NextMethod function</span></span>
<span data-ttu-id="00a47-104">检索枚举中的下一个方法，该方法以调用[BeginMethodEa）](beginmethodenumeration.md)开头。</span><span class="sxs-lookup"><span data-stu-id="00a47-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="00a47-105">语法</span><span class="sxs-lookup"><span data-stu-id="00a47-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="00a47-106">parameters</span><span class="sxs-lookup"><span data-stu-id="00a47-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="00a47-107">[在]此参数未使用。</span><span class="sxs-lookup"><span data-stu-id="00a47-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="00a47-108">[在]指向[IWbem ClassObject 实例](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针。</span><span class="sxs-lookup"><span data-stu-id="00a47-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="00a47-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="00a47-109">[in] Reserved.</span></span> <span data-ttu-id="00a47-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="00a47-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="00a47-111">[出]指向调用`null`之前的指针。</span><span class="sxs-lookup"><span data-stu-id="00a47-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="00a47-112">当函数返回时，包含方法名称的新地址`BSTR`。</span><span class="sxs-lookup"><span data-stu-id="00a47-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="00a47-113">[出]接收指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针的指针，其中包含方法的`in`参数。</span><span class="sxs-lookup"><span data-stu-id="00a47-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="00a47-114">[出]接收指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)的指针的指针，其中包含方法的`out`参数。</span><span class="sxs-lookup"><span data-stu-id="00a47-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="00a47-115">返回值</span><span class="sxs-lookup"><span data-stu-id="00a47-115">Return value</span></span>

<span data-ttu-id="00a47-116">此函数返回的以下值在*WbemCli.h*标头文件中定义，或者您可以在代码中将它们定义为常量：</span><span class="sxs-lookup"><span data-stu-id="00a47-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="00a47-117">一直</span><span class="sxs-lookup"><span data-stu-id="00a47-117">Constant</span></span>  |<span data-ttu-id="00a47-118">值</span><span class="sxs-lookup"><span data-stu-id="00a47-118">Value</span></span>  |<span data-ttu-id="00a47-119">说明</span><span class="sxs-lookup"><span data-stu-id="00a47-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="00a47-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="00a47-120">0x8004101d</span></span> | <span data-ttu-id="00a47-121">没有调用该[`BeginEnumeration`](beginenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="00a47-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="00a47-122">0</span><span class="sxs-lookup"><span data-stu-id="00a47-122">0</span></span> | <span data-ttu-id="00a47-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="00a47-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="00a47-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="00a47-124">0x40005</span></span> | <span data-ttu-id="00a47-125">枚举中没有更多的属性。</span><span class="sxs-lookup"><span data-stu-id="00a47-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="00a47-126">备注</span><span class="sxs-lookup"><span data-stu-id="00a47-126">Remarks</span></span>

<span data-ttu-id="00a47-127">此函数包装对[IWbemClassObject：：NextMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)的调用。</span><span class="sxs-lookup"><span data-stu-id="00a47-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="00a47-128">调用方通过调用[BeginMethod 枚举](beginmethodenumeration.md)函数来开始枚举序列，然后调用 [NextMethod] 函数，直到函数返回`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="00a47-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="00a47-129">或者，调用方通过调用[EndMethod 枚举](endmethodenumeration.md)来完成序列。</span><span class="sxs-lookup"><span data-stu-id="00a47-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="00a47-130">调用方可以随时调用[EndMethodEa 枚举](endmethodenumeration.md)，从而提前终止枚举。</span><span class="sxs-lookup"><span data-stu-id="00a47-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="00a47-131">示例</span><span class="sxs-lookup"><span data-stu-id="00a47-131">Example</span></span>

<span data-ttu-id="00a47-132">有关C++示例，请参阅[IWbemClassObject：：NextMethod 方法](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)。</span><span class="sxs-lookup"><span data-stu-id="00a47-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="00a47-133">要求</span><span class="sxs-lookup"><span data-stu-id="00a47-133">Requirements</span></span>  
 <span data-ttu-id="00a47-134">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="00a47-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00a47-135">**标题：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="00a47-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="00a47-136">**.NET 框架版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="00a47-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00a47-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00a47-137">See also</span></span>

- [<span data-ttu-id="00a47-138">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="00a47-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
