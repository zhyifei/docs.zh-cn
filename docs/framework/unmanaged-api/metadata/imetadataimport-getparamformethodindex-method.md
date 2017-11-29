---
title: "IMetaDataImport::GetParamForMethodIndex 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamForMethodIndex
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cda4ffde7d38d74ddf7a81b6f0af4a556693094d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="0c4f1-102">IMetaDataImport::GetParamForMethodIndex 方法</span><span class="sxs-lookup"><span data-stu-id="0c4f1-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="0c4f1-103">获取表示指定的 MethodDef 标记所表示的方法的指定的参数的标记。</span><span class="sxs-lookup"><span data-stu-id="0c4f1-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c4f1-104">语法</span><span class="sxs-lookup"><span data-stu-id="0c4f1-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0c4f1-105">参数</span><span class="sxs-lookup"><span data-stu-id="0c4f1-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="0c4f1-106">[in]一个表示要返回的参数标记的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="0c4f1-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="0c4f1-107">[in]中的序号位置的参数列表的请求的参数的出现位置。</span><span class="sxs-lookup"><span data-stu-id="0c4f1-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="0c4f1-108">从另一个使用该方法的返回值在位置 0 开始编号参数。</span><span class="sxs-lookup"><span data-stu-id="0c4f1-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="0c4f1-109">[out]指向一个 ParamDef 标记，用于表示请求的参数的指针。</span><span class="sxs-lookup"><span data-stu-id="0c4f1-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0c4f1-110">要求</span><span class="sxs-lookup"><span data-stu-id="0c4f1-110">Requirements</span></span>  
 <span data-ttu-id="0c4f1-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0c4f1-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c4f1-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0c4f1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0c4f1-113">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="0c4f1-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0c4f1-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c4f1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4f1-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c4f1-115">See Also</span></span>  
 [<span data-ttu-id="0c4f1-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="0c4f1-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="0c4f1-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="0c4f1-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
