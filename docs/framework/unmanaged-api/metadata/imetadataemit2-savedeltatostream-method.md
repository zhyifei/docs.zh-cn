---
title: IMetaDataEmit2::SaveDeltaToStream 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SaveDeltaToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SaveDeltaToStream
helpviewer_keywords:
- IMetaDataEmit2::SaveDeltaToStream method [.NET Framework metadata]
- SaveDeltaToStream method [.NET Framework metadata]
ms.assetid: ecd786e8-f9a4-4190-a6ef-af18e8c6d654
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0702a7a58e6bd8c13254da5adce17c9adf6fa0cf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569449"
---
# <a name="imetadataemit2savedeltatostream-method"></a><span data-ttu-id="3b7e2-102">IMetaDataEmit2::SaveDeltaToStream 方法</span><span class="sxs-lookup"><span data-stu-id="3b7e2-102">IMetaDataEmit2::SaveDeltaToStream Method</span></span>
<span data-ttu-id="3b7e2-103">将更改从当前会话中编辑和继续保存到指定的流。</span><span class="sxs-lookup"><span data-stu-id="3b7e2-103">Saves changes from the current edit-and-continue session to the specified stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b7e2-104">语法</span><span class="sxs-lookup"><span data-stu-id="3b7e2-104">Syntax</span></span>  
  
```  
HRESULT SaveDeltaToStream (  
    [in] IStream     *pIStream,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3b7e2-105">参数</span><span class="sxs-lookup"><span data-stu-id="3b7e2-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="3b7e2-106">[in]指向要将更改保存到可写入的流的接口指针。</span><span class="sxs-lookup"><span data-stu-id="3b7e2-106">[in] An interface pointer to the writable stream to which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="3b7e2-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="3b7e2-107">[in] Reserved.</span></span> <span data-ttu-id="3b7e2-108">此值必须为零。</span><span class="sxs-lookup"><span data-stu-id="3b7e2-108">This value must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b7e2-109">要求</span><span class="sxs-lookup"><span data-stu-id="3b7e2-109">Requirements</span></span>  
 <span data-ttu-id="3b7e2-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b7e2-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b7e2-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3b7e2-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3b7e2-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="3b7e2-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3b7e2-113">**.NET Framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b7e2-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b7e2-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="3b7e2-114">See also</span></span>
- [<span data-ttu-id="3b7e2-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="3b7e2-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="3b7e2-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="3b7e2-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
