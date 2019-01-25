---
title: IMetaDataEmit::DefineMemberRef 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineMemberRef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineMemberRef
helpviewer_keywords:
- DefineMemberRef method [.NET Framework metadata]
- IMetaDataEmit::DefineMemberRef method [.NET Framework metadata]
ms.assetid: 21b5bcb8-ea75-4962-8acc-ad17584061e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 578f79136f6ccc8a6b7eac644b2a5084d30d2ba0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722824"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="c78e4-102">IMetaDataEmit::DefineMemberRef 方法</span><span class="sxs-lookup"><span data-stu-id="c78e4-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="c78e4-103">定义对当前作用域之外的模块的成员的引用，并获取该引用定义的标记。</span><span class="sxs-lookup"><span data-stu-id="c78e4-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c78e4-104">语法</span><span class="sxs-lookup"><span data-stu-id="c78e4-104">Syntax</span></span>  
  
```  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c78e4-105">参数</span><span class="sxs-lookup"><span data-stu-id="c78e4-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="c78e4-106">[in]如果该成员不是全局; 为目标成员的类或接口，令牌如果该成员是全局的`mdModuleRef`标记，表示该其他文件。</span><span class="sxs-lookup"><span data-stu-id="c78e4-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="c78e4-107">[in]目标成员的名称。</span><span class="sxs-lookup"><span data-stu-id="c78e4-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="c78e4-108">[in]目标成员的签名。</span><span class="sxs-lookup"><span data-stu-id="c78e4-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="c78e4-109">[in]中的字节计数`pvSigBlob`。</span><span class="sxs-lookup"><span data-stu-id="c78e4-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="c78e4-110">[out]`mdMemberRef`分配标记。</span><span class="sxs-lookup"><span data-stu-id="c78e4-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c78e4-111">要求</span><span class="sxs-lookup"><span data-stu-id="c78e4-111">Requirements</span></span>  
 <span data-ttu-id="c78e4-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c78e4-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c78e4-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="c78e4-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c78e4-114">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c78e4-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c78e4-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c78e4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c78e4-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="c78e4-116">See also</span></span>
- [<span data-ttu-id="c78e4-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="c78e4-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c78e4-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="c78e4-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
