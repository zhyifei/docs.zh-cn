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
ms.openlocfilehash: 5c6ef901f43cd6568f17657ed8e58bc2cc2cc0a1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61922260"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="ca5cc-102">ICorDebugAppDomain2 接口</span><span class="sxs-lookup"><span data-stu-id="ca5cc-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="ca5cc-103">提供方法以使用数组、 指针、 函数指针和引用类型。</span><span class="sxs-lookup"><span data-stu-id="ca5cc-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="ca5cc-104">此接口是 ICorDebugAppDomain 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="ca5cc-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ca5cc-105">方法</span><span class="sxs-lookup"><span data-stu-id="ca5cc-105">Methods</span></span>  
  
|<span data-ttu-id="ca5cc-106">方法</span><span class="sxs-lookup"><span data-stu-id="ca5cc-106">Method</span></span>|<span data-ttu-id="ca5cc-107">描述</span><span class="sxs-lookup"><span data-stu-id="ca5cc-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ca5cc-108">GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="ca5cc-108">GetArrayOrPointerType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="ca5cc-109">获取指定的类型或指针或引用为指定类型的数组。</span><span class="sxs-lookup"><span data-stu-id="ca5cc-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="ca5cc-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="ca5cc-110">GetFunctionPointerType</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="ca5cc-111">获取一个指向具有给定的签名的函数。</span><span class="sxs-lookup"><span data-stu-id="ca5cc-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca5cc-112">备注</span><span class="sxs-lookup"><span data-stu-id="ca5cc-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ca5cc-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="ca5cc-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca5cc-114">要求</span><span class="sxs-lookup"><span data-stu-id="ca5cc-114">Requirements</span></span>  
 <span data-ttu-id="ca5cc-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca5cc-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca5cc-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca5cc-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca5cc-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca5cc-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca5cc-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca5cc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca5cc-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ca5cc-119">See also</span></span>

- [<span data-ttu-id="ca5cc-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="ca5cc-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
