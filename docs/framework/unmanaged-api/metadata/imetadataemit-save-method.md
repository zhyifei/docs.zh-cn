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
ms.openlocfilehash: 23f6a301c4c11be92e05dbac0d4f69817d857a28
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003933"
---
# <a name="imetadataemitsave-method"></a><span data-ttu-id="97200-102">IMetaDataEmit::Save 方法</span><span class="sxs-lookup"><span data-stu-id="97200-102">IMetaDataEmit::Save Method</span></span>
<span data-ttu-id="97200-103">将当前范围中的所有元数据保存到指定地址处的文件。</span><span class="sxs-lookup"><span data-stu-id="97200-103">Saves all metadata in the current scope to the file at the specified address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97200-104">语法</span><span class="sxs-lookup"><span data-stu-id="97200-104">Syntax</span></span>  
  
```cpp  
HRESULT Save (
    [in]  LPCWSTR     szFile,
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="97200-105">参数</span><span class="sxs-lookup"><span data-stu-id="97200-105">Parameters</span></span>  
 `wzFile`  
 <span data-ttu-id="97200-106">中要保存到的文件的名称。</span><span class="sxs-lookup"><span data-stu-id="97200-106">[in] The name of the file to save to.</span></span> <span data-ttu-id="97200-107">如果此值为 null，则内存中的副本将保存到上次使用的位置。</span><span class="sxs-lookup"><span data-stu-id="97200-107">If this value is null, the in-memory copy will be saved to the last location that was used.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="97200-108">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="97200-108">[in] Reserved.</span></span> <span data-ttu-id="97200-109">必须为零。</span><span class="sxs-lookup"><span data-stu-id="97200-109">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97200-110">要求</span><span class="sxs-lookup"><span data-stu-id="97200-110">Requirements</span></span>  
 <span data-ttu-id="97200-111">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97200-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97200-112">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="97200-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="97200-113">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="97200-113">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="97200-114">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97200-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97200-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97200-115">See also</span></span>

- [<span data-ttu-id="97200-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="97200-116">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="97200-117">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="97200-117">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
