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
ms.openlocfilehash: 843c6df1ef41fdd3227b92275182432ad4cc43b1
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379729"
---
# <a name="icordebugthreadgetactiveframe-method"></a><span data-ttu-id="f62a5-102">ICorDebugThread::GetActiveFrame 方法</span><span class="sxs-lookup"><span data-stu-id="f62a5-102">ICorDebugThread::GetActiveFrame Method</span></span>
<span data-ttu-id="f62a5-103">获取一个接口指针，该指针指向此 ICorDebugThread 对象上的活动（最新的）帧。</span><span class="sxs-lookup"><span data-stu-id="f62a5-103">Gets an interface pointer to the active (most recent) frame on this ICorDebugThread object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f62a5-104">语法</span><span class="sxs-lookup"><span data-stu-id="f62a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f62a5-105">参数</span><span class="sxs-lookup"><span data-stu-id="f62a5-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="f62a5-106">弄指向表示帧的 ICorDebugFrame 接口对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="f62a5-106">[out] A pointer to the address of an ICorDebugFrame interface object that represents a frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f62a5-107">备注</span><span class="sxs-lookup"><span data-stu-id="f62a5-107">Remarks</span></span>  
 <span data-ttu-id="f62a5-108">`ppFrame`如果当前没有活动帧，则参数为 null。</span><span class="sxs-lookup"><span data-stu-id="f62a5-108">The `ppFrame` parameter is null if no frame is currently active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f62a5-109">要求</span><span class="sxs-lookup"><span data-stu-id="f62a5-109">Requirements</span></span>  
 <span data-ttu-id="f62a5-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f62a5-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f62a5-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f62a5-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f62a5-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f62a5-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f62a5-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f62a5-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
