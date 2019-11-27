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
ms.openlocfilehash: 7ef944fd06d07dc8c4e49061a5e72d8acc4d0465
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436346"
---
# <a name="iceegengetilsection-method"></a><span data-ttu-id="c02e2-102">ICeeGen::GetIlSection 方法</span><span class="sxs-lookup"><span data-stu-id="c02e2-102">ICeeGen::GetIlSection Method</span></span>
<span data-ttu-id="c02e2-103">获取由指定句柄引用的中间语言代码库的部分。</span><span class="sxs-lookup"><span data-stu-id="c02e2-103">Gets the section of the intermediate language code base referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="c02e2-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="c02e2-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c02e2-105">语法</span><span class="sxs-lookup"><span data-stu-id="c02e2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetIlSection (  
    [in] HCEESECTION  *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c02e2-106">参数</span><span class="sxs-lookup"><span data-stu-id="c02e2-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="c02e2-107">中要获取的节的句柄。</span><span class="sxs-lookup"><span data-stu-id="c02e2-107">[in] The handle to the section to get.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c02e2-108">要求</span><span class="sxs-lookup"><span data-stu-id="c02e2-108">Requirements</span></span>  
 <span data-ttu-id="c02e2-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c02e2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c02e2-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="c02e2-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c02e2-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="c02e2-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c02e2-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c02e2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c02e2-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c02e2-113">See also</span></span>

- [<span data-ttu-id="c02e2-114">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="c02e2-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
