---
title: ICorDebugValue::GetSize 方法
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetSize
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetSize
helpviewer_keywords:
- GetSize method, ICorDebugValue interface [.NET Framework debugging]
- ICorDebugValue::GetSize method [.NET Framework debugging]
ms.assetid: 445a9ee3-e050-4f3a-931a-96b0efb00110
topic_type:
- apiref
ms.openlocfilehash: 3d26ddb6d89af60acf6dc1214b0423ba75e488ff
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791169"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="a7aaa-102">ICorDebugValue::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="a7aaa-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="a7aaa-103">获取此 "ICorDebugValue" 对象的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a7aaa-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7aaa-104">语法</span><span class="sxs-lookup"><span data-stu-id="a7aaa-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7aaa-105">参数</span><span class="sxs-lookup"><span data-stu-id="a7aaa-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="a7aaa-106">弄此值对象的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a7aaa-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7aaa-107">备注</span><span class="sxs-lookup"><span data-stu-id="a7aaa-107">Remarks</span></span>  
 <span data-ttu-id="a7aaa-108">如果值的类型为引用类型，则此方法返回指针的大小，而不是对象的大小。</span><span class="sxs-lookup"><span data-stu-id="a7aaa-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="a7aaa-109">`ICorDebugValue::GetSize` 方法返回64位平台上大于 4 GB 的对象 `COR_E_OVERFLOW`。</span><span class="sxs-lookup"><span data-stu-id="a7aaa-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="a7aaa-110">使用[ICorDebugValue3：： GetSize64](icordebugvalue3-getsize64-method.md)方法代替大于 4 GB 的对象。</span><span class="sxs-lookup"><span data-stu-id="a7aaa-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7aaa-111">需求</span><span class="sxs-lookup"><span data-stu-id="a7aaa-111">Requirements</span></span>  
 <span data-ttu-id="a7aaa-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a7aaa-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7aaa-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7aaa-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7aaa-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7aaa-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7aaa-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7aaa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7aaa-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7aaa-116">See also</span></span>

- [<span data-ttu-id="a7aaa-117">GetSize64 方法</span><span class="sxs-lookup"><span data-stu-id="a7aaa-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
