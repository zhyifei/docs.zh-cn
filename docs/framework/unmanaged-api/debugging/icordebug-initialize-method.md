---
title: "ICorDebug::Initialize 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebug.Initialize
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebug::Initialize
helpviewer_keywords:
- Initialize method, ICorDebug interface [.NET Framework debugging]
- ICorDebug::Initialize method [.NET Framework debugging]
ms.assetid: 6fae3b23-5c9f-47c0-85d8-6bb75e050786
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 12665472b201e6d89be9c5cc6c78b82de067d6a6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuginitialize-method"></a><span data-ttu-id="3da21-102">ICorDebug::Initialize 方法</span><span class="sxs-lookup"><span data-stu-id="3da21-102">ICorDebug::Initialize Method</span></span>
<span data-ttu-id="3da21-103">初始化 `ICorDebug` 对象。</span><span class="sxs-lookup"><span data-stu-id="3da21-103">Initializes the `ICorDebug` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3da21-104">语法</span><span class="sxs-lookup"><span data-stu-id="3da21-104">Syntax</span></span>  
  
```  
HRESULT Initialize ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3da21-105">备注</span><span class="sxs-lookup"><span data-stu-id="3da21-105">Remarks</span></span>  
 <span data-ttu-id="3da21-106">调试器必须调用`Initialize`在创建时间来初始化调试服务。</span><span class="sxs-lookup"><span data-stu-id="3da21-106">The debugger must call `Initialize` at creation time to initialize the debugging services.</span></span> <span data-ttu-id="3da21-107">必须对任何其他方法之前调用此方法`ICorDebug`调用。</span><span class="sxs-lookup"><span data-stu-id="3da21-107">This method must be called before any other method on `ICorDebug` is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3da21-108">要求</span><span class="sxs-lookup"><span data-stu-id="3da21-108">Requirements</span></span>  
 <span data-ttu-id="3da21-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3da21-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3da21-110">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3da21-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3da21-111">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3da21-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3da21-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3da21-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3da21-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3da21-113">See Also</span></span>  
 [<span data-ttu-id="3da21-114">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="3da21-114">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
