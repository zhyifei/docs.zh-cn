---
title: ICeeGen::GetSectionDataLen 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetSectionDataLen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionDataLen
helpviewer_keywords:
- ICeeGen::GetSectionDataLen method [.NET Framework metadata]
- GetSectionDataLen method [.NET Framework metadata]
ms.assetid: e2a06ee4-b8ee-49c7-935a-c1031a29eef2
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ca01f78cf46d4f7543b949c820eb6b1971687e23
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198707"
---
# <a name="iceegengetsectiondatalen-method"></a><span data-ttu-id="aa620-102">ICeeGen::GetSectionDataLen 方法</span><span class="sxs-lookup"><span data-stu-id="aa620-102">ICeeGen::GetSectionDataLen Method</span></span>
<span data-ttu-id="aa620-103">获取指定的节的长度。</span><span class="sxs-lookup"><span data-stu-id="aa620-103">Gets the length of the specified section.</span></span>  
  
 <span data-ttu-id="aa620-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="aa620-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa620-105">语法</span><span class="sxs-lookup"><span data-stu-id="aa620-105">Syntax</span></span>  
  
```  
HRESULT GetSectionDataLen (  
    [in]  HCEESECTION  section,  
    [out] ULONG        *dataLen  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa620-106">参数</span><span class="sxs-lookup"><span data-stu-id="aa620-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="aa620-107">[in]将检索其长度的数据部分。</span><span class="sxs-lookup"><span data-stu-id="aa620-107">[in] The data section whose length will be retrieved.</span></span>  
  
 `dataLen`  
 <span data-ttu-id="aa620-108">[out]返回的指定部分的长度。</span><span class="sxs-lookup"><span data-stu-id="aa620-108">[out] The returned length of the specified section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aa620-109">备注</span><span class="sxs-lookup"><span data-stu-id="aa620-109">Remarks</span></span>  
 <span data-ttu-id="aa620-110">调用`GetSectionDataLen`仅在具有未由其他方法的特殊部分要求。</span><span class="sxs-lookup"><span data-stu-id="aa620-110">Call `GetSectionDataLen` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa620-111">要求</span><span class="sxs-lookup"><span data-stu-id="aa620-111">Requirements</span></span>  
 <span data-ttu-id="aa620-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="aa620-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa620-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="aa620-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa620-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="aa620-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa620-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa620-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa620-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="aa620-116">See also</span></span>

- [<span data-ttu-id="aa620-117">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="aa620-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
