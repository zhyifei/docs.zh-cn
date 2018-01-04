---
title: "IMetaDataImport::GetTypeSpecFromToken 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetTypeSpecFromToken
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetTypeSpecFromToken
helpviewer_keywords:
- GetTypeSpecFromToken method [.NET Framework metadata]
- IMetaDataImport::GetTypeSpecFromToken method [.NET Framework metadata]
ms.assetid: ee518bda-3296-482e-a7b7-e9d51dd1a181
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10d4d9dcad2494410cc361617d5292c519b6dc00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="98fa3-102">IMetaDataImport::GetTypeSpecFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="98fa3-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="98fa3-103">获取指定标记所表示的类型规范的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="98fa3-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98fa3-104">语法</span><span class="sxs-lookup"><span data-stu-id="98fa3-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98fa3-105">参数</span><span class="sxs-lookup"><span data-stu-id="98fa3-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="98fa3-106">[in]与请求的元数据签名关联的 TypeSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="98fa3-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="98fa3-107">[out]指向的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="98fa3-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="98fa3-108">[out]大小，以字节为单位的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="98fa3-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98fa3-109">返回值</span><span class="sxs-lookup"><span data-stu-id="98fa3-109">Return Value</span></span>  
 <span data-ttu-id="98fa3-110">指示成功或失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="98fa3-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="98fa3-111">可以用失败宏测试失败。</span><span class="sxs-lookup"><span data-stu-id="98fa3-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98fa3-112">惠?</span><span class="sxs-lookup"><span data-stu-id="98fa3-112">Requirements</span></span>  
 <span data-ttu-id="98fa3-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="98fa3-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98fa3-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="98fa3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="98fa3-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="98fa3-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="98fa3-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98fa3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98fa3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="98fa3-117">See Also</span></span>  
 [<span data-ttu-id="98fa3-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="98fa3-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="98fa3-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="98fa3-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
