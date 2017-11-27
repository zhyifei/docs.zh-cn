---
title: "IMetaDataEmit::SetModuleProps 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.SetModuleProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 0653f0407486e09ab51ef05e74218207268b6e8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="c5bd8-102">IMetaDataEmit::SetModuleProps 方法</span><span class="sxs-lookup"><span data-stu-id="c5bd8-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="c5bd8-103">更新对由调用定义的模块引用[imetadataemit:: Definemoduleref](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)。</span><span class="sxs-lookup"><span data-stu-id="c5bd8-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5bd8-104">语法</span><span class="sxs-lookup"><span data-stu-id="c5bd8-104">Syntax</span></span>  
  
```  
HRESULT SetModuleProps (   
    [in]  LPCWSTR     szName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c5bd8-105">参数</span><span class="sxs-lookup"><span data-stu-id="c5bd8-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="c5bd8-106">[in]Unicode 中的模块名称。</span><span class="sxs-lookup"><span data-stu-id="c5bd8-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="c5bd8-107">这是只是文件名而不是完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="c5bd8-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5bd8-108">要求</span><span class="sxs-lookup"><span data-stu-id="c5bd8-108">Requirements</span></span>  
 <span data-ttu-id="c5bd8-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c5bd8-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5bd8-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c5bd8-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5bd8-111">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c5bd8-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c5bd8-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5bd8-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5bd8-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5bd8-113">See Also</span></span>  
 [<span data-ttu-id="c5bd8-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="c5bd8-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="c5bd8-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="c5bd8-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
