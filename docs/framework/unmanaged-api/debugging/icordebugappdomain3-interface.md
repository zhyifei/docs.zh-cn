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
ms.openlocfilehash: 7c141ca9a8e1c74015883f45cb2eaa9183bb3d89
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59177523"
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="ff31a-102">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="ff31a-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="ff31a-103">提供方法来检索有关托管表示形式的信息[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中当前加载的类型。</span><span class="sxs-lookup"><span data-stu-id="ff31a-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="ff31a-104">此接口是 ICorDebugAppDomain 和 ICorDebugAppDomain2 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="ff31a-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ff31a-105">方法</span><span class="sxs-lookup"><span data-stu-id="ff31a-105">Methods</span></span>  
  
|<span data-ttu-id="ff31a-106">方法</span><span class="sxs-lookup"><span data-stu-id="ff31a-106">Method</span></span>|<span data-ttu-id="ff31a-107">描述</span><span class="sxs-lookup"><span data-stu-id="ff31a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ff31a-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span><span class="sxs-lookup"><span data-stu-id="ff31a-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="ff31a-109">获取所有缓存的枚举器[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="ff31a-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="ff31a-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span><span class="sxs-lookup"><span data-stu-id="ff31a-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="ff31a-111">获取一个枚举器的缓存[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中的类型基于其接口标识符。</span><span class="sxs-lookup"><span data-stu-id="ff31a-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ff31a-112">备注</span><span class="sxs-lookup"><span data-stu-id="ff31a-112">Remarks</span></span>  
 <span data-ttu-id="ff31a-113">此接口旨在由结合函数评估调用调试器使用`M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`。</span><span class="sxs-lookup"><span data-stu-id="ff31a-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="ff31a-114">当方法检索支持的接口标识符[!INCLUDE[wrt](../../../../includes/wrt-md.md)]服务器对象，调试器可能使用此接口中定义的方法将其映射到对应于这些接口的托管类型。</span><span class="sxs-lookup"><span data-stu-id="ff31a-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="ff31a-115">若要检索此接口的实例，请运行`QueryInterface`ICorDebugAppDomain 或 ICorDebugAppDomain2 接口的实例上。</span><span class="sxs-lookup"><span data-stu-id="ff31a-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ff31a-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ff31a-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff31a-117">要求</span><span class="sxs-lookup"><span data-stu-id="ff31a-117">Requirements</span></span>  
 **<span data-ttu-id="ff31a-118">平台：</span><span class="sxs-lookup"><span data-stu-id="ff31a-118">Platforms:</span></span>** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]  
  
 <span data-ttu-id="ff31a-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ff31a-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ff31a-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff31a-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ff31a-121">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="ff31a-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ff31a-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="ff31a-122">See also</span></span>

- [<span data-ttu-id="ff31a-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="ff31a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
