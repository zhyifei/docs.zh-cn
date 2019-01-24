---
title: ICorDebugClass2 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb70016560f453caf7a7a3eed3e1aa6b5fc9f0ef
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557354"
---
# <a name="icordebugclass2-interface1"></a><span data-ttu-id="48746-102">ICorDebugClass2 接口 1</span><span class="sxs-lookup"><span data-stu-id="48746-102">ICorDebugClass2 Interface1</span></span>
<span data-ttu-id="48746-103">表示泛型类或具有 <xref:System.Type> 类型的方法参数的类。</span><span class="sxs-lookup"><span data-stu-id="48746-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="48746-104">此接口扩展[ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="48746-104">This interface extends [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="48746-105">方法</span><span class="sxs-lookup"><span data-stu-id="48746-105">Methods</span></span>  
  
|<span data-ttu-id="48746-106">方法</span><span class="sxs-lookup"><span data-stu-id="48746-106">Method</span></span>|<span data-ttu-id="48746-107">描述</span><span class="sxs-lookup"><span data-stu-id="48746-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="48746-108">GetParameterizedType 方法</span><span class="sxs-lookup"><span data-stu-id="48746-108">GetParameterizedType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="48746-109">获取此类的类型声明。</span><span class="sxs-lookup"><span data-stu-id="48746-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="48746-110">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="48746-110">SetJMCStatus Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="48746-111">对于此类的每个方法，设置一个值，指示方法是否是用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="48746-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48746-112">备注</span><span class="sxs-lookup"><span data-stu-id="48746-112">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="48746-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="48746-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48746-114">要求</span><span class="sxs-lookup"><span data-stu-id="48746-114">Requirements</span></span>  
 <span data-ttu-id="48746-115">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="48746-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48746-116">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="48746-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="48746-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="48746-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="48746-118">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48746-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48746-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="48746-119">See also</span></span>
- [<span data-ttu-id="48746-120">ICorDebugClass Interface1</span><span class="sxs-lookup"><span data-stu-id="48746-120">ICorDebugClass Interface1</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [<span data-ttu-id="48746-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="48746-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
