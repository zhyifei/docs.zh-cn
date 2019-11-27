---
title: IMetaDataImport::GetMethodProps 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetMethodProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetMethodProps
helpviewer_keywords:
- GetMethodProps method [.NET Framework metadata]
- IMetaDataImport::GetMethodProps method [.NET Framework metadata]
ms.assetid: e0667ef7-1d31-4c89-a2d3-d426f023f8d2
topic_type:
- apiref
ms.openlocfilehash: 4a258ce9121a287929ca5bc39c480f1ca2596e78
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437458"
---
# <a name="imetadataimportgetmethodprops-method"></a><span data-ttu-id="94630-102">IMetaDataImport::GetMethodProps 方法</span><span class="sxs-lookup"><span data-stu-id="94630-102">IMetaDataImport::GetMethodProps Method</span></span>
<span data-ttu-id="94630-103">获取与指定的 MethodDef 标记引用的方法关联的元数据。</span><span class="sxs-lookup"><span data-stu-id="94630-103">Gets the metadata associated with the method referenced by the specified MethodDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94630-104">语法</span><span class="sxs-lookup"><span data-stu-id="94630-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodProps (  
    [in]  mdMethodDef         mb,  
    [out] mdTypeDef           *pClass,  
    [out] LPWSTR              szMethod,  
    [in]  ULONG               cchMethod,  
    [out] ULONG               *pchMethod,  
    [out] DWORD               *pdwAttr,  
    [out] PCCOR_SIGNATURE     *ppvSigBlob,  
    [out] ULONG               *pcbSigBlob,  
    [out] ULONG               *pulCodeRVA,  
    [out] DWORD               *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94630-105">参数</span><span class="sxs-lookup"><span data-stu-id="94630-105">Parameters</span></span>  
 `mb`  
 <span data-ttu-id="94630-106">中MethodDef 标记，它表示要为其返回元数据的方法。</span><span class="sxs-lookup"><span data-stu-id="94630-106">[in] The MethodDef token that represents the method to return metadata for.</span></span>  
  
 `pClass`  
 <span data-ttu-id="94630-107">弄一个指针，指向表示实现方法的类型的 TypeDef 标记。</span><span class="sxs-lookup"><span data-stu-id="94630-107">[out] A Pointer to a TypeDef token that represents the type that implements the method.</span></span>  
  
 `szMethod`  
 <span data-ttu-id="94630-108">弄指向包含方法名称的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="94630-108">[out] A Pointer to a buffer that has the method's name.</span></span>  
  
 `cchMethod`  
 <span data-ttu-id="94630-109">中请求的 `szMethod`大小。</span><span class="sxs-lookup"><span data-stu-id="94630-109">[in] The requested size of `szMethod`.</span></span>  
  
 `pchMethod`  
 <span data-ttu-id="94630-110">弄一个指针，它指向 `szMethod`的宽字符大小，或者在截断的情况下，为方法名称中的实际宽字符数。</span><span class="sxs-lookup"><span data-stu-id="94630-110">[out] A Pointer to the size in wide characters of `szMethod`, or in the case of truncation, the actual number of wide characters in the method name.</span></span>  
  
 `pdwAttr`  
 <span data-ttu-id="94630-111">弄一个指针，指向与方法关联的任何标志。</span><span class="sxs-lookup"><span data-stu-id="94630-111">[out] A pointer to any flags associated with the method.</span></span>  
  
 `ppvSigBlob`  
 <span data-ttu-id="94630-112">弄指向方法的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="94630-112">[out] A pointer to the binary metadata signature of the method.</span></span>  
  
 `pcbSigBlob`  
 <span data-ttu-id="94630-113">弄一个指针，指向 `ppvSigBlob`的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="94630-113">[out] A Pointer to the size in bytes of `ppvSigBlob`.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="94630-114">弄指向方法的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="94630-114">[out] A pointer to the relative virtual address of the method.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="94630-115">弄一个指针，指向方法的任何实现标志。</span><span class="sxs-lookup"><span data-stu-id="94630-115">[out] A pointer to any implementation flags for the method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94630-116">要求</span><span class="sxs-lookup"><span data-stu-id="94630-116">Requirements</span></span>  
 <span data-ttu-id="94630-117">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="94630-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94630-118">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="94630-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="94630-119">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="94630-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="94630-120">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94630-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94630-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="94630-121">See also</span></span>

- [<span data-ttu-id="94630-122">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="94630-122">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="94630-123">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="94630-123">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
