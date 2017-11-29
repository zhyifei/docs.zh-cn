---
title: "ICorDebugStringValue 接口 1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue
helpviewer_keywords: ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03ae6fba5d880b11baac695866853e0b3a4d8cc7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvalue-interface1"></a><span data-ttu-id="c1a5c-102">ICorDebugStringValue 接口 1</span><span class="sxs-lookup"><span data-stu-id="c1a5c-102">ICorDebugStringValue Interface1</span></span>
<span data-ttu-id="c1a5c-103">应用于字符串值的 ICorDebugHeapValue 的子类。</span><span class="sxs-lookup"><span data-stu-id="c1a5c-103">A subclass of ICorDebugHeapValue that applies to string values.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c1a5c-104">方法</span><span class="sxs-lookup"><span data-stu-id="c1a5c-104">Methods</span></span>  
  
|<span data-ttu-id="c1a5c-105">方法</span><span class="sxs-lookup"><span data-stu-id="c1a5c-105">Method</span></span>|<span data-ttu-id="c1a5c-106">描述</span><span class="sxs-lookup"><span data-stu-id="c1a5c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c1a5c-107">GetLength 方法</span><span class="sxs-lookup"><span data-stu-id="c1a5c-107">GetLength Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|<span data-ttu-id="c1a5c-108">获取引用的字符串中的字符数`ICorDebugStringValue`。</span><span class="sxs-lookup"><span data-stu-id="c1a5c-108">Gets the number of characters in the string referenced by this `ICorDebugStringValue`.</span></span>|  
|[<span data-ttu-id="c1a5c-109">GetString 方法</span><span class="sxs-lookup"><span data-stu-id="c1a5c-109">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|<span data-ttu-id="c1a5c-110">获取此引用的字符串`ICorDebugStringValue`。</span><span class="sxs-lookup"><span data-stu-id="c1a5c-110">Gets the string referenced by this `ICorDebugStringValue`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1a5c-111">备注</span><span class="sxs-lookup"><span data-stu-id="c1a5c-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c1a5c-112">此接口不支持跨计算机或跨进程远程调用。</span><span class="sxs-lookup"><span data-stu-id="c1a5c-112">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1a5c-113">要求</span><span class="sxs-lookup"><span data-stu-id="c1a5c-113">Requirements</span></span>  
 <span data-ttu-id="c1a5c-114">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1a5c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1a5c-115">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c1a5c-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c1a5c-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1a5c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1a5c-117">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1a5c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1a5c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1a5c-118">See Also</span></span>  
 [<span data-ttu-id="c1a5c-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="c1a5c-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
