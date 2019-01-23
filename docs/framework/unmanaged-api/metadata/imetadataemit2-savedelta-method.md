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
ms.openlocfilehash: 27d9b891475d0fb45c9ec34f3363b0d76fe394c4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54493199"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="34682-102">IMetaDataEmit2::SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="34682-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="34682-103">将更改从当前会话中编辑和继续保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="34682-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34682-104">语法</span><span class="sxs-lookup"><span data-stu-id="34682-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="34682-105">参数</span><span class="sxs-lookup"><span data-stu-id="34682-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="34682-106">[in]要将更改保存在其下的文件名。</span><span class="sxs-lookup"><span data-stu-id="34682-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="34682-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="34682-107">[in] Reserved.</span></span> <span data-ttu-id="34682-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="34682-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34682-109">要求</span><span class="sxs-lookup"><span data-stu-id="34682-109">Requirements</span></span>  
 <span data-ttu-id="34682-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="34682-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34682-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="34682-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="34682-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="34682-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="34682-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34682-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34682-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="34682-114">See also</span></span>
- [<span data-ttu-id="34682-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="34682-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="34682-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="34682-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
