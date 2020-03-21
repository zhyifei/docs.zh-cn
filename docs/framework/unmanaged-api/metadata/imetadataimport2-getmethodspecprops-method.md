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
ms.openlocfilehash: 0bfbfec930c193ea05a01bd5bd9f46d2ec6714b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175286"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="44833-102">IMetaDataImport2::GetMethodSpecProps 方法</span><span class="sxs-lookup"><span data-stu-id="44833-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="44833-103">获取指定方法Spec令牌引用的方法的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="44833-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44833-104">语法</span><span class="sxs-lookup"><span data-stu-id="44833-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,
   [out] ULONG            *pcbSigBlob  
);
```  
  
## <a name="parameters"></a><span data-ttu-id="44833-105">parameters</span><span class="sxs-lookup"><span data-stu-id="44833-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="44833-106">[在]表示方法实例化的 MethodSpec 令牌。</span><span class="sxs-lookup"><span data-stu-id="44833-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="44833-107">[出]指向表示方法定义的方法Def 或方法Ref 令牌的指针。</span><span class="sxs-lookup"><span data-stu-id="44833-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="44833-108">[出]指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="44833-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="44833-109">[出]的大小（以字节为单位）的大小`ppvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="44833-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44833-110">要求</span><span class="sxs-lookup"><span data-stu-id="44833-110">Requirements</span></span>  
 <span data-ttu-id="44833-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="44833-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44833-112">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="44833-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="44833-113">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="44833-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="44833-114">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44833-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44833-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44833-115">See also</span></span>

- [<span data-ttu-id="44833-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="44833-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="44833-117">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="44833-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
