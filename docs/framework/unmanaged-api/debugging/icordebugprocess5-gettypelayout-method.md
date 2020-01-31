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
ms.openlocfilehash: 306d881c05c2fcdb15a53a439bfce6eff3afffa8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792310"
---
# <a name="icordebugprocess5gettypelayout-method"></a><span data-ttu-id="7ecb4-102">ICorDebugProcess5::GetTypeLayout 方法</span><span class="sxs-lookup"><span data-stu-id="7ecb4-102">ICorDebugProcess5::GetTypeLayout Method</span></span>
<span data-ttu-id="7ecb4-103">根据对象的类型标识符获取有关该对象在内存中的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="7ecb4-103">Gets information about the layout of an object in memory based on its type identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ecb4-104">语法</span><span class="sxs-lookup"><span data-stu-id="7ecb4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ecb4-105">参数</span><span class="sxs-lookup"><span data-stu-id="7ecb4-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="7ecb4-106">中一个[COR_TYPEID](cor-typeid-structure.md)标记，它指定需要其布局的类型。</span><span class="sxs-lookup"><span data-stu-id="7ecb4-106">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the type whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="7ecb4-107">弄指向[COR_TYPE_LAYOUT](cor-type-layout-structure.md)结构的指针，该结构包含有关内存中对象的布局的信息。</span><span class="sxs-lookup"><span data-stu-id="7ecb4-107">[out] A pointer to a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that contains information about the layout of the object in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ecb4-108">备注</span><span class="sxs-lookup"><span data-stu-id="7ecb4-108">Remarks</span></span>  
 <span data-ttu-id="7ecb4-109">`ICorDebugProcess5::GetTypeLayout` 方法根据对象[COR_TYPEID](cor-typeid-structure.md)提供有关该对象的信息，该对象由许多其他[ICorDebugProcess5](icordebugprocess5-interface.md)方法返回。</span><span class="sxs-lookup"><span data-stu-id="7ecb4-109">The `ICorDebugProcess5::GetTypeLayout` method provides information about an object based on its [COR_TYPEID](cor-typeid-structure.md), which is returned by a number of other [ICorDebugProcess5](icordebugprocess5-interface.md) methods.</span></span> <span data-ttu-id="7ecb4-110">此信息由方法填充的[COR_TYPE_LAYOUT](cor-type-layout-structure.md)结构提供。</span><span class="sxs-lookup"><span data-stu-id="7ecb4-110">The information is provided by a [COR_TYPE_LAYOUT](cor-type-layout-structure.md) structure that is populated by the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ecb4-111">需求</span><span class="sxs-lookup"><span data-stu-id="7ecb4-111">Requirements</span></span>  
 <span data-ttu-id="7ecb4-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7ecb4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ecb4-113">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ecb4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ecb4-114">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ecb4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ecb4-115">**.NET Framework 版本：** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ecb4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ecb4-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ecb4-116">See also</span></span>

- [<span data-ttu-id="7ecb4-117">COR_TYPE_LAYOUT 结构</span><span class="sxs-lookup"><span data-stu-id="7ecb4-117">COR_TYPE_LAYOUT Structure</span></span>](cor-type-layout-structure.md)
- [<span data-ttu-id="7ecb4-118">ICorDebugProcess5 接口</span><span class="sxs-lookup"><span data-stu-id="7ecb4-118">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="7ecb4-119">调试接口</span><span class="sxs-lookup"><span data-stu-id="7ecb4-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
