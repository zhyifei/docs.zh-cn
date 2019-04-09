---
title: ResetSecurity 函数 （非托管 API 参考）
description: ResetSecurity 函数将分配给当前线程的模拟令牌。
ms.date: 11/06/2017
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
ms.openlocfilehash: e937690c184d810549e8ab11ef1fc2273a45c5f5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115123"
---
# <a name="resetsecurity-function"></a><span data-ttu-id="2d0c8-103">ResetSecurity 函数</span><span class="sxs-lookup"><span data-stu-id="2d0c8-103">ResetSecurity function</span></span>
<span data-ttu-id="2d0c8-104">将提供的模拟令牌分配给当前线程。</span><span class="sxs-lookup"><span data-stu-id="2d0c8-104">Assigns the supplied impersonation token to the current thread.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="2d0c8-105">语法</span><span class="sxs-lookup"><span data-stu-id="2d0c8-105">Syntax</span></span>  
  
```  
HRESULT ResetSecurity (
   [in] HANDLE token
); 
```  

## <a name="parameters"></a><span data-ttu-id="2d0c8-106">参数</span><span class="sxs-lookup"><span data-stu-id="2d0c8-106">Parameters</span></span>

`token`  
<span data-ttu-id="2d0c8-107">[in]要与当前线程关联的模拟令牌。</span><span class="sxs-lookup"><span data-stu-id="2d0c8-107">[in] The impersonation token to associate with the current thread.</span></span> <span data-ttu-id="2d0c8-108">其值可为 `null`。</span><span class="sxs-lookup"><span data-stu-id="2d0c8-108">Its value can be `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="2d0c8-109">返回值</span><span class="sxs-lookup"><span data-stu-id="2d0c8-109">Return value</span></span>

<span data-ttu-id="2d0c8-110">如果函数成功，返回值是`S_OK`(0)。</span><span class="sxs-lookup"><span data-stu-id="2d0c8-110">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="2d0c8-111">如果函数失败，返回值是一个非零错误代码。</span><span class="sxs-lookup"><span data-stu-id="2d0c8-111">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="2d0c8-112">若要获得扩展错误信息，请调用[GetErrorInfo](geterrorinfo.md)函数。</span><span class="sxs-lookup"><span data-stu-id="2d0c8-112">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="2d0c8-113">要求</span><span class="sxs-lookup"><span data-stu-id="2d0c8-113">Requirements</span></span>  
 <span data-ttu-id="2d0c8-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2d0c8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2d0c8-115">**标头：** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="2d0c8-115">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="2d0c8-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="2d0c8-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2d0c8-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="2d0c8-117">See also</span></span>

- [<span data-ttu-id="2d0c8-118">WMI 和性能计数器（非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="2d0c8-118">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
