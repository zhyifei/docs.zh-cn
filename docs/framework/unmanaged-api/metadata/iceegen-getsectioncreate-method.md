---
title: ICeeGen::GetSectionCreate 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9768dfd43b6b60df1660c48cb6d6f498b049e256
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61905510"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="eaca4-102">ICeeGen::GetSectionCreate 方法</span><span class="sxs-lookup"><span data-stu-id="eaca4-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="eaca4-103">生成并获取使用指定的名称和标记值的代码节。</span><span class="sxs-lookup"><span data-stu-id="eaca4-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="eaca4-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="eaca4-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eaca4-105">语法</span><span class="sxs-lookup"><span data-stu-id="eaca4-105">Syntax</span></span>  
  
```  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="eaca4-106">参数</span><span class="sxs-lookup"><span data-stu-id="eaca4-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="eaca4-107">[in]指向一个字符串，指定要创建的节的名称的指针。</span><span class="sxs-lookup"><span data-stu-id="eaca4-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="eaca4-108">[in]指定选项的标志。</span><span class="sxs-lookup"><span data-stu-id="eaca4-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="eaca4-109">[out]指向新创建的代码部分的指针。</span><span class="sxs-lookup"><span data-stu-id="eaca4-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eaca4-110">备注</span><span class="sxs-lookup"><span data-stu-id="eaca4-110">Remarks</span></span>  
 <span data-ttu-id="eaca4-111">调用`GetSectionCreate`仅在具有未由其他方法的特殊部分要求。</span><span class="sxs-lookup"><span data-stu-id="eaca4-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eaca4-112">要求</span><span class="sxs-lookup"><span data-stu-id="eaca4-112">Requirements</span></span>  
 <span data-ttu-id="eaca4-113">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eaca4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eaca4-114">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="eaca4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="eaca4-115">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="eaca4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="eaca4-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eaca4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaca4-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="eaca4-117">See also</span></span>

- [<span data-ttu-id="eaca4-118">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="eaca4-118">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
