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
ms.openlocfilehash: ada126b41f1c634f7d8daa58480406ac26f92377
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177908"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="a021b-102">ICeeGen::GetString 方法</span><span class="sxs-lookup"><span data-stu-id="a021b-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="a021b-103">获取存储在指定相对虚拟地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="a021b-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="a021b-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="a021b-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a021b-105">语法</span><span class="sxs-lookup"><span data-stu-id="a021b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a021b-106">parameters</span><span class="sxs-lookup"><span data-stu-id="a021b-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="a021b-107">[在]要返回的字符串的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="a021b-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="a021b-108">[出]返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="a021b-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a021b-109">要求</span><span class="sxs-lookup"><span data-stu-id="a021b-109">Requirements</span></span>  
 <span data-ttu-id="a021b-110">**平台：** 请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="a021b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a021b-111">**标题：** 科尔赫</span><span class="sxs-lookup"><span data-stu-id="a021b-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="a021b-112">**库：** 用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="a021b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="a021b-113">**.NET 框架版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a021b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a021b-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a021b-114">See also</span></span>

- [<span data-ttu-id="a021b-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="a021b-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)
