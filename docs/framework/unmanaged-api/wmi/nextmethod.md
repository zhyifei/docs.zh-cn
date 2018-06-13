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
ms.openlocfilehash: cd4559663194cb845fb0cc040e1f6739e38caa0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461138"
---
# <a name="nextmethod-function"></a><span data-ttu-id="26fa8-103">NextMethod 函数</span><span class="sxs-lookup"><span data-stu-id="26fa8-103">NextMethod function</span></span>
<span data-ttu-id="26fa8-104">检索到的调用开始枚举中的下一步方法[BeginMethodEnumeration](beginmethodenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="26fa8-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="26fa8-105">语法</span><span class="sxs-lookup"><span data-stu-id="26fa8-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="26fa8-106">参数</span><span class="sxs-lookup"><span data-stu-id="26fa8-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="26fa8-107">[in]未使用此参数。</span><span class="sxs-lookup"><span data-stu-id="26fa8-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="26fa8-108">[in]指向的指针[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)实例。</span><span class="sxs-lookup"><span data-stu-id="26fa8-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="26fa8-109">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="26fa8-109">[in] Reserved.</span></span> <span data-ttu-id="26fa8-110">此参数必须为 0。</span><span class="sxs-lookup"><span data-stu-id="26fa8-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="26fa8-111">[out]一个指针，它指向`null`之前调用。</span><span class="sxs-lookup"><span data-stu-id="26fa8-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="26fa8-112">当函数返回时，新的地址`BSTR`包含方法的名称。</span><span class="sxs-lookup"><span data-stu-id="26fa8-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="26fa8-113">[out]一个指针，它接收一个指针，到[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)包含`in`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="26fa8-113">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="26fa8-114">[out]一个指针，它接收一个指针，到[IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx)包含`out`方法的参数。</span><span class="sxs-lookup"><span data-stu-id="26fa8-114">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="26fa8-115">返回值</span><span class="sxs-lookup"><span data-stu-id="26fa8-115">Return value</span></span>

<span data-ttu-id="26fa8-116">此函数返回以下值中定义*WbemCli.h*标头文件，或者你可以定义它们常量作为在代码中：</span><span class="sxs-lookup"><span data-stu-id="26fa8-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="26fa8-117">返回的常量</span><span class="sxs-lookup"><span data-stu-id="26fa8-117">Constant</span></span>  |<span data-ttu-id="26fa8-118">值</span><span class="sxs-lookup"><span data-stu-id="26fa8-118">Value</span></span>  |<span data-ttu-id="26fa8-119">描述</span><span class="sxs-lookup"><span data-stu-id="26fa8-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="26fa8-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="26fa8-120">0x8004101d</span></span> | <span data-ttu-id="26fa8-121">没有不需要调用[ `BeginEnumeration` ](beginenumeration.md)函数。</span><span class="sxs-lookup"><span data-stu-id="26fa8-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="26fa8-122">0</span><span class="sxs-lookup"><span data-stu-id="26fa8-122">0</span></span> | <span data-ttu-id="26fa8-123">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="26fa8-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="26fa8-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="26fa8-124">0x40005</span></span> | <span data-ttu-id="26fa8-125">枚举中没有更多属性。</span><span class="sxs-lookup"><span data-stu-id="26fa8-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="26fa8-126">备注</span><span class="sxs-lookup"><span data-stu-id="26fa8-126">Remarks</span></span>

<span data-ttu-id="26fa8-127">此函数包装对的调用[IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="26fa8-127">This function wraps a call to the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="26fa8-128">调用方通过调用开始枚举序列[BeginMethodEnumeration](beginmethodenumeration.md)函数，并随后调用 [NextMethod] 函数，直到函数返回`WBEM_S_NO_MORE_DATA`。</span><span class="sxs-lookup"><span data-stu-id="26fa8-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="26fa8-129">调用方 （可选） 通过调用完成序列[EndMethodEnumeration](endmethodenumeration.md)。</span><span class="sxs-lookup"><span data-stu-id="26fa8-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="26fa8-130">调用方可能较早终止枚举，通过调用[EndMethodEnumeration](endmethodenumeration.md)在任何时间。</span><span class="sxs-lookup"><span data-stu-id="26fa8-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="26fa8-131">示例</span><span class="sxs-lookup"><span data-stu-id="26fa8-131">Example</span></span>

<span data-ttu-id="26fa8-132">有关 c + + 示例，请参阅[IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx)方法。</span><span class="sxs-lookup"><span data-stu-id="26fa8-132">For a C++ example, see the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="26fa8-133">要求</span><span class="sxs-lookup"><span data-stu-id="26fa8-133">Requirements</span></span>  
 <span data-ttu-id="26fa8-134">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26fa8-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26fa8-135">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="26fa8-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="26fa8-136">**.NET framework 版本：** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="26fa8-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26fa8-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="26fa8-137">See also</span></span>  
[<span data-ttu-id="26fa8-138">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="26fa8-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
