---
title: ICorDebugAppDomain3::GetCachedWinRTTypes 方法
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3.GetCachedWinRTTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes
helpviewer_keywords:
- ICorDebugAppDomain3::GetCachedWinRTTypes method [.NET Framework debugging]
- GetCachedWinRTTypes method, ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 9afd0e04-a403-41e2-9528-a6dcbcdcbd4d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 73a08e83d67c973294938a030b95b906aec6be6d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61962599"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="5652e-102">ICorDebugAppDomain3::GetCachedWinRTTypes 方法</span><span class="sxs-lookup"><span data-stu-id="5652e-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="5652e-103">获取所有缓存的枚举器[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="5652e-103">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5652e-104">语法</span><span class="sxs-lookup"><span data-stu-id="5652e-104">Syntax</span></span>  
  
```  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="5652e-105">参数</span><span class="sxs-lookup"><span data-stu-id="5652e-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="5652e-106">[out]一个指向[ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)接口对象的可枚举的托管的表示形式[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中当前加载的类型。</span><span class="sxs-lookup"><span data-stu-id="5652e-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5652e-107">要求</span><span class="sxs-lookup"><span data-stu-id="5652e-107">Requirements</span></span>  
 <span data-ttu-id="5652e-108">**平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5652e-108">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="5652e-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5652e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5652e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5652e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5652e-111">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5652e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5652e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="5652e-112">See also</span></span>

- [<span data-ttu-id="5652e-113">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="5652e-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
