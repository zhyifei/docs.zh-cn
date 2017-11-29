---
title: "ICorDebugInternalFrame::GetFrameType 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame.GetFrameType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9d3dd087662c938b2f733458d1e92cff577e9f7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="7b5bf-102">ICorDebugInternalFrame::GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="7b5bf-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="7b5bf-103">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="7b5bf-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b5bf-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b5bf-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b5bf-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b5bf-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="7b5bf-106">[out]指向 CorDebugInternalFrameType 枚举，该值指示由此内部帧的类型的值的指针`ICorDebugInternalFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="7b5bf-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b5bf-107">备注</span><span class="sxs-lookup"><span data-stu-id="7b5bf-107">Remarks</span></span>  
 <span data-ttu-id="7b5bf-108">内部的帧类型都不会 STUBFRAME_NONE。</span><span class="sxs-lookup"><span data-stu-id="7b5bf-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="7b5bf-109">调试器应适当忽略无法识别内部帧类型。</span><span class="sxs-lookup"><span data-stu-id="7b5bf-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b5bf-110">要求</span><span class="sxs-lookup"><span data-stu-id="7b5bf-110">Requirements</span></span>  
 <span data-ttu-id="7b5bf-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b5bf-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b5bf-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7b5bf-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b5bf-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b5bf-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b5bf-114">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b5bf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
