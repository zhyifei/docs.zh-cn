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
ms.openlocfilehash: afb0c09c09236267be2a999ce5c130feebb52b6f
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447904"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="77001-102">IMetaDataEmit2::SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="77001-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="77001-103">将当前的 "编辑并继续" 会话中的更改保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="77001-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77001-104">语法</span><span class="sxs-lookup"><span data-stu-id="77001-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77001-105">参数</span><span class="sxs-lookup"><span data-stu-id="77001-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="77001-106">中用于保存更改的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="77001-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="77001-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="77001-107">[in] Reserved.</span></span> <span data-ttu-id="77001-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="77001-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77001-109">要求</span><span class="sxs-lookup"><span data-stu-id="77001-109">Requirements</span></span>  
 <span data-ttu-id="77001-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="77001-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77001-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="77001-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77001-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="77001-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="77001-113">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="77001-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="77001-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77001-114">See also</span></span>

- [<span data-ttu-id="77001-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="77001-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="77001-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="77001-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
