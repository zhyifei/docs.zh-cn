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
ms.openlocfilehash: 696389b51328e167212fb2292a873c34b9263811
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431816"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="398e1-102">IMetaDataEmit::DefineMemberRef 方法</span><span class="sxs-lookup"><span data-stu-id="398e1-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="398e1-103">定义对当前范围之外的模块成员的引用，并获取该引用定义的标记。</span><span class="sxs-lookup"><span data-stu-id="398e1-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="398e1-104">语法</span><span class="sxs-lookup"><span data-stu-id="398e1-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (   
    [in]  mdToken           tkImport,   
    [in]  LPCWSTR           szName,   
    [in]  PCCOR_SIGNATURE   pvSigBlob,   
    [in]  ULONG             cbSigBlob,   
    [out] mdMemberRef       *pmr   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="398e1-105">参数</span><span class="sxs-lookup"><span data-stu-id="398e1-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="398e1-106">中目标成员的类或接口的标记（如果成员不是全局成员）;如果成员是全局成员，则为该其他文件的 `mdModuleRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="398e1-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="398e1-107">中目标成员的名称。</span><span class="sxs-lookup"><span data-stu-id="398e1-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="398e1-108">中目标成员的签名。</span><span class="sxs-lookup"><span data-stu-id="398e1-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="398e1-109">中`pvSigBlob`中的字节计数。</span><span class="sxs-lookup"><span data-stu-id="398e1-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="398e1-110">弄分配 `mdMemberRef` 标记。</span><span class="sxs-lookup"><span data-stu-id="398e1-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="398e1-111">要求</span><span class="sxs-lookup"><span data-stu-id="398e1-111">Requirements</span></span>  
 <span data-ttu-id="398e1-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="398e1-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="398e1-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="398e1-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="398e1-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="398e1-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="398e1-115">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="398e1-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="398e1-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="398e1-116">See also</span></span>

- [<span data-ttu-id="398e1-117">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="398e1-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="398e1-118">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="398e1-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
