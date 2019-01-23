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
ms.openlocfilehash: b7cba6db456d15ebcfedb305343962b37e5ca1a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491956"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="fd928-102">ICorThreadpool::CorDeleteTimer 方法</span><span class="sxs-lookup"><span data-stu-id="fd928-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="fd928-103">此方法支持 .NET Framework 基础结构，但不适合直接在代码中使用。</span><span class="sxs-lookup"><span data-stu-id="fd928-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd928-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd928-104">Syntax</span></span>  
  
```  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="fd928-105">要求</span><span class="sxs-lookup"><span data-stu-id="fd928-105">Requirements</span></span>  
 <span data-ttu-id="fd928-106">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd928-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd928-107">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="fd928-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fd928-108">**库：** 包含为 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="fd928-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd928-109">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd928-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd928-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd928-110">See also</span></span>
- [<span data-ttu-id="fd928-111">ICorThreadpool 接口</span><span class="sxs-lookup"><span data-stu-id="fd928-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
