---
title: ICorDebugAssembly2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly2
helpviewer_keywords:
- ICorDebugAssembly2 interface [.NET Framework debugging]
ms.assetid: c0766e29-e573-4f9a-a928-167d1de5aa7e
topic_type:
- apiref
ms.openlocfilehash: 23b38f86cd81fb0161e50b60b40bed0ba0b423b2
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894868"
---
# <a name="icordebugassembly2-interface"></a><span data-ttu-id="12bdd-102">ICorDebugAssembly2 接口</span><span class="sxs-lookup"><span data-stu-id="12bdd-102">ICorDebugAssembly2 Interface</span></span>

<span data-ttu-id="12bdd-103">表示一个程序集。</span><span class="sxs-lookup"><span data-stu-id="12bdd-103">Represents an assembly.</span></span> <span data-ttu-id="12bdd-104">此接口是 ICorDebugAssembly 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="12bdd-104">This interface is an extension of the ICorDebugAssembly interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="12bdd-105">方法</span><span class="sxs-lookup"><span data-stu-id="12bdd-105">Methods</span></span>  
  
|<span data-ttu-id="12bdd-106">方法</span><span class="sxs-lookup"><span data-stu-id="12bdd-106">Method</span></span>|<span data-ttu-id="12bdd-107">说明</span><span class="sxs-lookup"><span data-stu-id="12bdd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="12bdd-108">IsFullyTrusted 方法</span><span class="sxs-lookup"><span data-stu-id="12bdd-108">IsFullyTrusted Method</span></span>](icordebugassembly2-isfullytrusted-method.md)|<span data-ttu-id="12bdd-109">获取一个值，该值指示运行时安全系统是否已向程序集授予完全信任。</span><span class="sxs-lookup"><span data-stu-id="12bdd-109">Gets a value that indicates whether the assembly has been granted full trust by the runtime security system.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="12bdd-110">备注</span><span class="sxs-lookup"><span data-stu-id="12bdd-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12bdd-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="12bdd-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12bdd-112">要求</span><span class="sxs-lookup"><span data-stu-id="12bdd-112">Requirements</span></span>  
 <span data-ttu-id="12bdd-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="12bdd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12bdd-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="12bdd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="12bdd-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12bdd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12bdd-116">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12bdd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12bdd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12bdd-117">See also</span></span>

- [<span data-ttu-id="12bdd-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="12bdd-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
