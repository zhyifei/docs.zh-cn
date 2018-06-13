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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0023b8ad815b9204ed56791698c7242dfe90bec4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421653"
---
# <a name="icordebugvaluegetsize-method"></a><span data-ttu-id="bef30-102">ICorDebugValue::GetSize 方法</span><span class="sxs-lookup"><span data-stu-id="bef30-102">ICorDebugValue::GetSize Method</span></span>
<span data-ttu-id="bef30-103">获取用字节表示，此"ICorDebugValue"对象的大小。</span><span class="sxs-lookup"><span data-stu-id="bef30-103">Gets the size, in bytes, of this "ICorDebugValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bef30-104">语法</span><span class="sxs-lookup"><span data-stu-id="bef30-104">Syntax</span></span>  
  
```  
HRESULT GetSize (  
    [out] ULONG32   *pSize  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bef30-105">参数</span><span class="sxs-lookup"><span data-stu-id="bef30-105">Parameters</span></span>  
 `pSize`  
 <span data-ttu-id="bef30-106">[out]以字节为单位，此值对象的大小。</span><span class="sxs-lookup"><span data-stu-id="bef30-106">[out] The size, in bytes, of this value object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bef30-107">备注</span><span class="sxs-lookup"><span data-stu-id="bef30-107">Remarks</span></span>  
 <span data-ttu-id="bef30-108">如果值的类型是引用类型，此方法将返回指针的大小，而不是对象的大小。</span><span class="sxs-lookup"><span data-stu-id="bef30-108">If the value's type is a reference type, this method returns the size of the pointer rather than the size of the object.</span></span>  
  
 <span data-ttu-id="bef30-109">`ICorDebugValue::GetSize`方法返回`COR_E_OVERFLOW`大于 64 位平台上的 4 GB 的对象。</span><span class="sxs-lookup"><span data-stu-id="bef30-109">The `ICorDebugValue::GetSize` method returns `COR_E_OVERFLOW` for objects that are larger than 4 GB on 64-bit platforms.</span></span> <span data-ttu-id="bef30-110">使用[icordebugvalue3:: Getsize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)方法相反的对象，是大于 4 GB。</span><span class="sxs-lookup"><span data-stu-id="bef30-110">Use the [ICorDebugValue3::GetSize64](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md) method instead for objects that are larger than 4 GB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bef30-111">要求</span><span class="sxs-lookup"><span data-stu-id="bef30-111">Requirements</span></span>  
 <span data-ttu-id="bef30-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="bef30-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bef30-113">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bef30-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bef30-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bef30-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bef30-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bef30-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bef30-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="bef30-116">See Also</span></span>  
    
 [<span data-ttu-id="bef30-117">GetSize64 方法</span><span class="sxs-lookup"><span data-stu-id="bef30-117">GetSize64 Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-getsize64-method.md)
