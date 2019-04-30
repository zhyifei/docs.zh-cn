---
title: ICorDebugThread::GetRegisterSet 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetRegisterSet
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetRegisterSet
helpviewer_keywords:
- ICorDebugThread::GetRegisterSet method [.NET Framework debugging]
- GetRegisterSet method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3b9b6260-98ac-4cfd-88e5-5d7614f94a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 909bcad035516c494d1f867b71bb8f52939eba13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993988"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="11048-102">ICorDebugThread::GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="11048-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="11048-103">获取与此 ICorDebugThread 对象的活动部分相关联的寄存器集的接口指针。</span><span class="sxs-lookup"><span data-stu-id="11048-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11048-104">语法</span><span class="sxs-lookup"><span data-stu-id="11048-104">Syntax</span></span>  
  
```  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11048-105">参数</span><span class="sxs-lookup"><span data-stu-id="11048-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="11048-106">[out]指向的地址的指针[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)接口对象，表示注册为此线程的活动部分。</span><span class="sxs-lookup"><span data-stu-id="11048-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11048-107">要求</span><span class="sxs-lookup"><span data-stu-id="11048-107">Requirements</span></span>  
 <span data-ttu-id="11048-108">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="11048-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11048-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11048-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11048-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11048-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11048-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11048-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
