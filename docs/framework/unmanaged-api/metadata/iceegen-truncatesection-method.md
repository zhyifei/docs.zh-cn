---
title: ICeeGen::TruncateSection 方法
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a7b21179faec0b6f37b8084c9ee8a0bfd327193e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443559"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="4f072-102">ICeeGen::TruncateSection 方法</span><span class="sxs-lookup"><span data-stu-id="4f072-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="4f072-103">通过指定长度截断指定的代码段。</span><span class="sxs-lookup"><span data-stu-id="4f072-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="4f072-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="4f072-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f072-105">语法</span><span class="sxs-lookup"><span data-stu-id="4f072-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f072-106">参数</span><span class="sxs-lookup"><span data-stu-id="4f072-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="4f072-107">[in]要截断的部分。</span><span class="sxs-lookup"><span data-stu-id="4f072-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="4f072-108">[in]长度 （以字节为单位，用来截断部分）。</span><span class="sxs-lookup"><span data-stu-id="4f072-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f072-109">备注</span><span class="sxs-lookup"><span data-stu-id="4f072-109">Remarks</span></span>  
 <span data-ttu-id="4f072-110">调用`TruncateSection`仅当你有特殊的段中要求未由其他方法。</span><span class="sxs-lookup"><span data-stu-id="4f072-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f072-111">要求</span><span class="sxs-lookup"><span data-stu-id="4f072-111">Requirements</span></span>  
 <span data-ttu-id="4f072-112">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4f072-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f072-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4f072-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4f072-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4f072-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4f072-115">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f072-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f072-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="4f072-116">See Also</span></span>  
 [<span data-ttu-id="4f072-117">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="4f072-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
