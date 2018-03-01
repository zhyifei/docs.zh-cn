---
title: "ICeeGen::TruncateSection 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICeeGen.TruncateSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::TruncateSection
helpviewer_keywords:
- TruncateSection method [.NET Framework metadata]
- ICeeGen::TruncateSection method [.NET Framework metadata]
ms.assetid: 0451d752-1e5c-4c9a-8bad-6cd35b7ba3df
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8e7deaaab58f1ee51bd3675faec892db5228c787
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="ac9fc-102">ICeeGen::TruncateSection 方法</span><span class="sxs-lookup"><span data-stu-id="ac9fc-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="ac9fc-103">通过指定长度截断指定的代码段。</span><span class="sxs-lookup"><span data-stu-id="ac9fc-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="ac9fc-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="ac9fc-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac9fc-105">语法</span><span class="sxs-lookup"><span data-stu-id="ac9fc-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ac9fc-106">参数</span><span class="sxs-lookup"><span data-stu-id="ac9fc-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="ac9fc-107">[in]要截断的部分。</span><span class="sxs-lookup"><span data-stu-id="ac9fc-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="ac9fc-108">[in]长度 （以字节为单位，用来截断部分）。</span><span class="sxs-lookup"><span data-stu-id="ac9fc-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ac9fc-109">备注</span><span class="sxs-lookup"><span data-stu-id="ac9fc-109">Remarks</span></span>  
 <span data-ttu-id="ac9fc-110">调用`TruncateSection`仅当你有特殊的段中要求未由其他方法。</span><span class="sxs-lookup"><span data-stu-id="ac9fc-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac9fc-111">惠?</span><span class="sxs-lookup"><span data-stu-id="ac9fc-111">Requirements</span></span>  
 <span data-ttu-id="ac9fc-112">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ac9fc-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac9fc-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="ac9fc-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac9fc-114">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="ac9fc-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac9fc-115">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac9fc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac9fc-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="ac9fc-116">See Also</span></span>  
 [<span data-ttu-id="ac9fc-117">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="ac9fc-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
