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
ms.openlocfilehash: d62f4f8a34123bcd3f0cbe56f1c1b958bcaa6ef2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33413366"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="3fbd7-102">ICorDebugFrame::GetCallee 方法</span><span class="sxs-lookup"><span data-stu-id="3fbd7-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="3fbd7-103">获取一个指针指向 ICorDebugFrame 对象调用此帧的当前链中。</span><span class="sxs-lookup"><span data-stu-id="3fbd7-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3fbd7-104">语法</span><span class="sxs-lookup"><span data-stu-id="3fbd7-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3fbd7-105">参数</span><span class="sxs-lookup"><span data-stu-id="3fbd7-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="3fbd7-106">[out]指向的地址的指针`ICorDebugFrame`表示被调用的帧的对象。</span><span class="sxs-lookup"><span data-stu-id="3fbd7-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="3fbd7-107">此值为 null，如果调用的帧为当前的链中的最内层帧。</span><span class="sxs-lookup"><span data-stu-id="3fbd7-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3fbd7-108">要求</span><span class="sxs-lookup"><span data-stu-id="3fbd7-108">Requirements</span></span>  
 <span data-ttu-id="3fbd7-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3fbd7-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3fbd7-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3fbd7-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3fbd7-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3fbd7-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3fbd7-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3fbd7-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
