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
ms.openlocfilehash: dd09ce27c0fea9dca8fd86afc563651d68542e13
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786355"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="f807b-102">ICorDebug::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="f807b-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="f807b-103">初始化 `ICorDebug` 对象。</span><span class="sxs-lookup"><span data-stu-id="f807b-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f807b-104">语法</span><span class="sxs-lookup"><span data-stu-id="f807b-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="f807b-105">备注</span><span class="sxs-lookup"><span data-stu-id="f807b-105">Remarks</span></span>  
 <span data-ttu-id="f807b-106">调试器必须调用`Initialize`在创建时时间来初始化调试服务。</span><span class="sxs-lookup"><span data-stu-id="f807b-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="f807b-107">必须在任何其他方法之前调用此方法`ICorDebug`调用。</span><span class="sxs-lookup"><span data-stu-id="f807b-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f807b-108">要求</span><span class="sxs-lookup"><span data-stu-id="f807b-108">Requirements</span></span>  
 <span data-ttu-id="f807b-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f807b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f807b-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f807b-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f807b-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f807b-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f807b-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f807b-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f807b-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f807b-113">See also</span></span>

- [<span data-ttu-id="f807b-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="f807b-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
