---
title: IMetaDataEmit::SetFieldMarshal 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldMarshal
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldMarshal
helpviewer_keywords:
- SetFieldMarshal method [.NET Framework metadata]
- IMetaDataEmit::SetFieldMarshal method [.NET Framework metadata]
ms.assetid: be232314-7f69-4855-bfab-63361bd22307
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82675af85f049aeb288b3dcc18f222c0387a37b3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150392"
---
# <a name="imetadataemitsetfieldmarshal-method"></a><span data-ttu-id="61e3e-102">IMetaDataEmit::SetFieldMarshal 方法</span><span class="sxs-lookup"><span data-stu-id="61e3e-102">IMetaDataEmit::SetFieldMarshal Method</span></span>
<span data-ttu-id="61e3e-103">设置 PInvoke 封送处理指定的标记所引用的字段、 方法将返回或方法参数的信息。</span><span class="sxs-lookup"><span data-stu-id="61e3e-103">Sets the PInvoke marshaling information for the field, method return, or method parameter referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61e3e-104">语法</span><span class="sxs-lookup"><span data-stu-id="61e3e-104">Syntax</span></span>  
  
```  
HRESULT SetFieldMarshal (  
    [in]  mdToken          tk,   
    [in]  PCCOR_SIGNATURE  pvNativeType,   
    [in]  ULONG            cbNativeType   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="61e3e-105">参数</span><span class="sxs-lookup"><span data-stu-id="61e3e-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="61e3e-106">[in]目标数据的项的标记。</span><span class="sxs-lookup"><span data-stu-id="61e3e-106">[in] The token for target data item.</span></span> <span data-ttu-id="61e3e-107">这可以是`mdFieldDef`或`mdParamDef`令牌。</span><span class="sxs-lookup"><span data-stu-id="61e3e-107">This is either a `mdFieldDef` or a `mdParamDef` token.</span></span>  
  
 `pvNativeType`  
 <span data-ttu-id="61e3e-108">[in]非托管类型的签名。</span><span class="sxs-lookup"><span data-stu-id="61e3e-108">[in] The signature for unmanaged type.</span></span>  
  
 `cbNativeType`  
 <span data-ttu-id="61e3e-109">[in]中的字节计数`pvNativeType`。</span><span class="sxs-lookup"><span data-stu-id="61e3e-109">[in] The count of bytes in `pvNativeType`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61e3e-110">要求</span><span class="sxs-lookup"><span data-stu-id="61e3e-110">Requirements</span></span>  
 <span data-ttu-id="61e3e-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="61e3e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61e3e-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="61e3e-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="61e3e-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="61e3e-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="61e3e-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="61e3e-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="61e3e-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="61e3e-115">See also</span></span>

- [<span data-ttu-id="61e3e-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="61e3e-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="61e3e-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="61e3e-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
