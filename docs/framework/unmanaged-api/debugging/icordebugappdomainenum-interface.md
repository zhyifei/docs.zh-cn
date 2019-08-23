---
title: ICorDebugAppDomainEnum 接口
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomainEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomainEnum
helpviewer_keywords:
- ICorDebugAppDomainEnum interface [.NET Framework debugging]
ms.assetid: e9226e6e-ca2c-428e-bb38-0c099210f507
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c48c222a34e2e78f29c33e49da331d97d409bae1
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69949751"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="4d851-102">ICorDebugAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="4d851-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="4d851-103">提供方法, 该方法从枚举中的下`ICorDebugAppDomainEnum`一个位置开始返回指定数目的值。 `Next`</span><span class="sxs-lookup"><span data-stu-id="4d851-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="4d851-104">此接口是 "ICorDebugEnum" 的子类。</span><span class="sxs-lookup"><span data-stu-id="4d851-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d851-105">方法</span><span class="sxs-lookup"><span data-stu-id="4d851-105">Methods</span></span>  
  
|<span data-ttu-id="4d851-106">方法</span><span class="sxs-lookup"><span data-stu-id="4d851-106">Method</span></span>|<span data-ttu-id="4d851-107">描述</span><span class="sxs-lookup"><span data-stu-id="4d851-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d851-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="4d851-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="4d851-109">从当前游标位置开始, 获取集合中指定数量的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="4d851-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d851-110">备注</span><span class="sxs-lookup"><span data-stu-id="4d851-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="4d851-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="4d851-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d851-112">要求</span><span class="sxs-lookup"><span data-stu-id="4d851-112">Requirements</span></span>  
 <span data-ttu-id="4d851-113">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4d851-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d851-114">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="4d851-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d851-115">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d851-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d851-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d851-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d851-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d851-117">See also</span></span>

- [<span data-ttu-id="4d851-118">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="4d851-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="4d851-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="4d851-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
