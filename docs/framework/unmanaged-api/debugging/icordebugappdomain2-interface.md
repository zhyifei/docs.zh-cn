---
title: ICorDebugAppDomain2 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain2
helpviewer_keywords:
- ICorDebugAppDomain2 interface [.NET Framework debugging]
ms.assetid: 314d29f3-feb0-4a92-9530-b569c280cc31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 63772c6642cc6f7f96a375beab4f7ef1b4884139
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69959848"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="8aaf7-102">ICorDebugAppDomain2 接口</span><span class="sxs-lookup"><span data-stu-id="8aaf7-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="8aaf7-103">提供使用数组、指针、函数指针和引用类型的方法。</span><span class="sxs-lookup"><span data-stu-id="8aaf7-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="8aaf7-104">此接口是 ICorDebugAppDomain 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="8aaf7-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8aaf7-105">方法</span><span class="sxs-lookup"><span data-stu-id="8aaf7-105">Methods</span></span>  
  
|<span data-ttu-id="8aaf7-106">方法</span><span class="sxs-lookup"><span data-stu-id="8aaf7-106">Method</span></span>|<span data-ttu-id="8aaf7-107">描述</span><span class="sxs-lookup"><span data-stu-id="8aaf7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8aaf7-108">GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="8aaf7-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="8aaf7-109">获取指定类型的数组, 或指定类型的指针或引用。</span><span class="sxs-lookup"><span data-stu-id="8aaf7-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="8aaf7-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="8aaf7-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="8aaf7-111">获取一个指针, 该指针指向具有给定签名的函数。</span><span class="sxs-lookup"><span data-stu-id="8aaf7-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8aaf7-112">备注</span><span class="sxs-lookup"><span data-stu-id="8aaf7-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8aaf7-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="8aaf7-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aaf7-114">要求</span><span class="sxs-lookup"><span data-stu-id="8aaf7-114">Requirements</span></span>  
 <span data-ttu-id="8aaf7-115">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8aaf7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aaf7-116">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="8aaf7-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8aaf7-117">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8aaf7-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8aaf7-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aaf7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aaf7-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="8aaf7-119">See also</span></span>

- [<span data-ttu-id="8aaf7-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="8aaf7-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
