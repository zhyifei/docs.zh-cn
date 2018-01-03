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
ms.workload: dotnet
ms.openlocfilehash: e5d3d11e3897ff56ffcd475eb363405651578c1c
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomainenum-interface1"></a><span data-ttu-id="a4ec3-102">ICorDebugAppDomainEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="a4ec3-102">ICorDebugAppDomainEnum Interface1</span></span>
<span data-ttu-id="a4ec3-103">提供`Next`方法，返回指定的数目的`ICorDebugAppDomainEnum`枚举中的下一个位置开始的值。</span><span class="sxs-lookup"><span data-stu-id="a4ec3-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="a4ec3-104">此接口是"ICorDebugEnum"的子类。</span><span class="sxs-lookup"><span data-stu-id="a4ec3-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a4ec3-105">方法</span><span class="sxs-lookup"><span data-stu-id="a4ec3-105">Methods</span></span>  
  
|<span data-ttu-id="a4ec3-106">方法</span><span class="sxs-lookup"><span data-stu-id="a4ec3-106">Method</span></span>|<span data-ttu-id="a4ec3-107">描述</span><span class="sxs-lookup"><span data-stu-id="a4ec3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a4ec3-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="a4ec3-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="a4ec3-109">从开始在当前光标位置处的集合获取指定的数目的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="a4ec3-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a4ec3-110">备注</span><span class="sxs-lookup"><span data-stu-id="a4ec3-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a4ec3-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a4ec3-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4ec3-112">惠?</span><span class="sxs-lookup"><span data-stu-id="a4ec3-112">Requirements</span></span>  
 <span data-ttu-id="a4ec3-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4ec3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4ec3-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a4ec3-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a4ec3-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4ec3-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4ec3-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4ec3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4ec3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4ec3-117">See Also</span></span>  
 [<span data-ttu-id="a4ec3-118">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="a4ec3-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="a4ec3-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="a4ec3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
