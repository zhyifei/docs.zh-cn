---
title: "ICorDebugInstanceFieldSymbol 接口"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fbf3f07f5669c4fcafa4d3cc4119fc715539651d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="icordebuginstancefieldsymbol-interface"></a><span data-ttu-id="acfdb-102">ICorDebugInstanceFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="acfdb-102">ICorDebugInstanceFieldSymbol Interface</span></span>
<span data-ttu-id="acfdb-103">表示某一实例字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="acfdb-103">Represents the debug symbol information for an instance field.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="acfdb-104">方法</span><span class="sxs-lookup"><span data-stu-id="acfdb-104">Methods</span></span>  
  
|<span data-ttu-id="acfdb-105">方法</span><span class="sxs-lookup"><span data-stu-id="acfdb-105">Method</span></span>|<span data-ttu-id="acfdb-106">描述</span><span class="sxs-lookup"><span data-stu-id="acfdb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="acfdb-107">GetName 方法</span><span class="sxs-lookup"><span data-stu-id="acfdb-107">GetName Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getname-method.md)|<span data-ttu-id="acfdb-108">获取实例字段的名称。</span><span class="sxs-lookup"><span data-stu-id="acfdb-108">Gets the name of the instance field.</span></span>|  
|[<span data-ttu-id="acfdb-109">GetOffset 方法</span><span class="sxs-lookup"><span data-stu-id="acfdb-109">GetOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getoffset-method.md)|<span data-ttu-id="acfdb-110">获取父类中此示例字段的偏移量（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="acfdb-110">Gets the offset in bytes of this instance field in its parent class.</span></span>|  
|[<span data-ttu-id="acfdb-111">GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="acfdb-111">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-getsize-method.md)|<span data-ttu-id="acfdb-112">获取实例字段的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="acfdb-112">Gets the size in bytes of the instance field.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="acfdb-113">备注</span><span class="sxs-lookup"><span data-stu-id="acfdb-113">Remarks</span></span>  
 <span data-ttu-id="acfdb-114">`ICorDebugInstanceFieldSymbol` 接口用于检索实例字段的调试符号信息。</span><span class="sxs-lookup"><span data-stu-id="acfdb-114">The `ICorDebugInstanceFieldSymbol` interface is used to retrieve the debug symbol information for an instance field.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="acfdb-115">此接口仅适用于 .NET Native。</span><span class="sxs-lookup"><span data-stu-id="acfdb-115">This interface is available with .NET Native only.</span></span> <span data-ttu-id="acfdb-116">如果在 .NET Native 外为 ICorDebug 方案实现此接口，则公共语言运行时将忽略此接口。</span><span class="sxs-lookup"><span data-stu-id="acfdb-116">If you implement this interface for ICorDebug scenarios outside of .NET Native, the common language runtime will ignore this interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acfdb-117">要求</span><span class="sxs-lookup"><span data-stu-id="acfdb-117">Requirements</span></span>  
 <span data-ttu-id="acfdb-118">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="acfdb-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acfdb-119">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="acfdb-119">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="acfdb-120">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="acfdb-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="acfdb-121">**.NET framework 版本：**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acfdb-121">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acfdb-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="acfdb-122">See Also</span></span>  
 [<span data-ttu-id="acfdb-123">ICorDebugStaticFieldSymbol 接口</span><span class="sxs-lookup"><span data-stu-id="acfdb-123">ICorDebugStaticFieldSymbol Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md)  
 [<span data-ttu-id="acfdb-124">调试接口</span><span class="sxs-lookup"><span data-stu-id="acfdb-124">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="acfdb-125">调试</span><span class="sxs-lookup"><span data-stu-id="acfdb-125">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
