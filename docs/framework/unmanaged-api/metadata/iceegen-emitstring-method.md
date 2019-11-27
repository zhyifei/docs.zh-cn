---
title: ICeeGen::EmitString 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.EmitString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::EmitString
helpviewer_keywords:
- EmitString method [.NET Framework metadata]
- ICeeGen::EmitString method [.NET Framework metadata]
ms.assetid: ad2710a7-edb8-4493-8619-3fce235e3334
topic_type:
- apiref
ms.openlocfilehash: 8433ff6e0ec550d6b0558bfb9c7698c49e98278c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436381"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="5196b-102">ICeeGen::EmitString 方法</span><span class="sxs-lookup"><span data-stu-id="5196b-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="5196b-103">向基本代码发出指定的字符串。</span><span class="sxs-lookup"><span data-stu-id="5196b-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="5196b-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="5196b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5196b-105">语法</span><span class="sxs-lookup"><span data-stu-id="5196b-105">Syntax</span></span>  
  
```cpp  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5196b-106">参数</span><span class="sxs-lookup"><span data-stu-id="5196b-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="5196b-107">中要发出的字符串。</span><span class="sxs-lookup"><span data-stu-id="5196b-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="5196b-108">弄发出的字符串的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="5196b-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5196b-109">要求</span><span class="sxs-lookup"><span data-stu-id="5196b-109">Requirements</span></span>  
 <span data-ttu-id="5196b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5196b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5196b-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="5196b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5196b-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5196b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5196b-113">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5196b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5196b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5196b-114">See also</span></span>

- [<span data-ttu-id="5196b-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="5196b-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
