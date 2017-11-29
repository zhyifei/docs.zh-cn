---
title: "ICorDebugAppDomain::EnumerateBreakpoints 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain.EnumerateBreakpoints
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain::EnumerateBreakpoints
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateBreakpoints method [.NET Framework debugging]
- EnumerateBreakpoints method [.NET Framework debugging]
ms.assetid: 206069c5-25cb-4794-9d69-67c5aa7ed0af
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a29bb5b8a21a9d8082564ec377edc20cd62378a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomainenumeratebreakpoints-method"></a><span data-ttu-id="1c336-102">ICorDebugAppDomain::EnumerateBreakpoints 方法</span><span class="sxs-lookup"><span data-stu-id="1c336-102">ICorDebugAppDomain::EnumerateBreakpoints Method</span></span>
<span data-ttu-id="1c336-103">应用程序域中获取所有活动断点的枚举数。</span><span class="sxs-lookup"><span data-stu-id="1c336-103">Gets an enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c336-104">语法</span><span class="sxs-lookup"><span data-stu-id="1c336-104">Syntax</span></span>  
  
```  
HRESULT EnumerateBreakpoints (  
    [out] ICorDebugBreakpointEnum   **ppBreakpoints  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1c336-105">参数</span><span class="sxs-lookup"><span data-stu-id="1c336-105">Parameters</span></span>  
 `ppBreakpoints`  
 <span data-ttu-id="1c336-106">[out]指向的地址是应用程序域中的所有活动断点的枚举器的 ICorDebugBreakpointEnum 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="1c336-106">[out] A pointer to the address of an ICorDebugBreakpointEnum object that is the enumerator for all active breakpoints in the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c336-107">备注</span><span class="sxs-lookup"><span data-stu-id="1c336-107">Remarks</span></span>  
 <span data-ttu-id="1c336-108">枚举器包括所有类型的断点，包括函数断点和数据断点。</span><span class="sxs-lookup"><span data-stu-id="1c336-108">The enumerator includes all types of breakpoints, including function breakpoints and data breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1c336-109">要求</span><span class="sxs-lookup"><span data-stu-id="1c336-109">Requirements</span></span>  
 <span data-ttu-id="1c336-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1c336-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c336-111">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1c336-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1c336-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1c336-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1c336-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c336-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
