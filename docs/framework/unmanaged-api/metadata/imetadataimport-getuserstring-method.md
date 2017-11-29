---
title: "IMetaDataImport::GetUserString 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetUserString
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetUserString
helpviewer_keywords:
- IMetaDataImport::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0fd3bb47-58b5-4083-b241-b9719df7a285
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 340d5cdfcb218f74a43ed6e88f5175a1d215a1b9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetuserstring-method"></a><span data-ttu-id="6e13f-102">IMetaDataImport::GetUserString 方法</span><span class="sxs-lookup"><span data-stu-id="6e13f-102">IMetaDataImport::GetUserString Method</span></span>
<span data-ttu-id="6e13f-103">获取指定元数据标记所表示的文字字符串。</span><span class="sxs-lookup"><span data-stu-id="6e13f-103">Gets the literal string represented by the specified metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e13f-104">语法</span><span class="sxs-lookup"><span data-stu-id="6e13f-104">Syntax</span></span>  
  
```  
HRESULT GetUserString (  
   [in]   mdString    stk,  
   [out]  LPWSTR      szString,  
   [in]   ULONG       cchString,  
   [out]  ULONG       *pchString  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6e13f-105">参数</span><span class="sxs-lookup"><span data-stu-id="6e13f-105">Parameters</span></span>  
 `stk`  
 <span data-ttu-id="6e13f-106">[in]要返回的关联的字符串的字符串标记。</span><span class="sxs-lookup"><span data-stu-id="6e13f-106">[in] The String token to return the associated string for.</span></span>  
  
 `szString`  
 <span data-ttu-id="6e13f-107">[out]请求的字符串的副本。</span><span class="sxs-lookup"><span data-stu-id="6e13f-107">[out] A copy of the requested string.</span></span>  
  
 `cchString`  
 <span data-ttu-id="6e13f-108">[in]以宽字符为单位的所请求的最大大小`szString`。</span><span class="sxs-lookup"><span data-stu-id="6e13f-108">[in] The maximum size in wide characters of the requested `szString`.</span></span>  
  
 `pchString`  
 <span data-ttu-id="6e13f-109">[out]在返回的宽字符的大小`szString`。</span><span class="sxs-lookup"><span data-stu-id="6e13f-109">[out] The size in wide characters of the returned `szString`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6e13f-110">要求</span><span class="sxs-lookup"><span data-stu-id="6e13f-110">Requirements</span></span>  
 <span data-ttu-id="6e13f-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="6e13f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6e13f-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6e13f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6e13f-113">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="6e13f-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6e13f-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6e13f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e13f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e13f-115">See Also</span></span>  
 [<span data-ttu-id="6e13f-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="6e13f-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="6e13f-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="6e13f-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
