---
title: LoadFromHistory 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 19674b45af84e1e6a6ca169f7b6654c6e3847416
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544659"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="ed1bf-102">LoadFromHistory 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="ed1bf-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="ed1bf-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="ed1bf-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="ed1bf-104">Windows Presentation Foundation (WPF) 基础结构用于 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="ed1bf-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed1bf-105">语法</span><span class="sxs-lookup"><span data-stu-id="ed1bf-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed1bf-106">参数</span><span class="sxs-lookup"><span data-stu-id="ed1bf-106">Parameters</span></span>  
 <span data-ttu-id="ed1bf-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="ed1bf-107">pHistoryStream</span></span>  
 <span data-ttu-id="ed1bf-108">指向历史记录信息的流的指针。</span><span class="sxs-lookup"><span data-stu-id="ed1bf-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="ed1bf-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="ed1bf-109">pBindCtx</span></span>  
 <span data-ttu-id="ed1bf-110">指向绑定上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="ed1bf-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed1bf-111">要求</span><span class="sxs-lookup"><span data-stu-id="ed1bf-111">Requirements</span></span>  
 <span data-ttu-id="ed1bf-112">**平台：** 请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ed1bf-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed1bf-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="ed1bf-113">**DLL:**</span></span>  
  
 <span data-ttu-id="ed1bf-114">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="ed1bf-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="ed1bf-115">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="ed1bf-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="ed1bf-116">**.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed1bf-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed1bf-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="ed1bf-117">See Also</span></span>  
 [<span data-ttu-id="ed1bf-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="ed1bf-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
