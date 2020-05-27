---
title: IMetaDataEmit::SaveToStream 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SaveToStream
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SaveToStream
helpviewer_keywords:
- IMetaDataEmit::SaveToStream method [.NET Framework metadata]
- SaveToStream method [.NET Framework metadata]
ms.assetid: e0290a49-3818-4a43-ad46-3014faa34f97
topic_type:
- apiref
ms.openlocfilehash: 87e00a69643b6bc403188fb0fdb6f9e3f3d82115
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84003867"
---
# <a name="imetadataemitsavetostream-method"></a><span data-ttu-id="c6c69-102">IMetaDataEmit::SaveToStream 方法</span><span class="sxs-lookup"><span data-stu-id="c6c69-102">IMetaDataEmit::SaveToStream Method</span></span>
<span data-ttu-id="c6c69-103">将当前范围中的所有元数据保存到指定的 `IStream` 。</span><span class="sxs-lookup"><span data-stu-id="c6c69-103">Saves all metadata in the current scope to the specified `IStream`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6c69-104">语法</span><span class="sxs-lookup"><span data-stu-id="c6c69-104">Syntax</span></span>  
  
```cpp  
HRESULT SaveToStream (
    [in]  IStream     *pIStream,  
    [in]  DWORD       dwSaveFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6c69-105">参数</span><span class="sxs-lookup"><span data-stu-id="c6c69-105">Parameters</span></span>  
 `pIStream`  
 <span data-ttu-id="c6c69-106">中要保存到的可写流。</span><span class="sxs-lookup"><span data-stu-id="c6c69-106">[in] The writable stream to save to.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="c6c69-107">[in] 保留。</span><span class="sxs-lookup"><span data-stu-id="c6c69-107">[in] Reserved.</span></span> <span data-ttu-id="c6c69-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="c6c69-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6c69-109">要求</span><span class="sxs-lookup"><span data-stu-id="c6c69-109">Requirements</span></span>  
 <span data-ttu-id="c6c69-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c69-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6c69-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c6c69-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c6c69-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c6c69-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6c69-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c69-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6c69-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c6c69-114">See also</span></span>

- [<span data-ttu-id="c6c69-115">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="c6c69-115">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c6c69-116">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="c6c69-116">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
