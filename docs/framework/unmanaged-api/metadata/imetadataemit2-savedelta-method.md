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
ms.openlocfilehash: 0ebcab7a759b64bfbb254df1c1aa339cde77d054
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175559"
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="5bcc9-102">IMetaDataEmit2::SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="5bcc9-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="5bcc9-103">将当前编辑和继续会话的更改保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="5bcc9-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bcc9-104">语法</span><span class="sxs-lookup"><span data-stu-id="5bcc9-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,
    [in] DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bcc9-105">parameters</span><span class="sxs-lookup"><span data-stu-id="5bcc9-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="5bcc9-106">[在]要保存的文件名将发生更改。</span><span class="sxs-lookup"><span data-stu-id="5bcc9-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="5bcc9-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="5bcc9-107">[in] Reserved.</span></span> <span data-ttu-id="5bcc9-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="5bcc9-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bcc9-109">要求</span><span class="sxs-lookup"><span data-stu-id="5bcc9-109">Requirements</span></span>  
 <span data-ttu-id="5bcc9-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5bcc9-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bcc9-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="5bcc9-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5bcc9-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5bcc9-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5bcc9-113">**.NET 框架版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5bcc9-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bcc9-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bcc9-114">See also</span></span>

- [<span data-ttu-id="5bcc9-115">IMetaDataEmit2 Interface</span><span class="sxs-lookup"><span data-stu-id="5bcc9-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="5bcc9-116">IMetaDataEmit Interface</span><span class="sxs-lookup"><span data-stu-id="5bcc9-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
