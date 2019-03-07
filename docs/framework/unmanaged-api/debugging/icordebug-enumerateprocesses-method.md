---
title: ICorDebug::EnumerateProcesses 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.EnumerateProcesses
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- EnumerateProcesses
helpviewer_keywords:
- EnumerateProcesses method [.NET Framework debugging]
- ICorDebug::EnumerateProcesses method [.NET Framework debugging]
ms.assetid: ba25d166-1d28-4f1d-aca2-de298bbca669
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ecf5160a7ceb7a4d2f1d64d83f573f8450966dc0
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476667"
---
# <a name="icordebugenumerateprocesses-method"></a><span data-ttu-id="3f61e-102">ICorDebug::EnumerateProcesses 方法</span><span class="sxs-lookup"><span data-stu-id="3f61e-102">ICorDebug::EnumerateProcesses Method</span></span>
<span data-ttu-id="3f61e-103">获取正在调试的进程的枚举数。</span><span class="sxs-lookup"><span data-stu-id="3f61e-103">Gets an enumerator for the processes that are being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f61e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3f61e-104">Syntax</span></span>  
  
```  
HRESULT EnumerateProcesses (  
    [out] ICorDebugProcessEnum      **ppProcess  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f61e-105">参数</span><span class="sxs-lookup"><span data-stu-id="3f61e-105">Parameters</span></span>  
 `ppProcess`  
 <span data-ttu-id="3f61e-106">指向一个 ICorDebugProcessEnum 对象，它正在调试的进程的枚举器的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3f61e-106">A pointer to the address of an ICorDebugProcessEnum object that is the enumerator for the processes being debugged.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f61e-107">要求</span><span class="sxs-lookup"><span data-stu-id="3f61e-107">Requirements</span></span>  
 <span data-ttu-id="3f61e-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3f61e-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f61e-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f61e-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f61e-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f61e-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f61e-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f61e-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f61e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3f61e-112">See also</span></span>
- [<span data-ttu-id="3f61e-113">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="3f61e-113">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
