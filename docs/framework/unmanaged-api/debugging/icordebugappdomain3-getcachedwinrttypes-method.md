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
ms.openlocfilehash: 4ba981d86f90af449820ce13aa847169ca877429
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67737769"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="2bfaa-102">ICorDebugAppDomain3::GetCachedWinRTTypes 方法</span><span class="sxs-lookup"><span data-stu-id="2bfaa-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="2bfaa-103">获取所有已缓存的 Windows 运行时类型的枚举数。</span><span class="sxs-lookup"><span data-stu-id="2bfaa-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bfaa-104">语法</span><span class="sxs-lookup"><span data-stu-id="2bfaa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (   
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2bfaa-105">参数</span><span class="sxs-lookup"><span data-stu-id="2bfaa-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="2bfaa-106">[out]一个指向[ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)可以枚举当前 Windows 运行时类型的托管表示形式的接口对象加载到应用程序域中。</span><span class="sxs-lookup"><span data-stu-id="2bfaa-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2bfaa-107">要求</span><span class="sxs-lookup"><span data-stu-id="2bfaa-107">Requirements</span></span>  
 <span data-ttu-id="2bfaa-108">**平台：** Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="2bfaa-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="2bfaa-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2bfaa-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2bfaa-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2bfaa-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2bfaa-111">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2bfaa-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bfaa-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2bfaa-112">See also</span></span>

- [<span data-ttu-id="2bfaa-113">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="2bfaa-113">ICorDebugAppDomain3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-interface.md)
