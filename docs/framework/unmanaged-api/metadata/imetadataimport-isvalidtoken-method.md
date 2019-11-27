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
ms.openlocfilehash: edf24de8ae38aab97e41a53cc86ae5aa6c592c50
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74434701"
---
# <a name="imetadataimportisvalidtoken-method"></a><span data-ttu-id="c75d5-102">IMetaDataImport::IsValidToken 方法</span><span class="sxs-lookup"><span data-stu-id="c75d5-102">IMetaDataImport::IsValidToken Method</span></span>
<span data-ttu-id="c75d5-103">获取指示指定的标记是否包含对代码对象的有效引用的值。</span><span class="sxs-lookup"><span data-stu-id="c75d5-103">Gets a value indicating whether the specified token holds a valid reference to a code object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c75d5-104">语法</span><span class="sxs-lookup"><span data-stu-id="c75d5-104">Syntax</span></span>  
  
```cpp  
BOOL IsValidToken (  
   [in] mdToken     tk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c75d5-105">参数</span><span class="sxs-lookup"><span data-stu-id="c75d5-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="c75d5-106">中要检查其引用有效性的标记。</span><span class="sxs-lookup"><span data-stu-id="c75d5-106">[in] The token to check the reference validity for.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c75d5-107">返回值</span><span class="sxs-lookup"><span data-stu-id="c75d5-107">Return Value</span></span>  
 <span data-ttu-id="c75d5-108">如果 `tk` 是当前范围内的有效元数据标记，则 `true`。</span><span class="sxs-lookup"><span data-stu-id="c75d5-108">`true` if `tk` is a valid metadata token within the current scope.</span></span> <span data-ttu-id="c75d5-109">否则为 `false`。</span><span class="sxs-lookup"><span data-stu-id="c75d5-109">Otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c75d5-110">要求</span><span class="sxs-lookup"><span data-stu-id="c75d5-110">Requirements</span></span>  
 <span data-ttu-id="c75d5-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c75d5-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c75d5-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c75d5-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c75d5-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="c75d5-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c75d5-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c75d5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c75d5-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c75d5-115">See also</span></span>

- [<span data-ttu-id="c75d5-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c75d5-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c75d5-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c75d5-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
