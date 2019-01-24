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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f7b4cf6c50d624f82a75f19b8e3f42c73910c4e5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709294"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="5701d-102">ICorDebug::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="5701d-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="5701d-103">初始化 `ICorDebug` 对象。</span><span class="sxs-lookup"><span data-stu-id="5701d-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5701d-104">语法</span><span class="sxs-lookup"><span data-stu-id="5701d-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5701d-105">备注</span><span class="sxs-lookup"><span data-stu-id="5701d-105">Remarks</span></span>  
 <span data-ttu-id="5701d-106">调试器必须调用`Initialize`在创建时时间来初始化调试服务。</span><span class="sxs-lookup"><span data-stu-id="5701d-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="5701d-107">必须在任何其他方法之前调用此方法`ICorDebug`调用。</span><span class="sxs-lookup"><span data-stu-id="5701d-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5701d-108">要求</span><span class="sxs-lookup"><span data-stu-id="5701d-108">Requirements</span></span>  
 <span data-ttu-id="5701d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5701d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5701d-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5701d-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5701d-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5701d-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5701d-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5701d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5701d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5701d-113">See also</span></span>
- [<span data-ttu-id="5701d-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="5701d-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
