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
ms.openlocfilehash: c0c5dabd4145098941e9e8a7e36fa3215c26713d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084893"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="3df21-102">CreateAssemblyEnum 函数</span><span class="sxs-lookup"><span data-stu-id="3df21-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="3df21-103">获取一个指向[IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)可以枚举中具有指定的程序集的对象的实例[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)。</span><span class="sxs-lookup"><span data-stu-id="3df21-103">Gets a pointer to an [IAssemblyEnum](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df21-104">语法</span><span class="sxs-lookup"><span data-stu-id="3df21-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3df21-105">参数</span><span class="sxs-lookup"><span data-stu-id="3df21-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="3df21-106">[out]指向包含所请求的内存位置`IAssemblyEnum`指针。</span><span class="sxs-lookup"><span data-stu-id="3df21-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="3df21-107">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="3df21-107">[in] Reserved for future extensibility.</span></span> `pUnkReserved` <span data-ttu-id="3df21-108">必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="3df21-108">must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="3df21-109">[in]`IAssemblyName`的请求的程序集。</span><span class="sxs-lookup"><span data-stu-id="3df21-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="3df21-110">此名称用于筛选枚举。</span><span class="sxs-lookup"><span data-stu-id="3df21-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="3df21-111">它可以为 null 以枚举在全局程序集缓存中的所有程序集。</span><span class="sxs-lookup"><span data-stu-id="3df21-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3df21-112">[in]用于修改枚举器的行为的标志。</span><span class="sxs-lookup"><span data-stu-id="3df21-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="3df21-113">此参数包含中的一位完全[ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="3df21-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](../../../../docs/framework/unmanaged-api/fusion/asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="3df21-114">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="3df21-114">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="3df21-115">必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="3df21-115">must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3df21-116">备注</span><span class="sxs-lookup"><span data-stu-id="3df21-116">Remarks</span></span>  
 <span data-ttu-id="3df21-117">`dwFlags`参数包含一位完全从`ASM_CACHE_FLAGS`枚举。</span><span class="sxs-lookup"><span data-stu-id="3df21-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3df21-118">要求</span><span class="sxs-lookup"><span data-stu-id="3df21-118">Requirements</span></span>  
 <span data-ttu-id="3df21-119">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3df21-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3df21-120">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="3df21-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="3df21-121">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3df21-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="3df21-122">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="3df21-122">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3df21-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="3df21-123">See also</span></span>

- [<span data-ttu-id="3df21-124">IAssemblyEnum 接口</span><span class="sxs-lookup"><span data-stu-id="3df21-124">IAssemblyEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyenum-interface.md)
- [<span data-ttu-id="3df21-125">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="3df21-125">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="3df21-126">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="3df21-126">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
