---
title: ICorDebugTypeEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugTypeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugTypeEnum
helpviewer_keywords:
- ICorDebugTypeEnum interface [.NET Framework debugging]
ms.assetid: 159ccfcf-b37c-4ad9-8e0d-a9a443262472
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 121c4bca3419ef1e34a03ff7600285948ca4c237
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61986994"
---
# <a name="icordebugtypeenum-interface"></a><span data-ttu-id="983c1-102">ICorDebugTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="983c1-102">ICorDebugTypeEnum Interface</span></span>
<span data-ttu-id="983c1-103">实现"ICorDebugEnum"方法，并枚举"ICorDebugType"数组。</span><span class="sxs-lookup"><span data-stu-id="983c1-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugType" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="983c1-104">方法</span><span class="sxs-lookup"><span data-stu-id="983c1-104">Methods</span></span>  
  
|<span data-ttu-id="983c1-105">方法</span><span class="sxs-lookup"><span data-stu-id="983c1-105">Method</span></span>|<span data-ttu-id="983c1-106">描述</span><span class="sxs-lookup"><span data-stu-id="983c1-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="983c1-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="983c1-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-next-method.md)|<span data-ttu-id="983c1-108">获取指定的数目的`ICorDebugType`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="983c1-108">Gets the specified number of `ICorDebugType` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="983c1-109">备注</span><span class="sxs-lookup"><span data-stu-id="983c1-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="983c1-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="983c1-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983c1-111">要求</span><span class="sxs-lookup"><span data-stu-id="983c1-111">Requirements</span></span>  
 <span data-ttu-id="983c1-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="983c1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983c1-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="983c1-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="983c1-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="983c1-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="983c1-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983c1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983c1-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="983c1-116">See also</span></span>

- [<span data-ttu-id="983c1-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="983c1-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
