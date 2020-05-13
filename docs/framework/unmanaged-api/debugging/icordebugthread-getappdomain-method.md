---
title: ICorDebugThread::GetAppDomain 方法
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetAppDomain
helpviewer_keywords:
- GetAppDomain method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetAppDomain method [.NET Framework debugging]
ms.assetid: 415b3d34-8b35-4b60-a318-140646cc83f8
topic_type:
- apiref
ms.openlocfilehash: 52efebf8a2786afaabe87b96b35a13c5fa1eb578
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379782"
---
# <a name="icordebugthreadgetappdomain-method"></a><span data-ttu-id="a0fa1-102">ICorDebugThread::GetAppDomain 方法</span><span class="sxs-lookup"><span data-stu-id="a0fa1-102">ICorDebugThread::GetAppDomain Method</span></span>
<span data-ttu-id="a0fa1-103">获取一个接口指针，该指针指向此 ICorDebugThread 当前正在执行的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-103">Gets an interface pointer to the application domain in which this ICorDebugThread is currently executing.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0fa1-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0fa1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0fa1-105">参数</span><span class="sxs-lookup"><span data-stu-id="a0fa1-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="a0fa1-106">弄指向 ICorDebugAppDomain 对象的指针，该对象表示此线程当前正在执行的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-106">[out] A pointer to an ICorDebugAppDomain object that represents the application domain in which this thread is currently executing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0fa1-107">要求</span><span class="sxs-lookup"><span data-stu-id="a0fa1-107">Requirements</span></span>  
 <span data-ttu-id="a0fa1-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0fa1-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0fa1-109">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0fa1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0fa1-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0fa1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0fa1-111">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0fa1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
