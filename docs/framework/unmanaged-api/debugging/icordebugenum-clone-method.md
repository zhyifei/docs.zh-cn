---
title: ICorDebugEnum::Clone 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5d1226f64df379b5c40304221e9e66eebcdb17b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479228"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="f9b31-102">ICorDebugEnum::Clone 方法</span><span class="sxs-lookup"><span data-stu-id="f9b31-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="f9b31-103">创建此 ICorDebugEnum 对象的副本。</span><span class="sxs-lookup"><span data-stu-id="f9b31-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9b31-104">语法</span><span class="sxs-lookup"><span data-stu-id="f9b31-104">Syntax</span></span>  
  
```  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9b31-105">参数</span><span class="sxs-lookup"><span data-stu-id="f9b31-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="f9b31-106">[out]指向的地址的指针`ICorDebugEnum`对象，它是一份`ICorDebugEnum`对象。</span><span class="sxs-lookup"><span data-stu-id="f9b31-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9b31-107">要求</span><span class="sxs-lookup"><span data-stu-id="f9b31-107">Requirements</span></span>  
 <span data-ttu-id="f9b31-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f9b31-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9b31-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f9b31-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f9b31-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9b31-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9b31-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9b31-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
