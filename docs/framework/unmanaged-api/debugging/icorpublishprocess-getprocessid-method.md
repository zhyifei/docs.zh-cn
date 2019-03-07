---
title: ICorPublishProcess::GetProcessID 方法
ms.date: 03/30/2017
api_name:
- ICorPublishProcess.GetProcessID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess::GetProcessID
helpviewer_keywords:
- ICorPublishProcess::GetProcessID method [.NET Framework debugging]
- GetProcessID method [.NET Framework debugging]
ms.assetid: f31185e0-f01d-463a-b392-42163e39bfe9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 61c67e074fc32098fa0d8326ea2f0ecfb1efa952
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57471762"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="db396-102">ICorPublishProcess::GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="db396-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="db396-103">获取此进程的操作系统识别符。</span><span class="sxs-lookup"><span data-stu-id="db396-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db396-104">语法</span><span class="sxs-lookup"><span data-stu-id="db396-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db396-105">参数</span><span class="sxs-lookup"><span data-stu-id="db396-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="db396-106">[out]指向表示此进程的标识符[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="db396-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db396-107">要求</span><span class="sxs-lookup"><span data-stu-id="db396-107">Requirements</span></span>  
 <span data-ttu-id="db396-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="db396-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db396-109">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="db396-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="db396-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db396-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db396-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db396-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db396-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="db396-112">See also</span></span>
- [<span data-ttu-id="db396-113">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="db396-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
