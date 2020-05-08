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
ms.openlocfilehash: aeecf19cb85ce5d7781c3dfedca079e97cab76ce
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895359"
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="b6413-102">ICorDebug::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="b6413-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="b6413-103">初始化 `ICorDebug` 对象。</span><span class="sxs-lookup"><span data-stu-id="b6413-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6413-104">语法</span><span class="sxs-lookup"><span data-stu-id="b6413-104">Syntax</span></span>  
  
```cpp  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b6413-105">备注</span><span class="sxs-lookup"><span data-stu-id="b6413-105">Remarks</span></span>  
 <span data-ttu-id="b6413-106">调试器必须在创建`Initialize`时调用来初始化调试服务。</span><span class="sxs-lookup"><span data-stu-id="b6413-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="b6413-107">调用任何其他方法之前`ICorDebug` ，必须先调用此方法。</span><span class="sxs-lookup"><span data-stu-id="b6413-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6413-108">要求</span><span class="sxs-lookup"><span data-stu-id="b6413-108">Requirements</span></span>  
 <span data-ttu-id="b6413-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b6413-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6413-110">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6413-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6413-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6413-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6413-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6413-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6413-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6413-113">See also</span></span>

- [<span data-ttu-id="b6413-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="b6413-114">ICorDebug Interface</span></span>](icordebug-interface.md)
