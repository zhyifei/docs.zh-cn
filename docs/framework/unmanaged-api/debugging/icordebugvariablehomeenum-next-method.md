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
ms.openlocfilehash: 2bb6fee00bb99555bc19f35e1250880cc3985f7f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790929"
---
# <a name="icordebugvariablehomeenumnext-method"></a><span data-ttu-id="8c598-102">ICorDebugVariableHomeEnum：： Next 方法</span><span class="sxs-lookup"><span data-stu-id="8c598-102">ICorDebugVariableHomeEnum::Next Method</span></span>
<span data-ttu-id="8c598-103">获取指定数量的[ICorDebugVariableHome](icordebugvariablehome-interface.md)实例，其中包含有关函数中的局部变量和参数的信息。</span><span class="sxs-lookup"><span data-stu-id="8c598-103">Gets the specified number of [ICorDebugVariableHome](icordebugvariablehome-interface.md) instances that contain information about the local variables and arguments in a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8c598-104">语法</span><span class="sxs-lookup"><span data-stu-id="8c598-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] ICorDebugVariableHome *homes[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8c598-105">参数</span><span class="sxs-lookup"><span data-stu-id="8c598-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="8c598-106">[in] 要检索的对象数。</span><span class="sxs-lookup"><span data-stu-id="8c598-106">[in] The number of objects to be retrieved.</span></span>  
  
 `homes`  
 <span data-ttu-id="8c598-107">指针的数组，其中每个都指向一个[ICorDebugVariableHome](icordebugvariablehome-interface.md)对象，该对象提供有关函数的局部变量或自变量的信息。</span><span class="sxs-lookup"><span data-stu-id="8c598-107">An array of pointers, each of which points to a [ICorDebugVariableHome](icordebugvariablehome-interface.md) object that provides information about  a local variable or argument of a function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="8c598-108">弄对象中实际返回的实例数。</span><span class="sxs-lookup"><span data-stu-id="8c598-108">[out] The number of instances actually returned in objects.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8c598-109">返回值</span><span class="sxs-lookup"><span data-stu-id="8c598-109">Return Value</span></span>  
 <span data-ttu-id="8c598-110">方法返回以下值。</span><span class="sxs-lookup"><span data-stu-id="8c598-110">The method returns the following values.</span></span>  
  
|<span data-ttu-id="8c598-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8c598-111">HRESULT</span></span>|<span data-ttu-id="8c598-112">描述</span><span class="sxs-lookup"><span data-stu-id="8c598-112">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8c598-113">该方法成功完成。</span><span class="sxs-lookup"><span data-stu-id="8c598-113">The method completed successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8c598-114">检索到的实例的实际数量（在 `pceltFetched`中反映）小于请求的实例数。</span><span class="sxs-lookup"><span data-stu-id="8c598-114">The actual number of instances retrieved, as reflected in `pceltFetched`, is less than the number of instances requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c598-115">备注</span><span class="sxs-lookup"><span data-stu-id="8c598-115">Remarks</span></span>  
 <span data-ttu-id="8c598-116">[ICorDebugVariableHomeEnum：： Next](icordebugvariablehomeenum-next-method.md)方法从枚举器当前位置开始检索最多 `celt` 个对象。</span><span class="sxs-lookup"><span data-stu-id="8c598-116">The [ICorDebugVariableHomeEnum::Next](icordebugvariablehomeenum-next-method.md) method retrieves a maximum of  `celt` objects starting at the current position of the enumerator.</span></span> <span data-ttu-id="8c598-117">当方法返回时，`pceltFetched` 包含检索到的对象的实际数目。</span><span class="sxs-lookup"><span data-stu-id="8c598-117">When the method returns, `pceltFetched` contains the actual number of objects retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c598-118">需求</span><span class="sxs-lookup"><span data-stu-id="8c598-118">Requirements</span></span>  
 <span data-ttu-id="8c598-119">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8c598-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c598-120">**标头**：CorDebug.idl、CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8c598-120">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c598-121">**库：** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8c598-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c598-122">**.NET Framework 版本：** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c598-122">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c598-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c598-123">See also</span></span>

- [<span data-ttu-id="8c598-124">ICorDebugVariableHomeEnum 接口</span><span class="sxs-lookup"><span data-stu-id="8c598-124">ICorDebugVariableHomeEnum Interface</span></span>](icordebugvariablehomeenum-interface.md)
- [<span data-ttu-id="8c598-125">ICorDebugVariableHome 接口</span><span class="sxs-lookup"><span data-stu-id="8c598-125">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
