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
ms.openlocfilehash: 5433c49db8e507c6026ab0e87040dd5634ad0808
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430433"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="0c52d-102">CreateAssemblyNameObject 函数</span><span class="sxs-lookup"><span data-stu-id="0c52d-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="0c52d-103">获取到的接口指针[IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)表示具有指定名称的程序集的唯一标识的实例。</span><span class="sxs-lookup"><span data-stu-id="0c52d-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c52d-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c52d-104">Syntax</span></span>  
  
```  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c52d-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c52d-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="0c52d-106">[out]返回`IAssemblyName`。</span><span class="sxs-lookup"><span data-stu-id="0c52d-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="0c52d-107">[in]要为其创建新程序集的名称`IAssemblyName`实例。</span><span class="sxs-lookup"><span data-stu-id="0c52d-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0c52d-108">[in]要传递给对象构造函数的标志。</span><span class="sxs-lookup"><span data-stu-id="0c52d-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="0c52d-109">[in]留待将来扩展。</span><span class="sxs-lookup"><span data-stu-id="0c52d-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="0c52d-110">`pvReserved` 必须是 null 引用。</span><span class="sxs-lookup"><span data-stu-id="0c52d-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c52d-111">要求</span><span class="sxs-lookup"><span data-stu-id="0c52d-111">Requirements</span></span>  
 <span data-ttu-id="0c52d-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c52d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c52d-113">**标头：** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="0c52d-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="0c52d-114">**库：** 作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0c52d-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c52d-115">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c52d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c52d-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c52d-116">See Also</span></span>  
 [<span data-ttu-id="0c52d-117">IAssemblyName 接口</span><span class="sxs-lookup"><span data-stu-id="0c52d-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [<span data-ttu-id="0c52d-118">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="0c52d-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
