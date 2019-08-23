---
title: ICorDebugStringValue 接口
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1cfaf886d09d843f4dbf61af55a9388454b050ca
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957428"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="2c6d7-102">ICorDebugStringValue 接口</span><span class="sxs-lookup"><span data-stu-id="2c6d7-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="2c6d7-103">应用于字符串值的 ICorDebugHeapValue 的子类。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2c6d7-104">方法</span><span class="sxs-lookup"><span data-stu-id="2c6d7-104">Methods</span></span>  
  
|<span data-ttu-id="2c6d7-105">方法</span><span class="sxs-lookup"><span data-stu-id="2c6d7-105">Method</span></span>|<span data-ttu-id="2c6d7-106">描述</span><span class="sxs-lookup"><span data-stu-id="2c6d7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2c6d7-107">GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="2c6d7-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="2c6d7-108">获取此`ICorDebugStringValue`引用的字符串中的字符数。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="2c6d7-109">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="2c6d7-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="2c6d7-110">获取此`ICorDebugStringValue`引用的字符串。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2c6d7-111">备注</span><span class="sxs-lookup"><span data-stu-id="2c6d7-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2c6d7-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c6d7-113">要求</span><span class="sxs-lookup"><span data-stu-id="2c6d7-113">Requirements</span></span>  
 <span data-ttu-id="2c6d7-114">**适用**请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2c6d7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c6d7-115">**标头：** Cordebug.idl, Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="2c6d7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c6d7-116">**类库**CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c6d7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c6d7-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c6d7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c6d7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2c6d7-118">See also</span></span>

- [<span data-ttu-id="2c6d7-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="2c6d7-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
