---
title: ICorDebugProcess5::GetTypeLayout 方法
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: a348c3b2ad33a5d68b1bc46e9a284f2d2a9c7304
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121286"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="89166-102">ICorDebugProcess5::GetTypeLayout 方法</span><span class="sxs-lookup"><span data-stu-id="89166-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="89166-103">根据对象的类型标识符获取有关该对象在内存中的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="89166-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89166-104">语法</span><span class="sxs-lookup"><span data-stu-id="89166-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89166-105">参数</span><span class="sxs-lookup"><span data-stu-id="89166-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="89166-106">中指定所需布局的类型的[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)标记。</span><span class="sxs-lookup"><span data-stu-id="89166-106">[in] A [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="89166-107">弄指向[COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)结构的指针，该结构包含有关内存中对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="89166-107">[out] A pointer to a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89166-108">备注</span><span class="sxs-lookup"><span data-stu-id="89166-108">Remarks</span></span>  
 <span data-ttu-id="89166-109">`ICorDebugProcess5::GetTypeLayout` 方法根据对象的[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)提供有关该对象的信息，该对象由多个其他[ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="89166-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="89166-110">此信息由方法填充的[COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)结构提供。</span><span class="sxs-lookup"><span data-stu-id="89166-110">The information is provided by a [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89166-111">要求</span><span class="sxs-lookup"><span data-stu-id="89166-111">Requirements</span></span>  
 <span data-ttu-id="89166-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="89166-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89166-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89166-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89166-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89166-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89166-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89166-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89166-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="89166-116">See also</span></span>

- [<span data-ttu-id="89166-117">COR_TYPE_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="89166-117">COR_TYPE_LAYOUT Structure</span></span>](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [<span data-ttu-id="89166-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="89166-118">ICorDebugProcess5 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [<span data-ttu-id="89166-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="89166-119">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
