---
title: ICeeGen::GetString 方法
ms.date: 03/30/2017
api_name:
- ICeeGen.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICeeGen::GetString
helpviewer_keywords:
- ICeeGen::GetString method [.NET Framework metadata]
- GetString method, ICeeGen interface [.NET Framework metadata]
ms.assetid: 7cc22562-128c-440a-9147-55ff20f173d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70d78942d4db2fea2cc1ccbcc5ddb20d743e9fdf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "59093665"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="4eb74-102">ICeeGen::GetString 方法</span><span class="sxs-lookup"><span data-stu-id="4eb74-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="4eb74-103">获取存储在指定的相对虚拟地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="4eb74-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="4eb74-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="4eb74-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4eb74-105">语法</span><span class="sxs-lookup"><span data-stu-id="4eb74-105">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in]  ULONG      RVA,   
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4eb74-106">参数</span><span class="sxs-lookup"><span data-stu-id="4eb74-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="4eb74-107">[in]要返回的字符串相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="4eb74-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="4eb74-108">[out]返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="4eb74-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4eb74-109">要求</span><span class="sxs-lookup"><span data-stu-id="4eb74-109">Requirements</span></span>  
 <span data-ttu-id="4eb74-110">**平台：** 请参阅[系统需求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4eb74-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4eb74-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4eb74-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4eb74-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="4eb74-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4eb74-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4eb74-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4eb74-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="4eb74-114">See also</span></span>

- [<span data-ttu-id="4eb74-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="4eb74-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
