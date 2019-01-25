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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f51ce9a4b45bd674f53cf7b4c4d6cedb8d46858d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54586418"
---
# <a name="iceegenemitstring-method"></a><span data-ttu-id="71279-102">ICeeGen::EmitString 方法</span><span class="sxs-lookup"><span data-stu-id="71279-102">ICeeGen::EmitString Method</span></span>
<span data-ttu-id="71279-103">将指定的字符串发出到基本代码。</span><span class="sxs-lookup"><span data-stu-id="71279-103">Emits the specified string into the code base.</span></span>  
  
 <span data-ttu-id="71279-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="71279-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71279-105">语法</span><span class="sxs-lookup"><span data-stu-id="71279-105">Syntax</span></span>  
  
```  
HRESULT EmitString (  
    [in]  LPWSTR    lpString,  
    [out] ULONG     *RVA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="71279-106">参数</span><span class="sxs-lookup"><span data-stu-id="71279-106">Parameters</span></span>  
 `lpString`  
 <span data-ttu-id="71279-107">[in]要发出的字符串。</span><span class="sxs-lookup"><span data-stu-id="71279-107">[in] The string to emit.</span></span>  
  
 `RVA`  
 <span data-ttu-id="71279-108">[out]发出的字符串的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="71279-108">[out] The relative virtual address of the emitted string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="71279-109">要求</span><span class="sxs-lookup"><span data-stu-id="71279-109">Requirements</span></span>  
 <span data-ttu-id="71279-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="71279-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="71279-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="71279-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="71279-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="71279-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="71279-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="71279-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71279-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="71279-114">See also</span></span>
- [<span data-ttu-id="71279-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="71279-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
