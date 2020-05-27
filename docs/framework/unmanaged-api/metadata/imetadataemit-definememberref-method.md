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
ms.openlocfilehash: 576f4561ed782f091840ac378831110a1bfef9c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004683"
---
# <a name="imetadataemitdefinememberref-method"></a><span data-ttu-id="767ab-102">IMetaDataEmit::DefineMemberRef 方法</span><span class="sxs-lookup"><span data-stu-id="767ab-102">IMetaDataEmit::DefineMemberRef Method</span></span>
<span data-ttu-id="767ab-103">定义对当前范围之外的模块成员的引用，并获取该引用定义的标记。</span><span class="sxs-lookup"><span data-stu-id="767ab-103">Defines a reference to a member of a module outside the current scope, and gets a token to that reference definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="767ab-104">语法</span><span class="sxs-lookup"><span data-stu-id="767ab-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineMemberRef (
    [in]  mdToken           tkImport,
    [in]  LPCWSTR           szName,
    [in]  PCCOR_SIGNATURE   pvSigBlob,
    [in]  ULONG             cbSigBlob,
    [out] mdMemberRef       *pmr
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="767ab-105">参数</span><span class="sxs-lookup"><span data-stu-id="767ab-105">Parameters</span></span>  
 `tkImport`  
 <span data-ttu-id="767ab-106">中目标成员的类或接口的标记（如果成员不是全局成员）;如果成员是全局成员，则 `mdModuleRef` 为该其他文件的标记。</span><span class="sxs-lookup"><span data-stu-id="767ab-106">[in] Token for the target member's class or interface, if the member is not global; if the member is global, the `mdModuleRef` token for that other file.</span></span>  
  
 `szName`  
 <span data-ttu-id="767ab-107">中目标成员的名称。</span><span class="sxs-lookup"><span data-stu-id="767ab-107">[in] The name of the target member.</span></span>  
  
 `pvSigBlob`  
 <span data-ttu-id="767ab-108">中目标成员的签名。</span><span class="sxs-lookup"><span data-stu-id="767ab-108">[in] The signature of the target member.</span></span>  
  
 `cbSigBlob`  
 <span data-ttu-id="767ab-109">中中的字节数 `pvSigBlob` 。</span><span class="sxs-lookup"><span data-stu-id="767ab-109">[in] The count of bytes in `pvSigBlob`.</span></span>  
  
 `pmr`  
 <span data-ttu-id="767ab-110">弄`mdMemberRef`分配的令牌。</span><span class="sxs-lookup"><span data-stu-id="767ab-110">[out] The `mdMemberRef` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="767ab-111">要求</span><span class="sxs-lookup"><span data-stu-id="767ab-111">Requirements</span></span>  
 <span data-ttu-id="767ab-112">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="767ab-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="767ab-113">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="767ab-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="767ab-114">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="767ab-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="767ab-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="767ab-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="767ab-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="767ab-116">See also</span></span>

- [<span data-ttu-id="767ab-117">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="767ab-117">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="767ab-118">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="767ab-118">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
