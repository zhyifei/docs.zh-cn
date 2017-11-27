---
title: "ICorDebugCode2 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugCode2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode2
helpviewer_keywords: ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e7de0bdddd20dd073adfd38565bb1e94e8f2806e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode2-interface1"></a><span data-ttu-id="38296-102">ICorDebugCode2 接口 1</span><span class="sxs-lookup"><span data-stu-id="38296-102">ICorDebugCode2 Interface1</span></span>
<span data-ttu-id="38296-103">提供扩展功能的"icor 调试代码"的方法。</span><span class="sxs-lookup"><span data-stu-id="38296-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38296-104">方法</span><span class="sxs-lookup"><span data-stu-id="38296-104">Methods</span></span>  
  
|<span data-ttu-id="38296-105">方法</span><span class="sxs-lookup"><span data-stu-id="38296-105">Method</span></span>|<span data-ttu-id="38296-106">描述</span><span class="sxs-lookup"><span data-stu-id="38296-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38296-107">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="38296-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="38296-108">获取此代码对象组成的代码块。</span><span class="sxs-lookup"><span data-stu-id="38296-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="38296-109">GetCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="38296-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="38296-110">获取用于指定此代码对象是任一在实时 (JIT) 编译或使用本机映像生成器 (Ngen.exe) 生成所依据的条件的标志。</span><span class="sxs-lookup"><span data-stu-id="38296-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38296-111">备注</span><span class="sxs-lookup"><span data-stu-id="38296-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="38296-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="38296-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38296-113">要求</span><span class="sxs-lookup"><span data-stu-id="38296-113">Requirements</span></span>  
 <span data-ttu-id="38296-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38296-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38296-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38296-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38296-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38296-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38296-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38296-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38296-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38296-118">See Also</span></span>  
    
 [<span data-ttu-id="38296-119">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="38296-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="38296-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="38296-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
