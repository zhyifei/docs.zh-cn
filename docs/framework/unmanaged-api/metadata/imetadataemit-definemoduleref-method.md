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
ms.openlocfilehash: c736eccfd5d05ec9b65e6ed26187e7c7b4387c5d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431731"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="983cd-102">IMetaDataEmit::DefineModuleRef 方法</span><span class="sxs-lookup"><span data-stu-id="983cd-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="983cd-103">创建具有指定名称的模块的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="983cd-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="983cd-104">语法</span><span class="sxs-lookup"><span data-stu-id="983cd-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="983cd-105">参数</span><span class="sxs-lookup"><span data-stu-id="983cd-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="983cd-106">中其他元数据文件（通常为 DLL）的名称。</span><span class="sxs-lookup"><span data-stu-id="983cd-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="983cd-107">这只是文件名。</span><span class="sxs-lookup"><span data-stu-id="983cd-107">This is the file name only.</span></span> <span data-ttu-id="983cd-108">不要使用完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="983cd-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="983cd-109">弄分配 `mdModuleRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="983cd-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="983cd-110">要求</span><span class="sxs-lookup"><span data-stu-id="983cd-110">Requirements</span></span>  
 <span data-ttu-id="983cd-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="983cd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="983cd-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="983cd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="983cd-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="983cd-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="983cd-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="983cd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="983cd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="983cd-115">See also</span></span>

- [<span data-ttu-id="983cd-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="983cd-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="983cd-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="983cd-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
