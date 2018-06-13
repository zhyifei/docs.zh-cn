---
title: ICorDebugVariableHomeEnum::Next 方法
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum::Next
helpviewer_keywords:
- ICorDebugVariableHomeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: eb9ea96c-5b58-4655-8104-094fc8b393b8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d5ab18d6c2ae8bbf47a3bcd7cb892530be4f8f4e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33421579"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="c5afc-102">ICorDebugVariableHomeEnum::Next 方法</span><span class="sxs-lookup"><span data-stu-id="c5afc-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="c5afc-103">获取指定的数目的[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)包含有关本地变量和函数中的自变量的信息的实例。</span><span class="sxs-lookup"><span data-stu-id="c5afc-103">Gets the specified number of [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5afc-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5afc-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5afc-105">参数</span><span class="sxs-lookup"><span data-stu-id="c5afc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="c5afc-106">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="c5afc-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="c5afc-107">一个指针，其中每个指向数组[ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)提供有关本地变量或函数参数的信息的对象。</span><span class="sxs-lookup"><span data-stu-id="c5afc-107">An array of pointers, each of which points to a [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="c5afc-108">[out]在对象中实际返回的实例数。</span><span class="sxs-lookup"><span data-stu-id="c5afc-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5afc-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c5afc-109">Return Value</span></span>  
 <span data-ttu-id="c5afc-110">该方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="c5afc-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="c5afc-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c5afc-111">HRESULT</span></span>|<span data-ttu-id="c5afc-112">描述</span><span class="sxs-lookup"><span data-stu-id="c5afc-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c5afc-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c5afc-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c5afc-114">检索实例的实际数量，具体体现在`pceltFetched`，小于请求的实例数。</span><span class="sxs-lookup"><span data-stu-id="c5afc-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c5afc-115">备注</span><span class="sxs-lookup"><span data-stu-id="c5afc-115">Remarks</span></span>  
 <span data-ttu-id="c5afc-116">[ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)方法检索的最多`celt`对象的枚举器当前位置开始。</span><span class="sxs-lookup"><span data-stu-id="c5afc-116">The [ICorDebugVariableHomeEnum::Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="c5afc-117">方法返回时，`pceltFetched`包含的实际检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="c5afc-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5afc-118">要求</span><span class="sxs-lookup"><span data-stu-id="c5afc-118">Requirements</span></span>  
 <span data-ttu-id="c5afc-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5afc-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5afc-120">**标头：** CorDebug.idl、 CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c5afc-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c5afc-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c5afc-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c5afc-122">**.NET framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5afc-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5afc-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c5afc-123">See Also</span></span>  
 [<span data-ttu-id="c5afc-124">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c5afc-124">ICorDebugVariableHomeEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
 [<span data-ttu-id="c5afc-125">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="c5afc-125">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
