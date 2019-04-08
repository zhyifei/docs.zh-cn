---
title: ICorDebugILCode2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILCode2
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: f9dc2afd-df8a-464d-bdbf-5af0a1d4bf85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a27dbd8b5013937bb97f37113687405c988c1fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142657"
---
# <a name="icordebugilcode2-interface"></a><span data-ttu-id="9488b-102">ICorDebugILCode2 接口</span><span class="sxs-lookup"><span data-stu-id="9488b-102">ICorDebugILCode2 Interface</span></span>
<span data-ttu-id="9488b-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="9488b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="9488b-104">进行逻辑扩展[ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)接口，以提供的方法的返回函数的局部变量签名，该标记和映射将探查器检测中间语言 (IL) 偏移量到原始方法的 IL偏移量。</span><span class="sxs-lookup"><span data-stu-id="9488b-104">Logically extends the [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) interface to provide methods that return the token for a function's local variable signature, and that map a profiler's instrumented intermediate language (IL) offsets to original method IL offsets.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9488b-105">方法</span><span class="sxs-lookup"><span data-stu-id="9488b-105">Methods</span></span>  
  
|<span data-ttu-id="9488b-106">方法</span><span class="sxs-lookup"><span data-stu-id="9488b-106">Method</span></span>|<span data-ttu-id="9488b-107">描述</span><span class="sxs-lookup"><span data-stu-id="9488b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9488b-108">GetInstrumentedILMap 方法</span><span class="sxs-lookup"><span data-stu-id="9488b-108">GetInstrumentedILMap Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md)|<span data-ttu-id="9488b-109">返回从探查器检测到的 IL 偏移量到此实例的原始方法的 IL 偏移量的映射。</span><span class="sxs-lookup"><span data-stu-id="9488b-109">Returns a map from profiler instrumented IL offsets to original method IL offsets for this instance.</span></span>|  
|[<span data-ttu-id="9488b-110">GetLocalVarSigToken 方法</span><span class="sxs-lookup"><span data-stu-id="9488b-110">GetLocalVarSigToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getlocalvarsigtoken-method.md)|<span data-ttu-id="9488b-111">获取元数据标记，用于由此实例表示的函数的局部变量签名。</span><span class="sxs-lookup"><span data-stu-id="9488b-111">Gets the metadata token for the local variable signature for the function that is represented by this instance.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9488b-112">要求</span><span class="sxs-lookup"><span data-stu-id="9488b-112">Requirements</span></span>  
 <span data-ttu-id="9488b-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9488b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9488b-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9488b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9488b-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9488b-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="9488b-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="9488b-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9488b-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="9488b-117">See also</span></span>

- [<span data-ttu-id="9488b-118">ICorDebugILCode 接口</span><span class="sxs-lookup"><span data-stu-id="9488b-118">ICorDebugILCode Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)
- [<span data-ttu-id="9488b-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="9488b-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="9488b-120">调试</span><span class="sxs-lookup"><span data-stu-id="9488b-120">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
