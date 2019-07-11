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
ms.openlocfilehash: 19f1839aa2c4ca810e76c1745103a00c6f5ea5a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777574"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="1d210-102">IMetaDataEmit::DefineModuleRef 方法</span><span class="sxs-lookup"><span data-stu-id="1d210-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="1d210-103">具有指定名称创建一个模块的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="1d210-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d210-104">语法</span><span class="sxs-lookup"><span data-stu-id="1d210-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (     
    [in]  LPCWSTR           szName,   
    [out] mdModuleRef       *pmur   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d210-105">参数</span><span class="sxs-lookup"><span data-stu-id="1d210-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="1d210-106">[in]另一台元数据文件，通常的 DLL 的名称。</span><span class="sxs-lookup"><span data-stu-id="1d210-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="1d210-107">这是只是文件名。</span><span class="sxs-lookup"><span data-stu-id="1d210-107">This is the file name only.</span></span> <span data-ttu-id="1d210-108">不要使用完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="1d210-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="1d210-109">[out]已分配`mdModuleRef`令牌。</span><span class="sxs-lookup"><span data-stu-id="1d210-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d210-110">要求</span><span class="sxs-lookup"><span data-stu-id="1d210-110">Requirements</span></span>  
 <span data-ttu-id="1d210-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d210-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d210-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1d210-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d210-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1d210-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1d210-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d210-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d210-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="1d210-115">See also</span></span>

- [<span data-ttu-id="1d210-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="1d210-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1d210-117">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="1d210-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
