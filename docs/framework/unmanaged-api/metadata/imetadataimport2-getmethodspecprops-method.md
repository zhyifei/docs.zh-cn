---
title: IMetaDataImport2::GetMethodSpecProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport2.GetMethodSpecProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2::GetMethodSpecProps
helpviewer_keywords:
- GetMethodSpecProps method [.NET Framework metadata]
- IMetaDataImport2::GetMethodSpecProps method [.NET Framework metadata]
ms.assetid: 9544b711-e669-4eaf-8630-ee862e5e4489
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c35212e7d261a5b385823fdaa345f6fbd638571c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079339"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="7908d-102">IMetaDataImport2::GetMethodSpecProps 方法</span><span class="sxs-lookup"><span data-stu-id="7908d-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="7908d-103">获取指定 MethodSpec 所引用的方法的元数据签名标记。</span><span class="sxs-lookup"><span data-stu-id="7908d-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7908d-104">语法</span><span class="sxs-lookup"><span data-stu-id="7908d-104">Syntax</span></span>  
  
```  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="7908d-105">参数</span><span class="sxs-lookup"><span data-stu-id="7908d-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="7908d-106">[in]表示方法的实例化的 MethodSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="7908d-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="7908d-107">[out]指向表示方法定义的 MethodDef 或指令标记的指针。</span><span class="sxs-lookup"><span data-stu-id="7908d-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="7908d-108">[out]指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="7908d-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="7908d-109">[out]大小，以字节为单位的`ppvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="7908d-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7908d-110">要求</span><span class="sxs-lookup"><span data-stu-id="7908d-110">Requirements</span></span>  
 <span data-ttu-id="7908d-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7908d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7908d-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7908d-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7908d-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7908d-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7908d-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7908d-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7908d-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="7908d-115">See also</span></span>

- [<span data-ttu-id="7908d-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7908d-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="7908d-117">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7908d-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
