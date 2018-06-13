---
title: ICorDebugType2::GetTypeID 方法
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5bc1407f8444b78154981619742bd0da188c4335
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422066"
---
# <a name="icordebugtype2gettypeid-method"></a><span data-ttu-id="7c2aa-102">ICorDebugType2::GetTypeID 方法</span><span class="sxs-lookup"><span data-stu-id="7c2aa-102">ICorDebugType2::GetTypeID Method</span></span>
<span data-ttu-id="7c2aa-103">获取[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)此类型。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-103">Gets a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c2aa-104">语法</span><span class="sxs-lookup"><span data-stu-id="7c2aa-104">Syntax</span></span>  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7c2aa-105">参数</span><span class="sxs-lookup"><span data-stu-id="7c2aa-105">Parameters</span></span>  
 `id`  
 <span data-ttu-id="7c2aa-106">[out]指向的指针[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)为此 ICorDebugType。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-106">[out] A pointer to the [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) for this ICorDebugType.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7c2aa-107">返回值</span><span class="sxs-lookup"><span data-stu-id="7c2aa-107">Return Value</span></span>  
 <span data-ttu-id="7c2aa-108">如果成功，则返回值是 `S_OK`；如果失败，则返回失败 `HRESULT` 代码。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-108">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="7c2aa-109">`HRESULT`代码如下：</span><span class="sxs-lookup"><span data-stu-id="7c2aa-109">The `HRESULT` codes include the following:</span></span>  
  
|<span data-ttu-id="7c2aa-110">返回代码</span><span class="sxs-lookup"><span data-stu-id="7c2aa-110">Return code</span></span>|<span data-ttu-id="7c2aa-111">描述</span><span class="sxs-lookup"><span data-stu-id="7c2aa-111">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="7c2aa-112">方法成功。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-112">Method succeeded.</span></span> <span data-ttu-id="7c2aa-113">该方法已检索有效[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-113">The method has retrieved a valid [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).</span></span>|  
|`CORDBG_E_CLASS_NOT_LOADED`|<span data-ttu-id="7c2aa-114">尚未加载该类型。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-114">The type has not been loaded.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="7c2aa-115">不支持的类型。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-115">The type is not supported.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c2aa-116">备注</span><span class="sxs-lookup"><span data-stu-id="7c2aa-116">Remarks</span></span>  
 <span data-ttu-id="7c2aa-117">此方法从 ICorDebugType，表示可能或可能不具有已加载到运行时，为的类型提供映射[COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md)，后者相当于一个不透明处理标识入运行时加载的类型。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-117">This method provides a mapping from the ICorDebugType, which represents a type that may or may not have been loaded into the runtime, to a [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), which serves as an opaque handle that identifies a type loaded into the runtime.</span></span>  
  
 <span data-ttu-id="7c2aa-118">当 ICorDebugType 表示的类型，但尚未被加载，则此方法返回`CORDBG_E_CLASS_NOT_LOADED`。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-118">When the type that the ICorDebugType represents has not yet been loaded, this method returns `CORDBG_E_CLASS_NOT_LOADED`.</span></span>  <span data-ttu-id="7c2aa-119">如果不支持的类型，它将返回`CORDBG_E_UNSUPPORTED`。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-119">If the type is not supported, it returns `CORDBG_E_UNSUPPORTED`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c2aa-120">要求</span><span class="sxs-lookup"><span data-stu-id="7c2aa-120">Requirements</span></span>  
 <span data-ttu-id="7c2aa-121">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7c2aa-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c2aa-122">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c2aa-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c2aa-123">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c2aa-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c2aa-124">**.NET framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c2aa-124">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c2aa-125">请参阅</span><span class="sxs-lookup"><span data-stu-id="7c2aa-125">See Also</span></span>  
 [<span data-ttu-id="7c2aa-126">ICorDebugType2 接口</span><span class="sxs-lookup"><span data-stu-id="7c2aa-126">ICorDebugType2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
