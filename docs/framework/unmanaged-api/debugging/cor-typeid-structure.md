---
title: COR_TYPEID 结构
ms.date: 03/30/2017
api_name:
- COR_TYPEID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_TYPEID
helpviewer_keywords:
- COR_TYPEID structure [.NET Framework debugging]
ms.assetid: 1e172b14-ee22-4943-b3b8-3740e7bdcd2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51104516008ffee0694c72733cb5f82b5ba6d8cf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609435"
---
# <a name="cortypeid-structure"></a><span data-ttu-id="8bdae-102">COR_TYPEID 结构</span><span class="sxs-lookup"><span data-stu-id="8bdae-102">COR_TYPEID Structure</span></span>
<span data-ttu-id="8bdae-103">包含类型标识符。</span><span class="sxs-lookup"><span data-stu-id="8bdae-103">Contains a type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bdae-104">语法</span><span class="sxs-lookup"><span data-stu-id="8bdae-104">Syntax</span></span>  
  
```  
typedef struct COR_TYPEID{  
    UINT64 token1;  
    UINT64 token2;  
} COR_TYPEID;  
```  
  
## <a name="members"></a><span data-ttu-id="8bdae-105">成员</span><span class="sxs-lookup"><span data-stu-id="8bdae-105">Members</span></span>  
  
|<span data-ttu-id="8bdae-106">成员</span><span class="sxs-lookup"><span data-stu-id="8bdae-106">Member</span></span>|<span data-ttu-id="8bdae-107">描述</span><span class="sxs-lookup"><span data-stu-id="8bdae-107">Description</span></span>|  
|------------|-----------------|  
|`token1`|<span data-ttu-id="8bdae-108">第一个标记。</span><span class="sxs-lookup"><span data-stu-id="8bdae-108">The first token.</span></span>|  
|`token2`|<span data-ttu-id="8bdae-109">第二个标记。</span><span class="sxs-lookup"><span data-stu-id="8bdae-109">The second token.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8bdae-110">备注</span><span class="sxs-lookup"><span data-stu-id="8bdae-110">Remarks</span></span>  
 <span data-ttu-id="8bdae-111">`COR_TYPEID`结构返回的大量调试方法，提供要进行垃圾回收的对象有关的信息。</span><span class="sxs-lookup"><span data-stu-id="8bdae-111">The `COR_TYPEID` structure is returned by a number of debugging methods that provide information about objects to be garbage-collected.</span></span> <span data-ttu-id="8bdae-112">它可以然后作为参数传递到其他调试方法，提供与项相关的其他信息。</span><span class="sxs-lookup"><span data-stu-id="8bdae-112">It can then be passed as an argument to other debugging methods that provide additional information about that item.</span></span> <span data-ttu-id="8bdae-113">例如，通过枚举[ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)对象，您可以检索各个[COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md)表示托管堆上的单个对象的对象。</span><span class="sxs-lookup"><span data-stu-id="8bdae-113">For example, by enumerating an [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) object, you can retrieve individual [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) objects that represent individual objects on the managed heap.</span></span> <span data-ttu-id="8bdae-114">然后，可以传递`COR_TYPEID`值从`COR_HEAPOBJECT.type`字段[ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md)方法来检索一个 ICorDebugType 对象，提供有关对象的类型信息。</span><span class="sxs-lookup"><span data-stu-id="8bdae-114">You can then pass the `COR_TYPEID` value from the `COR_HEAPOBJECT.type` field to the [ICorDebugProcess5::GetTypeForTypeID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-gettypefortypeid-method.md) method to retrieve an ICorDebugType object that provides type information about the object.</span></span>  
  
 <span data-ttu-id="8bdae-115">一个`COR_TYPEID`旨在不透明对象。</span><span class="sxs-lookup"><span data-stu-id="8bdae-115">A `COR_TYPEID` object is intended to be opaque.</span></span> <span data-ttu-id="8bdae-116">其各个字段不应访问或操作。</span><span class="sxs-lookup"><span data-stu-id="8bdae-116">Its individual fields should not be accessed or manipulated.</span></span> <span data-ttu-id="8bdae-117">其唯一用途是作为提供的标识符作为`out`中参数的方法调用和可，反过来，传递给其他方法，以提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="8bdae-117">Its sole use is as an identifier that is provided as an `out` parameter in a method call and that can, in turn, be passed to other methods to provide additional information.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bdae-118">要求</span><span class="sxs-lookup"><span data-stu-id="8bdae-118">Requirements</span></span>  
 <span data-ttu-id="8bdae-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bdae-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bdae-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8bdae-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8bdae-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8bdae-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8bdae-122">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bdae-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bdae-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="8bdae-123">See also</span></span>

- [<span data-ttu-id="8bdae-124">调试结构</span><span class="sxs-lookup"><span data-stu-id="8bdae-124">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="8bdae-125">调试</span><span class="sxs-lookup"><span data-stu-id="8bdae-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
