---
title: ICorDebugObjectEnum 接口
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
ms.openlocfilehash: 0526c050bcf1316eccf2c756a404fbb971e6d7d0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792741"
---
# <a name="icordebugobjectenum-interface"></a><span data-ttu-id="b7056-102">ICorDebugObjectEnum 接口</span><span class="sxs-lookup"><span data-stu-id="b7056-102">ICorDebugObjectEnum Interface</span></span>

<span data-ttu-id="b7056-103">实现 ICorDebugEnum 方法，并按它们的相对虚拟地址（Rva）枚举对象的数组。</span><span class="sxs-lookup"><span data-stu-id="b7056-103">Implements ICorDebugEnum methods, and enumerates arrays of objects by their relative virtual addresses (RVAs).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b7056-104">方法</span><span class="sxs-lookup"><span data-stu-id="b7056-104">Methods</span></span>  
  
|<span data-ttu-id="b7056-105">方法</span><span class="sxs-lookup"><span data-stu-id="b7056-105">Method</span></span>|<span data-ttu-id="b7056-106">描述</span><span class="sxs-lookup"><span data-stu-id="b7056-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b7056-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="b7056-107">Next Method</span></span>](icordebugobjectenum-next-method.md)|<span data-ttu-id="b7056-108">从当前位置开始，获取枚举中指定数量的对象的 Rva。</span><span class="sxs-lookup"><span data-stu-id="b7056-108">Gets the RVAs of the specified number of objects from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b7056-109">备注</span><span class="sxs-lookup"><span data-stu-id="b7056-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b7056-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="b7056-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7056-111">需求</span><span class="sxs-lookup"><span data-stu-id="b7056-111">Requirements</span></span>  
 <span data-ttu-id="b7056-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b7056-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7056-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b7056-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b7056-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7056-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7056-115">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7056-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7056-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b7056-116">See also</span></span>

- [<span data-ttu-id="b7056-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="b7056-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
