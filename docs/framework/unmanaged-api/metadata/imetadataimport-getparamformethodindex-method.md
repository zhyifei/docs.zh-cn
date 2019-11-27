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
ms.openlocfilehash: a70691b9c519bc59ae7df7a86d5d6697db565575
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437160"
---
# <a name="imetadataimportgetparamformethodindex-method"></a><span data-ttu-id="03892-102">IMetaDataImport::GetParamForMethodIndex 方法</span><span class="sxs-lookup"><span data-stu-id="03892-102">IMetaDataImport::GetParamForMethodIndex Method</span></span>
<span data-ttu-id="03892-103">获取表示指定的 MethodDef 标记所表示的方法的指定参数的令牌。</span><span class="sxs-lookup"><span data-stu-id="03892-103">Gets the token that represents a specified parameter of the method represented by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03892-104">语法</span><span class="sxs-lookup"><span data-stu-id="03892-104">Syntax</span></span>  
  
```cpp  
HRESULT GetParamForMethodIndex (  
   [in]  mdMethodDef      md,  
   [in]  ULONG            ulParamSeq,  
   [out] mdParamDef       *ppd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03892-105">参数</span><span class="sxs-lookup"><span data-stu-id="03892-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="03892-106">中一个标记，表示要为其返回参数标记的方法。</span><span class="sxs-lookup"><span data-stu-id="03892-106">[in] A token that represents the method to return the parameter token for.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="03892-107">中参数列表中出现请求的参数的序号位置。</span><span class="sxs-lookup"><span data-stu-id="03892-107">[in] The ordinal position in the parameter list where the requested parameter occurs.</span></span> <span data-ttu-id="03892-108">参数从1开始编号，方法的返回值位于位置零。</span><span class="sxs-lookup"><span data-stu-id="03892-108">Parameters are numbered starting from one, with the method's return value in position zero.</span></span>  
  
 `ppd`  
 <span data-ttu-id="03892-109">弄一个指针，指向表示请求的参数的 ParamDef 标记。</span><span class="sxs-lookup"><span data-stu-id="03892-109">[out] A pointer to a ParamDef token that represents the requested parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03892-110">要求</span><span class="sxs-lookup"><span data-stu-id="03892-110">Requirements</span></span>  
 <span data-ttu-id="03892-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="03892-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03892-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="03892-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03892-113">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="03892-113">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03892-114">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03892-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03892-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03892-115">See also</span></span>

- [<span data-ttu-id="03892-116">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="03892-116">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="03892-117">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="03892-117">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
