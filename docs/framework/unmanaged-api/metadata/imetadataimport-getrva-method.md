---
title: IMetaDataImport::GetRVA 方法
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetRVA
helpviewer_keywords:
- GetRVA method [.NET Framework metadata]
- IMetaDataImport::GetRVA method [.NET Framework metadata]
ms.assetid: ea422217-988b-4acd-b2db-c55357938275
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96c013cd3e45e4ede0cbc9f42bf511a2eb3fc12d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223584"
---
# <a name="imetadataimportgetrva-method"></a><span data-ttu-id="7b40c-102">IMetaDataImport::GetRVA 方法</span><span class="sxs-lookup"><span data-stu-id="7b40c-102">IMetaDataImport::GetRVA Method</span></span>
<span data-ttu-id="7b40c-103">获取相对虚拟地址 (RVA) 和实现的方法或字段所指定的标记表示的标志。</span><span class="sxs-lookup"><span data-stu-id="7b40c-103">Gets the relative virtual address (RVA) and the implementation flags of the method or field represented by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b40c-104">语法</span><span class="sxs-lookup"><span data-stu-id="7b40c-104">Syntax</span></span>  
  
```  
HRESULT GetRVA (  
   [in]  mdToken     tk,   
   [out] ULONG       *pulCodeRVA,   
   [out]  DWORD      *pdwImplFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7b40c-105">参数</span><span class="sxs-lookup"><span data-stu-id="7b40c-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="7b40c-106">[in]表示要返回的 RVA 的代码对象的 MethodDef 或 FieldDef 元数据标记。</span><span class="sxs-lookup"><span data-stu-id="7b40c-106">[in] A MethodDef or FieldDef metadata token that represents the code object to return the RVA for.</span></span> <span data-ttu-id="7b40c-107">如果令牌 FieldDef，字段必须是全局变量。</span><span class="sxs-lookup"><span data-stu-id="7b40c-107">If the token is a FieldDef, the field must be a global variable.</span></span>  
  
 `pulCodeRVA`  
 <span data-ttu-id="7b40c-108">[out]指向标记所表示的代码对象的相对虚拟地址的指针。</span><span class="sxs-lookup"><span data-stu-id="7b40c-108">[out] A pointer to the relative virtual address of the code object represented by the token.</span></span>  
  
 `pdwImplFlags`  
 <span data-ttu-id="7b40c-109">[out]一个指向该方法的实现标志。</span><span class="sxs-lookup"><span data-stu-id="7b40c-109">[out] A pointer to the implementation flags for the method.</span></span> <span data-ttu-id="7b40c-110">此值是从一个位掩码[CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md)枚举。</span><span class="sxs-lookup"><span data-stu-id="7b40c-110">This value is a bitmask from the [CorMethodImpl](../../../../docs/framework/unmanaged-api/metadata/cormethodimpl-enumeration.md) enumeration.</span></span> <span data-ttu-id="7b40c-111">值`pdwImplFlags`无效，仅当`tk`是 MethodDef 标记。</span><span class="sxs-lookup"><span data-stu-id="7b40c-111">The value of `pdwImplFlags` is valid only if `tk` is a MethodDef token.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b40c-112">要求</span><span class="sxs-lookup"><span data-stu-id="7b40c-112">Requirements</span></span>  
 <span data-ttu-id="7b40c-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7b40c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b40c-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7b40c-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7b40c-115">**库：** 包含为 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7b40c-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="7b40c-116">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="7b40c-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="7b40c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7b40c-117">See also</span></span>

- [<span data-ttu-id="7b40c-118">IMetaDataImport 接口</span><span class="sxs-lookup"><span data-stu-id="7b40c-118">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7b40c-119">IMetaDataImport2 接口</span><span class="sxs-lookup"><span data-stu-id="7b40c-119">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
