---
title: ICeeGen::GetIlSection 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetIlSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetIlSection
helpviewer_keywords:
- GetIlSection method [.NET Framework metadata]
- ICeeGen::GetIlSection method [.NET Framework metadata]
ms.assetid: 6f2db2ca-203f-4ac3-9530-208642ca385e
topic_type:
- apiref
ms.openlocfilehash: 05f39befa8966046cd71db82da37c44f20992cff
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008802"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="8bba0-102">ICeeGen::GetIlSection 方法</span><span class="sxs-lookup"><span data-stu-id="8bba0-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="8bba0-103">获取由指定句柄引用的中间语言代码库的部分。</span><span class="sxs-lookup"><span data-stu-id="8bba0-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="8bba0-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="8bba0-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bba0-105">语法</span><span class="sxs-lookup"><span data-stu-id="8bba0-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8bba0-106">参数</span><span class="sxs-lookup"><span data-stu-id="8bba0-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="8bba0-107">中要获取的节的句柄。</span><span class="sxs-lookup"><span data-stu-id="8bba0-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bba0-108">要求</span><span class="sxs-lookup"><span data-stu-id="8bba0-108">Requirements</span></span>  
 <span data-ttu-id="8bba0-109">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8bba0-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bba0-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="8bba0-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bba0-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="8bba0-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bba0-112">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bba0-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bba0-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8bba0-113">See also</span></span>

- [<span data-ttu-id="8bba0-114">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="8bba0-114">ICeeGen Interface</span></span>](iceegen-interface.md)
