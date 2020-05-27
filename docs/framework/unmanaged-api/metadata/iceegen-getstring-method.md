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
ms.openlocfilehash: b7b15261d825c1bd5f217c4cecd82ed36a716d0e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008256"
---
# <a name="iceegengetstring-method"></a><span data-ttu-id="1d30e-102">ICeeGen::GetString 方法</span><span class="sxs-lookup"><span data-stu-id="1d30e-102">ICeeGen::GetString Method</span></span>
<span data-ttu-id="1d30e-103">获取存储在指定的相对虚拟地址的字符串。</span><span class="sxs-lookup"><span data-stu-id="1d30e-103">Gets the string stored at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="1d30e-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="1d30e-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d30e-105">语法</span><span class="sxs-lookup"><span data-stu-id="1d30e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetString (  
    [in]  ULONG      RVA,
    [out] LPWSTR     *lpString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d30e-106">参数</span><span class="sxs-lookup"><span data-stu-id="1d30e-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="1d30e-107">中要返回的字符串的相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="1d30e-107">[in] The relative virtual address of the string to return.</span></span>  
  
 `lpString`  
 <span data-ttu-id="1d30e-108">弄返回的字符串。</span><span class="sxs-lookup"><span data-stu-id="1d30e-108">[out] The returned string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d30e-109">要求</span><span class="sxs-lookup"><span data-stu-id="1d30e-109">Requirements</span></span>  
 <span data-ttu-id="1d30e-110">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="1d30e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d30e-111">**标头：** Cor</span><span class="sxs-lookup"><span data-stu-id="1d30e-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d30e-112">**库：** 用作 Mscoree.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="1d30e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d30e-113">**.NET Framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d30e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d30e-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d30e-114">See also</span></span>

- [<span data-ttu-id="1d30e-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="1d30e-115">ICeeGen Interface</span></span>](iceegen-interface.md)
