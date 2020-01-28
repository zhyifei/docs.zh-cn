---
title: LoadFromHistory 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727929"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c1743-102">LoadFromHistory 函数（WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="c1743-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="c1743-103">此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="c1743-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="c1743-104">由用于 Windows 管理的 Windows Presentation Foundation （WPF）基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="c1743-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1743-105">语法</span><span class="sxs-lookup"><span data-stu-id="c1743-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1743-106">参数</span><span class="sxs-lookup"><span data-stu-id="c1743-106">Parameters</span></span>  
 <span data-ttu-id="c1743-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="c1743-107">pHistoryStream</span></span>  
 <span data-ttu-id="c1743-108">指向历史记录信息流的指针。</span><span class="sxs-lookup"><span data-stu-id="c1743-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="c1743-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="c1743-109">pBindCtx</span></span>  
 <span data-ttu-id="c1743-110">指向绑定上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="c1743-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1743-111">需求</span><span class="sxs-lookup"><span data-stu-id="c1743-111">Requirements</span></span>  
 <span data-ttu-id="c1743-112">**平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="c1743-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1743-113">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="c1743-113">**DLL:**</span></span>  
  
 <span data-ttu-id="c1743-114">在 .NET Framework 3.0 和3.5： PresentationHostDLL</span><span class="sxs-lookup"><span data-stu-id="c1743-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="c1743-115">在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="c1743-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="c1743-116">**.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1743-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1743-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c1743-117">See also</span></span>

- [<span data-ttu-id="c1743-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="c1743-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
