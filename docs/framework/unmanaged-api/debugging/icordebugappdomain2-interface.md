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
ms.openlocfilehash: 1643d91f373ff233540026440ee21aa4c146f3e3
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895136"
---
# <a name="icordebugappdomain2-interface"></a><span data-ttu-id="d3143-102">ICorDebugAppDomain2 接口</span><span class="sxs-lookup"><span data-stu-id="d3143-102">ICorDebugAppDomain2 Interface</span></span>

<span data-ttu-id="d3143-103">提供使用数组、指针、函数指针和引用类型的方法。</span><span class="sxs-lookup"><span data-stu-id="d3143-103">Provides methods to work with arrays, pointers, function pointers, and reference types.</span></span> <span data-ttu-id="d3143-104">此接口是 ICorDebugAppDomain 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="d3143-104">This interface is an extension of the ICorDebugAppDomain interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3143-105">方法</span><span class="sxs-lookup"><span data-stu-id="d3143-105">Methods</span></span>  
  
|<span data-ttu-id="d3143-106">方法</span><span class="sxs-lookup"><span data-stu-id="d3143-106">Method</span></span>|<span data-ttu-id="d3143-107">说明</span><span class="sxs-lookup"><span data-stu-id="d3143-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3143-108">GetArrayOrPointerType 方法</span><span class="sxs-lookup"><span data-stu-id="d3143-108">GetArrayOrPointerType Method</span></span>](icordebugappdomain2-getarrayorpointertype-method.md)|<span data-ttu-id="d3143-109">获取指定类型的数组，或指定类型的指针或引用。</span><span class="sxs-lookup"><span data-stu-id="d3143-109">Gets an array of the specified type, or a pointer or reference to the specified type.</span></span>|  
|[<span data-ttu-id="d3143-110">GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="d3143-110">GetFunctionPointerType</span></span>](icordebugappdomain2-getfunctionpointertype-method.md)|<span data-ttu-id="d3143-111">获取一个指针，该指针指向具有给定签名的函数。</span><span class="sxs-lookup"><span data-stu-id="d3143-111">Gets a pointer to a function that has a given signature.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d3143-112">备注</span><span class="sxs-lookup"><span data-stu-id="d3143-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d3143-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d3143-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3143-114">要求</span><span class="sxs-lookup"><span data-stu-id="d3143-114">Requirements</span></span>  
 <span data-ttu-id="d3143-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d3143-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3143-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3143-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3143-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3143-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3143-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3143-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3143-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3143-119">See also</span></span>

- [<span data-ttu-id="d3143-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="d3143-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
