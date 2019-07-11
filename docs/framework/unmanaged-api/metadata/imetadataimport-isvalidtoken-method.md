---
title: IMetaDataImport::IsValidToken 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.IsValidToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::IsValidToken
helpviewer_keywords:
- IMetaDataImport::IsValidToken method [.NET Framework metadata]
- IsValidToken method [.NET Framework metadata]
ms.assetid: aeb0fc63-9eff-4384-9284-cb9900572d74
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 753449924f3415eb826b59d3a887eb69b9efba39
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778783"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="82226-102">IMetaDataImport::IsValidToken 方法</span><span class="sxs-lookup"><span data-stu-id="82226-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="82226-103">获取指示指定的标记是否包含对代码对象的有效引用的值。</span><span class="sxs-lookup"><span data-stu-id="82226-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82226-104">语法</span><span class="sxs-lookup"><span data-stu-id="82226-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82226-105">参数</span><span class="sxs-lookup"><span data-stu-id="82226-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="82226-106">[in]要检查有关引用有效性的标记。</span><span class="sxs-lookup"><span data-stu-id="82226-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="82226-107">返回值</span><span class="sxs-lookup"><span data-stu-id="82226-107">Return Value</span></span>  
 <span data-ttu-id="82226-108">`true` 如果`tk`是当前作用域内的有效的元数据标记。</span><span class="sxs-lookup"><span data-stu-id="82226-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="82226-109">否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="82226-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82226-110">要求</span><span class="sxs-lookup"><span data-stu-id="82226-110">Requirements</span></span>  
 <span data-ttu-id="82226-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="82226-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82226-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="82226-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82226-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="82226-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="82226-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82226-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82226-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="82226-115">See also</span></span>

- [<span data-ttu-id="82226-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="82226-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="82226-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="82226-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
