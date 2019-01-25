---
title: ICorDebugBoxValue Interface1
ms.date: 03/30/2017
api_name:
- ICorDebugBoxValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBoxValue
helpviewer_keywords:
- ICorDebugBoxValue interface [.NET Framework debugging]
ms.assetid: 3d3ae7e2-97d4-46de-a2c3-cb78f3490f9d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 549f3f782d544c967838206804640b577da2f877
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699007"
---
# <a name="icordebugboxvalue-interface1"></a><span data-ttu-id="318b2-102">ICorDebugBoxValue Interface1</span><span class="sxs-lookup"><span data-stu-id="318b2-102">ICorDebugBoxValue Interface1</span></span>
<span data-ttu-id="318b2-103">"ICorDebugHeapValue"表示装箱的值类对象的子类。</span><span class="sxs-lookup"><span data-stu-id="318b2-103">A subclass of "ICorDebugHeapValue" that represents a boxed value class object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="318b2-104">方法</span><span class="sxs-lookup"><span data-stu-id="318b2-104">Methods</span></span>  
  
|<span data-ttu-id="318b2-105">方法</span><span class="sxs-lookup"><span data-stu-id="318b2-105">Method</span></span>|<span data-ttu-id="318b2-106">描述</span><span class="sxs-lookup"><span data-stu-id="318b2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="318b2-107">GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="318b2-107">GetObject Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugboxvalue-getobject-method.md)|<span data-ttu-id="318b2-108">到装箱"ICorDebugObjectValue"实例获取的接口指针。</span><span class="sxs-lookup"><span data-stu-id="318b2-108">Gets an interface pointer to the boxed "ICorDebugObjectValue" instance.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="318b2-109">备注</span><span class="sxs-lookup"><span data-stu-id="318b2-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="318b2-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="318b2-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="318b2-111">要求</span><span class="sxs-lookup"><span data-stu-id="318b2-111">Requirements</span></span>  
 <span data-ttu-id="318b2-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="318b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="318b2-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="318b2-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="318b2-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="318b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="318b2-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="318b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="318b2-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="318b2-116">See also</span></span>
- [<span data-ttu-id="318b2-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="318b2-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
