---
title: ICorDebugFrame::GetCallee 方法
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: b83dec65e1dd4fc610be3190e8126e6d9d38a6e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121227"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="391ac-102">ICorDebugFrame::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="391ac-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="391ac-103">获取一个指针，该指针指向此框架调用的当前链中的 ICorDebugFrame 对象。</span><span class="sxs-lookup"><span data-stu-id="391ac-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="391ac-104">语法</span><span class="sxs-lookup"><span data-stu-id="391ac-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="391ac-105">参数</span><span class="sxs-lookup"><span data-stu-id="391ac-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="391ac-106">弄一个指针，指向表示被调用的帧的 `ICorDebugFrame` 对象的地址。</span><span class="sxs-lookup"><span data-stu-id="391ac-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="391ac-107">如果调用帧是当前链中最内层的帧，则此值为 null。</span><span class="sxs-lookup"><span data-stu-id="391ac-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="391ac-108">要求</span><span class="sxs-lookup"><span data-stu-id="391ac-108">Requirements</span></span>  
 <span data-ttu-id="391ac-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="391ac-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="391ac-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="391ac-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="391ac-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="391ac-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="391ac-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="391ac-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
