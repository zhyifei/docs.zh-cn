---
title: ICorDebugStepper2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStepper2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper2
helpviewer_keywords:
- ICorDebugStepper2 interface [.NET Framework debugging]
ms.assetid: 7a191c2a-95ea-4d47-83b0-44de2b632d63
topic_type:
- apiref
ms.openlocfilehash: d154cf10e60935d12653c70875323079f92ae288
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791732"
---
# <a name="icordebugstepper2-interface"></a><span data-ttu-id="90877-102">ICorDebugStepper2 接口</span><span class="sxs-lookup"><span data-stu-id="90877-102">ICorDebugStepper2 Interface</span></span>
<span data-ttu-id="90877-103">为 "仅我的代码" （JMC）调试提供支持。</span><span class="sxs-lookup"><span data-stu-id="90877-103">Provides support for just my code (JMC) debugging.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="90877-104">方法</span><span class="sxs-lookup"><span data-stu-id="90877-104">Methods</span></span>  
  
|<span data-ttu-id="90877-105">方法</span><span class="sxs-lookup"><span data-stu-id="90877-105">Method</span></span>|<span data-ttu-id="90877-106">描述</span><span class="sxs-lookup"><span data-stu-id="90877-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="90877-107">SetJMC 方法</span><span class="sxs-lookup"><span data-stu-id="90877-107">SetJMC Method</span></span>](icordebugstepper2-setjmc-method.md)|<span data-ttu-id="90877-108">设置一个值，该值指定此 ICorDebugStepper 是否仅通过应用程序开发人员编写的代码执行步骤。</span><span class="sxs-lookup"><span data-stu-id="90877-108">Sets a value that specifies whether this ICorDebugStepper steps only through code that is authored by an application's developer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="90877-109">备注</span><span class="sxs-lookup"><span data-stu-id="90877-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="90877-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="90877-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90877-111">需求</span><span class="sxs-lookup"><span data-stu-id="90877-111">Requirements</span></span>  
 <span data-ttu-id="90877-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90877-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90877-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="90877-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="90877-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="90877-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="90877-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90877-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90877-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90877-116">See also</span></span>

- [<span data-ttu-id="90877-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="90877-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
