---
title: "ResetSecurity 函数 （非托管 API 参考）"
description: "ResetSecurity 函数将模拟令牌分配给当前线程。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- ResetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- ResetSecurity
helpviewer_keywords:
- ResetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: bacee65633d25e705d978d3902a6804516a88bf4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="resetsecurity-function"></a><span data-ttu-id="160d1-103">ResetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="160d1-103">ResetSecurity function</span></span>
<span data-ttu-id="160d1-104">将提供的模拟令牌分配给当前线程。</span><span class="sxs-lookup"><span data-stu-id="160d1-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="160d1-105">语法</span><span class="sxs-lookup"><span data-stu-id="160d1-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="160d1-106">参数</span><span class="sxs-lookup"><span data-stu-id="160d1-106">Parameters</span></span>

`token`  
<span data-ttu-id="160d1-107">[in]要将与当前线程相关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="160d1-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="160d1-108">其值可为 `null`。</span><span class="sxs-lookup"><span data-stu-id="160d1-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="160d1-109">返回值</span><span class="sxs-lookup"><span data-stu-id="160d1-109">Return value</span></span>

<span data-ttu-id="160d1-110">如果函数成功，则返回值是`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="160d1-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="160d1-111">如果函数失败，返回值将为非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="160d1-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="160d1-112">若要获得扩展的错误信息，调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="160d1-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="160d1-113">惠?</span><span class="sxs-lookup"><span data-stu-id="160d1-113">Requirements</span></span>  
 <span data-ttu-id="160d1-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="160d1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="160d1-115">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="160d1-115">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="160d1-116">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="160d1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="160d1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="160d1-117">See also</span></span>  
[<span data-ttu-id="160d1-118">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="160d1-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
