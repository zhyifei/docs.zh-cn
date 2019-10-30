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
ms.openlocfilehash: 6cc3ec1c802c28b74248380aa7f686e675a92f1d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088844"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="55d2a-102">ICorDebugAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="55d2a-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="55d2a-103">提供 `Next` 方法，该方法从枚举中的下一个位置开始返回指定数目的 `ICorDebugAppDomainEnum` 值。</span><span class="sxs-lookup"><span data-stu-id="55d2a-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="55d2a-104">此接口是 "ICorDebugEnum" 的子类。</span><span class="sxs-lookup"><span data-stu-id="55d2a-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="55d2a-105">方法</span><span class="sxs-lookup"><span data-stu-id="55d2a-105">Methods</span></span>  
  
|<span data-ttu-id="55d2a-106">方法</span><span class="sxs-lookup"><span data-stu-id="55d2a-106">Method</span></span>|<span data-ttu-id="55d2a-107">描述</span><span class="sxs-lookup"><span data-stu-id="55d2a-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="55d2a-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="55d2a-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="55d2a-109">从当前游标位置开始，获取集合中指定数量的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="55d2a-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55d2a-110">备注</span><span class="sxs-lookup"><span data-stu-id="55d2a-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="55d2a-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="55d2a-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55d2a-112">要求</span><span class="sxs-lookup"><span data-stu-id="55d2a-112">Requirements</span></span>  
 <span data-ttu-id="55d2a-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="55d2a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55d2a-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="55d2a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55d2a-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55d2a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55d2a-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55d2a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55d2a-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="55d2a-117">See also</span></span>

- [<span data-ttu-id="55d2a-118">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="55d2a-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="55d2a-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="55d2a-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
