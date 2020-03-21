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
ms.openlocfilehash: e5fd1730bbe5b6f2905691dce41a7f503227534a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179070"
---
# <a name="icordebugappdomain3getcachedwinrttypes-method"></a><span data-ttu-id="2738e-102">ICorDebugAppDomain3::GetCachedWinRTTypes 方法</span><span class="sxs-lookup"><span data-stu-id="2738e-102">ICorDebugAppDomain3::GetCachedWinRTTypes Method</span></span>
<span data-ttu-id="2738e-103">获取所有缓存的 Windows 运行时类型的枚举器。</span><span class="sxs-lookup"><span data-stu-id="2738e-103">Gets an enumerator for all cached Windows Runtime types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2738e-104">语法</span><span class="sxs-lookup"><span data-stu-id="2738e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCachedWinRTTypes (
    [out] ICorDebugGuidToTypeEnum **ppGuidToTypeEnum)  
;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2738e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="2738e-105">Parameters</span></span>  
 `ppGuidToTypeEnum`  
 <span data-ttu-id="2738e-106">[出]指向[ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)接口对象的指针，该对象可以枚举当前在应用程序域中加载的 Windows 运行时类型的托管表示形式。</span><span class="sxs-lookup"><span data-stu-id="2738e-106">[out] A pointer to an [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md) interface object that can enumerate the managed representations of Windows Runtime types currently loaded in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2738e-107">要求</span><span class="sxs-lookup"><span data-stu-id="2738e-107">Requirements</span></span>  
 <span data-ttu-id="2738e-108">**平台：** 窗口运行时</span><span class="sxs-lookup"><span data-stu-id="2738e-108">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="2738e-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2738e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2738e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2738e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2738e-111">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2738e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2738e-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2738e-112">See also</span></span>

- [<span data-ttu-id="2738e-113">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="2738e-113">ICorDebugAppDomain3 Interface</span></span>](icordebugappdomain3-interface.md)
