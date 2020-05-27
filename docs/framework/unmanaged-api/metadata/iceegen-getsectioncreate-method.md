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
ms.openlocfilehash: 0cf7b15392c90694db659f6faff6feecbef65466
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008313"
---
# <a name="iceegengetsectioncreate-method"></a><span data-ttu-id="8b3c6-102">ICeeGen::GetSectionCreate 方法</span><span class="sxs-lookup"><span data-stu-id="8b3c6-102">ICeeGen::GetSectionCreate Method</span></span>
<span data-ttu-id="8b3c6-103">使用指定的名称和标志值生成并获取代码部分。</span><span class="sxs-lookup"><span data-stu-id="8b3c6-103">Generates and gets a code section using the specified name and flag values.</span></span>  
  
 <span data-ttu-id="8b3c6-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="8b3c6-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b3c6-105">语法</span><span class="sxs-lookup"><span data-stu-id="8b3c6-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSectionCreate (  
    [in]  const char     *name,  
    [in]  DWORD          flags,  
    [out] HCEESECTION    *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b3c6-106">参数</span><span class="sxs-lookup"><span data-stu-id="8b3c6-106">Parameters</span></span>  
 `name`  
 <span data-ttu-id="8b3c6-107">中指向字符串的指针，该字符串指定要创建的节的名称。</span><span class="sxs-lookup"><span data-stu-id="8b3c6-107">[in] A pointer to a string that specifies the name of the section to be created.</span></span>  
  
 `flags`  
 <span data-ttu-id="8b3c6-108">中指定选项的标志。</span><span class="sxs-lookup"><span data-stu-id="8b3c6-108">[in] Flags that specify options.</span></span>  
  
 `section`  
 <span data-ttu-id="8b3c6-109">弄指向新创建的代码部分的指针。</span><span class="sxs-lookup"><span data-stu-id="8b3c6-109">[out] A pointer to the newly created code section.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8b3c6-110">备注</span><span class="sxs-lookup"><span data-stu-id="8b3c6-110">Remarks</span></span>  
 <span data-ttu-id="8b3c6-111">`GetSectionCreate`仅当有特殊部分的要求不是由其他方法处理时才调用。</span><span class="sxs-lookup"><span data-stu-id="8b3c6-111">Call `GetSectionCreate` only if you have special section requirements that are not handled by other methods.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b3c6-112">要求</span><span class="sxs-lookup"><span data-stu-id="8b3c6-112">Requirements</span></span>  
 <span data-ttu-id="8b3c6-113">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8b3c6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b3c6-114">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8b3c6-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b3c6-115">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8b3c6-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b3c6-116">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b3c6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b3c6-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b3c6-117">See also</span></span>

- [<span data-ttu-id="8b3c6-118">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="8b3c6-118">ICeeGen Interface</span></span>](iceegen-interface.md)
