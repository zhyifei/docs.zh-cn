---
title: "ICorDebugGuidToTypeEnum 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9993a5aaaef3d5b83d21e3641029af12119188da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="34557-102">ICorDebugGuidToTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="34557-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="34557-103">提供定义一组的 Guid 和其相应的类型，由 ICorDebugType 实例之间的映射的枚举器。</span><span class="sxs-lookup"><span data-stu-id="34557-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="34557-104">此接口继承自 ICorDebugEnum 接口的方法。</span><span class="sxs-lookup"><span data-stu-id="34557-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="34557-105">方法</span><span class="sxs-lookup"><span data-stu-id="34557-105">Methods</span></span>  
  
|<span data-ttu-id="34557-106">方法</span><span class="sxs-lookup"><span data-stu-id="34557-106">Method</span></span>|<span data-ttu-id="34557-107">描述</span><span class="sxs-lookup"><span data-stu-id="34557-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="34557-108">Icordebugguidtotypeenum:: Next</span><span class="sxs-lookup"><span data-stu-id="34557-108">ICorDebugGuidToTypeEnum::Next</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="34557-109">获取指定的数目的[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)映射 Guid 类型信息的实例。</span><span class="sxs-lookup"><span data-stu-id="34557-109">Gets the specified number of [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34557-110">备注</span><span class="sxs-lookup"><span data-stu-id="34557-110">Remarks</span></span>  
 <span data-ttu-id="34557-111">`ICorDebugGuidToTypeEnum`接口对象可通过调用检索[icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="34557-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="34557-112">调试器可以调用此接口[下一步](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md)方法来检索[CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md)管理表示形式表示的映射的对象[!INCLUDE[wrt](../../../../includes/wrt-md.md)]中加载的类型用于对调用应用程序域[icordebugappdomain3:: Getcachedwinrttypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="34557-112">A debugger can call this interface's [Next](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](../../../../docs/framework/unmanaged-api/debugging/cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34557-113">惠?</span><span class="sxs-lookup"><span data-stu-id="34557-113">Requirements</span></span>  
 <span data-ttu-id="34557-114">**平台：**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34557-114">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="34557-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="34557-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="34557-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="34557-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="34557-117">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34557-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34557-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="34557-118">See Also</span></span>  
 [<span data-ttu-id="34557-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="34557-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
