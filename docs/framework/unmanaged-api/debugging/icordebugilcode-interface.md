---
title: ICorDebugILCode 接口
ms.date: 03/30/2017
api_name:
- ICorDebugILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 51c4de0c-3813-4142-be25-a85bb84efb90
topic_type:
- apiref
ms.openlocfilehash: d96b747bccebe36cce2377d325a678c280c8e693
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782466"
---
# <a name="icordebugilcode-interface"></a><span data-ttu-id="a9a09-102">ICorDebugILCode 接口</span><span class="sxs-lookup"><span data-stu-id="a9a09-102">ICorDebugILCode Interface</span></span>
<span data-ttu-id="a9a09-103">[仅在 .NET Framework 4.5.2 及更高版本中受支持]</span><span class="sxs-lookup"><span data-stu-id="a9a09-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="a9a09-104">表示中间语言 (IL) 代码段。</span><span class="sxs-lookup"><span data-stu-id="a9a09-104">Represents a segment of intermediate language (IL) code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a9a09-105">方法</span><span class="sxs-lookup"><span data-stu-id="a9a09-105">Methods</span></span>  
  
|<span data-ttu-id="a9a09-106">方法</span><span class="sxs-lookup"><span data-stu-id="a9a09-106">Method</span></span>|<span data-ttu-id="a9a09-107">描述</span><span class="sxs-lookup"><span data-stu-id="a9a09-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a9a09-108">GetEHClauses 方法</span><span class="sxs-lookup"><span data-stu-id="a9a09-108">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)|<span data-ttu-id="a9a09-109">返回指向为此 IL 定义的异常处理 (EH) 子句列表的指针。</span><span class="sxs-lookup"><span data-stu-id="a9a09-109">Returns a pointer to a list of exception handling (EH) clauses that are defined for this IL.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a9a09-110">需求</span><span class="sxs-lookup"><span data-stu-id="a9a09-110">Requirements</span></span>  
 <span data-ttu-id="a9a09-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a9a09-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9a09-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a9a09-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9a09-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9a09-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9a09-114">**.NET Framework 版本：** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9a09-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9a09-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a9a09-115">See also</span></span>

- [<span data-ttu-id="a9a09-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="a9a09-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a9a09-117">调试</span><span class="sxs-lookup"><span data-stu-id="a9a09-117">Debugging</span></span>](index.md)
