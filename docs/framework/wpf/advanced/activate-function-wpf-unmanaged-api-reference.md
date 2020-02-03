---
title: 激活函数 WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: 9c0a235e8b94294ab82da88e43f7446c29739c12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734508"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f3a3e-102">Activate 函数（WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="f3a3e-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="f3a3e-103">此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="f3a3e-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="f3a3e-104">由用于 Windows 管理的 Windows Presentation Foundation （WPF）基础结构使用。</span><span class="sxs-lookup"><span data-stu-id="f3a3e-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="f3a3e-105">语法</span><span class="sxs-lookup"><span data-stu-id="f3a3e-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="f3a3e-106">参数</span><span class="sxs-lookup"><span data-stu-id="f3a3e-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="f3a3e-107">指向窗口的激活参数的指针。</span><span class="sxs-lookup"><span data-stu-id="f3a3e-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="f3a3e-108">指向单个元素缓冲区的地址的指针，该缓冲区包含指向 <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> 对象的指针。</span><span class="sxs-lookup"><span data-stu-id="f3a3e-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="f3a3e-109">要求</span><span class="sxs-lookup"><span data-stu-id="f3a3e-109">Requirements</span></span>

<span data-ttu-id="f3a3e-110">**平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f3a3e-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="f3a3e-111">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="f3a3e-111">**DLL:**</span></span>

<span data-ttu-id="f3a3e-112">在 .NET Framework 3.0 和3.5： PresentationHostDLL</span><span class="sxs-lookup"><span data-stu-id="f3a3e-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="f3a3e-113">在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="f3a3e-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="f3a3e-114">**.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3a3e-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f3a3e-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3a3e-115">See also</span></span>

- [<span data-ttu-id="f3a3e-116">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="f3a3e-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
