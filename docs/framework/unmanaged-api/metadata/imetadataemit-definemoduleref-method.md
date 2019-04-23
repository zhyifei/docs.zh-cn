---
title: IMetaDataEmit::DefineModuleRef 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f52f102102cb654035d49eea0f4b0a9061475a3a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59128812"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="a4b8d-102">IMetaDataEmit::DefineModuleRef 方法</span><span class="sxs-lookup"><span data-stu-id="a4b8d-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="a4b8d-103">具有指定名称创建一个模块的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="a4b8d-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4b8d-104">语法</span><span class="sxs-lookup"><span data-stu-id="a4b8d-104">Syntax</span></span>  
  
```  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4b8d-105">参数</span><span class="sxs-lookup"><span data-stu-id="a4b8d-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="a4b8d-106">[in]另一台元数据文件，通常的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="a4b8d-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="a4b8d-107">这是只是文件名。</span><span class="sxs-lookup"><span data-stu-id="a4b8d-107">This is the file name only.</span></span> <span data-ttu-id="a4b8d-108">不要使用完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="a4b8d-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="a4b8d-109">[out]已分配`mdModuleRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="a4b8d-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4b8d-110">要求</span><span class="sxs-lookup"><span data-stu-id="a4b8d-110">Requirements</span></span>  
 <span data-ttu-id="a4b8d-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a4b8d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4b8d-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="a4b8d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a4b8d-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a4b8d-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a4b8d-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4b8d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4b8d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="a4b8d-115">See also</span></span>

- [<span data-ttu-id="a4b8d-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="a4b8d-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="a4b8d-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="a4b8d-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
