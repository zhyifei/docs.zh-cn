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
ms.openlocfilehash: 3d27cf1987d7e9896885f87857554f4039c8d714
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788982"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="ae676-102">ICorDebug::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="ae676-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="ae676-103">初始化 `ICorDebug` 对象。</span><span class="sxs-lookup"><span data-stu-id="ae676-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae676-104">语法</span><span class="sxs-lookup"><span data-stu-id="ae676-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="ae676-105">备注</span><span class="sxs-lookup"><span data-stu-id="ae676-105">Remarks</span></span>  
 <span data-ttu-id="ae676-106">调试器必须在创建时调用 `Initialize`，才能初始化调试服务。</span><span class="sxs-lookup"><span data-stu-id="ae676-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="ae676-107">在调用 `ICorDebug` 上的任何其他方法之前，必须先调用此方法。</span><span class="sxs-lookup"><span data-stu-id="ae676-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae676-108">需求</span><span class="sxs-lookup"><span data-stu-id="ae676-108">Requirements</span></span>  
 <span data-ttu-id="ae676-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ae676-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae676-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ae676-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ae676-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ae676-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ae676-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae676-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae676-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae676-113">See also</span></span>

- [<span data-ttu-id="ae676-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="ae676-114">ICorDebug Interface</span></span>](icordebug-interface.md)
