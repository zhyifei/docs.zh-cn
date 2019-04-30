---
title: ICorDebugInternalFrame::GetFrameType 方法
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a0b6f0550bad534379b562c3df9da9ab917f5270
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946327"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="2231b-102">ICorDebugInternalFrame::GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="2231b-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="2231b-103">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="2231b-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2231b-104">语法</span><span class="sxs-lookup"><span data-stu-id="2231b-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2231b-105">参数</span><span class="sxs-lookup"><span data-stu-id="2231b-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="2231b-106">[out]指向 CorDebugInternalFrameType 枚举，该值指示由此内部框架的类型的值的指针`ICorDebugInternalFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="2231b-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2231b-107">备注</span><span class="sxs-lookup"><span data-stu-id="2231b-107">Remarks</span></span>  
 <span data-ttu-id="2231b-108">内部框架类型永远不会将 STUBFRAME_NONE。</span><span class="sxs-lookup"><span data-stu-id="2231b-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="2231b-109">调试器应适当忽略无法识别内部帧类型。</span><span class="sxs-lookup"><span data-stu-id="2231b-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2231b-110">要求</span><span class="sxs-lookup"><span data-stu-id="2231b-110">Requirements</span></span>  
 <span data-ttu-id="2231b-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2231b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2231b-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2231b-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2231b-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2231b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2231b-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2231b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
