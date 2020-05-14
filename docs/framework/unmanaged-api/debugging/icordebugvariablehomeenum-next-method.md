---
title: ICorDebugVariableHomeEnum：： Next 方法
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
ms.openlocfilehash: 980f563d3b11fbfcce48b6d7c05275af520e14f1
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396508"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="1e789-102">ICorDebugVariableHomeEnum：： Next 方法</span><span class="sxs-lookup"><span data-stu-id="1e789-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="1e789-103">获取指定数量的[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例，其中包含有关函数中的局部变量和参数的信息。</span><span class="sxs-lookup"><span data-stu-id="1e789-103">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e789-104">语法</span><span class="sxs-lookup"><span data-stu-id="1e789-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e789-105">参数</span><span class="sxs-lookup"><span data-stu-id="1e789-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="1e789-106">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="1e789-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="1e789-107">指针的数组，其中每个都指向一个[ICorDebugVariableHome](icordebugvariablehome-interface.md)对象，该对象提供有关函数的局部变量或自变量的信息。</span><span class="sxs-lookup"><span data-stu-id="1e789-107">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="1e789-108">弄对象中实际返回的实例数。</span><span class="sxs-lookup"><span data-stu-id="1e789-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1e789-109">返回值</span><span class="sxs-lookup"><span data-stu-id="1e789-109">Return Value</span></span>  
 <span data-ttu-id="1e789-110">方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="1e789-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="1e789-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1e789-111">HRESULT</span></span>|<span data-ttu-id="1e789-112">说明</span><span class="sxs-lookup"><span data-stu-id="1e789-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="1e789-113">该方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="1e789-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1e789-114">检索到的实际实例数小于所请求的 `pceltFetched` 实例数。</span><span class="sxs-lookup"><span data-stu-id="1e789-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e789-115">备注</span><span class="sxs-lookup"><span data-stu-id="1e789-115">Remarks</span></span>  
 <span data-ttu-id="1e789-116">[ICorDebugVariableHomeEnum：： Next](icordebugvariablehomeenum-next-method.md)方法 `celt` 从枚举器的当前位置开始检索最多对象。</span><span class="sxs-lookup"><span data-stu-id="1e789-116">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="1e789-117">当方法返回时， `pceltFetched` 包含检索到的对象的实际数目。</span><span class="sxs-lookup"><span data-stu-id="1e789-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1e789-118">要求</span><span class="sxs-lookup"><span data-stu-id="1e789-118">Requirements</span></span>  
 <span data-ttu-id="1e789-119">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1e789-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e789-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1e789-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1e789-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1e789-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1e789-122">**.NET Framework 版本：**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e789-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e789-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e789-123">See also</span></span>

- [<span data-ttu-id="1e789-124">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="1e789-124">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="1e789-125">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="1e789-125">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
