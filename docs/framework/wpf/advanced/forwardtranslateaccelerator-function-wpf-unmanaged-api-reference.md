---
title: ForwardTranslateAccelerator 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: 02d5d23ec44d9fb7a244fc635ac174cf81ead173
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57362183"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="24417-102">ForwardTranslateAccelerator 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="24417-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="24417-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="24417-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="24417-104">Windows Presentation Foundation (WPF) 基础结构使用的 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="24417-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="24417-105">语法</span><span class="sxs-lookup"><span data-stu-id="24417-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,   
   VARIANT_BOOL appUnhandled  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="24417-106">参数</span><span class="sxs-lookup"><span data-stu-id="24417-106">Parameters</span></span>  
 <span data-ttu-id="24417-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="24417-107">pMsg</span></span>  
 <span data-ttu-id="24417-108">一条消息指向的指针。</span><span class="sxs-lookup"><span data-stu-id="24417-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="24417-109">appUnhandled</span><span class="sxs-lookup"><span data-stu-id="24417-109">appUnhandled</span></span>  
 <span data-ttu-id="24417-110">`true` 当应用程序已提供有机会处理输入的消息，但不是处理它;否则为`false`。</span><span class="sxs-lookup"><span data-stu-id="24417-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="24417-111">要求</span><span class="sxs-lookup"><span data-stu-id="24417-111">Requirements</span></span>  
 <span data-ttu-id="24417-112">**平台：** 请参阅[.NET Framework 系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="24417-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24417-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="24417-113">**DLL:**</span></span>  
  
 <span data-ttu-id="24417-114">在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="24417-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="24417-115">在.NET Framework 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="24417-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="24417-116">**.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24417-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24417-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="24417-117">See also</span></span>
- [<span data-ttu-id="24417-118">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="24417-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
