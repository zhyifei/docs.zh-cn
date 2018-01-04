---
title: "ICorDebugHeapValue2::CreateHandle 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugHeapValue2.CreateHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eeef3215c3740cdaa7d1b78b73fde9e76d7b40c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="c29b4-102">ICorDebugHeapValue2::CreateHandle 方法</span><span class="sxs-lookup"><span data-stu-id="c29b4-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="c29b4-103">创建此 ICorDebugHeapValue2 对象所表示的堆值的指定类型句柄。</span><span class="sxs-lookup"><span data-stu-id="c29b4-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c29b4-104">语法</span><span class="sxs-lookup"><span data-stu-id="c29b4-104">Syntax</span></span>  
  
```  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c29b4-105">参数</span><span class="sxs-lookup"><span data-stu-id="c29b4-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="c29b4-106">[in]CorDebugHandleType 枚举，指定要创建的句柄的类型的值。</span><span class="sxs-lookup"><span data-stu-id="c29b4-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="c29b4-107">[out]指向一个 ICorDebugHandleValue 对象，表示此堆值的新句柄的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="c29b4-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c29b4-108">备注</span><span class="sxs-lookup"><span data-stu-id="c29b4-108">Remarks</span></span>  
 <span data-ttu-id="c29b4-109">句柄将在堆值中，关联的应用程序域中创建，并将变为无效，如果应用程序域获取卸载。</span><span class="sxs-lookup"><span data-stu-id="c29b4-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="c29b4-110">对此函数对于相同的堆值的多个调用将创建多个句柄。</span><span class="sxs-lookup"><span data-stu-id="c29b4-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="c29b4-111">句柄会影响垃圾回收器的性能，因为调试器应本身将限制为相对较小的处于活动状态一次句柄 (大约 256) 数。</span><span class="sxs-lookup"><span data-stu-id="c29b4-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c29b4-112">惠?</span><span class="sxs-lookup"><span data-stu-id="c29b4-112">Requirements</span></span>  
 <span data-ttu-id="c29b4-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c29b4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c29b4-114">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c29b4-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c29b4-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c29b4-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c29b4-116">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c29b4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
