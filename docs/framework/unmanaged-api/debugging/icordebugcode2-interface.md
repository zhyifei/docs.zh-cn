---
title: ICorDebugCode2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugCode2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode2
helpviewer_keywords:
- ICorDebugCode2 interface [.NET Framework debugging]
ms.assetid: 9321903b-7dea-40d8-ba32-99016c00cc46
topic_type:
- apiref
ms.openlocfilehash: a9ce778cfa1aed4dcf6117c4fe2eca23ccda37a3
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777948"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="caa88-102">ICorDebugCode2 接口</span><span class="sxs-lookup"><span data-stu-id="caa88-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="caa88-103">提供扩展 "ICorDebugCode" 的功能的方法。</span><span class="sxs-lookup"><span data-stu-id="caa88-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="caa88-104">方法</span><span class="sxs-lookup"><span data-stu-id="caa88-104">Methods</span></span>  
  
|<span data-ttu-id="caa88-105">方法</span><span class="sxs-lookup"><span data-stu-id="caa88-105">Method</span></span>|<span data-ttu-id="caa88-106">描述</span><span class="sxs-lookup"><span data-stu-id="caa88-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="caa88-107">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="caa88-107">GetCodeChunks Method</span></span>](icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="caa88-108">获取包含此代码对象的代码块。</span><span class="sxs-lookup"><span data-stu-id="caa88-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="caa88-109">GetCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="caa88-109">GetCompilerFlags Method</span></span>](icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="caa88-110">获取标志，这些标志指定此代码对象是实时（JIT）编译或使用本机映像生成器（Ngen.exe）生成的。</span><span class="sxs-lookup"><span data-stu-id="caa88-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="caa88-111">备注</span><span class="sxs-lookup"><span data-stu-id="caa88-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="caa88-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="caa88-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="caa88-113">需求</span><span class="sxs-lookup"><span data-stu-id="caa88-113">Requirements</span></span>  
 <span data-ttu-id="caa88-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="caa88-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caa88-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="caa88-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="caa88-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="caa88-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="caa88-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caa88-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caa88-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="caa88-118">See also</span></span>

- [<span data-ttu-id="caa88-119">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="caa88-119">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
- [<span data-ttu-id="caa88-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="caa88-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
