---
title: ICorDebugThread::GetActiveFrame 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetActiveFrame
helpviewer_keywords:
- ICorDebugThread::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 8d6d3a1a-fef6-4f2f-a22c-3bdd30d70e07
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 051491173bbcef3d87d9a3dbe854eece46c49e0d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994053"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="d1a5f-102">ICorDebugThread::GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="d1a5f-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="d1a5f-103">获取此 ICorDebugThread 对象上活动的 （最新的） 帧的接口指针。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1a5f-104">语法</span><span class="sxs-lookup"><span data-stu-id="d1a5f-104">Syntax</span></span>  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d1a5f-105">参数</span><span class="sxs-lookup"><span data-stu-id="d1a5f-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="d1a5f-106">[out]指向表示框架的 ICorDebugFrame 接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1a5f-107">备注</span><span class="sxs-lookup"><span data-stu-id="d1a5f-107">Remarks</span></span>  
 <span data-ttu-id="d1a5f-108">`ppFrame`参数为 null，如果没有框架当前处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1a5f-109">要求</span><span class="sxs-lookup"><span data-stu-id="d1a5f-109">Requirements</span></span>  
 <span data-ttu-id="d1a5f-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d1a5f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1a5f-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d1a5f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d1a5f-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d1a5f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d1a5f-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1a5f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
