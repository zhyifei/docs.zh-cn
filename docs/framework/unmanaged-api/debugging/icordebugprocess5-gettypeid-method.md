---
title: ICorDebugProcess5::GetTypeID 方法
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess5.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeID
helpviewer_keywords:
- ICorDebugProcess5::GetTypeID method [.NET Framework debugging]
- GetTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 47dbaea4-8857-462e-93ba-fff880fc9e50
topic_type:
- apiref
ms.openlocfilehash: 499e1fd859a66bb6992c6d02a46e38c514503bd8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205589"
---
# <a name="icordebugprocess5gettypeid-method"></a><span data-ttu-id="ddacb-102">ICorDebugProcess5::GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="ddacb-102">ICorDebugProcess5::GetTypeID Method</span></span>
<span data-ttu-id="ddacb-103">将对象地址转换为[COR_TYPEID](cor-typeid-structure.md)的标识符。</span><span class="sxs-lookup"><span data-stu-id="ddacb-103">Converts an object address to a [COR_TYPEID](cor-typeid-structure.md) identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ddacb-104">语法</span><span class="sxs-lookup"><span data-stu-id="ddacb-104">Syntax</span></span>  
  
```cpp
HRESULT GetTypeID(  
    [in] CORDB_ADDRESS obj,  
    [out] COR_TYPEID *pId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ddacb-105">参数</span><span class="sxs-lookup"><span data-stu-id="ddacb-105">Parameters</span></span>  
 `obj`  
 <span data-ttu-id="ddacb-106">中对象地址。</span><span class="sxs-lookup"><span data-stu-id="ddacb-106">[in] The object address.</span></span>  
  
 `pId`  
 <span data-ttu-id="ddacb-107">一个指针，指向用于标识对象的[COR_TYPEID](cor-typeid-structure.md)值。</span><span class="sxs-lookup"><span data-stu-id="ddacb-107">A pointer to the [COR_TYPEID](cor-typeid-structure.md) value that identifies the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ddacb-108">备注</span><span class="sxs-lookup"><span data-stu-id="ddacb-108">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ddacb-109">要求</span><span class="sxs-lookup"><span data-stu-id="ddacb-109">Requirements</span></span>  
 <span data-ttu-id="ddacb-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ddacb-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ddacb-111">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ddacb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ddacb-112">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ddacb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ddacb-113">**.NET Framework 版本：**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ddacb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddacb-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddacb-114">See also</span></span>

- [<span data-ttu-id="ddacb-115">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="ddacb-115">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="ddacb-116">调试接口</span><span class="sxs-lookup"><span data-stu-id="ddacb-116">Debugging Interfaces</span></span>](debugging-interfaces.md)
