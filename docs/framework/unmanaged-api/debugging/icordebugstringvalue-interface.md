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
ms.openlocfilehash: 6709b14ce8e7bc131f9feb7a277fb41851ee4352
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173987"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="c606f-102">ICorDebugStringValue 接口</span><span class="sxs-lookup"><span data-stu-id="c606f-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="c606f-103">应用于字符串值的 ICorDebugHeapValue 子类。</span><span class="sxs-lookup"><span data-stu-id="c606f-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c606f-104">方法</span><span class="sxs-lookup"><span data-stu-id="c606f-104">Methods</span></span>  
  
|<span data-ttu-id="c606f-105">方法</span><span class="sxs-lookup"><span data-stu-id="c606f-105">Method</span></span>|<span data-ttu-id="c606f-106">描述</span><span class="sxs-lookup"><span data-stu-id="c606f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c606f-107">GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="c606f-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="c606f-108">获取此引用的字符串中的字符数`ICorDebugStringValue`。</span><span class="sxs-lookup"><span data-stu-id="c606f-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="c606f-109">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="c606f-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="c606f-110">获取此引用的字符串`ICorDebugStringValue`。</span><span class="sxs-lookup"><span data-stu-id="c606f-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c606f-111">备注</span><span class="sxs-lookup"><span data-stu-id="c606f-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c606f-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c606f-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c606f-113">要求</span><span class="sxs-lookup"><span data-stu-id="c606f-113">Requirements</span></span>  
 <span data-ttu-id="c606f-114">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c606f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c606f-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c606f-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c606f-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c606f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c606f-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c606f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c606f-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="c606f-118">See also</span></span>

- [<span data-ttu-id="c606f-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="c606f-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
