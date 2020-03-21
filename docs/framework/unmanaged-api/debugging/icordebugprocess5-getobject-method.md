---
title: ICorDebugProcess5::GetObject 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetObject
helpviewer_keywords:
- GetObject method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetObject method [.NET Framework debugging]
ms.assetid: c8111502-5a20-447f-9dc2-76e8acd7ed5a
topic_type:
- apiref
ms.openlocfilehash: 4b48132ee60bcaebb218d8f583de6558372f5055
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178612"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="3185e-102">ICorDebugProcess5::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="3185e-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="3185e-103">将对象地址转换为"ICorDebugObjectValue"对象。</span><span class="sxs-lookup"><span data-stu-id="3185e-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3185e-104">语法</span><span class="sxs-lookup"><span data-stu-id="3185e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3185e-105">parameters</span><span class="sxs-lookup"><span data-stu-id="3185e-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="3185e-106">[在]对象地址。</span><span class="sxs-lookup"><span data-stu-id="3185e-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="3185e-107">[出]指向"ICorDebugObjectValue"对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="3185e-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3185e-108">备注</span><span class="sxs-lookup"><span data-stu-id="3185e-108">Remarks</span></span>  
 <span data-ttu-id="3185e-109">如果不`addr`指向有效的托管对象，`GetObject`则 方法将返回`E_FAIL`。</span><span class="sxs-lookup"><span data-stu-id="3185e-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3185e-110">要求</span><span class="sxs-lookup"><span data-stu-id="3185e-110">Requirements</span></span>  
 <span data-ttu-id="3185e-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3185e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3185e-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3185e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3185e-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3185e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3185e-114">**.NET 框架版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3185e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3185e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3185e-115">See also</span></span>

- [<span data-ttu-id="3185e-116">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="3185e-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="3185e-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="3185e-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
