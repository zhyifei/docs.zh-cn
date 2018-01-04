---
title: "SetSecurity 函数 （非托管 API 参考）"
description: "SetSecurity 函数检索当前线程的模拟令牌。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: SetSecurity
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: SetSecurity
helpviewer_keywords: SetSecurity function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: abb716d64bde9b298203e54d862ff4f1b2bcd170
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="setsecurity-function"></a><span data-ttu-id="9bfd5-103">SetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="9bfd5-103">SetSecurity function</span></span>
<span data-ttu-id="9bfd5-104">检索与当前线程关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-104">Retrieves the impersonation token associated with the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="9bfd5-105">语法</span><span class="sxs-lookup"><span data-stu-id="9bfd5-105">Syntax</span></span>  
  
```  
HRESULT SetSecurity (
   [out] boolean* pNeedToReset, 
   [out] HANDLE* pCurrentThreadToken
); 
```  

## <a name="parameters"></a><span data-ttu-id="9bfd5-106">参数</span><span class="sxs-lookup"><span data-stu-id="9bfd5-106">Parameters</span></span>

<span data-ttu-id="9bfd5-107">`pNeedToReset`[out]当函数返回时，包含指向的`boolean`，该值指示令牌是否应该重置通过调用[ResetSecurity](resetsecurity.md)函数。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-107">`pNeedToReset` [out] When the function returns, contains a pointer to a `boolean` that indicates whether the token should be reset by calling the [ResetSecurity](resetsecurity.md) function.</span></span>  

`token`  
<span data-ttu-id="9bfd5-108">[out]当函数返回时，包含与当前线程关联的模拟令牌的句柄的指针。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-108">[out] When the function returns, contains a pointer to the handle of the impersonation token associated with the current thread.</span></span> <span data-ttu-id="9bfd5-109">其值可以是`null`是否没有与当前线程关联的标记。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-109">Its value can be `null` if there is no token associated with the current thread.</span></span> 

## <a name="return-value"></a><span data-ttu-id="9bfd5-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9bfd5-110">Return value</span></span>

<span data-ttu-id="9bfd5-111">如果函数成功，则返回值是`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="9bfd5-112">如果函数失败，返回值将为非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="9bfd5-113">若要获得扩展的错误信息，调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="9bfd5-114">惠?</span><span class="sxs-lookup"><span data-stu-id="9bfd5-114">Requirements</span></span>  
 <span data-ttu-id="9bfd5-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9bfd5-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9bfd5-116">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="9bfd5-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9bfd5-117">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9bfd5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9bfd5-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="9bfd5-118">See also</span></span>  
[<span data-ttu-id="9bfd5-119">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="9bfd5-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
