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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137600"
---
# <a name="icordebugtypeenum-interface"></a><span data-ttu-id="040cf-102">ICorDebugTypeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="040cf-102">ICorDebugTypeEnum Interface</span></span>
<span data-ttu-id="040cf-103">实现"ICorDebugEnum"方法，并枚举"ICorDebugType"数组。</span><span class="sxs-lookup"><span data-stu-id="040cf-103">Implements "ICorDebugEnum" methods and enumerates "ICorDebugType" arrays.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="040cf-104">方法</span><span class="sxs-lookup"><span data-stu-id="040cf-104">Methods</span></span>  
  
|<span data-ttu-id="040cf-105">方法</span><span class="sxs-lookup"><span data-stu-id="040cf-105">Method</span></span>|<span data-ttu-id="040cf-106">描述</span><span class="sxs-lookup"><span data-stu-id="040cf-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="040cf-107">Next 方法</span><span class="sxs-lookup"><span data-stu-id="040cf-107">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtypeenum-next-method.md)|<span data-ttu-id="040cf-108">获取指定的数目的`ICorDebugType`从当前位置开始枚举的实例。</span><span class="sxs-lookup"><span data-stu-id="040cf-108">Gets the specified number of `ICorDebugType` instances from the enumeration, starting at the current position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="040cf-109">备注</span><span class="sxs-lookup"><span data-stu-id="040cf-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="040cf-110">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="040cf-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="040cf-111">要求</span><span class="sxs-lookup"><span data-stu-id="040cf-111">Requirements</span></span>  
 <span data-ttu-id="040cf-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="040cf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="040cf-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="040cf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="040cf-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="040cf-114">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="040cf-115">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="040cf-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="040cf-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="040cf-116">See also</span></span>

- [<span data-ttu-id="040cf-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="040cf-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
