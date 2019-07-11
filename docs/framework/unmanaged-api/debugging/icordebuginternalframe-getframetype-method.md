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
ms.openlocfilehash: 2a5461cc6a78347cdbe0d0b13f8111cb24c11006
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760057"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="ca1a1-102">ICorDebugInternalFrame::GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="ca1a1-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="ca1a1-103">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="ca1a1-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca1a1-104">语法</span><span class="sxs-lookup"><span data-stu-id="ca1a1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca1a1-105">参数</span><span class="sxs-lookup"><span data-stu-id="ca1a1-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="ca1a1-106">[out]指向 CorDebugInternalFrameType 枚举，该值指示由此内部框架的类型的值的指针`ICorDebugInternalFrame`对象。</span><span class="sxs-lookup"><span data-stu-id="ca1a1-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ca1a1-107">备注</span><span class="sxs-lookup"><span data-stu-id="ca1a1-107">Remarks</span></span>  
 <span data-ttu-id="ca1a1-108">内部框架类型永远不会将 STUBFRAME_NONE。</span><span class="sxs-lookup"><span data-stu-id="ca1a1-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="ca1a1-109">调试器应适当忽略无法识别内部帧类型。</span><span class="sxs-lookup"><span data-stu-id="ca1a1-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca1a1-110">要求</span><span class="sxs-lookup"><span data-stu-id="ca1a1-110">Requirements</span></span>  
 <span data-ttu-id="ca1a1-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca1a1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca1a1-112">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca1a1-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca1a1-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca1a1-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca1a1-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca1a1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
