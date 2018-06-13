---
title: ICorDebugAppDomain3 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain3
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain3
helpviewer_keywords:
- ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c130b92fd5114d067730da3b7cd138d98cf0577
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407400"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="e7354-102">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="e7354-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="e7354-103">提供用于检索有关托管表示形式的信息方法[!INCLUDE[wrt](../../../../includes/wrt-md.md)]当前加载的应用程序域中的类型。</span><span class="sxs-lookup"><span data-stu-id="e7354-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="e7354-104">此接口是 ICorDebugAppDomain 和 ICorDebugAppDomain2 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="e7354-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e7354-105">方法</span><span class="sxs-lookup"><span data-stu-id="e7354-105">Methods</span></span>  
  
|<span data-ttu-id="e7354-106">方法</span><span class="sxs-lookup"><span data-stu-id="e7354-106">Method</span></span>|<span data-ttu-id="e7354-107">描述</span><span class="sxs-lookup"><span data-stu-id="e7354-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e7354-108">Icordebugappdomain3:: Getcachedwinrttypes</span><span class="sxs-lookup"><span data-stu-id="e7354-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="e7354-109">获取所有缓存的枚举数[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="e7354-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="e7354-110">Icordebugappdomain3:: Getcachedwinrttypesforiids</span><span class="sxs-lookup"><span data-stu-id="e7354-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="e7354-111">获取一个枚举器，为缓存[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中的类型基于其接口标识符。</span><span class="sxs-lookup"><span data-stu-id="e7354-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e7354-112">备注</span><span class="sxs-lookup"><span data-stu-id="e7354-112">Remarks</span></span>  
 <span data-ttu-id="e7354-113">此接口旨在由结合函数评估调用调试器使用`M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`。</span><span class="sxs-lookup"><span data-stu-id="e7354-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="e7354-114">当方法检索支持的接口标识符[!INCLUDE[wrt](../../../../includes/wrt-md.md)]服务器对象时，调试器可能使用此接口中定义的方法可将其映射为对应于这些接口的托管类型。</span><span class="sxs-lookup"><span data-stu-id="e7354-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="e7354-115">若要检索此接口的实例，运行`QueryInterface`ICorDebugAppDomain 或 ICorDebugAppDomain2 接口的实例上。</span><span class="sxs-lookup"><span data-stu-id="e7354-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e7354-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="e7354-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7354-117">要求</span><span class="sxs-lookup"><span data-stu-id="e7354-117">Requirements</span></span>  
 <span data-ttu-id="e7354-118">**平台：** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7354-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="e7354-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7354-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7354-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7354-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7354-121">**.NET framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7354-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7354-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="e7354-122">See Also</span></span>  
 [<span data-ttu-id="e7354-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="e7354-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
