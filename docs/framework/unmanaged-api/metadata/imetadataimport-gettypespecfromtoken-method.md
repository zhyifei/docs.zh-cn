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
ms.openlocfilehash: 34b7cebfa063a3ad077b74a753fd37ba67ff53a5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175312"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="a0bde-102">IMetaDataImport::GetTypeSpecFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="a0bde-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="a0bde-103">获取指定标记所表示的类型规范的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="a0bde-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0bde-104">语法</span><span class="sxs-lookup"><span data-stu-id="a0bde-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (
   [in]  mdTypeSpec            typespec,
   [out] PCCOR_SIGNATURE       *ppvSig,
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0bde-105">parameters</span><span class="sxs-lookup"><span data-stu-id="a0bde-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="a0bde-106">[在]与请求的元数据签名关联的 TypeSpec 令牌。</span><span class="sxs-lookup"><span data-stu-id="a0bde-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="a0bde-107">[出]指向二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="a0bde-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="a0bde-108">[出]元数据签名的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="a0bde-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a0bde-109">返回值</span><span class="sxs-lookup"><span data-stu-id="a0bde-109">Return Value</span></span>  
 <span data-ttu-id="a0bde-110">指示成功或失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="a0bde-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="a0bde-111">可以使用 FAILED 宏测试故障。</span><span class="sxs-lookup"><span data-stu-id="a0bde-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0bde-112">要求</span><span class="sxs-lookup"><span data-stu-id="a0bde-112">Requirements</span></span>  
 <span data-ttu-id="a0bde-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a0bde-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0bde-114">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a0bde-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a0bde-115">**库：** 作为资源包含在 MsCorEE.dll 中</span><span class="sxs-lookup"><span data-stu-id="a0bde-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a0bde-116">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0bde-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0bde-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0bde-117">See also</span></span>

- [<span data-ttu-id="a0bde-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="a0bde-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="a0bde-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="a0bde-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
