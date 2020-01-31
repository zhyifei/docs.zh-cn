---
title: ICorDebugClass2 接口
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
ms.openlocfilehash: 795e9f4862992d95eeef98a986545cca47d828c6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784143"
---
# <a name="icordebugclass2-interface"></a><span data-ttu-id="2233e-102">ICorDebugClass2 接口</span><span class="sxs-lookup"><span data-stu-id="2233e-102">ICorDebugClass2 Interface</span></span>

<span data-ttu-id="2233e-103">表示泛型类或具有 <xref:System.Type> 类型的方法参数的类。</span><span class="sxs-lookup"><span data-stu-id="2233e-103">Represents a generic class or a class with a method parameter of type <xref:System.Type>.</span></span> <span data-ttu-id="2233e-104">此接口扩展[ICorDebugClass](icordebugclass-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="2233e-104">This interface extends [ICorDebugClass](icordebugclass-interface.md).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2233e-105">方法</span><span class="sxs-lookup"><span data-stu-id="2233e-105">Methods</span></span>  
  
|<span data-ttu-id="2233e-106">方法</span><span class="sxs-lookup"><span data-stu-id="2233e-106">Method</span></span>|<span data-ttu-id="2233e-107">描述</span><span class="sxs-lookup"><span data-stu-id="2233e-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2233e-108">GetParameterizedType 方法</span><span class="sxs-lookup"><span data-stu-id="2233e-108">GetParameterizedType Method</span></span>](icordebugclass2-getparameterizedtype-method.md)|<span data-ttu-id="2233e-109">获取此类的类型声明。</span><span class="sxs-lookup"><span data-stu-id="2233e-109">Gets the type declaration for this class.</span></span>|  
|[<span data-ttu-id="2233e-110">SetJMCStatus 方法</span><span class="sxs-lookup"><span data-stu-id="2233e-110">SetJMCStatus Method</span></span>](icordebugclass2-setjmcstatus-method.md)|<span data-ttu-id="2233e-111">对于此类的每个方法，设置一个值，该值指示该方法是否为用户定义的代码。</span><span class="sxs-lookup"><span data-stu-id="2233e-111">For each method of this class, sets a value that indicates whether the method is user-defined code.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2233e-112">备注</span><span class="sxs-lookup"><span data-stu-id="2233e-112">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2233e-113">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2233e-113">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2233e-114">需求</span><span class="sxs-lookup"><span data-stu-id="2233e-114">Requirements</span></span>  
 <span data-ttu-id="2233e-115">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2233e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2233e-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2233e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2233e-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2233e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2233e-118">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2233e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2233e-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2233e-119">See also</span></span>

- [<span data-ttu-id="2233e-120">ICorDebugClass 接口</span><span class="sxs-lookup"><span data-stu-id="2233e-120">ICorDebugClass Interface</span></span>](icordebugclass-interface.md)
- [<span data-ttu-id="2233e-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="2233e-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
