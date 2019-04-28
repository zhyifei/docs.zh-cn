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
ms.openlocfilehash: a4480d54390aea2771e2939b0a0825f6c49c3564
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61766125"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="3ccae-102">LoadFromHistory 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="3ccae-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="3ccae-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="3ccae-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="3ccae-104">Windows Presentation Foundation (WPF) 基础结构使用的 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="3ccae-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ccae-105">语法</span><span class="sxs-lookup"><span data-stu-id="3ccae-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="3ccae-106">参数</span><span class="sxs-lookup"><span data-stu-id="3ccae-106">Parameters</span></span>  
 <span data-ttu-id="3ccae-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="3ccae-107">pHistoryStream</span></span>  
 <span data-ttu-id="3ccae-108">指向流的历史记录信息的指针。</span><span class="sxs-lookup"><span data-stu-id="3ccae-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="3ccae-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="3ccae-109">pBindCtx</span></span>  
 <span data-ttu-id="3ccae-110">指向绑定上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="3ccae-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ccae-111">要求</span><span class="sxs-lookup"><span data-stu-id="3ccae-111">Requirements</span></span>  
 <span data-ttu-id="3ccae-112">**平台：** 请参阅[.NET Framework 系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3ccae-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ccae-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="3ccae-113">**DLL:**</span></span>  
  
 <span data-ttu-id="3ccae-114">在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="3ccae-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="3ccae-115">在.NET Framework 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="3ccae-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="3ccae-116">**.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ccae-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ccae-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="3ccae-117">See also</span></span>

- [<span data-ttu-id="3ccae-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="3ccae-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
