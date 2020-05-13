---
title: ICorDebugProcess5::GetTypeForTypeID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: ea7f7a9d4589e4f08b1b1e20b4d073bb5f822714
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212758"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a><span data-ttu-id="372e6-102">ICorDebugProcess5::GetTypeForTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="372e6-102">ICorDebugProcess5::GetTypeForTypeID Method</span></span>
<span data-ttu-id="372e6-103">将类型标识符转换为 ICorDebugType 值。</span><span class="sxs-lookup"><span data-stu-id="372e6-103">Converts a type identifier to an ICorDebugType value.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="372e6-104">语法</span><span class="sxs-lookup"><span data-stu-id="372e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="372e6-105">参数</span><span class="sxs-lookup"><span data-stu-id="372e6-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="372e6-106">中类型标识符。</span><span class="sxs-lookup"><span data-stu-id="372e6-106">[in] The type identifier.</span></span>  
  
 `ppType`  
 <span data-ttu-id="372e6-107">弄指向 ICorDebugType 对象地址的指针。</span><span class="sxs-lookup"><span data-stu-id="372e6-107">[out] A pointer to the address of an ICorDebugType object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="372e6-108">备注</span><span class="sxs-lookup"><span data-stu-id="372e6-108">Remarks</span></span>  
 <span data-ttu-id="372e6-109">在某些情况下，返回类型标识符的方法可能返回 null `COR_TYPEID` 值。</span><span class="sxs-lookup"><span data-stu-id="372e6-109">In some cases, methods that return a type identifier may return a null `COR_TYPEID` value.</span></span> <span data-ttu-id="372e6-110">如果此值作为 `id` 参数传递，则 `GetTypeForTypeID` 方法将失败，并返回 `E_FAIL` 。</span><span class="sxs-lookup"><span data-stu-id="372e6-110">If this value is passed as the `id` argument, the `GetTypeForTypeID` method will fail and return `E_FAIL`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="372e6-111">要求</span><span class="sxs-lookup"><span data-stu-id="372e6-111">Requirements</span></span>  
 <span data-ttu-id="372e6-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="372e6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="372e6-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="372e6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="372e6-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="372e6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="372e6-115">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="372e6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="372e6-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="372e6-116">See also</span></span>

- [<span data-ttu-id="372e6-117">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="372e6-117">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="372e6-118">调试接口</span><span class="sxs-lookup"><span data-stu-id="372e6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
