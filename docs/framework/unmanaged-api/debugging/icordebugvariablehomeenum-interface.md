---
title: ICorDebugVariableHomeEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: d5962de8cc2762f6ecf4864c5255da0fe83918e4
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396534"
---
# <a name="icordebugvariablehomeenum-interface"></a><span data-ttu-id="d0cd5-102">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="d0cd5-102">ICorDebugVariableHomeEnum Interface</span></span>
<span data-ttu-id="d0cd5-103">提供对函数中的局部变量和参数的枚举器。</span><span class="sxs-lookup"><span data-stu-id="d0cd5-103">Provides an enumerator to the local variables and arguments in a function.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d0cd5-104">方法</span><span class="sxs-lookup"><span data-stu-id="d0cd5-104">Methods</span></span>  
  
|<span data-ttu-id="d0cd5-105">方法</span><span class="sxs-lookup"><span data-stu-id="d0cd5-105">Method</span></span>|<span data-ttu-id="d0cd5-106">说明</span><span class="sxs-lookup"><span data-stu-id="d0cd5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d0cd5-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="d0cd5-107">Next Method</span></span>](icordebugvariablehomeenum-next-method.md)|<span data-ttu-id="d0cd5-108">获取指定数量的[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例，其中包含有关函数中的局部变量和参数的信息。</span><span class="sxs-lookup"><span data-stu-id="d0cd5-108">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d0cd5-109">备注</span><span class="sxs-lookup"><span data-stu-id="d0cd5-109">Remarks</span></span>  
 <span data-ttu-id="d0cd5-110">`ICorDebugVariableHomeEnum`接口实现 ICorDebugEnum 接口。</span><span class="sxs-lookup"><span data-stu-id="d0cd5-110">The `ICorDebugVariableHomeEnum` interface implements the ICorDebugEnum interface.</span></span>  
  
 <span data-ttu-id="d0cd5-111">`ICorDebugVariableHomeEnum`实例通过调用[ICorDebugCode4：： EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md)方法，使用[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例进行填充。</span><span class="sxs-lookup"><span data-stu-id="d0cd5-111">An `ICorDebugVariableHomeEnum` instance is populated with [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances by calling the [ICorDebugCode4::EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) method.</span></span> <span data-ttu-id="d0cd5-112">集合中的每个[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例都表示函数中的局部变量或自变量。</span><span class="sxs-lookup"><span data-stu-id="d0cd5-112">Each [ICorDebugVariableHome](icordebugvariablehome-interface.md) instance in the collection represents a local variable or argument in a function.</span></span> <span data-ttu-id="d0cd5-113">可以通过调用[ICorDebugVariableHomeEnum：： Next](icordebugvariablehomeenum-next-method.md)方法来枚举集合中的[ICorDebugVariableHome](icordebugvariablehome-interface.md)对象。</span><span class="sxs-lookup"><span data-stu-id="d0cd5-113">The  [ICorDebugVariableHome](icordebugvariablehome-interface.md) objects in the collection can be enumerated by calling the [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0cd5-114">要求</span><span class="sxs-lookup"><span data-stu-id="d0cd5-114">Requirements</span></span>  
 <span data-ttu-id="d0cd5-115">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d0cd5-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0cd5-116">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d0cd5-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d0cd5-117">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0cd5-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0cd5-118">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0cd5-118">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0cd5-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="d0cd5-119">See also</span></span>

- [<span data-ttu-id="d0cd5-120">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="d0cd5-120">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
- [<span data-ttu-id="d0cd5-121">调试接口</span><span class="sxs-lookup"><span data-stu-id="d0cd5-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
