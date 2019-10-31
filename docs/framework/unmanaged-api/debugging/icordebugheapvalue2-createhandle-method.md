---
title: ICorDebugHeapValue2::CreateHandle 方法
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: b9eab1274f2d0ad562c0dec6adeddb85c6cfc458
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138382"
---
# <a name="icordebugheapvalue2createhandle-method"></a><span data-ttu-id="a53de-102">ICorDebugHeapValue2::CreateHandle 方法</span><span class="sxs-lookup"><span data-stu-id="a53de-102">ICorDebugHeapValue2::CreateHandle Method</span></span>
<span data-ttu-id="a53de-103">为此 ICorDebugHeapValue2 对象表示的堆值创建指定类型的句柄。</span><span class="sxs-lookup"><span data-stu-id="a53de-103">Creates a handle of the specified type for the heap value represented by this ICorDebugHeapValue2 object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a53de-104">语法</span><span class="sxs-lookup"><span data-stu-id="a53de-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a53de-105">参数</span><span class="sxs-lookup"><span data-stu-id="a53de-105">Parameters</span></span>  
 `type`  
 <span data-ttu-id="a53de-106">中CorDebugHandleType 枚举的一个值，该值指定要创建的句柄的类型。</span><span class="sxs-lookup"><span data-stu-id="a53de-106">[in] A value of the CorDebugHandleType enumeration that specifies the type of handle to be created.</span></span>  
  
 `ppHandle`  
 <span data-ttu-id="a53de-107">弄指向 ICorDebugHandleValue 对象的地址的指针，该对象表示此堆值的新句柄。</span><span class="sxs-lookup"><span data-stu-id="a53de-107">[out] A pointer to the address of an ICorDebugHandleValue object that represents the new handle for this heap value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a53de-108">备注</span><span class="sxs-lookup"><span data-stu-id="a53de-108">Remarks</span></span>  
 <span data-ttu-id="a53de-109">该句柄将在与堆值相关联的应用程序域中创建，如果应用程序域已卸载，则将变为无效。</span><span class="sxs-lookup"><span data-stu-id="a53de-109">The handle will be created in the application domain that is associated with the heap value, and will become invalid if the application domain gets unloaded.</span></span>  
  
 <span data-ttu-id="a53de-110">对于同一堆值多次调用此函数会创建多个句柄。</span><span class="sxs-lookup"><span data-stu-id="a53de-110">Multiple calls to this function for the same heap value will create multiple handles.</span></span> <span data-ttu-id="a53de-111">因为句柄会影响垃圾回收器的性能，所以调试程序应将自身限制为一个相对较小的句柄数（大约为256），每次处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="a53de-111">Because handles affect the performance of the garbage collector, the debugger should limit itself to a relatively small number of handles (about 256) that are active at a time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a53de-112">要求</span><span class="sxs-lookup"><span data-stu-id="a53de-112">Requirements</span></span>  
 <span data-ttu-id="a53de-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a53de-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a53de-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a53de-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a53de-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a53de-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a53de-116">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a53de-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
