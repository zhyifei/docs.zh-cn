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
ms.openlocfilehash: 6b598352f734cf47514a82de1d0fca65d430a9ab
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209961"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="98ed7-102">ICorDebugInternalFrame::GetFrameType 方法</span><span class="sxs-lookup"><span data-stu-id="98ed7-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="98ed7-103">获取此内部帧的类型。</span><span class="sxs-lookup"><span data-stu-id="98ed7-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ed7-104">语法</span><span class="sxs-lookup"><span data-stu-id="98ed7-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="98ed7-105">参数</span><span class="sxs-lookup"><span data-stu-id="98ed7-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="98ed7-106">弄一个指针，指向 CorDebugInternalFrameType 枚举的值，该值指示由此对象表示的内部帧的类型 `ICorDebugInternalFrame` 。</span><span class="sxs-lookup"><span data-stu-id="98ed7-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98ed7-107">备注</span><span class="sxs-lookup"><span data-stu-id="98ed7-107">Remarks</span></span>  
 <span data-ttu-id="98ed7-108">内部帧类型永远不会 STUBFRAME_NONE。</span><span class="sxs-lookup"><span data-stu-id="98ed7-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="98ed7-109">调试器应正常忽略无法识别的内部帧类型。</span><span class="sxs-lookup"><span data-stu-id="98ed7-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98ed7-110">要求</span><span class="sxs-lookup"><span data-stu-id="98ed7-110">Requirements</span></span>  
 <span data-ttu-id="98ed7-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98ed7-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98ed7-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="98ed7-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="98ed7-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98ed7-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98ed7-114">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98ed7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
