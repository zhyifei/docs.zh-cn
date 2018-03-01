---
title: "LPTHREAD_START_ROUTINE 函数指针"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- LPTHREAD_START_ROUTINE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- LPTHREAD_START_ROUTINE
helpviewer_keywords:
- LPTHREAD_START_ROUTINE function pointer [.NET Framework hosting]
ms.assetid: 7b9b93b0-fe92-42ba-8693-701168a29dde
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d28cdbfa2cb6c2c1f6b730e34b623a621119bc3a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="lpthreadstartroutine-function-pointer"></a><span data-ttu-id="2b5c3-102">LPTHREAD_START_ROUTINE 函数指针</span><span class="sxs-lookup"><span data-stu-id="2b5c3-102">LPTHREAD_START_ROUTINE Function Pointer</span></span>
<span data-ttu-id="2b5c3-103">指向通知线程已开始执行的主机的函数。</span><span class="sxs-lookup"><span data-stu-id="2b5c3-103">Points to a function that notifies the host that a thread has started to execute.</span></span>  
  
 <span data-ttu-id="2b5c3-104">中已弃用此函数指针[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="2b5c3-104">This function pointer has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b5c3-105">语法</span><span class="sxs-lookup"><span data-stu-id="2b5c3-105">Syntax</span></span>  
  
```  
typedef DWORD (__stdcall *LPTHREAD_START_ROUTINE) (  
    [in] LPVOID lpThreadParameter  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2b5c3-106">参数</span><span class="sxs-lookup"><span data-stu-id="2b5c3-106">Parameters</span></span>  
 `lpThreadParameter`  
 <span data-ttu-id="2b5c3-107">[in]指向已开始执行的代码的指针。</span><span class="sxs-lookup"><span data-stu-id="2b5c3-107">[in] A pointer to the code that has started executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b5c3-108">备注</span><span class="sxs-lookup"><span data-stu-id="2b5c3-108">Remarks</span></span>  
 <span data-ttu-id="2b5c3-109">到函数`LPTHREAD_START_ROUTINE`点是一个回调函数，必须在承载应用程序的编写器实现。</span><span class="sxs-lookup"><span data-stu-id="2b5c3-109">The function to which `LPTHREAD_START_ROUTINE` points is a callback function and must be implemented by the writer of the hosting application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b5c3-110">惠?</span><span class="sxs-lookup"><span data-stu-id="2b5c3-110">Requirements</span></span>  
 <span data-ttu-id="2b5c3-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b5c3-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b5c3-112">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2b5c3-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b5c3-113">**库：** MSCorWks.dll</span><span class="sxs-lookup"><span data-stu-id="2b5c3-113">**Library:** MSCorWks.dll</span></span>  
  
 <span data-ttu-id="2b5c3-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b5c3-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b5c3-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="2b5c3-115">See Also</span></span>  
 [<span data-ttu-id="2b5c3-116">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="2b5c3-116">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
