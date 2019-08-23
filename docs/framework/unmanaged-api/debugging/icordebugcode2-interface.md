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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9cb7be64089a55e7b653fcd6272219abba311af8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69960801"
---
# <a name="icordebugcode2-interface"></a><span data-ttu-id="179eb-102">ICorDebugCode2 接口</span><span class="sxs-lookup"><span data-stu-id="179eb-102">ICorDebugCode2 Interface</span></span>

<span data-ttu-id="179eb-103">提供扩展 "ICorDebugCode" 的功能的方法。</span><span class="sxs-lookup"><span data-stu-id="179eb-103">Provides methods that extend the capabilities of "ICorDebugCode".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="179eb-104">方法</span><span class="sxs-lookup"><span data-stu-id="179eb-104">Methods</span></span>  
  
|<span data-ttu-id="179eb-105">方法</span><span class="sxs-lookup"><span data-stu-id="179eb-105">Method</span></span>|<span data-ttu-id="179eb-106">描述</span><span class="sxs-lookup"><span data-stu-id="179eb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="179eb-107">GetCodeChunks 方法</span><span class="sxs-lookup"><span data-stu-id="179eb-107">GetCodeChunks Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcodechunks-method.md)|<span data-ttu-id="179eb-108">获取包含此代码对象的代码块。</span><span class="sxs-lookup"><span data-stu-id="179eb-108">Gets the chunks of code that this code object is composed of.</span></span>|  
|[<span data-ttu-id="179eb-109">GetCompilerFlags 方法</span><span class="sxs-lookup"><span data-stu-id="179eb-109">GetCompilerFlags Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode2-getcompilerflags-method.md)|<span data-ttu-id="179eb-110">获取标志, 这些标志指定此代码对象是实时 (JIT) 编译或使用本机映像生成器 (Ngen.exe) 生成的。</span><span class="sxs-lookup"><span data-stu-id="179eb-110">Gets the flags that specify the conditions under which this code object was either just-in-time (JIT) compiled or generated using the native image generator (Ngen.exe).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="179eb-111">备注</span><span class="sxs-lookup"><span data-stu-id="179eb-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="179eb-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="179eb-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="179eb-113">要求</span><span class="sxs-lookup"><span data-stu-id="179eb-113">Requirements</span></span>  
 <span data-ttu-id="179eb-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="179eb-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="179eb-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="179eb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="179eb-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="179eb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="179eb-117">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="179eb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="179eb-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="179eb-118">See also</span></span>

- [<span data-ttu-id="179eb-119">ICorDebugCode3 接口</span><span class="sxs-lookup"><span data-stu-id="179eb-119">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
- [<span data-ttu-id="179eb-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="179eb-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
