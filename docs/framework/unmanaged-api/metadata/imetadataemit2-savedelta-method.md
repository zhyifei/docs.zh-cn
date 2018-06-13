---
title: IMetaDataEmit2::SaveDelta 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDelta
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7098bceee6bf60cd7781606ffc889b6af9c3e3cf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33445330"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="90635-102">IMetaDataEmit2::SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="90635-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="90635-103">将更改从当前的编辑并继续会话保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="90635-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90635-104">语法</span><span class="sxs-lookup"><span data-stu-id="90635-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90635-105">参数</span><span class="sxs-lookup"><span data-stu-id="90635-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="90635-106">[in]要保存在其下的文件名称更改。</span><span class="sxs-lookup"><span data-stu-id="90635-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="90635-107">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="90635-107">[in] Reserved.</span></span> <span data-ttu-id="90635-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="90635-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="90635-109">要求</span><span class="sxs-lookup"><span data-stu-id="90635-109">Requirements</span></span>  
 <span data-ttu-id="90635-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="90635-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90635-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="90635-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="90635-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="90635-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="90635-113">**.NET framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90635-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90635-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="90635-114">See Also</span></span>  
 [<span data-ttu-id="90635-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="90635-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="90635-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="90635-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
