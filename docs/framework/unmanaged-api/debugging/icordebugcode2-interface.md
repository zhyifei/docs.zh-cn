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
ms.workload: dotnet
ms.openlocfilehash: 54cada8e8211b3837e30f3d058d54af1eaf96a83
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcode2-interface1"></a><span data-ttu-id="51e6e-102">ICorDebugCode2 接口 1</span><span class="sxs-lookup"><span data-stu-id="51e6e-102">ICorDebugCode2 Interface1</span></span>
<span data-ttu-id="51e6e-103">提供扩展功能的"icor 调试代码"的方法。</span><span class="sxs-lookup"><span data-stu-id="51e6e-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51e6e-104">方法</span><span class="sxs-lookup"><span data-stu-id="51e6e-104">Methods</span></span>  
  
|<span data-ttu-id="51e6e-105">方法</span><span class="sxs-lookup"><span data-stu-id="51e6e-105">Method</span></span>|<span data-ttu-id="51e6e-106">描述</span><span class="sxs-lookup"><span data-stu-id="51e6e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51e6e-107">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="51e6e-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="51e6e-108">获取此代码对象组成的代码块。</span><span class="sxs-lookup"><span data-stu-id="51e6e-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="51e6e-109">GetCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="51e6e-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="51e6e-110">获取用于指定此代码对象是任一在实时 (JIT) 编译或使用本机映像生成器 (Ngen.exe) 生成所依据的条件的标志。</span><span class="sxs-lookup"><span data-stu-id="51e6e-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51e6e-111">备注</span><span class="sxs-lookup"><span data-stu-id="51e6e-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="51e6e-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="51e6e-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51e6e-113">惠?</span><span class="sxs-lookup"><span data-stu-id="51e6e-113">Requirements</span></span>  
 <span data-ttu-id="51e6e-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51e6e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51e6e-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51e6e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51e6e-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51e6e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51e6e-117">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51e6e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51e6e-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="51e6e-118">See Also</span></span>  
    
 [<span data-ttu-id="51e6e-119">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="51e6e-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)  
 [<span data-ttu-id="51e6e-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="51e6e-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
