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
ms.openlocfilehash: 3c62bd73b693322bd679b07b46e3549e1cfc8a56
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133400"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="84d83-102">ICorDebugThread::GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="84d83-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="84d83-103">获取一个接口指针，该指针指向与此 ICorDebugThread 对象的活动部分关联的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="84d83-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84d83-104">语法</span><span class="sxs-lookup"><span data-stu-id="84d83-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="84d83-105">参数</span><span class="sxs-lookup"><span data-stu-id="84d83-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="84d83-106">弄指向[ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md)接口对象地址的指针，该对象表示此线程的活动部分的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="84d83-106">[out] A pointer to the address of an [ICorDebugRegisterSet](../../../../docs/framework/unmanaged-api/debugging/icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84d83-107">要求</span><span class="sxs-lookup"><span data-stu-id="84d83-107">Requirements</span></span>  
 <span data-ttu-id="84d83-108">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="84d83-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84d83-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84d83-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84d83-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84d83-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84d83-111">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84d83-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
