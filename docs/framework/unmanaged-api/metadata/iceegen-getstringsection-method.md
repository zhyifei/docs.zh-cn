---
title: "ICeeGen::GetStringSection 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetStringSection
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetStringSection
helpviewer_keywords:
- ICeeGen::GetStringSection method [.NET Framework metadata]
- GetStringSection method [.NET Framework metadata]
ms.assetid: a2267d39-69d1-4de1-bf37-f752cafacc71
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ce511b4610a6ff681eb70bfeb6a7a7afe162818e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetstringsection-method"></a><span data-ttu-id="81bbb-102">ICeeGen::GetStringSection 方法</span><span class="sxs-lookup"><span data-stu-id="81bbb-102">ICeeGen::GetStringSection Method</span></span>
<span data-ttu-id="81bbb-103">获取由指定的句柄引用的代码部分的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="81bbb-103">Gets a string representation of the code section referenced by the specified handle.</span></span>  
  
 <span data-ttu-id="81bbb-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="81bbb-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81bbb-105">语法</span><span class="sxs-lookup"><span data-stu-id="81bbb-105">Syntax</span></span>  
  
```  
HRESULT GetStringSection (  
    [in, out] HCEESECTION     *section  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81bbb-106">参数</span><span class="sxs-lookup"><span data-stu-id="81bbb-106">Parameters</span></span>  
 `section`  
 <span data-ttu-id="81bbb-107">[在中，out]窗口的句柄的代码段。</span><span class="sxs-lookup"><span data-stu-id="81bbb-107">[in, out] The handle to the code section.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81bbb-108">要求</span><span class="sxs-lookup"><span data-stu-id="81bbb-108">Requirements</span></span>  
 <span data-ttu-id="81bbb-109">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="81bbb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81bbb-110">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="81bbb-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="81bbb-111">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="81bbb-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="81bbb-112">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81bbb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81bbb-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="81bbb-113">See Also</span></span>  
 [<span data-ttu-id="81bbb-114">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="81bbb-114">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
