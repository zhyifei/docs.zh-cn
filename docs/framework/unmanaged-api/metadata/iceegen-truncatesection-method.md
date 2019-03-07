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
ms.openlocfilehash: 69f536e6add43d664eba436e185275632dc0063a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479345"
---
# <a name="iceegentruncatesection-method"></a><span data-ttu-id="33d08-102">ICeeGen::TruncateSection 方法</span><span class="sxs-lookup"><span data-stu-id="33d08-102">ICeeGen::TruncateSection Method</span></span>
<span data-ttu-id="33d08-103">通过指定长度截断指定的代码部分。</span><span class="sxs-lookup"><span data-stu-id="33d08-103">Truncates the specified code section by the specified length.</span></span>  
  
 <span data-ttu-id="33d08-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="33d08-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33d08-105">语法</span><span class="sxs-lookup"><span data-stu-id="33d08-105">Syntax</span></span>  
  
```  
HRESULT TruncateSection (  
    [in]  HCEESECTION     section,  
    [in]  ULONG           len  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33d08-106">参数</span><span class="sxs-lookup"><span data-stu-id="33d08-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="33d08-107">[in]要截断的部分。</span><span class="sxs-lookup"><span data-stu-id="33d08-107">[in] The section to truncate.</span></span>  
  
 `len`  
 <span data-ttu-id="33d08-108">[in]长度 （以字节为单位，按其截断部分）。</span><span class="sxs-lookup"><span data-stu-id="33d08-108">[in] The length, in bytes, by which to truncate the section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33d08-109">备注</span><span class="sxs-lookup"><span data-stu-id="33d08-109">Remarks</span></span>  
 <span data-ttu-id="33d08-110">调用`TruncateSection`仅在具有未由其他方法的特殊部分要求。</span><span class="sxs-lookup"><span data-stu-id="33d08-110">Call `TruncateSection` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33d08-111">要求</span><span class="sxs-lookup"><span data-stu-id="33d08-111">Requirements</span></span>  
 <span data-ttu-id="33d08-112">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="33d08-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33d08-113">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="33d08-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="33d08-114">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="33d08-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="33d08-115">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33d08-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="33d08-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="33d08-116">See also</span></span>
- [<span data-ttu-id="33d08-117">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="33d08-117">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
