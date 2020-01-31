---
title: ICorDebugType2：： GetTypeID 方法
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
ms.openlocfilehash: 631f605fd18559b36071964e35a15761cd4c8228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791225"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="e4ebe-102">ICorDebugType2：： GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="e4ebe-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="e4ebe-103">获取此类型的[COR_TYPEID](cor-typeid-structure.md) 。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-103">Gets a [COR_TYPEID](cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4ebe-104">语法</span><span class="sxs-lookup"><span data-stu-id="e4ebe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4ebe-105">参数</span><span class="sxs-lookup"><span data-stu-id="e4ebe-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="e4ebe-106">弄指向此 ICorDebugType 的[COR_TYPEID](cor-typeid-structure.md)的指针。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-106">[out] A pointer to the [COR_TYPEID](cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e4ebe-107">返回值</span><span class="sxs-lookup"><span data-stu-id="e4ebe-107">Return Value</span></span>  
 <span data-ttu-id="e4ebe-108">如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="e4ebe-109">`HRESULT` 代码包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="e4ebe-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="e4ebe-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="e4ebe-110">Return code</span></span>|<span data-ttu-id="e4ebe-111">描述</span><span class="sxs-lookup"><span data-stu-id="e4ebe-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="e4ebe-112">方法成功。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-112">Method succeeded.</span></span> <span data-ttu-id="e4ebe-113">方法已检索到有效[COR_TYPEID](cor-typeid-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-113">The method has retrieved a valid [COR_TYPEID](cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="e4ebe-114">尚未加载类型。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="e4ebe-115">不支持该类型。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e4ebe-116">备注</span><span class="sxs-lookup"><span data-stu-id="e4ebe-116">Remarks</span></span>  
 <span data-ttu-id="e4ebe-117">此方法提供了一个从 ICorDebugType 的映射，该映射表示可能尚未加载到运行时中的类型，也称为一个[COR_TYPEID](cor-typeid-structure.md)，它用作标识加载到运行时中的类型的不透明句柄。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="e4ebe-118">如果尚未加载 ICorDebugType 所表示的类型，则此方法将返回 `CORDBG_E_CLASS_NOT_LOADED`。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="e4ebe-119">如果该类型不受支持，它将返回 `CORDBG_E_UNSUPPORTED`。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4ebe-120">需求</span><span class="sxs-lookup"><span data-stu-id="e4ebe-120">Requirements</span></span>  
 <span data-ttu-id="e4ebe-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4ebe-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4ebe-122">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4ebe-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4ebe-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4ebe-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4ebe-124">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4ebe-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4ebe-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4ebe-125">See also</span></span>

- [<span data-ttu-id="e4ebe-126">ICorDebugType2 接口</span><span class="sxs-lookup"><span data-stu-id="e4ebe-126">ICorDebugType2 Interface</span></span>](icordebugtype2-interface.md)
