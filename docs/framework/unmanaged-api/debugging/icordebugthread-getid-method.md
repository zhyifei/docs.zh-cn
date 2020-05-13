---
title: ICorDebugThread::GetID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetID
helpviewer_keywords:
- ICorDebugThread::GetID method [.NET Framework debugging]
- GetID method, ICorDebugThread interface [.NET Framework debugging]
ms.assetid: f1de4584-92df-42f3-9da4-fca03a1c6821
topic_type:
- apiref
ms.openlocfilehash: d01936481ec139757566d5b96cb95ea887cb8c20
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378059"
---
# <a name="icordebugthreadgetid-method"></a><span data-ttu-id="e0c21-102">ICorDebugThread::GetID 方法</span><span class="sxs-lookup"><span data-stu-id="e0c21-102">ICorDebugThread::GetID Method</span></span>
<span data-ttu-id="e0c21-103">获取此 ICorDebugThread 的活动部分的当前操作系统标识符。</span><span class="sxs-lookup"><span data-stu-id="e0c21-103">Gets the current operating system identifier of the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c21-104">语法</span><span class="sxs-lookup"><span data-stu-id="e0c21-104">Syntax</span></span>  
  
```cpp  
HRESULT GetID (  
    [out] DWORD *pdwThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c21-105">参数</span><span class="sxs-lookup"><span data-stu-id="e0c21-105">Parameters</span></span>  
 `pdwThreadId`  
 <span data-ttu-id="e0c21-106">弄线程的标识符。</span><span class="sxs-lookup"><span data-stu-id="e0c21-106">[out] The identifier of the thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c21-107">备注</span><span class="sxs-lookup"><span data-stu-id="e0c21-107">Remarks</span></span>  
 <span data-ttu-id="e0c21-108">操作系统标识符在进程执行期间可能会发生更改，并且可以是线程的不同部分的不同值。</span><span class="sxs-lookup"><span data-stu-id="e0c21-108">The operating system identifier can potentially change during execution of a process, and can be a different value for different parts of the thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0c21-109">要求</span><span class="sxs-lookup"><span data-stu-id="e0c21-109">Requirements</span></span>  
 <span data-ttu-id="e0c21-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e0c21-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0c21-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e0c21-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e0c21-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0c21-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0c21-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0c21-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
