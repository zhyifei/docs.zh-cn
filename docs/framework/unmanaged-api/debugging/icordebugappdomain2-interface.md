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
ms.openlocfilehash: 6f9bcec66ff613d19c1198ac9849ca28c978f537
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788945"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="9a8a1-102">ICorDebugAppDomain2 接口</span><span class="sxs-lookup"><span data-stu-id="9a8a1-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="9a8a1-103">提供使用数组、指针、函数指针和引用类型的方法。</span><span class="sxs-lookup"><span data-stu-id="9a8a1-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="9a8a1-104">此接口是 ICorDebugAppDomain 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="9a8a1-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a8a1-105">方法</span><span class="sxs-lookup"><span data-stu-id="9a8a1-105">Methods</span></span>  
  
|<span data-ttu-id="9a8a1-106">方法</span><span class="sxs-lookup"><span data-stu-id="9a8a1-106">Method</span></span>|<span data-ttu-id="9a8a1-107">描述</span><span class="sxs-lookup"><span data-stu-id="9a8a1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a8a1-108">GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="9a8a1-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="9a8a1-109">获取指定类型的数组，或指定类型的指针或引用。</span><span class="sxs-lookup"><span data-stu-id="9a8a1-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="9a8a1-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="9a8a1-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="9a8a1-111">获取一个指针，该指针指向具有给定签名的函数。</span><span class="sxs-lookup"><span data-stu-id="9a8a1-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a8a1-112">备注</span><span class="sxs-lookup"><span data-stu-id="9a8a1-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9a8a1-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="9a8a1-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a8a1-114">需求</span><span class="sxs-lookup"><span data-stu-id="9a8a1-114">Requirements</span></span>  
 <span data-ttu-id="9a8a1-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="9a8a1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a8a1-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9a8a1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9a8a1-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9a8a1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9a8a1-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a8a1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a8a1-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9a8a1-119">See also</span></span>

- [<span data-ttu-id="9a8a1-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="9a8a1-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
