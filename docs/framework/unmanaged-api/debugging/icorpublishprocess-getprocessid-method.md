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
ms.openlocfilehash: 6f3948e45b991e667ea90c7846ee0d6fd630c0db
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59165797"
---
# <a name="icorpublishprocessgetprocessid-method"></a><span data-ttu-id="cb758-102">ICorPublishProcess::GetProcessID 方法</span><span class="sxs-lookup"><span data-stu-id="cb758-102">ICorPublishProcess::GetProcessID Method</span></span>
<span data-ttu-id="cb758-103">获取此进程的操作系统识别符。</span><span class="sxs-lookup"><span data-stu-id="cb758-103">Gets the operating system identifier for this process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb758-104">语法</span><span class="sxs-lookup"><span data-stu-id="cb758-104">Syntax</span></span>  
  
```  
HRESULT GetProcessID (  
    [out] unsigned   *pid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cb758-105">参数</span><span class="sxs-lookup"><span data-stu-id="cb758-105">Parameters</span></span>  
 `pid`  
 <span data-ttu-id="cb758-106">[out]指向表示此进程的标识符[ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="cb758-106">[out] A pointer to the identifier of the process represented by this [ICorPublishProcess](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md) object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb758-107">要求</span><span class="sxs-lookup"><span data-stu-id="cb758-107">Requirements</span></span>  
 <span data-ttu-id="cb758-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cb758-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb758-109">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cb758-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cb758-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb758-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cb758-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="cb758-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb758-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb758-112">See also</span></span>

- [<span data-ttu-id="cb758-113">ICorPublishProcess 接口</span><span class="sxs-lookup"><span data-stu-id="cb758-113">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)
