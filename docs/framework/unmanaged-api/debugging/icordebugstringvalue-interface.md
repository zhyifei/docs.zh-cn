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
ms.openlocfilehash: d1d3a5eb6e0b24b40a35c13a99465dd3c7032a91
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138945"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="d58a3-102">ICorDebugStringValue 接口</span><span class="sxs-lookup"><span data-stu-id="d58a3-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="d58a3-103">应用于字符串值的 ICorDebugHeapValue 的子类。</span><span class="sxs-lookup"><span data-stu-id="d58a3-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d58a3-104">方法</span><span class="sxs-lookup"><span data-stu-id="d58a3-104">Methods</span></span>  
  
|<span data-ttu-id="d58a3-105">方法</span><span class="sxs-lookup"><span data-stu-id="d58a3-105">Method</span></span>|<span data-ttu-id="d58a3-106">描述</span><span class="sxs-lookup"><span data-stu-id="d58a3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d58a3-107">GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="d58a3-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="d58a3-108">获取此 `ICorDebugStringValue`所引用的字符串中的字符数。</span><span class="sxs-lookup"><span data-stu-id="d58a3-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="d58a3-109">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="d58a3-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="d58a3-110">获取此 `ICorDebugStringValue`引用的字符串。</span><span class="sxs-lookup"><span data-stu-id="d58a3-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d58a3-111">备注</span><span class="sxs-lookup"><span data-stu-id="d58a3-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d58a3-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="d58a3-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d58a3-113">要求</span><span class="sxs-lookup"><span data-stu-id="d58a3-113">Requirements</span></span>  
 <span data-ttu-id="d58a3-114">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d58a3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d58a3-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d58a3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d58a3-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d58a3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d58a3-117">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d58a3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d58a3-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d58a3-118">See also</span></span>

- [<span data-ttu-id="d58a3-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="d58a3-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
