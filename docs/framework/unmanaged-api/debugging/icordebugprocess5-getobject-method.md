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
ms.openlocfilehash: de570507c4312f09def0908b9d56e5371c63527e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207291"
---
# <a name="icordebugprocess5getobject-method"></a><span data-ttu-id="a6f53-102">ICorDebugProcess5::GetObject 方法</span><span class="sxs-lookup"><span data-stu-id="a6f53-102">ICorDebugProcess5::GetObject Method</span></span>
<span data-ttu-id="a6f53-103">将对象地址转换为 "ICorDebugObjectValue" 对象。</span><span class="sxs-lookup"><span data-stu-id="a6f53-103">Converts an object address to an "ICorDebugObjectValue" object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6f53-104">语法</span><span class="sxs-lookup"><span data-stu-id="a6f53-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObject(  
    [in] CORDB_ADDRESS addr,
    [out] ICorDebugObjectValue **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6f53-105">参数</span><span class="sxs-lookup"><span data-stu-id="a6f53-105">Parameters</span></span>  
 `addr`  
 <span data-ttu-id="a6f53-106">中对象地址。</span><span class="sxs-lookup"><span data-stu-id="a6f53-106">[in] The object address.</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a6f53-107">弄一个指向 "ICorDebugObjectValue" 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="a6f53-107">[out] A pointer to the address of an  "ICorDebugObjectValue" object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a6f53-108">备注</span><span class="sxs-lookup"><span data-stu-id="a6f53-108">Remarks</span></span>  
 <span data-ttu-id="a6f53-109">如果不 `addr` 指向有效的托管对象，该方法将 `GetObject` 返回 `E_FAIL` 。</span><span class="sxs-lookup"><span data-stu-id="a6f53-109">If `addr` does not point to a valid managed object, the `GetObject` method returns `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6f53-110">要求</span><span class="sxs-lookup"><span data-stu-id="a6f53-110">Requirements</span></span>  
 <span data-ttu-id="a6f53-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a6f53-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6f53-112">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6f53-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6f53-113">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6f53-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6f53-114">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6f53-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6f53-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a6f53-115">See also</span></span>

- [<span data-ttu-id="a6f53-116">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="a6f53-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="a6f53-117">调试接口</span><span class="sxs-lookup"><span data-stu-id="a6f53-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
