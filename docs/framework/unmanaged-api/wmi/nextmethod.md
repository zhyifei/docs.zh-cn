---
title: NextMethod 函数 （非托管 API 参考）
description: NextMethod 函数检索枚举中的下一步方法。
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b3667f7371131a4c1394ba5ca619d1f605c89ce
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59190881"
---
# <a name="nextmethod-function"></a><span data-ttu-id="4a9b9-103">NextMethod 函数</span><span class="sxs-lookup"><span data-stu-id="4a9b9-103">NextMethod function</span></span>
<span data-ttu-id="4a9b9-104">检索到的调用开始枚举中的下一步方法[BeginMethodEnumeration](beginmethodenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="4a9b9-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a9b9-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="4a9b9-106">参数</span><span class="sxs-lookup"><span data-stu-id="4a9b9-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4a9b9-107">[in]此参数是未使用。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4a9b9-108">[in]一个指向[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)实例。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="4a9b9-109">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-109">[in] Reserved.</span></span> <span data-ttu-id="4a9b9-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="4a9b9-111">[out]一个指针，它指向`null`之前调用。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="4a9b9-112">当该函数返回时，一个新的地址`BSTR`，其中包含方法名称。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="4a9b9-113">[out]接收指向指针的指针[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ，其中包含`in`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="4a9b9-114">[out]接收指向指针的指针[IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ，其中包含`out`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="4a9b9-115">返回值</span><span class="sxs-lookup"><span data-stu-id="4a9b9-115">Return value</span></span>

<span data-ttu-id="4a9b9-116">此函数返回以下值中定义*WbemCli.h*标头文件，也可以在定义它们为常量在代码中：</span><span class="sxs-lookup"><span data-stu-id="4a9b9-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4a9b9-117">返回的常量</span><span class="sxs-lookup"><span data-stu-id="4a9b9-117">Constant</span></span>  |<span data-ttu-id="4a9b9-118">“值”</span><span class="sxs-lookup"><span data-stu-id="4a9b9-118">Value</span></span>  |<span data-ttu-id="4a9b9-119">描述</span><span class="sxs-lookup"><span data-stu-id="4a9b9-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="4a9b9-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="4a9b9-120">0x8004101d</span></span> | <span data-ttu-id="4a9b9-121">出现不需要调用[ `BeginEnumeration` ](beginenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4a9b9-122">0</span><span class="sxs-lookup"><span data-stu-id="4a9b9-122">0</span></span> | <span data-ttu-id="4a9b9-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="4a9b9-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="4a9b9-124">0x40005</span></span> | <span data-ttu-id="4a9b9-125">枚举中没有更多属性。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="4a9b9-126">备注</span><span class="sxs-lookup"><span data-stu-id="4a9b9-126">Remarks</span></span>

<span data-ttu-id="4a9b9-127">此函数包装对的调用[IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)方法。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="4a9b9-128">调用方通过调用开始枚举序列[BeginMethodEnumeration](beginmethodenumeration.md)函数，并随后调用 [NextMethod] 函数，直到该函数将返回`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="4a9b9-129">（可选） 调用方通过调用完成序列[EndMethodEnumeration](endmethodenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="4a9b9-130">调用方可能会提前终止枚举，通过调用[EndMethodEnumeration](endmethodenumeration.md)在任何时间。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="4a9b9-131">示例</span><span class="sxs-lookup"><span data-stu-id="4a9b9-131">Example</span></span>

<span data-ttu-id="4a9b9-132">有关C++的示例中，请参阅[IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod)方法。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4a9b9-133">要求</span><span class="sxs-lookup"><span data-stu-id="4a9b9-133">Requirements</span></span>  
 <span data-ttu-id="4a9b9-134">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a9b9-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a9b9-135">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4a9b9-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="4a9b9-136">**.NET Framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4a9b9-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a9b9-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a9b9-137">See also</span></span>

- [<span data-ttu-id="4a9b9-138">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="4a9b9-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
