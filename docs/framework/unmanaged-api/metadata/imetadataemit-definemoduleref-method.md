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
ms.openlocfilehash: efff491d92ac7910f43f76965ef98d1d0e4ba0aa
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004421"
---
# <a name="imetadataemitdefinemoduleref-method"></a><span data-ttu-id="8b2ab-102">IMetaDataEmit::DefineModuleRef 方法</span><span class="sxs-lookup"><span data-stu-id="8b2ab-102">IMetaDataEmit::DefineModuleRef Method</span></span>
<span data-ttu-id="8b2ab-103">创建具有指定名称的模块的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="8b2ab-103">Creates the metadata signature for a module with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b2ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="8b2ab-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineModuleRef (
    [in]  LPCWSTR           szName,
    [out] mdModuleRef       *pmur
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b2ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="8b2ab-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="8b2ab-106">中其他元数据文件（通常为 DLL）的名称。</span><span class="sxs-lookup"><span data-stu-id="8b2ab-106">[in] The name of the other metadata file, typically a DLL.</span></span> <span data-ttu-id="8b2ab-107">这只是文件名。</span><span class="sxs-lookup"><span data-stu-id="8b2ab-107">This is the file name only.</span></span> <span data-ttu-id="8b2ab-108">不要使用完整路径名称。</span><span class="sxs-lookup"><span data-stu-id="8b2ab-108">Do not use a full path name.</span></span>  
  
 `pmur`  
 <span data-ttu-id="8b2ab-109">弄已分配的 `mdModuleRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="8b2ab-109">[out] The assigned `mdModuleRef` token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b2ab-110">要求</span><span class="sxs-lookup"><span data-stu-id="8b2ab-110">Requirements</span></span>  
 <span data-ttu-id="8b2ab-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b2ab-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b2ab-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8b2ab-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b2ab-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8b2ab-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8b2ab-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b2ab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b2ab-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b2ab-115">See also</span></span>

- [<span data-ttu-id="8b2ab-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="8b2ab-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8b2ab-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="8b2ab-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
