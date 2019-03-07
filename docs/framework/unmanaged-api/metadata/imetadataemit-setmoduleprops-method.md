---
title: IMetaDataEmit::SetModuleProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5219a414c5961128d4eaa27c1f18d635938dc5ba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57497400"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="53b9d-102">IMetaDataEmit::SetModuleProps 方法</span><span class="sxs-lookup"><span data-stu-id="53b9d-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="53b9d-103">更新对由调用之前定义的模块的引用[imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)。</span><span class="sxs-lookup"><span data-stu-id="53b9d-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="53b9d-104">语法</span><span class="sxs-lookup"><span data-stu-id="53b9d-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="53b9d-105">参数</span><span class="sxs-lookup"><span data-stu-id="53b9d-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="53b9d-106">[in]Unicode 中的模块名称。</span><span class="sxs-lookup"><span data-stu-id="53b9d-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="53b9d-107">这是只是文件名而不是完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="53b9d-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="53b9d-108">要求</span><span class="sxs-lookup"><span data-stu-id="53b9d-108">Requirements</span></span>  
 <span data-ttu-id="53b9d-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="53b9d-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="53b9d-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="53b9d-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="53b9d-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="53b9d-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="53b9d-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="53b9d-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53b9d-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="53b9d-113">See also</span></span>
- [<span data-ttu-id="53b9d-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="53b9d-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="53b9d-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="53b9d-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
