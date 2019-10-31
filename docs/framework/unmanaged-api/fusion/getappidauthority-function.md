---
title: GetAppIdAuthority 函数
ms.date: 03/30/2017
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
ms.openlocfilehash: 22a6af61251942f068676daaee2bdfa868e32a97
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134559"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="3a15d-102">GetAppIdAuthority 函数</span><span class="sxs-lookup"><span data-stu-id="3a15d-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="3a15d-103">获取一个指针，该指针指向管理应用程序标识和引用的密钥的[IAppIdAuthority](iappidauthority-interface.md)实例。</span><span class="sxs-lookup"><span data-stu-id="3a15d-103">Gets a pointer to an [IAppIdAuthority](iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a15d-104">语法</span><span class="sxs-lookup"><span data-stu-id="3a15d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a15d-105">参数</span><span class="sxs-lookup"><span data-stu-id="3a15d-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="3a15d-106">弄返回的 `IAppIdAuthority` 指针。</span><span class="sxs-lookup"><span data-stu-id="3a15d-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a15d-107">要求</span><span class="sxs-lookup"><span data-stu-id="3a15d-107">Requirements</span></span>  
 <span data-ttu-id="3a15d-108">**平台：** 请参阅[系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3a15d-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a15d-109">**标头：** 隔离。h</span><span class="sxs-lookup"><span data-stu-id="3a15d-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="3a15d-110">**.NET Framework 版本：** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a15d-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a15d-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="3a15d-111">See also</span></span>

- [<span data-ttu-id="3a15d-112">IAppIdAuthority 接口</span><span class="sxs-lookup"><span data-stu-id="3a15d-112">IAppIdAuthority Interface</span></span>](iappidauthority-interface.md)
- [<span data-ttu-id="3a15d-113">合成全局静态函数</span><span class="sxs-lookup"><span data-stu-id="3a15d-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
