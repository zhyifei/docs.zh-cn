---
title: IMetaDataImport::GetUserString 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 358346af540c8b6b7ee1523e763bebbacf8cd2bb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127811"
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="5ff15-102">IMetaDataImport::GetUserString 方法</span><span class="sxs-lookup"><span data-stu-id="5ff15-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="5ff15-103">获取指定元数据标记所表示的文字字符串。</span><span class="sxs-lookup"><span data-stu-id="5ff15-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ff15-104">语法</span><span class="sxs-lookup"><span data-stu-id="5ff15-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ff15-105">参数</span><span class="sxs-lookup"><span data-stu-id="5ff15-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="5ff15-106">[in]要返回的关联的字符串的字符串标记。</span><span class="sxs-lookup"><span data-stu-id="5ff15-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="5ff15-107">[out]所需字符串的副本。</span><span class="sxs-lookup"><span data-stu-id="5ff15-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="5ff15-108">[in]以宽字符为单位的所请求的最大大小`szString`。</span><span class="sxs-lookup"><span data-stu-id="5ff15-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="5ff15-109">[out]以宽字符为单位返回大小`szString`。</span><span class="sxs-lookup"><span data-stu-id="5ff15-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ff15-110">要求</span><span class="sxs-lookup"><span data-stu-id="5ff15-110">Requirements</span></span>  
 <span data-ttu-id="5ff15-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5ff15-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ff15-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5ff15-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ff15-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5ff15-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="5ff15-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="5ff15-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5ff15-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ff15-115">See also</span></span>

- [<span data-ttu-id="5ff15-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="5ff15-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5ff15-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="5ff15-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
