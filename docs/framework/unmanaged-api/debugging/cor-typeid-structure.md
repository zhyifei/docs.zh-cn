---
title: "COR_TYPEID 结构"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_TYPEID
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_TYPEID
helpviewer_keywords: COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ca6c9b3b02314843a3eaf01d8cd4a9eac5513efa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="cortypeid-structure"></a><span data-ttu-id="d8448-102">COR_TYPEID 结构</span><span class="sxs-lookup"><span data-stu-id="d8448-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="d8448-103">包含类型标识符。</span><span class="sxs-lookup"><span data-stu-id="d8448-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8448-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8448-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="d8448-105">成员</span><span class="sxs-lookup"><span data-stu-id="d8448-105">Members</span></span>  
  
|<span data-ttu-id="d8448-106">成员</span><span class="sxs-lookup"><span data-stu-id="d8448-106">Member</span></span>|<span data-ttu-id="d8448-107">描述</span><span class="sxs-lookup"><span data-stu-id="d8448-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="d8448-108">第一个标记。</span><span class="sxs-lookup"><span data-stu-id="d8448-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="d8448-109">第二个标记。</span><span class="sxs-lookup"><span data-stu-id="d8448-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8448-110">备注</span><span class="sxs-lookup"><span data-stu-id="d8448-110">Remarks</span></span>  
 <span data-ttu-id="d8448-111">`COR_TYPEID`结构返回由大量调试方法，提供有关要进行垃圾回收的对象的信息。</span><span class="sxs-lookup"><span data-stu-id="d8448-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="d8448-112">它可以然后作为参数传递给其他调试的方法，提供有关该项目的其他信息。</span><span class="sxs-lookup"><span data-stu-id="d8448-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="d8448-113">例如，通过枚举[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)对象，你可以检索各个[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)表示托管堆上的单个对象的对象。</span><span class="sxs-lookup"><span data-stu-id="d8448-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="d8448-114">然后可以将传递`COR_TYPEID`值从`COR_HEAPOBJECT.type`字段[icordebugprocess5:: Gettypefortypeid](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)方法来检索一个 ICorDebugType 对象，提供有关对象的类型信息。</span><span class="sxs-lookup"><span data-stu-id="d8448-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="d8448-115">A`COR_TYPEID`对象用于不透明。</span><span class="sxs-lookup"><span data-stu-id="d8448-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="d8448-116">其各个字段不应访问或操作。</span><span class="sxs-lookup"><span data-stu-id="d8448-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="d8448-117">其唯一的用途是作为标识符用作`out`中参数的方法调用和可，反过来，传递给其他方法来提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="d8448-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8448-118">惠?</span><span class="sxs-lookup"><span data-stu-id="d8448-118">Requirements</span></span>  
 <span data-ttu-id="d8448-119">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8448-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8448-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8448-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8448-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8448-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8448-122">**.NET framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8448-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8448-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8448-123">See Also</span></span>  
 [<span data-ttu-id="d8448-124">调试结构</span><span class="sxs-lookup"><span data-stu-id="d8448-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="d8448-125">调试</span><span class="sxs-lookup"><span data-stu-id="d8448-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
