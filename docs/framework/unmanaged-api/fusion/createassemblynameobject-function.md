---
title: CreateAssemblyNameObject 函数
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1412231b53763ce8e6c2400497396d2f178d8e7a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54666288"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="eb3f8-102">CreateAssemblyNameObject 函数</span><span class="sxs-lookup"><span data-stu-id="eb3f8-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="eb3f8-103">获取到的接口指针[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)实例，它表示具有指定名称的程序集的唯一标识。</span><span class="sxs-lookup"><span data-stu-id="eb3f8-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb3f8-104">语法</span><span class="sxs-lookup"><span data-stu-id="eb3f8-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb3f8-105">参数</span><span class="sxs-lookup"><span data-stu-id="eb3f8-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="eb3f8-106">[out]返回`IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="eb3f8-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="eb3f8-107">[in]要为其创建新程序集的名称`IAssemblyName`实例。</span><span class="sxs-lookup"><span data-stu-id="eb3f8-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="eb3f8-108">[in]要传递给对象构造函数的标志。</span><span class="sxs-lookup"><span data-stu-id="eb3f8-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="eb3f8-109">[in]保留供将来的扩展。</span><span class="sxs-lookup"><span data-stu-id="eb3f8-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="eb3f8-110">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="eb3f8-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb3f8-111">要求</span><span class="sxs-lookup"><span data-stu-id="eb3f8-111">Requirements</span></span>  
 <span data-ttu-id="eb3f8-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eb3f8-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb3f8-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="eb3f8-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="eb3f8-114">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eb3f8-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eb3f8-115">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb3f8-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb3f8-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="eb3f8-116">See also</span></span>
- [<span data-ttu-id="eb3f8-117">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="eb3f8-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="eb3f8-118">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="eb3f8-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
