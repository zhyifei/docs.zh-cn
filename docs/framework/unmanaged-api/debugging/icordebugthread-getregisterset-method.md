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
ms.openlocfilehash: 606453424d34dcb22716c308d210fb257d1c37a7
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378869"
---
# <a name="icordebugthreadgetregisterset-method"></a><span data-ttu-id="95e3d-102">ICorDebugThread::GetRegisterSet 方法</span><span class="sxs-lookup"><span data-stu-id="95e3d-102">ICorDebugThread::GetRegisterSet Method</span></span>
<span data-ttu-id="95e3d-103">获取一个接口指针，该指针指向与此 ICorDebugThread 对象的活动部分关联的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="95e3d-103">Gets an interface pointer to the register set that is associated with the active part of this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95e3d-104">语法</span><span class="sxs-lookup"><span data-stu-id="95e3d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRegisterSet (  
    [out] ICorDebugRegisterSet **ppRegisters  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95e3d-105">参数</span><span class="sxs-lookup"><span data-stu-id="95e3d-105">Parameters</span></span>  
 `ppRegisters`  
 <span data-ttu-id="95e3d-106">弄指向[ICorDebugRegisterSet](icordebugregisterset-interface.md)接口对象地址的指针，该对象表示此线程的活动部分的寄存器集。</span><span class="sxs-lookup"><span data-stu-id="95e3d-106">[out] A pointer to the address of an [ICorDebugRegisterSet](icordebugregisterset-interface.md) interface object that represents the register set for the active part of this thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95e3d-107">要求</span><span class="sxs-lookup"><span data-stu-id="95e3d-107">Requirements</span></span>  
 <span data-ttu-id="95e3d-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95e3d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95e3d-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95e3d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95e3d-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95e3d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95e3d-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95e3d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
