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
ms.openlocfilehash: b05f5a3f29c7b72ed83c1456175f68ef9b986e3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61987177"
---
# <a name="icordebugthreadgetactivechain-method"></a><span data-ttu-id="816c9-102">ICorDebugThread::GetActiveChain 方法</span><span class="sxs-lookup"><span data-stu-id="816c9-102">ICorDebugThread::GetActiveChain Method</span></span>
<span data-ttu-id="816c9-103">获取此 ICorDebugThread 对象上活动的 （最新的） 堆栈链的接口指针。</span><span class="sxs-lookup"><span data-stu-id="816c9-103">Gets an interface pointer to the active (most recent) stack chain on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="816c9-104">语法</span><span class="sxs-lookup"><span data-stu-id="816c9-104">Syntax</span></span>  
  
```  
HRESULT GetActiveChain (  
    [out] ICorDebugChain **ppChain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="816c9-105">参数</span><span class="sxs-lookup"><span data-stu-id="816c9-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="816c9-106">[out]指向一个 ICorDebugChain 对象，表示堆栈链的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="816c9-106">[out] A pointer to the address of an ICorDebugChain object that represents the stack chain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="816c9-107">备注</span><span class="sxs-lookup"><span data-stu-id="816c9-107">Remarks</span></span>  
 <span data-ttu-id="816c9-108">`ppChain`参数为 null，如果没有堆栈链是当前处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="816c9-108">The `ppChain` parameter is null if no stack chain is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="816c9-109">要求</span><span class="sxs-lookup"><span data-stu-id="816c9-109">Requirements</span></span>  
 <span data-ttu-id="816c9-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="816c9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="816c9-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="816c9-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="816c9-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="816c9-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="816c9-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="816c9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
