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
ms.openlocfilehash: 9ff7128f55236ae4d0c3a9067a279c496cfb6798
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396755"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="8d411-102">ICorDebugValue::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="8d411-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="8d411-103">获取此 "ICorDebugValue" 对象的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8d411-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d411-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d411-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d411-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d411-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="8d411-106">弄此值对象的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="8d411-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d411-107">备注</span><span class="sxs-lookup"><span data-stu-id="8d411-107">Remarks</span></span>  
 <span data-ttu-id="8d411-108">如果值的类型为引用类型，则此方法返回指针的大小，而不是对象的大小。</span><span class="sxs-lookup"><span data-stu-id="8d411-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="8d411-109">此 `ICorDebugValue::GetSize` 方法 `COR_E_OVERFLOW` 为64位平台上大于 4 GB 的对象返回。</span><span class="sxs-lookup"><span data-stu-id="8d411-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="8d411-110">使用[ICorDebugValue3：： GetSize64](icordebugvalue3-getsize64-method.md)方法代替大于 4 GB 的对象。</span><span class="sxs-lookup"><span data-stu-id="8d411-110">Use the [ICorDebugValue3::GetSize64](icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d411-111">要求</span><span class="sxs-lookup"><span data-stu-id="8d411-111">Requirements</span></span>  
 <span data-ttu-id="8d411-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d411-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d411-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8d411-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8d411-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d411-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d411-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d411-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d411-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d411-116">See also</span></span>

- [<span data-ttu-id="8d411-117">GetSize64 方法</span><span class="sxs-lookup"><span data-stu-id="8d411-117">GetSize64 Method</span></span>](icordebugvalue3-getsize64-method.md)
