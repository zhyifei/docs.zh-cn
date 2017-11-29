---
title: "LoadFromHistory 函数 （WPF 非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: LoadFromHistory
api_location: PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cdb68700ab0c11bbd6b09b83a826dc5ca4faa086
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="870e8-102">LoadFromHistory 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="870e8-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="870e8-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="870e8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="870e8-104">Windows Presentation Foundation (WPF) 基础结构用于 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="870e8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="870e8-105">语法</span><span class="sxs-lookup"><span data-stu-id="870e8-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="870e8-106">参数</span><span class="sxs-lookup"><span data-stu-id="870e8-106">Parameters</span></span>  
 <span data-ttu-id="870e8-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="870e8-107">pHistoryStream</span></span>  
 <span data-ttu-id="870e8-108">指向历史记录信息的流的指针。</span><span class="sxs-lookup"><span data-stu-id="870e8-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="870e8-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="870e8-109">pBindCtx</span></span>  
 <span data-ttu-id="870e8-110">指向绑定上下文的指针。</span><span class="sxs-lookup"><span data-stu-id="870e8-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="870e8-111">要求</span><span class="sxs-lookup"><span data-stu-id="870e8-111">Requirements</span></span>  
 <span data-ttu-id="870e8-112">**平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="870e8-112">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="870e8-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="870e8-113">**DLL:**</span></span>  
  
 <span data-ttu-id="870e8-114">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="870e8-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="870e8-115">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="870e8-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="870e8-116">**.NET framework 版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="870e8-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="870e8-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="870e8-117">See Also</span></span>  
 [<span data-ttu-id="870e8-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="870e8-118">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
