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
ms.openlocfilehash: 2f56792bbdf11c099205efd0cb35e3bf02d67632
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466604"
---
# <a name="icorpublishenumskip-method"></a><span data-ttu-id="6f7e7-102">ICorPublishEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="6f7e7-102">ICorPublishEnum::Skip Method</span></span>
<span data-ttu-id="6f7e7-103">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="6f7e7-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f7e7-104">语法</span><span class="sxs-lookup"><span data-stu-id="6f7e7-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG   celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f7e7-105">参数</span><span class="sxs-lookup"><span data-stu-id="6f7e7-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="6f7e7-106">[in]要向前移动游标的项的数目。</span><span class="sxs-lookup"><span data-stu-id="6f7e7-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f7e7-107">要求</span><span class="sxs-lookup"><span data-stu-id="6f7e7-107">Requirements</span></span>  
 <span data-ttu-id="6f7e7-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6f7e7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f7e7-109">**标头：** CorPub.idl CorPub.h</span><span class="sxs-lookup"><span data-stu-id="6f7e7-109">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="6f7e7-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f7e7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f7e7-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f7e7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7e7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f7e7-112">See also</span></span>
- [<span data-ttu-id="6f7e7-113">ICorPublishEnum 接口</span><span class="sxs-lookup"><span data-stu-id="6f7e7-113">ICorPublishEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishenum-interface.md)
