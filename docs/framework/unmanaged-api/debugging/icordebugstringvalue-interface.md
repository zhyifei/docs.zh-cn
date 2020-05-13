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
ms.openlocfilehash: 5537a48fd085ce98de855fa1ec0913e2637e58e0
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "83376199"
---
# <a name="icordebugstringvalue-interface"></a><span data-ttu-id="102c7-102">ICorDebugStringValue 接口</span><span class="sxs-lookup"><span data-stu-id="102c7-102">ICorDebugStringValue Interface</span></span>
<span data-ttu-id="102c7-103">应用于字符串值的 ICorDebugHeapValue 的子类。</span><span class="sxs-lookup"><span data-stu-id="102c7-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="102c7-104">方法</span><span class="sxs-lookup"><span data-stu-id="102c7-104">Methods</span></span>  
  
|<span data-ttu-id="102c7-105">方法</span><span class="sxs-lookup"><span data-stu-id="102c7-105">Method</span></span>|<span data-ttu-id="102c7-106">描述</span><span class="sxs-lookup"><span data-stu-id="102c7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="102c7-107">GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="102c7-107">GetLength Method</span></span>](icordebugstringvalue-getlength-method.md)|<span data-ttu-id="102c7-108">获取此引用的字符串中的字符数 `ICorDebugStringValue` 。</span><span class="sxs-lookup"><span data-stu-id="102c7-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="102c7-109">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="102c7-109">GetString Method</span></span>](icordebugstringvalue-getstring-method.md)|<span data-ttu-id="102c7-110">获取此引用的字符串 `ICorDebugStringValue` 。</span><span class="sxs-lookup"><span data-stu-id="102c7-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="102c7-111">备注</span><span class="sxs-lookup"><span data-stu-id="102c7-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="102c7-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="102c7-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="102c7-113">要求</span><span class="sxs-lookup"><span data-stu-id="102c7-113">Requirements</span></span>  
 <span data-ttu-id="102c7-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="102c7-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="102c7-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="102c7-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="102c7-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="102c7-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="102c7-117">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="102c7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="102c7-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="102c7-118">See also</span></span>

- [<span data-ttu-id="102c7-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="102c7-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
