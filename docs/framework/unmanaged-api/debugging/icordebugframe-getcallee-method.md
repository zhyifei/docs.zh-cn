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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 10a5247632f242a4b4e0d33cf7fa7233d1b1e13b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754198"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="4150d-102">ICorDebugFrame::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="4150d-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="4150d-103">获取一个指针指向 ICorDebugFrame 对象调用此帧当前链中。</span><span class="sxs-lookup"><span data-stu-id="4150d-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4150d-104">语法</span><span class="sxs-lookup"><span data-stu-id="4150d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4150d-105">参数</span><span class="sxs-lookup"><span data-stu-id="4150d-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="4150d-106">[out]指向的地址的指针`ICorDebugFrame`对象，表示调用的帧。</span><span class="sxs-lookup"><span data-stu-id="4150d-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="4150d-107">此值为 null，如果调用的帧是当前的链中的最内层帧。</span><span class="sxs-lookup"><span data-stu-id="4150d-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4150d-108">要求</span><span class="sxs-lookup"><span data-stu-id="4150d-108">Requirements</span></span>  
 <span data-ttu-id="4150d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4150d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4150d-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4150d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4150d-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4150d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4150d-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4150d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
