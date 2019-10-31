---
title: ICorDebug::Initialize 方法
ms.date: 03/30/2017
api_name:
- ICorDebug.Initialize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type:
- apiref
ms.openlocfilehash: a5cda98cac0bc3fc6fb101fd0404b062224cb578
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134085"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="757d0-102">ICorDebug::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="757d0-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="757d0-103">初始化 `ICorDebug` 对象。</span><span class="sxs-lookup"><span data-stu-id="757d0-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="757d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="757d0-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="757d0-105">备注</span><span class="sxs-lookup"><span data-stu-id="757d0-105">Remarks</span></span>  
 <span data-ttu-id="757d0-106">调试器必须在创建时调用 `Initialize`，才能初始化调试服务。</span><span class="sxs-lookup"><span data-stu-id="757d0-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="757d0-107">在调用 `ICorDebug` 上的任何其他方法之前，必须先调用此方法。</span><span class="sxs-lookup"><span data-stu-id="757d0-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="757d0-108">要求</span><span class="sxs-lookup"><span data-stu-id="757d0-108">Requirements</span></span>  
 <span data-ttu-id="757d0-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="757d0-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="757d0-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="757d0-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="757d0-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="757d0-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="757d0-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="757d0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="757d0-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="757d0-113">See also</span></span>

- [<span data-ttu-id="757d0-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="757d0-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
