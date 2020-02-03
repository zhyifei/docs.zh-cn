---
title: ForwardTranslateAccelerator 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: f6e8208ffe2c186234f30f31e346ca6b1d0be4c0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76747047"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="8aa83-102">ForwardTranslateAccelerator 函数（WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="8aa83-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="8aa83-103">此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="8aa83-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="8aa83-104">由用于 Windows 管理的 Windows Presentation Foundation （WPF）基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="8aa83-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8aa83-105">语法</span><span class="sxs-lookup"><span data-stu-id="8aa83-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="8aa83-106">参数</span><span class="sxs-lookup"><span data-stu-id="8aa83-106">Parameters</span></span>  
 <span data-ttu-id="8aa83-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="8aa83-107">pMsg</span></span>  
 <span data-ttu-id="8aa83-108">指向消息的指针。</span><span class="sxs-lookup"><span data-stu-id="8aa83-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="8aa83-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="8aa83-109">appUnhandled</span></span>  
 <span data-ttu-id="8aa83-110">当应用程序有机会处理输入消息但尚未处理时 `true`;否则，`false`。</span><span class="sxs-lookup"><span data-stu-id="8aa83-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8aa83-111">要求</span><span class="sxs-lookup"><span data-stu-id="8aa83-111">Requirements</span></span>  
 <span data-ttu-id="8aa83-112">**平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="8aa83-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8aa83-113">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="8aa83-113">**DLL:**</span></span>  
  
 <span data-ttu-id="8aa83-114">在 .NET Framework 3.0 和3.5： PresentationHostDLL</span><span class="sxs-lookup"><span data-stu-id="8aa83-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="8aa83-115">在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="8aa83-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="8aa83-116">**.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8aa83-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8aa83-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8aa83-117">See also</span></span>

- [<span data-ttu-id="8aa83-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="8aa83-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
