---
title: ICorDebugObjectEnum 接口 1
ms.date: 03/30/2017
api_name:
- ICorDebugObjectEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectEnum
helpviewer_keywords:
- ICorDebugObjectEnum interface [.NET Framework debugging]
ms.assetid: 9ffb4498-7719-49d3-8890-df2c22248a0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3a9f10301db488e4ca68ce5fdaf0ba767053d7d4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54546996"
---
# <a name="icordebugobjectenum-interface1"></a><span data-ttu-id="a5dbb-102">ICorDebugObjectEnum 接口 1</span><span class="sxs-lookup"><span data-stu-id="a5dbb-102">ICorDebugObjectEnum Interface1</span></span>
<span data-ttu-id="a5dbb-103">实现 ICorDebugEnum 方法，并通过其相对虚拟地址 (Rva) 枚举对象的数组。</span><span class="sxs-lookup"><span data-stu-id="a5dbb-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a5dbb-104">方法</span><span class="sxs-lookup"><span data-stu-id="a5dbb-104">Methods</span></span>  
  
|<span data-ttu-id="a5dbb-105">方法</span><span class="sxs-lookup"><span data-stu-id="a5dbb-105">Method</span></span>|<span data-ttu-id="a5dbb-106">描述</span><span class="sxs-lookup"><span data-stu-id="a5dbb-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a5dbb-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="a5dbb-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectenum-next-method.md)|<span data-ttu-id="a5dbb-108">从当前位置开始枚举中获取指定数目的对象的 Rva。</span><span class="sxs-lookup"><span data-stu-id="a5dbb-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5dbb-109">备注</span><span class="sxs-lookup"><span data-stu-id="a5dbb-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a5dbb-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="a5dbb-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a5dbb-111">要求</span><span class="sxs-lookup"><span data-stu-id="a5dbb-111">Requirements</span></span>  
 <span data-ttu-id="a5dbb-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a5dbb-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5dbb-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a5dbb-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a5dbb-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a5dbb-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a5dbb-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5dbb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dbb-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="a5dbb-116">See also</span></span>
- [<span data-ttu-id="a5dbb-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="a5dbb-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
