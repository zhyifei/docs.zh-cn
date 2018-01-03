---
title: "ICorDebugAppDomain2 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2
helpviewer_keywords: ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c811107fcf32696aee17810af06ac0b2ddc9102d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugappdomain2-interface1"></a><span data-ttu-id="24370-102">ICorDebugAppDomain2 接口 1</span><span class="sxs-lookup"><span data-stu-id="24370-102">ICorDebugAppDomain2 Interface1</span></span>
<span data-ttu-id="24370-103">提供处理数组、 指针、 函数指针和引用类型的方法。</span><span class="sxs-lookup"><span data-stu-id="24370-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="24370-104">此接口是 ICorDebugAppDomain 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="24370-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24370-105">方法</span><span class="sxs-lookup"><span data-stu-id="24370-105">Methods</span></span>  
  
|<span data-ttu-id="24370-106">方法</span><span class="sxs-lookup"><span data-stu-id="24370-106">Method</span></span>|<span data-ttu-id="24370-107">描述</span><span class="sxs-lookup"><span data-stu-id="24370-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24370-108">GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="24370-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="24370-109">获取指定的类型、 指针或对指定的类型引用的数组。</span><span class="sxs-lookup"><span data-stu-id="24370-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="24370-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="24370-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="24370-111">获取一个指向具有给定的签名的函数。</span><span class="sxs-lookup"><span data-stu-id="24370-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="24370-112">备注</span><span class="sxs-lookup"><span data-stu-id="24370-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="24370-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="24370-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24370-114">惠?</span><span class="sxs-lookup"><span data-stu-id="24370-114">Requirements</span></span>  
 <span data-ttu-id="24370-115">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24370-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24370-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="24370-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="24370-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="24370-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="24370-118">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24370-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24370-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="24370-119">See Also</span></span>  
 [<span data-ttu-id="24370-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="24370-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
