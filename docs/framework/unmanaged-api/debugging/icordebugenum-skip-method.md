---
title: ICorDebugEnum::Skip 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Skip
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Skip
helpviewer_keywords:
- ICorDebugEnum::Skip method [.NET Framework debugging]
- Skip method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: e925d88a-67a5-4f76-88b8-09cedeed0232
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb651aa394022182b6730d57942199f570508436
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56965888"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="85b3f-102">ICorDebugEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="85b3f-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="85b3f-103">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="85b3f-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85b3f-104">语法</span><span class="sxs-lookup"><span data-stu-id="85b3f-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85b3f-105">参数</span><span class="sxs-lookup"><span data-stu-id="85b3f-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="85b3f-106">[in]要向前移动游标的项的数目。</span><span class="sxs-lookup"><span data-stu-id="85b3f-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85b3f-107">要求</span><span class="sxs-lookup"><span data-stu-id="85b3f-107">Requirements</span></span>  
 <span data-ttu-id="85b3f-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="85b3f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85b3f-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85b3f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85b3f-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85b3f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85b3f-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85b3f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85b3f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="85b3f-112">See also</span></span>
- [<span data-ttu-id="85b3f-113">ICorDebugEnum 接口</span><span class="sxs-lookup"><span data-stu-id="85b3f-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
