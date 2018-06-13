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
ms.openlocfilehash: 91e1697366bd3ee95fd040ee261d68417a8125e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423603"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="3062d-102">ICorPublishProcess::GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="3062d-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="3062d-103">获取此进程的操作系统识别符。</span><span class="sxs-lookup"><span data-stu-id="3062d-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3062d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3062d-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3062d-105">参数</span><span class="sxs-lookup"><span data-stu-id="3062d-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="3062d-106">[out]表示此进程的标识符的指针[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="3062d-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3062d-107">要求</span><span class="sxs-lookup"><span data-stu-id="3062d-107">Requirements</span></span>  
 <span data-ttu-id="3062d-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3062d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3062d-109">**标头：** CorPub.idl、 CorPub.h</span><span class="sxs-lookup"><span data-stu-id="3062d-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3062d-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3062d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3062d-111">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3062d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3062d-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3062d-112">See Also</span></span>  
 [<span data-ttu-id="3062d-113">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="3062d-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
