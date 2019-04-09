---
title: ICorPublishEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorPublishEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishEnum::Skip
helpviewer_keywords:
- ICorPublishEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 1680ec06-4ab0-447e-93ad-cdb8693fde5c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a98892964eb21746580e9115f86fd1be0832d9f2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59082036"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="cfc86-102">ICorPublishEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="cfc86-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="cfc86-103">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="cfc86-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfc86-104">语法</span><span class="sxs-lookup"><span data-stu-id="cfc86-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cfc86-105">参数</span><span class="sxs-lookup"><span data-stu-id="cfc86-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="cfc86-106">[in]要向前移动游标的项的数目。</span><span class="sxs-lookup"><span data-stu-id="cfc86-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cfc86-107">要求</span><span class="sxs-lookup"><span data-stu-id="cfc86-107">Requirements</span></span>  
 <span data-ttu-id="cfc86-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="cfc86-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfc86-109">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="cfc86-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="cfc86-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cfc86-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cfc86-111">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="cfc86-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cfc86-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="cfc86-112">See also</span></span>

- [<span data-ttu-id="cfc86-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="cfc86-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
