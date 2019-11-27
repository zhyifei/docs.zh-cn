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
ms.openlocfilehash: 6b5b3b3b5a3613668f4470f48083ae010cc9d336
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445252"
---
# <a name="imetadataimport2getmethodspecprops-method"></a><span data-ttu-id="98ffd-102">IMetaDataImport2::GetMethodSpecProps 方法</span><span class="sxs-lookup"><span data-stu-id="98ffd-102">IMetaDataImport2::GetMethodSpecProps Method</span></span>
<span data-ttu-id="98ffd-103">获取指定的 MethodSpec 标记所引用的方法的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="98ffd-103">Gets the metadata signature of the method referenced by the specified MethodSpec token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98ffd-104">语法</span><span class="sxs-lookup"><span data-stu-id="98ffd-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodSpecProps (  
   [in]  mdMethodSpec     mi,  
   [out] mdToken          *tkParent,  
   [out] PCCOR_SIGNATURE  *ppvSigBlob,   
   [out] ULONG            *pcbSigBlob  
);   
```  
  
## <a name="parameters"></a><span data-ttu-id="98ffd-105">参数</span><span class="sxs-lookup"><span data-stu-id="98ffd-105">Parameters</span></span>  
 `mi`  
 <span data-ttu-id="98ffd-106">中一个 MethodSpec 标记，表示方法的实例化。</span><span class="sxs-lookup"><span data-stu-id="98ffd-106">[in] A MethodSpec token that represents the instantiation of the method.</span></span>  
  
 `tkParent`  
 <span data-ttu-id="98ffd-107">弄一个指针，指向表示方法定义的 MethodDef 或 MethodRef 标记。</span><span class="sxs-lookup"><span data-stu-id="98ffd-107">[out] A pointer to the MethodDef or MethodRef token that represents the method definition.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="98ffd-108">弄指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="98ffd-108">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="98ffd-109">弄`ppvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="98ffd-109">[out] The size, in bytes, of `ppvSigBlob`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98ffd-110">要求</span><span class="sxs-lookup"><span data-stu-id="98ffd-110">Requirements</span></span>  
 <span data-ttu-id="98ffd-111">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98ffd-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98ffd-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="98ffd-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98ffd-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="98ffd-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98ffd-114">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98ffd-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98ffd-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98ffd-115">See also</span></span>

- [<span data-ttu-id="98ffd-116">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="98ffd-116">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
- [<span data-ttu-id="98ffd-117">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="98ffd-117">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
