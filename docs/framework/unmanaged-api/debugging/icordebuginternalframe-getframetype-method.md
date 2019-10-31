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
ms.openlocfilehash: b7a33fd6e2178e0e9188b81f516b231702fb6460
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122712"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="afd23-102">ICorDebugInternalFrame::GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="afd23-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="afd23-103">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="afd23-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="afd23-104">语法</span><span class="sxs-lookup"><span data-stu-id="afd23-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="afd23-105">参数</span><span class="sxs-lookup"><span data-stu-id="afd23-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="afd23-106">弄一个指针，指向 CorDebugInternalFrameType 枚举的值，该值指示由此 `ICorDebugInternalFrame` 对象表示的内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="afd23-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="afd23-107">备注</span><span class="sxs-lookup"><span data-stu-id="afd23-107">Remarks</span></span>  
 <span data-ttu-id="afd23-108">内部帧类型永远不会 STUBFRAME_NONE。</span><span class="sxs-lookup"><span data-stu-id="afd23-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="afd23-109">调试器应正常忽略无法识别的内部帧类型。</span><span class="sxs-lookup"><span data-stu-id="afd23-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="afd23-110">要求</span><span class="sxs-lookup"><span data-stu-id="afd23-110">Requirements</span></span>  
 <span data-ttu-id="afd23-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="afd23-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="afd23-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="afd23-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="afd23-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="afd23-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="afd23-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="afd23-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
