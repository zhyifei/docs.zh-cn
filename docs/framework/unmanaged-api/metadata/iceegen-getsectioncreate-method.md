---
title: "ICeeGen::GetSectionCreate 方法"
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
- ICeeGen.GetSectionCreate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetSectionCreate
helpviewer_keywords:
- ICeeGen::GetSectionCreate method [.NET Framework metadata]
- GetSectionCreate method [.NET Framework metadata]
ms.assetid: 154b2460-59ce-4874-a9f2-1b3353486ac5
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a069f65d3059bfa427ea20623ff9a2ac4049fd39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="7069f-102">ICeeGen::GetSectionCreate 方法</span><span class="sxs-lookup"><span data-stu-id="7069f-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="7069f-103">生成并获取使用指定的名称和标志值的代码节。</span><span class="sxs-lookup"><span data-stu-id="7069f-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="7069f-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="7069f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7069f-105">语法</span><span class="sxs-lookup"><span data-stu-id="7069f-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7069f-106">参数</span><span class="sxs-lookup"><span data-stu-id="7069f-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="7069f-107">[in]指向一个字符串，指定要创建的部分的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="7069f-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="7069f-108">[in]指定选项的标志。</span><span class="sxs-lookup"><span data-stu-id="7069f-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="7069f-109">[out]指向新创建的代码部分的指针。</span><span class="sxs-lookup"><span data-stu-id="7069f-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7069f-110">备注</span><span class="sxs-lookup"><span data-stu-id="7069f-110">Remarks</span></span>  
 <span data-ttu-id="7069f-111">调用`GetSectionCreate`仅当你有特殊的段中要求未由其他方法。</span><span class="sxs-lookup"><span data-stu-id="7069f-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7069f-112">惠?</span><span class="sxs-lookup"><span data-stu-id="7069f-112">Requirements</span></span>  
 <span data-ttu-id="7069f-113">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="7069f-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7069f-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7069f-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7069f-115">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="7069f-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7069f-116">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7069f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7069f-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7069f-117">See Also</span></span>  
 [<span data-ttu-id="7069f-118">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="7069f-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
