---
title: ICeeGen::GetStringSection 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetStringSection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type:
- apiref
ms.openlocfilehash: ba8da686d1834c81111828e9856525b96f575b93
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443261"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="e4b3f-102">ICeeGen::GetStringSection 方法</span><span class="sxs-lookup"><span data-stu-id="e4b3f-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="e4b3f-103">获取由指定句柄引用的代码段的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="e4b3f-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="e4b3f-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="e4b3f-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4b3f-105">语法</span><span class="sxs-lookup"><span data-stu-id="e4b3f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4b3f-106">参数</span><span class="sxs-lookup"><span data-stu-id="e4b3f-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="e4b3f-107">[in，out]代码部分的句柄。</span><span class="sxs-lookup"><span data-stu-id="e4b3f-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4b3f-108">要求</span><span class="sxs-lookup"><span data-stu-id="e4b3f-108">Requirements</span></span>  
 <span data-ttu-id="e4b3f-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="e4b3f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4b3f-110">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="e4b3f-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e4b3f-111">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="e4b3f-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="e4b3f-112">**.NET Framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4b3f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4b3f-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e4b3f-113">See also</span></span>

- [<span data-ttu-id="e4b3f-114">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="e4b3f-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
