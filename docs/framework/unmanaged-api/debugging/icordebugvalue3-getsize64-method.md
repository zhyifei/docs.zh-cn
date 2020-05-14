---
title: ICorDebugValue3::GetSize64 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue3::GetSize64
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue3::GetSize64
helpviewer_keywords:
- GetSize64 method, ICorDebugValue3 interface [.NET Framework debugging]
- ICorDebugValue3::GetSize64 method [.NET Framework debugging]
ms.assetid: fee56a29-3154-4192-958d-71da2ced3740
topic_type:
- apiref
ms.openlocfilehash: 6eb26de83a6cdce47477e6cb3dffd6a94d889975
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397028"
---
# <a name="icordebugvalue3getsize64-method"></a><span data-ttu-id="d8c94-102">ICorDebugValue3::GetSize64 方法</span><span class="sxs-lookup"><span data-stu-id="d8c94-102">ICorDebugValue3::GetSize64 Method</span></span>
<span data-ttu-id="d8c94-103">获取此[ICorDebugValue3](icordebugvalue3-interface.md)对象的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d8c94-103">Gets the size, in bytes, of this [ICorDebugValue3](icordebugvalue3-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8c94-104">语法</span><span class="sxs-lookup"><span data-stu-id="d8c94-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize64(  
    [out] ULONG64 *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d8c94-105">参数</span><span class="sxs-lookup"><span data-stu-id="d8c94-105">Parameters</span></span>  
 <span data-ttu-id="d8c94-106">pSize</span><span class="sxs-lookup"><span data-stu-id="d8c94-106">pSize</span></span>  
 <span data-ttu-id="d8c94-107">弄一个指针，指向该对象的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="d8c94-107">[out] A pointer to the size, in bytes, of this object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d8c94-108">备注</span><span class="sxs-lookup"><span data-stu-id="d8c94-108">Remarks</span></span>  
 <span data-ttu-id="d8c94-109">如果此值的类型为引用类型，则此方法返回指针的大小，而不是对象的大小。</span><span class="sxs-lookup"><span data-stu-id="d8c94-109">If this value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="d8c94-110">`ICorDebugValue3::GetSize`方法不同于其 output 参数类型中的[ICorDebugValue：： GetSize](icordebugvalue-getsize-method.md)方法。</span><span class="sxs-lookup"><span data-stu-id="d8c94-110">The `ICorDebugValue3::GetSize` method differs from the [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md) method in the type of its output parameter.</span></span> <span data-ttu-id="d8c94-111">在[ICorDebugValue：： GetSize](icordebugvalue-getsize-method.md)中，output 参数是 `ULONG32` ; 在中 `ICorDebugValue3::GetSize` ，它是一个 `ULONG64` 。</span><span class="sxs-lookup"><span data-stu-id="d8c94-111">In [ICorDebugValue::GetSize](icordebugvalue-getsize-method.md), the output parameter is a `ULONG32`; in `ICorDebugValue3::GetSize`, it is a `ULONG64`.</span></span> <span data-ttu-id="d8c94-112">这使[ICorDebugValue3](icordebugvalue3-interface.md)接口可以报告超过2gb 的数组的大小。</span><span class="sxs-lookup"><span data-stu-id="d8c94-112">This enables the [ICorDebugValue3](icordebugvalue3-interface.md) interface to report the size of arrays that exceed 2GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8c94-113">要求</span><span class="sxs-lookup"><span data-stu-id="d8c94-113">Requirements</span></span>  
 <span data-ttu-id="d8c94-114">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c94-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8c94-115">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d8c94-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d8c94-116">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d8c94-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d8c94-117">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8c94-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8c94-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8c94-118">See also</span></span>

- [<span data-ttu-id="d8c94-119">ICorDebugValue3 接口</span><span class="sxs-lookup"><span data-stu-id="d8c94-119">ICorDebugValue3 Interface</span></span>](icordebugvalue3-interface.md)
- [<span data-ttu-id="d8c94-120">调试接口</span><span class="sxs-lookup"><span data-stu-id="d8c94-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
