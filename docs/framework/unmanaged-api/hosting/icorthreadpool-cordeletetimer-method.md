---
title: ICorThreadpool::CorDeleteTimer 方法
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 098c23dd0ddff4342aa4cefbaa4e149ed95a1cb3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59178342"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="38be5-102">ICorThreadpool::CorDeleteTimer 方法</span><span class="sxs-lookup"><span data-stu-id="38be5-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="38be5-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="38be5-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38be5-104">语法</span><span class="sxs-lookup"><span data-stu-id="38be5-104">Syntax</span></span>  
  
```  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="38be5-105">要求</span><span class="sxs-lookup"><span data-stu-id="38be5-105">Requirements</span></span>  
 <span data-ttu-id="38be5-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38be5-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38be5-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="38be5-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="38be5-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="38be5-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="38be5-109">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="38be5-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="38be5-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="38be5-110">See also</span></span>

- [<span data-ttu-id="38be5-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="38be5-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
