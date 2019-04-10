---
title: IMetaDataEmit::SetFieldRVA 方法
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldRVA
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldRVA
helpviewer_keywords:
- IMetaDataEmit::SetFieldRVA method [.NET Framework metadata]
- SetFieldRVA method [.NET Framework metadata]
ms.assetid: 6dc37f9d-87ee-4cb3-9216-ced600184ce8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4ebde1d506a120a99e1c637c660b45d698994f5a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59181670"
---
# <a name="imetadataemitsetfieldrva-method"></a><span data-ttu-id="05202-102">IMetaDataEmit::SetFieldRVA 方法</span><span class="sxs-lookup"><span data-stu-id="05202-102">IMetaDataEmit::SetFieldRVA Method</span></span>
<span data-ttu-id="05202-103">设置指定标记所引用的字段的相对虚拟地址的全局变量值。</span><span class="sxs-lookup"><span data-stu-id="05202-103">Sets a global variable value for the relative virtual address of the field referenced by the specified token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05202-104">语法</span><span class="sxs-lookup"><span data-stu-id="05202-104">Syntax</span></span>  
  
```  
HRESULT SetFieldRVA (   
    [in]  mdFieldDef  fd,   
    [in]  ULONG       ulRVA   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05202-105">参数</span><span class="sxs-lookup"><span data-stu-id="05202-105">Parameters</span></span>  
 `fd`  
 <span data-ttu-id="05202-106">[in]目标字段的标记。</span><span class="sxs-lookup"><span data-stu-id="05202-106">[in] The token for the target field.</span></span>  
  
 `ulRVA`  
 <span data-ttu-id="05202-107">[in]代码或数据区域的地址。</span><span class="sxs-lookup"><span data-stu-id="05202-107">[in] The address of a code or data area.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05202-108">要求</span><span class="sxs-lookup"><span data-stu-id="05202-108">Requirements</span></span>  
 <span data-ttu-id="05202-109">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="05202-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05202-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="05202-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="05202-111">**库：** 用作 MSCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="05202-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="05202-112">.NET Framework 版本：</span><span class="sxs-lookup"><span data-stu-id="05202-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="05202-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="05202-113">See also</span></span>

- [<span data-ttu-id="05202-114">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="05202-114">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="05202-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="05202-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
