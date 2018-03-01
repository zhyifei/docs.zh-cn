---
title: "VerifyClientKey 函数 （非托管 API 参考）"
description: "VerifyClientKey 函数会确保客户端密钥都有正确的安全性。"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ada878ff8bc430ab2a2d48cac13a81b1f64d39f6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="verifyclientkey-function"></a><span data-ttu-id="37b9f-103">VerifyClientKey 函数</span><span class="sxs-lookup"><span data-stu-id="37b9f-103">VerifyClientKey function</span></span>
<span data-ttu-id="37b9f-104">确保客户端密钥具有正确的安全性。</span><span class="sxs-lookup"><span data-stu-id="37b9f-104">Ensures that the client key has the correct security.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="37b9f-105">语法</span><span class="sxs-lookup"><span data-stu-id="37b9f-105">Syntax</span></span>  
  
```  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a><span data-ttu-id="37b9f-106">返回值</span><span class="sxs-lookup"><span data-stu-id="37b9f-106">Return value</span></span>

<span data-ttu-id="37b9f-107">如果函数成功，则返回值是`ERROR_SUCCESS`(0)。</span><span class="sxs-lookup"><span data-stu-id="37b9f-107">If the function succeeds, the return value is `ERROR_SUCCESS` (0).</span></span>

<span data-ttu-id="37b9f-108">如果函数失败，返回值是一个非零错误代码中定义*WinError.h*。</span><span class="sxs-lookup"><span data-stu-id="37b9f-108">If the function fails, the return value is a non-zero error code defined in *WinError.h*.</span></span>

## <a name="requirements"></a><span data-ttu-id="37b9f-109">惠?</span><span class="sxs-lookup"><span data-stu-id="37b9f-109">Requirements</span></span>  
 <span data-ttu-id="37b9f-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="37b9f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37b9f-111">**标头：** WMINet_Utils.def</span><span class="sxs-lookup"><span data-stu-id="37b9f-111">**Header:** WMINet_Utils.def</span></span>  
  
 <span data-ttu-id="37b9f-112">**.NET framework 版本：**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="37b9f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37b9f-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="37b9f-113">See also</span></span>  
[<span data-ttu-id="37b9f-114">WMI 和性能计数器 （非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="37b9f-114">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
