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
ms.openlocfilehash: 15ce6b589beb6c8b30ff4e8b16440c8110cc466b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136896"
---
# <a name="cormarkthreadinthreadpool-function"></a><span data-ttu-id="948eb-102">CorMarkThreadInThreadPool 函数</span><span class="sxs-lookup"><span data-stu-id="948eb-102">CorMarkThreadInThreadPool Function</span></span>
<span data-ttu-id="948eb-103">标记当前正在执行的线程池线程以执行托管代码。</span><span class="sxs-lookup"><span data-stu-id="948eb-103">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="948eb-104">从 .NET Framework 版本2.0 开始，此函数不起作用。</span><span class="sxs-lookup"><span data-stu-id="948eb-104">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="948eb-105">这不是必需的，并且可以从代码中删除。</span><span class="sxs-lookup"><span data-stu-id="948eb-105">It is not required, and can be removed from your code.</span></span> <span data-ttu-id="948eb-106">此函数在 .NET Framework 4 中已弃用。</span><span class="sxs-lookup"><span data-stu-id="948eb-106">This function is deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="948eb-107">语法</span><span class="sxs-lookup"><span data-stu-id="948eb-107">Syntax</span></span>  
  
```cpp  
void CorMarkThreadInThreadPool ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="948eb-108">要求</span><span class="sxs-lookup"><span data-stu-id="948eb-108">Requirements</span></span>  
 <span data-ttu-id="948eb-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="948eb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="948eb-110">**标头：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="948eb-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="948eb-111">**库：** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="948eb-111">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="948eb-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="948eb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="948eb-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="948eb-113">See also</span></span>

- [<span data-ttu-id="948eb-114">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="948eb-114">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
