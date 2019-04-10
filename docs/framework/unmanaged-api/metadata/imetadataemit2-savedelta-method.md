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
ms.openlocfilehash: d97f536d54ac1cb77c5d0413d2437508374ac7f4
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168995"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="8d316-102">IMetaDataEmit2::SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="8d316-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="8d316-103">将更改从当前会话中编辑和继续保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="8d316-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d316-104">语法</span><span class="sxs-lookup"><span data-stu-id="8d316-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8d316-105">参数</span><span class="sxs-lookup"><span data-stu-id="8d316-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="8d316-106">[in]要将更改保存在其下的文件名。</span><span class="sxs-lookup"><span data-stu-id="8d316-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="8d316-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="8d316-107">[in] Reserved.</span></span> <span data-ttu-id="8d316-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="8d316-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d316-109">要求</span><span class="sxs-lookup"><span data-stu-id="8d316-109">Requirements</span></span>  
 <span data-ttu-id="8d316-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8d316-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d316-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8d316-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8d316-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8d316-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="8d316-113">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="8d316-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8d316-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="8d316-114">See also</span></span>

- [<span data-ttu-id="8d316-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="8d316-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="8d316-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="8d316-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
