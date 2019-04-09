---
title: IMetaDataEmit::Save 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.Save
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::Save
helpviewer_keywords:
- Save method, IMetaDataEmit interface [.NET Framework metadata]
- IMetaDataEmit::Save method [.NET Framework metadata]
ms.assetid: c1de8400-adfe-4a71-b828-a1d0cc1ea505
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49e45085b0fbca10e490f11ce588f68aa8237b46
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139069"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="64542-102">IMetaDataEmit::Save 方法</span><span class="sxs-lookup"><span data-stu-id="64542-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="64542-103">将所有元数据保存到指定地址处的文件在当前范围内。</span><span class="sxs-lookup"><span data-stu-id="64542-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64542-104">语法</span><span class="sxs-lookup"><span data-stu-id="64542-104">Syntax</span></span>  
  
```  
HRESULT Save (   
    [in]  LPCWSTR     szFile,   
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64542-105">参数</span><span class="sxs-lookup"><span data-stu-id="64542-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="64542-106">[in]若要将保存到文件的名称。</span><span class="sxs-lookup"><span data-stu-id="64542-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="64542-107">如果此值为 null，内存中副本将保存到上次使用的位置。</span><span class="sxs-lookup"><span data-stu-id="64542-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="64542-108">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="64542-108">[in] Reserved.</span></span> <span data-ttu-id="64542-109">必须为零。</span><span class="sxs-lookup"><span data-stu-id="64542-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64542-110">要求</span><span class="sxs-lookup"><span data-stu-id="64542-110">Requirements</span></span>  
 <span data-ttu-id="64542-111">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="64542-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64542-112">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="64542-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64542-113">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="64542-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="64542-114">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="64542-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="64542-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="64542-115">See also</span></span>

- [<span data-ttu-id="64542-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="64542-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="64542-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="64542-117">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
