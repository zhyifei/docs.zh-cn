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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0a8617c9e818ec514c912a85373c916559d89df3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443032"
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="5d278-102">ICeeGen::GetStringSection 方法</span><span class="sxs-lookup"><span data-stu-id="5d278-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="5d278-103">获取由指定的句柄引用的代码部分的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="5d278-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="5d278-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="5d278-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d278-105">语法</span><span class="sxs-lookup"><span data-stu-id="5d278-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d278-106">参数</span><span class="sxs-lookup"><span data-stu-id="5d278-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="5d278-107">[在中，out]窗口的句柄的代码段。</span><span class="sxs-lookup"><span data-stu-id="5d278-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d278-108">要求</span><span class="sxs-lookup"><span data-stu-id="5d278-108">Requirements</span></span>  
 <span data-ttu-id="5d278-109">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="5d278-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d278-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5d278-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5d278-111">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="5d278-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5d278-112">**.NET framework 版本：** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d278-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d278-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="5d278-113">See Also</span></span>  
 [<span data-ttu-id="5d278-114">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="5d278-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
