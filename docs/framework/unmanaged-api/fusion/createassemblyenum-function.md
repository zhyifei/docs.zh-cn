---
title: CreateAssemblyEnum 函数
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1db72c44b53b5abff9aee35094abc1e0e577fad4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795385"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="c53fd-102">CreateAssemblyEnum 函数</span><span class="sxs-lookup"><span data-stu-id="c53fd-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="c53fd-103">获取一个指针，该指针指向可使用指定的[IAssemblyName](iassemblyname-interface.md)枚举程序集中的对象的[IAssemblyEnum](iassemblyenum-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="c53fd-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c53fd-104">语法</span><span class="sxs-lookup"><span data-stu-id="c53fd-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="c53fd-105">参数</span><span class="sxs-lookup"><span data-stu-id="c53fd-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="c53fd-106">弄指向包含所请求`IAssemblyEnum`指针的内存位置的指针。</span><span class="sxs-lookup"><span data-stu-id="c53fd-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="c53fd-107">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="c53fd-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c53fd-108">`pUnkReserved`必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="c53fd-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="c53fd-109">中`IAssemblyName`请求的程序集的。</span><span class="sxs-lookup"><span data-stu-id="c53fd-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="c53fd-110">此名称用于筛选枚举。</span><span class="sxs-lookup"><span data-stu-id="c53fd-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="c53fd-111">它可以为 null，以枚举全局程序集缓存中的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="c53fd-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="c53fd-112">中用于修改枚举器的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="c53fd-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="c53fd-113">此参数正好包含[ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md)枚举中的一个位。</span><span class="sxs-lookup"><span data-stu-id="c53fd-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="c53fd-114">中保留以供将来进行扩展。</span><span class="sxs-lookup"><span data-stu-id="c53fd-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="c53fd-115">`pvReserved`必须为空引用。</span><span class="sxs-lookup"><span data-stu-id="c53fd-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c53fd-116">备注</span><span class="sxs-lookup"><span data-stu-id="c53fd-116">Remarks</span></span>  
 <span data-ttu-id="c53fd-117">参数只包含`ASM_CACHE_FLAGS`枚举中的一个位。 `dwFlags`</span><span class="sxs-lookup"><span data-stu-id="c53fd-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c53fd-118">要求</span><span class="sxs-lookup"><span data-stu-id="c53fd-118">Requirements</span></span>  
 <span data-ttu-id="c53fd-119">**适用**请参阅[系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c53fd-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c53fd-120">**标头：** 合成。h</span><span class="sxs-lookup"><span data-stu-id="c53fd-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="c53fd-121">**类库**作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c53fd-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c53fd-122">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c53fd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c53fd-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="c53fd-123">See also</span></span>

- [<span data-ttu-id="c53fd-124">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="c53fd-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="c53fd-125">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="c53fd-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="c53fd-126">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="c53fd-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
