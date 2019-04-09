---
title: CorMarkThreadInThreadPool 函数
ms.date: 03/30/2017
api_name:
- CorMarkThreadInThreadPool
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- CorMarkThreadInThreadPool
helpviewer_keywords:
- CorMarkThreadInThreadPool function [.NET Framework hosting]
ms.assetid: 3f958d41-e82e-4ec3-ae6f-16c7b3b31e3e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a39b0f2546d84cf24a58d5367c87d0a862aead93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085072"
---
# <a name="cormarkthreadinthreadpool-function"></a><span data-ttu-id="d5e8c-102">CorMarkThreadInThreadPool 函数</span><span class="sxs-lookup"><span data-stu-id="d5e8c-102">CorMarkThreadInThreadPool Function</span></span>
<span data-ttu-id="d5e8c-103">将标记为托管代码的执行当前正在执行的线程池线程。</span><span class="sxs-lookup"><span data-stu-id="d5e8c-103">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="d5e8c-104">从.NET Framework 2.0 版开始，此函数没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="d5e8c-104">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="d5e8c-105">它不是必需的并可以从你的代码。</span><span class="sxs-lookup"><span data-stu-id="d5e8c-105">It is not required, and can be removed from your code.</span></span> <span data-ttu-id="d5e8c-106">此函数已弃用在[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5e8c-106">This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5e8c-107">语法</span><span class="sxs-lookup"><span data-stu-id="d5e8c-107">Syntax</span></span>  
  
```  
void CorMarkThreadInThreadPool ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d5e8c-108">要求</span><span class="sxs-lookup"><span data-stu-id="d5e8c-108">Requirements</span></span>  
 <span data-ttu-id="d5e8c-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5e8c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5e8c-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5e8c-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5e8c-111">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5e8c-111">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d5e8c-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="d5e8c-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d5e8c-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d5e8c-113">See also</span></span>

- [<span data-ttu-id="d5e8c-114">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="d5e8c-114">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
