---
title: ICorDebugGuidToTypeEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum
helpviewer_keywords:
- ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: aa32b12b-05fc-4ea8-a904-adae25034269
topic_type:
- apiref
ms.openlocfilehash: 2663e5604cdd55472cc148b2d2b38599df81f11e
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794441"
---
# <a name="icordebugguidtotypeenum-interface"></a><span data-ttu-id="07ca1-102">ICorDebugGuidToTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="07ca1-102">ICorDebugGuidToTypeEnum Interface</span></span>
<span data-ttu-id="07ca1-103">提供一个枚举器，该枚举器定义一组 Guid 与它们对应的类型之间的映射（由 ICorDebugType 实例表示）。</span><span class="sxs-lookup"><span data-stu-id="07ca1-103">Provides an enumerator that defines the mapping between a set of GUIDs and their corresponding types, which are represented by ICorDebugType instances.</span></span> <span data-ttu-id="07ca1-104">此接口继承 ICorDebugEnum 接口中的方法。</span><span class="sxs-lookup"><span data-stu-id="07ca1-104">This interface inherits the methods from the ICorDebugEnum interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07ca1-105">方法</span><span class="sxs-lookup"><span data-stu-id="07ca1-105">Methods</span></span>  
  
|<span data-ttu-id="07ca1-106">方法</span><span class="sxs-lookup"><span data-stu-id="07ca1-106">Method</span></span>|<span data-ttu-id="07ca1-107">描述</span><span class="sxs-lookup"><span data-stu-id="07ca1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="07ca1-108">ICorDebugGuidToTypeEnum::Next</span><span class="sxs-lookup"><span data-stu-id="07ca1-108">ICorDebugGuidToTypeEnum::Next</span></span>](icordebugguidtotypeenum-next-method.md)|<span data-ttu-id="07ca1-109">获取指定数量的[CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md)实例，这些实例将 guid 映射到类型信息。</span><span class="sxs-lookup"><span data-stu-id="07ca1-109">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07ca1-110">备注</span><span class="sxs-lookup"><span data-stu-id="07ca1-110">Remarks</span></span>  
 <span data-ttu-id="07ca1-111">可以通过调用[ICorDebugAppDomain3：： GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md)方法来检索 `ICorDebugGuidToTypeEnum` 的接口对象。</span><span class="sxs-lookup"><span data-stu-id="07ca1-111">An `ICorDebugGuidToTypeEnum` interface object can be retrieved by calling the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span> <span data-ttu-id="07ca1-112">调试器可以调用此接口的[下一](icordebugguidtotypeenum-next-method.md)方法来检索[CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md)对象，这些对象表示在用于调用[ICorDebugAppDomain3：： GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md)方法的应用程序域中加载的 Windows 运行时类型的托管表示形式的映射。</span><span class="sxs-lookup"><span data-stu-id="07ca1-112">A debugger can call this interface's [Next](icordebugguidtotypeenum-next-method.md) method to retrieve [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects that represent mappings of managed representations of Windows Runtime types loaded in the application domain used for the call to the [ICorDebugAppDomain3::GetCachedWinRTTypes](icordebugappdomain3-getcachedwinrttypes-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07ca1-113">需求</span><span class="sxs-lookup"><span data-stu-id="07ca1-113">Requirements</span></span>  
 <span data-ttu-id="07ca1-114">**平台：** Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="07ca1-114">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="07ca1-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="07ca1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="07ca1-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="07ca1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="07ca1-117">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07ca1-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ca1-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07ca1-118">See also</span></span>

- [<span data-ttu-id="07ca1-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="07ca1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
