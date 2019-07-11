---
title: ICorDebugEval::GetThread 方法
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetThread
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetThread
helpviewer_keywords:
- GetThread method, ICorDebugEval interface [.NET Framework debugging]
- ICorDebugEval::GetThread method [.NET Framework debugging]
ms.assetid: 57163b0d-c8a7-44af-9078-e7a895d29f9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24bc096a0ba01c58aa963d69fa46a1d1bbe8be75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67752899"
---
# <a name="icordebugevalgetthread-method"></a><span data-ttu-id="423c7-102">ICorDebugEval::GetThread 方法</span><span class="sxs-lookup"><span data-stu-id="423c7-102">ICorDebugEval::GetThread Method</span></span>
<span data-ttu-id="423c7-103">获取此评估版正在执行或将执行的线程。</span><span class="sxs-lookup"><span data-stu-id="423c7-103">Gets the thread in which this evaluation is executing or will execute.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="423c7-104">语法</span><span class="sxs-lookup"><span data-stu-id="423c7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThread (  
    [out] ICorDebugThread   **ppThread  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="423c7-105">参数</span><span class="sxs-lookup"><span data-stu-id="423c7-105">Parameters</span></span>  
 `ppThread`  
 <span data-ttu-id="423c7-106">[out]指向一个 ICorDebugThread 对象，表示在线程的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="423c7-106">[out] A pointer to the address of an ICorDebugThread object that represents the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="423c7-107">要求</span><span class="sxs-lookup"><span data-stu-id="423c7-107">Requirements</span></span>  
 <span data-ttu-id="423c7-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="423c7-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="423c7-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="423c7-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="423c7-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="423c7-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="423c7-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="423c7-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
