---
title: "ICorDebugAppDomainEnum 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomainEnum
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomainEnum
helpviewer_keywords: ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a77ce6e00ed4bbf866b8761d6339f4191151a6f6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugappdomainenum-interface1"></a><span data-ttu-id="d0ecd-102">ICorDebugAppDomainEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="d0ecd-102">ICorDebugAppDomainEnum Interface1</span></span>
<span data-ttu-id="d0ecd-103">提供`Next`方法，返回指定的数目的`ICorDebugAppDomainEnum`枚举中的下一个位置开始的值。</span><span class="sxs-lookup"><span data-stu-id="d0ecd-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="d0ecd-104">此接口是"ICorDebugEnum"的子类。</span><span class="sxs-lookup"><span data-stu-id="d0ecd-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0ecd-105">方法</span><span class="sxs-lookup"><span data-stu-id="d0ecd-105">Methods</span></span>  
  
|<span data-ttu-id="d0ecd-106">方法</span><span class="sxs-lookup"><span data-stu-id="d0ecd-106">Method</span></span>|<span data-ttu-id="d0ecd-107">描述</span><span class="sxs-lookup"><span data-stu-id="d0ecd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0ecd-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="d0ecd-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="d0ecd-109">从开始在当前光标位置处的集合获取指定的数目的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="d0ecd-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0ecd-110">备注</span><span class="sxs-lookup"><span data-stu-id="d0ecd-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d0ecd-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d0ecd-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0ecd-112">要求</span><span class="sxs-lookup"><span data-stu-id="d0ecd-112">Requirements</span></span>  
 <span data-ttu-id="d0ecd-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0ecd-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0ecd-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0ecd-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0ecd-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0ecd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0ecd-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0ecd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0ecd-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0ecd-117">See Also</span></span>  
 [<span data-ttu-id="d0ecd-118">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="d0ecd-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="d0ecd-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="d0ecd-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
