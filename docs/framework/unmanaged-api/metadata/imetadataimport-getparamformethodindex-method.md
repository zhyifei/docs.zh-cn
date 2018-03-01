---
title: "IMetaDataImport::GetParamForMethodIndex 方法"
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
- IMetaDataImport.GetParamForMethodIndex
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamForMethodIndex
helpviewer_keywords:
- IMetaDataImport::GetParamForMethodIndex method [.NET Framework metadata]
- GetParamForMethodIndex method [.NET Framework metadata]
ms.assetid: ec3bfa95-1920-4511-932e-3ff23d76fcb8
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0cedc993e6b8794a15ff9927b06ff650ed76b79e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="053ca-102">IMetaDataImport::GetParamForMethodIndex 方法</span><span class="sxs-lookup"><span data-stu-id="053ca-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="053ca-103">获取表示指定的 MethodDef 标记所表示的方法的指定的参数的标记。</span><span class="sxs-lookup"><span data-stu-id="053ca-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="053ca-104">语法</span><span class="sxs-lookup"><span data-stu-id="053ca-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="053ca-105">参数</span><span class="sxs-lookup"><span data-stu-id="053ca-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="053ca-106">[in]一个表示要返回的参数标记的方法的标记。</span><span class="sxs-lookup"><span data-stu-id="053ca-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="053ca-107">[in]中的序号位置的参数列表的请求的参数的出现位置。</span><span class="sxs-lookup"><span data-stu-id="053ca-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="053ca-108">从另一个使用该方法的返回值在位置 0 开始编号参数。</span><span class="sxs-lookup"><span data-stu-id="053ca-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="053ca-109">[out]指向一个 ParamDef 标记，用于表示请求的参数的指针。</span><span class="sxs-lookup"><span data-stu-id="053ca-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="053ca-110">惠?</span><span class="sxs-lookup"><span data-stu-id="053ca-110">Requirements</span></span>  
 <span data-ttu-id="053ca-111">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="053ca-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="053ca-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="053ca-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="053ca-113">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="053ca-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="053ca-114">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="053ca-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="053ca-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="053ca-115">See Also</span></span>  
 [<span data-ttu-id="053ca-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="053ca-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="053ca-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="053ca-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
