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
ms.openlocfilehash: 1e2d7a344cabb1ab816e4fe696ebb47276397ec3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61774551"
---
# <a name="icordebugenumskip-method"></a><span data-ttu-id="2c55c-102">ICorDebugEnum::Skip 方法</span><span class="sxs-lookup"><span data-stu-id="2c55c-102">ICorDebugEnum::Skip Method</span></span>
<span data-ttu-id="2c55c-103">将光标向前移动在枚举中指定数目的项。</span><span class="sxs-lookup"><span data-stu-id="2c55c-103">Moves the cursor forward in the enumeration by the specified number of items.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c55c-104">语法</span><span class="sxs-lookup"><span data-stu-id="2c55c-104">Syntax</span></span>  
  
```  
HRESULT Skip (  
    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c55c-105">参数</span><span class="sxs-lookup"><span data-stu-id="2c55c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2c55c-106">[in]要向前移动游标的项的数目。</span><span class="sxs-lookup"><span data-stu-id="2c55c-106">[in] The number of items by which to move the cursor forward.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c55c-107">要求</span><span class="sxs-lookup"><span data-stu-id="2c55c-107">Requirements</span></span>  
 <span data-ttu-id="2c55c-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c55c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c55c-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c55c-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c55c-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c55c-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c55c-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c55c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c55c-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c55c-112">See also</span></span>

- [<span data-ttu-id="2c55c-113">ICorDebugEnum 接口</span><span class="sxs-lookup"><span data-stu-id="2c55c-113">ICorDebugEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-interface1.md)
