---
title: ICorDebugThread::GetActiveChain 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveChain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveChain
helpviewer_keywords:
- ICorDebugThread::GetActiveChain method [.NET Framework debugging]
- GetActiveChain method [.NET Framework debugging]
ms.assetid: f50de1f7-40ef-4949-b542-1d9a61f7bfef
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9030319ca12aafcf452e3ecd816fc269f0abfc0e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33417510"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="c68c1-102">ICorDebugThread::GetActiveChain 方法</span><span class="sxs-lookup"><span data-stu-id="c68c1-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="c68c1-103">获取此 ICorDebugThread 对象上的活动的 （最新） 堆栈链的接口指针。</span><span class="sxs-lookup"><span data-stu-id="c68c1-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c68c1-104">语法</span><span class="sxs-lookup"><span data-stu-id="c68c1-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c68c1-105">参数</span><span class="sxs-lookup"><span data-stu-id="c68c1-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="c68c1-106">[out]指向一个表示堆栈链的 ICorDebugChain 对象的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c68c1-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c68c1-107">备注</span><span class="sxs-lookup"><span data-stu-id="c68c1-107">Remarks</span></span>  
 <span data-ttu-id="c68c1-108">`ppChain`参数是没有堆栈链当前处于活动状态的情况下为 null。</span><span class="sxs-lookup"><span data-stu-id="c68c1-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c68c1-109">要求</span><span class="sxs-lookup"><span data-stu-id="c68c1-109">Requirements</span></span>  
 <span data-ttu-id="c68c1-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c68c1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c68c1-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c68c1-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c68c1-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c68c1-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c68c1-113">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c68c1-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
