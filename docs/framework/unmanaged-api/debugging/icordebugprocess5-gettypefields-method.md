---
title: ICorDebugProcess5::GetTypeFields 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 644b5ed751caaf1809250244b37badc8037b0f57
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792344"
---
# <a name="icordebugprocess5gettypefields-method"></a><span data-ttu-id="563f1-102">ICorDebugProcess5::GetTypeFields 方法</span><span class="sxs-lookup"><span data-stu-id="563f1-102">ICorDebugProcess5::GetTypeFields Method</span></span>
<span data-ttu-id="563f1-103">提供有关属于类型的字段的信息。</span><span class="sxs-lookup"><span data-stu-id="563f1-103">Provides information about the fields that belong to a type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="563f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="563f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="563f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="563f1-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="563f1-106">中检索其字段信息的类型的标识符。</span><span class="sxs-lookup"><span data-stu-id="563f1-106">[in] The identifier of the type whose field information is retrieved.</span></span>  
  
 `celt`  
 <span data-ttu-id="563f1-107">中要检索其字段信息的[COR_FIELD](cor-field-structure.md)对象的数量。</span><span class="sxs-lookup"><span data-stu-id="563f1-107">[in] The number of [COR_FIELD](cor-field-structure.md) objects whose field information is to be retrieved.</span></span>  
  
 `fields`  
 <span data-ttu-id="563f1-108">弄[COR_FIELD](cor-field-structure.md)对象的数组，这些对象提供有关属于类型的字段的信息。</span><span class="sxs-lookup"><span data-stu-id="563f1-108">[out] An array of [COR_FIELD](cor-field-structure.md) objects that provide information about the fields that belong to the type.</span></span>  
  
 `pceltNeeded`  
 <span data-ttu-id="563f1-109">弄一个指针，指向 `fields`中包含的[COR_FIELD](cor-field-structure.md)对象的数量。</span><span class="sxs-lookup"><span data-stu-id="563f1-109">[out] A pointer to the number of [COR_FIELD](cor-field-structure.md) objects included in `fields`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="563f1-110">备注</span><span class="sxs-lookup"><span data-stu-id="563f1-110">Remarks</span></span>  
 <span data-ttu-id="563f1-111">`celt` 参数，它指定方法用来填充 `fields`的字段信息的字段数，应与 `COR_TYPE_LAYOUT::numFields` 字段的值相对应。</span><span class="sxs-lookup"><span data-stu-id="563f1-111">The `celt` parameter, which specifies the number of fields whose field information the method uses to populate `fields`, should correspond to the value of the `COR_TYPE_LAYOUT::numFields` field.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="563f1-112">需求</span><span class="sxs-lookup"><span data-stu-id="563f1-112">Requirements</span></span>  
 <span data-ttu-id="563f1-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="563f1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="563f1-114">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="563f1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="563f1-115">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="563f1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="563f1-116">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="563f1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="563f1-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="563f1-117">See also</span></span>

- [<span data-ttu-id="563f1-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="563f1-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="563f1-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="563f1-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
