---
title: "ICorDebugAppDomain3 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain3
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain3
helpviewer_keywords: ICorDebugAppDomain3 interface [.NET Framework debugging]
ms.assetid: 875ef5be-c1e7-4d95-97e9-d3a667aeaba0
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 08f125d7fc388a9b2d31c9cc1cebf2605ffa7e23
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain3-interface"></a><span data-ttu-id="982cd-102">ICorDebugAppDomain3 接口</span><span class="sxs-lookup"><span data-stu-id="982cd-102">ICorDebugAppDomain3 Interface</span></span>
<span data-ttu-id="982cd-103">提供用于检索有关托管表示形式的信息方法[!INCLUDE[wrt](../../../../includes/wrt-md.md)]当前加载的应用程序域中的类型。</span><span class="sxs-lookup"><span data-stu-id="982cd-103">Provides methods to retrieve information about the managed representations of [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types currently loaded in an application domain.</span></span> <span data-ttu-id="982cd-104">此接口是 ICorDebugAppDomain 和 ICorDebugAppDomain2 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="982cd-104">This interface is an extension of the ICorDebugAppDomain and ICorDebugAppDomain2 interfaces.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="982cd-105">方法</span><span class="sxs-lookup"><span data-stu-id="982cd-105">Methods</span></span>  
  
|<span data-ttu-id="982cd-106">方法</span><span class="sxs-lookup"><span data-stu-id="982cd-106">Method</span></span>|<span data-ttu-id="982cd-107">描述</span><span class="sxs-lookup"><span data-stu-id="982cd-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="982cd-108">Icordebugappdomain3:: Getcachedwinrttypes</span><span class="sxs-lookup"><span data-stu-id="982cd-108">ICorDebugAppDomain3::GetCachedWinRTTypes</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypes-method.md)|<span data-ttu-id="982cd-109">获取所有缓存的枚举数[!INCLUDE[wrt](../../../../includes/wrt-md.md)]类型。</span><span class="sxs-lookup"><span data-stu-id="982cd-109">Gets an enumerator for all cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types.</span></span>|  
|[<span data-ttu-id="982cd-110">Icordebugappdomain3:: Getcachedwinrttypesforiids</span><span class="sxs-lookup"><span data-stu-id="982cd-110">ICorDebugAppDomain3::GetCachedWinRTTypesForIIDs</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain3-getcachedwinrttypesforiids-method.md)|<span data-ttu-id="982cd-111">获取一个枚举器，为缓存[!INCLUDE[wrt](../../../../includes/wrt-md.md)]应用程序域中的类型基于其接口标识符。</span><span class="sxs-lookup"><span data-stu-id="982cd-111">Gets an enumerator for cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] types in an application domain based on their interface identifiers.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="982cd-112">备注</span><span class="sxs-lookup"><span data-stu-id="982cd-112">Remarks</span></span>  
 <span data-ttu-id="982cd-113">此接口旨在由结合函数评估调用调试器使用`M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`。</span><span class="sxs-lookup"><span data-stu-id="982cd-113">This interface is meant to be used by a debugger in conjunction with a function evaluation call to `M:System.Runtime.InteropServices.Marshal.GetInspectableIIDs(System.Object)`.</span></span> <span data-ttu-id="982cd-114">当方法检索支持的接口标识符[!INCLUDE[wrt](../../../../includes/wrt-md.md)]服务器对象时，调试器可能使用此接口中定义的方法可将其映射为对应于这些接口的托管类型。</span><span class="sxs-lookup"><span data-stu-id="982cd-114">When the method retrieves the interface identifiers supported by a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] server object, the debugger may use the methods defined in this interface to map them to managed types that correspond to those interfaces.</span></span>  
  
 <span data-ttu-id="982cd-115">若要检索此接口的实例，运行`QueryInterface`ICorDebugAppDomain 或 ICorDebugAppDomain2 接口的实例上。</span><span class="sxs-lookup"><span data-stu-id="982cd-115">To retrieve an instance of this interface, run `QueryInterface` on an instance of the ICorDebugAppDomain or ICorDebugAppDomain2 interface.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="982cd-116">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="982cd-116">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="982cd-117">要求</span><span class="sxs-lookup"><span data-stu-id="982cd-117">Requirements</span></span>  
 <span data-ttu-id="982cd-118">**平台：**[!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span><span class="sxs-lookup"><span data-stu-id="982cd-118">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)]</span></span>  
  
 <span data-ttu-id="982cd-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="982cd-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="982cd-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="982cd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="982cd-121">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="982cd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="982cd-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="982cd-122">See Also</span></span>  
 [<span data-ttu-id="982cd-123">调试接口</span><span class="sxs-lookup"><span data-stu-id="982cd-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
