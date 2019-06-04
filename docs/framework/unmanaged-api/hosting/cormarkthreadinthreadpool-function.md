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
ms.openlocfilehash: f0200ad36490efc546daebfa93904676b0af7684
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490524"
---
# <a name="cormarkthreadinthreadpool-function"></a><span data-ttu-id="4d26d-102">CorMarkThreadInThreadPool 函数</span><span class="sxs-lookup"><span data-stu-id="4d26d-102">CorMarkThreadInThreadPool Function</span></span>
<span data-ttu-id="4d26d-103">将标记为托管代码的执行当前正在执行的线程池线程。</span><span class="sxs-lookup"><span data-stu-id="4d26d-103">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="4d26d-104">从.NET Framework 2.0 版开始，此函数没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="4d26d-104">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="4d26d-105">它不是必需的并可以从你的代码。</span><span class="sxs-lookup"><span data-stu-id="4d26d-105">It is not required, and can be removed from your code.</span></span> <span data-ttu-id="4d26d-106">.NET Framework 4 中已弃用此函数。</span><span class="sxs-lookup"><span data-stu-id="4d26d-106">This function is deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d26d-107">语法</span><span class="sxs-lookup"><span data-stu-id="4d26d-107">Syntax</span></span>  
  
```  
void CorMarkThreadInThreadPool ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4d26d-108">要求</span><span class="sxs-lookup"><span data-stu-id="4d26d-108">Requirements</span></span>  
 <span data-ttu-id="4d26d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d26d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d26d-110">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4d26d-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d26d-111">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4d26d-111">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d26d-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d26d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d26d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d26d-113">See also</span></span>

- [<span data-ttu-id="4d26d-114">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="4d26d-114">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
