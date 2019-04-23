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
ms.openlocfilehash: 651659a48ba9950cdd837889c4491c66fe40b507
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59202958"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="c0513-102">IMetaDataEmit::SetModuleProps 方法</span><span class="sxs-lookup"><span data-stu-id="c0513-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="c0513-103">更新对由调用之前定义的模块的引用[imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c0513-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0513-104">语法</span><span class="sxs-lookup"><span data-stu-id="c0513-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c0513-105">参数</span><span class="sxs-lookup"><span data-stu-id="c0513-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c0513-106">[in]Unicode 中的模块名称。</span><span class="sxs-lookup"><span data-stu-id="c0513-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="c0513-107">这是只是文件名而不是完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="c0513-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0513-108">要求</span><span class="sxs-lookup"><span data-stu-id="c0513-108">Requirements</span></span>  
 <span data-ttu-id="c0513-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c0513-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0513-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c0513-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0513-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c0513-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c0513-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0513-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0513-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0513-113">See also</span></span>

- [<span data-ttu-id="c0513-114">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="c0513-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c0513-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="c0513-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
