---
title: "IMetaDataEmit::DefineModuleRef 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataEmit.DefineModuleRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineModuleRef
helpviewer_keywords:
- DefineModuleRef method [.NET Framework metadata]
- IMetaDataEmit::DefineModuleRef method [.NET Framework metadata]
ms.assetid: f2833594-d90b-4a71-9a53-34b12470c64a
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2b745e216ca49ed5d226d6d531281880b43e4939
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="f7f45-102">IMetaDataEmit::DefineModuleRef 方法</span><span class="sxs-lookup"><span data-stu-id="f7f45-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="f7f45-103">创建具有指定名称的模块的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="f7f45-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f45-104">语法</span><span class="sxs-lookup"><span data-stu-id="f7f45-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7f45-105">参数</span><span class="sxs-lookup"><span data-stu-id="f7f45-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="f7f45-106">[in]其他元数据文件，通常的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="f7f45-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="f7f45-107">这是只是文件名。</span><span class="sxs-lookup"><span data-stu-id="f7f45-107">This is the file name only.</span></span> <span data-ttu-id="f7f45-108">不要使用完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="f7f45-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="f7f45-109">[out]分配`mdModuleRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="f7f45-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7f45-110">惠?</span><span class="sxs-lookup"><span data-stu-id="f7f45-110">Requirements</span></span>  
 <span data-ttu-id="f7f45-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f7f45-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7f45-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f7f45-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f7f45-113">**库：**用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="f7f45-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7f45-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f45-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f45-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="f7f45-115">See Also</span></span>  
 [<span data-ttu-id="f7f45-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="f7f45-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f7f45-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="f7f45-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
