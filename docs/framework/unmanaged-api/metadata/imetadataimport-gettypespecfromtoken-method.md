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
ms.openlocfilehash: 37a8c2580dad3e198290b72b49b0aacaf1804c25
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="c79d0-102">IMetaDataImport::GetTypeSpecFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="c79d0-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="c79d0-103">获取指定标记所表示的类型规范的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="c79d0-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c79d0-104">语法</span><span class="sxs-lookup"><span data-stu-id="c79d0-104">Syntax</span></span>  
  
```  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c79d0-105">参数</span><span class="sxs-lookup"><span data-stu-id="c79d0-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="c79d0-106">[in]与请求的元数据签名关联的 TypeSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="c79d0-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="c79d0-107">[out]指向的二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="c79d0-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="c79d0-108">[out]大小，以字节为单位的元数据签名。</span><span class="sxs-lookup"><span data-stu-id="c79d0-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c79d0-109">返回值</span><span class="sxs-lookup"><span data-stu-id="c79d0-109">Return Value</span></span>  
 <span data-ttu-id="c79d0-110">指示成功或失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="c79d0-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="c79d0-111">可以用失败宏测试失败。</span><span class="sxs-lookup"><span data-stu-id="c79d0-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c79d0-112">要求</span><span class="sxs-lookup"><span data-stu-id="c79d0-112">Requirements</span></span>  
 <span data-ttu-id="c79d0-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c79d0-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c79d0-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c79d0-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c79d0-115">**库：**作为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c79d0-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c79d0-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c79d0-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c79d0-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c79d0-117">See Also</span></span>  
 [<span data-ttu-id="c79d0-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="c79d0-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [<span data-ttu-id="c79d0-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="c79d0-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
