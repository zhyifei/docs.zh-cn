---
title: ICorDebugClass 接口
ms.date: 03/30/2017
api_name:
- ICorDebugClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass
helpviewer_keywords:
- ICorDebugClass interface [.NET Framework debugging]
ms.assetid: 03a6facb-f12f-49be-9839-e73b9c791cd5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7e1ad830e728fbe764085a5808a48e4cacedc595
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133622"
---
# <a name="icordebugclass-interface"></a><span data-ttu-id="de875-102">ICorDebugClass 接口</span><span class="sxs-lookup"><span data-stu-id="de875-102">ICorDebugClass Interface</span></span>

<span data-ttu-id="de875-103">表示基类型或复杂类型（即用户定义的类型）。</span><span class="sxs-lookup"><span data-stu-id="de875-103">Represents a type, which can be either basic or complex (that is, user-defined).</span></span> <span data-ttu-id="de875-104">如果该类型为泛型类型，则 `ICorDebugClass` 表示实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="de875-104">If the type is generic, `ICorDebugClass` represents the uninstantiated generic type.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="de875-105">方法</span><span class="sxs-lookup"><span data-stu-id="de875-105">Methods</span></span>  
  
|<span data-ttu-id="de875-106">方法</span><span class="sxs-lookup"><span data-stu-id="de875-106">Method</span></span>|<span data-ttu-id="de875-107">描述</span><span class="sxs-lookup"><span data-stu-id="de875-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="de875-108">GetModule 方法</span><span class="sxs-lookup"><span data-stu-id="de875-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getmodule-method.md)|<span data-ttu-id="de875-109">获取定义此类的模块。</span><span class="sxs-lookup"><span data-stu-id="de875-109">Gets the module that defines this class.</span></span>|  
|[<span data-ttu-id="de875-110">GetStaticFieldValue 方法</span><span class="sxs-lookup"><span data-stu-id="de875-110">GetStaticFieldValue Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-getstaticfieldvalue-method.md)|<span data-ttu-id="de875-111">获取指定的静态字段的值。</span><span class="sxs-lookup"><span data-stu-id="de875-111">Gets the value of the specified static field.</span></span>|  
|[<span data-ttu-id="de875-112">GetToken 方法</span><span class="sxs-lookup"><span data-stu-id="de875-112">GetToken Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-gettoken-method.md)|<span data-ttu-id="de875-113">获取`TypeDef`此类的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="de875-113">Gets the `TypeDef` metadata token for this class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de875-114">备注</span><span class="sxs-lookup"><span data-stu-id="de875-114">Remarks</span></span>  
 <span data-ttu-id="de875-115">`ICorDebugClass`接口表示未实例化的泛型类型。</span><span class="sxs-lookup"><span data-stu-id="de875-115">The `ICorDebugClass` interface represents an uninstantiated generic type.</span></span> <span data-ttu-id="de875-116">ICorDebugType 接口表示实例化泛型类型。</span><span class="sxs-lookup"><span data-stu-id="de875-116">The ICorDebugType interface represents an instantiated generic type.</span></span> <span data-ttu-id="de875-117">例如，`Hashtable<K, V>`将由表示`ICorDebugClass`，而`Hashtable<Int32, String>`将由表示`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="de875-117">For example, `Hashtable<K, V>` would be represented by `ICorDebugClass`, whereas `Hashtable<Int32, String>` would be represented by `ICorDebugType`.</span></span>  
  
 <span data-ttu-id="de875-118">非泛型类型表示由`ICorDebugClass`和`ICorDebugType`。</span><span class="sxs-lookup"><span data-stu-id="de875-118">Non-generic types are represented by both `ICorDebugClass` and `ICorDebugType`.</span></span> <span data-ttu-id="de875-119">在处理类型实例化在.NET Framework 2.0 版中引入的后一种接口。</span><span class="sxs-lookup"><span data-stu-id="de875-119">The latter interface was introduced in the .NET Framework version 2.0 to deal with type instantiation.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="de875-120">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="de875-120">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de875-121">要求</span><span class="sxs-lookup"><span data-stu-id="de875-121">Requirements</span></span>  
 <span data-ttu-id="de875-122">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="de875-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de875-123">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="de875-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="de875-124">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="de875-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="de875-125">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="de875-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="de875-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="de875-126">See also</span></span>

- [<span data-ttu-id="de875-127">调试接口</span><span class="sxs-lookup"><span data-stu-id="de875-127">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
