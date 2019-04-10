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
ms.openlocfilehash: da1fc949109455cf50767191a99a8a727116f77c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155189"
---
# <a name="icordebugappdomainenum-interface"></a><span data-ttu-id="345a4-102">ICorDebugAppDomainEnum 接口</span><span class="sxs-lookup"><span data-stu-id="345a4-102">ICorDebugAppDomainEnum Interface</span></span>

<span data-ttu-id="345a4-103">提供了`Next`方法，返回指定的数目的`ICorDebugAppDomainEnum`枚举中的下一个位置开始的值。</span><span class="sxs-lookup"><span data-stu-id="345a4-103">Provides the `Next` method, which returns a specified number of `ICorDebugAppDomainEnum` values starting at the next location in the enumeration.</span></span> <span data-ttu-id="345a4-104">此接口是"ICorDebugEnum"的子类。</span><span class="sxs-lookup"><span data-stu-id="345a4-104">This interface is a subclass of "ICorDebugEnum".</span></span>  
  
## <a name="methods"></a><span data-ttu-id="345a4-105">方法</span><span class="sxs-lookup"><span data-stu-id="345a4-105">Methods</span></span>  
  
|<span data-ttu-id="345a4-106">方法</span><span class="sxs-lookup"><span data-stu-id="345a4-106">Method</span></span>|<span data-ttu-id="345a4-107">描述</span><span class="sxs-lookup"><span data-stu-id="345a4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="345a4-108">Next 方法</span><span class="sxs-lookup"><span data-stu-id="345a4-108">Next Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugappdomainenum-next-method.md)|<span data-ttu-id="345a4-109">从集合中，从当前光标位置开始获取指定的数目的应用程序域。</span><span class="sxs-lookup"><span data-stu-id="345a4-109">Gets the specified number of application domains from the collection, starting at the current cursor position.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="345a4-110">备注</span><span class="sxs-lookup"><span data-stu-id="345a4-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="345a4-111">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="345a4-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="345a4-112">要求</span><span class="sxs-lookup"><span data-stu-id="345a4-112">Requirements</span></span>  
 <span data-ttu-id="345a4-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="345a4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="345a4-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="345a4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="345a4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="345a4-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="345a4-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="345a4-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="345a4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="345a4-117">See also</span></span>

- [<span data-ttu-id="345a4-118">ICorDebug 接口</span><span class="sxs-lookup"><span data-stu-id="345a4-118">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="345a4-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="345a4-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
