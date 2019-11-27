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
ms.openlocfilehash: 3ab24ab869e1f2cff9beafe50e6982ba2e7cf0aa
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436702"
---
# <a name="imetadataimportgettypespecfromtoken-method"></a><span data-ttu-id="5713a-102">IMetaDataImport::GetTypeSpecFromToken 方法</span><span class="sxs-lookup"><span data-stu-id="5713a-102">IMetaDataImport::GetTypeSpecFromToken Method</span></span>
<span data-ttu-id="5713a-103">获取指定标记所表示的类型规范的二进制元数据签名。</span><span class="sxs-lookup"><span data-stu-id="5713a-103">Gets the binary metadata signature of the type specification represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5713a-104">语法</span><span class="sxs-lookup"><span data-stu-id="5713a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeSpecFromToken (   
   [in]  mdTypeSpec            typespec,   
   [out] PCCOR_SIGNATURE       *ppvSig,   
   [out] ULONG                 *pcbSig  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5713a-105">参数</span><span class="sxs-lookup"><span data-stu-id="5713a-105">Parameters</span></span>  
 `typespec`  
 <span data-ttu-id="5713a-106">中与请求的元数据签名关联的 TypeSpec 标记。</span><span class="sxs-lookup"><span data-stu-id="5713a-106">[in] The TypeSpec token associated with the requested metadata signature.</span></span>  
  
 `ppvSig`  
 <span data-ttu-id="5713a-107">弄指向二进制元数据签名的指针。</span><span class="sxs-lookup"><span data-stu-id="5713a-107">[out] A pointer to the binary metadata signature.</span></span>  
  
 `pcbSig`  
 <span data-ttu-id="5713a-108">弄元数据签名的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="5713a-108">[out] The size, in bytes, of the metadata signature.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5713a-109">返回值</span><span class="sxs-lookup"><span data-stu-id="5713a-109">Return Value</span></span>  
 <span data-ttu-id="5713a-110">一个指示成功或失败的 HRESULT。</span><span class="sxs-lookup"><span data-stu-id="5713a-110">An HRESULT that indicates success or failure.</span></span> <span data-ttu-id="5713a-111">可以通过失败的宏测试失败。</span><span class="sxs-lookup"><span data-stu-id="5713a-111">Failures can be tested with the FAILED macro.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5713a-112">要求</span><span class="sxs-lookup"><span data-stu-id="5713a-112">Requirements</span></span>  
 <span data-ttu-id="5713a-113">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5713a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5713a-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5713a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5713a-115">**库：** 作为资源包括在 Mscoree.dll 中</span><span class="sxs-lookup"><span data-stu-id="5713a-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5713a-116">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5713a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5713a-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5713a-117">See also</span></span>

- [<span data-ttu-id="5713a-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="5713a-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="5713a-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="5713a-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
