---
title: IMetaDataImport::GetParamForMethodIndex 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7455d87caff86c57409f4bb016ec73c365a3d35d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487117"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="90e95-102">IMetaDataImport::GetParamForMethodIndex 方法</span><span class="sxs-lookup"><span data-stu-id="90e95-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="90e95-103">获取表示指定的 MethodDef 标记所表示的方法的指定的参数的标记。</span><span class="sxs-lookup"><span data-stu-id="90e95-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90e95-104">语法</span><span class="sxs-lookup"><span data-stu-id="90e95-104">Syntax</span></span>  
  
```  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="90e95-105">参数</span><span class="sxs-lookup"><span data-stu-id="90e95-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="90e95-106">[in]表示此方法返回的参数标记的标记。</span><span class="sxs-lookup"><span data-stu-id="90e95-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="90e95-107">[in]发生请求的参数序号位置在参数列表中。</span><span class="sxs-lookup"><span data-stu-id="90e95-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="90e95-108">从一个方法的返回值在位置 0 开始编号参数。</span><span class="sxs-lookup"><span data-stu-id="90e95-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="90e95-109">[out]指向表示请求的参数的 ParamDef 标记的指针。</span><span class="sxs-lookup"><span data-stu-id="90e95-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90e95-110">要求</span><span class="sxs-lookup"><span data-stu-id="90e95-110">Requirements</span></span>  
 <span data-ttu-id="90e95-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90e95-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90e95-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90e95-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90e95-113">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="90e95-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90e95-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90e95-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90e95-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="90e95-115">See also</span></span>
- [<span data-ttu-id="90e95-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="90e95-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="90e95-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="90e95-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
