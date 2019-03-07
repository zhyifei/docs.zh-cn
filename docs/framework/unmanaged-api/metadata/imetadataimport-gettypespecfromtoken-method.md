---
title: IMetaDataImport::GetTypeSpecFromToken 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeSpecFromToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8ecb529534f4ed1a1d12d9613ebd46f8b99fdb8
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487495"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="13fb7-102">IMetaDataImport::GetTypeSpecFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="13fb7-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="13fb7-103">获取指定标记所表示的类型规范的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="13fb7-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13fb7-104">语法</span><span class="sxs-lookup"><span data-stu-id="13fb7-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13fb7-105">参数</span><span class="sxs-lookup"><span data-stu-id="13fb7-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="13fb7-106">[in]与请求的元数据签名关联的 TypeSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="13fb7-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="13fb7-107">[out]指向二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="13fb7-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="13fb7-108">[out]大小，以字节为单位的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="13fb7-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="13fb7-109">返回值</span><span class="sxs-lookup"><span data-stu-id="13fb7-109">Return Value</span></span>  
 <span data-ttu-id="13fb7-110">一个 HRESULT，指示成功或失败。</span><span class="sxs-lookup"><span data-stu-id="13fb7-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="13fb7-111">可以使用 FAILED 宏测试失败。</span><span class="sxs-lookup"><span data-stu-id="13fb7-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13fb7-112">要求</span><span class="sxs-lookup"><span data-stu-id="13fb7-112">Requirements</span></span>  
 <span data-ttu-id="13fb7-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="13fb7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13fb7-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13fb7-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13fb7-115">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="13fb7-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13fb7-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13fb7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13fb7-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="13fb7-117">See also</span></span>
- [<span data-ttu-id="13fb7-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="13fb7-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="13fb7-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="13fb7-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
