---
title: "ICorDebugModuleBreakpoint::GetModule 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: afdd16cbdb2b33ad0806fbce1dab5e6d7130fb0c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="fd9b8-102">ICorDebugModuleBreakpoint::GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="fd9b8-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="fd9b8-103">"Icor 调试模块"引用在其中设置此断点的模块中获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd9b8-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd9b8-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd9b8-105">参数</span><span class="sxs-lookup"><span data-stu-id="fd9b8-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="fd9b8-106">[out]指向的地址的指针`ICorDebugModule`引用在其中设置断点的模块的接口。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd9b8-107">要求</span><span class="sxs-lookup"><span data-stu-id="fd9b8-107">Requirements</span></span>  
 <span data-ttu-id="fd9b8-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="fd9b8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd9b8-109">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fd9b8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fd9b8-110">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd9b8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd9b8-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd9b8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd9b8-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fd9b8-112">See Also</span></span>  
 
