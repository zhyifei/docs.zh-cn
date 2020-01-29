---
title: CreateIDispatchSTAForwarder 函数-WPF 非托管 API 参考
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738028"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="769b4-102">CreateIDispatchSTAForwarder 函数（WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="769b4-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="769b4-103">此 API 支持 Windows Presentation Foundation （WPF）基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="769b4-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="769b4-104">由 Windows Presentation Foundation （WPF）基础结构用于线程和 Windows 管理。</span><span class="sxs-lookup"><span data-stu-id="769b4-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769b4-105">구문</span><span class="sxs-lookup"><span data-stu-id="769b4-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="769b4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="769b4-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="769b4-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="769b4-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="769b4-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="769b4-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="769b4-109">指向 `IDispatch` 接口的指针。</span><span class="sxs-lookup"><span data-stu-id="769b4-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="769b4-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="769b4-110">ppForwarder</span></span>  
 <span data-ttu-id="769b4-111">指向 `IDispatch` 接口的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="769b4-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="769b4-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="769b4-112">Requirements</span></span>  
 <span data-ttu-id="769b4-113">**平台：** 请参阅[.NET Framework 系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="769b4-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="769b4-114">**.DLL**</span><span class="sxs-lookup"><span data-stu-id="769b4-114">**DLL:**</span></span>  
  
 <span data-ttu-id="769b4-115">在 .NET Framework 3.0 和3.5： PresentationHostDLL</span><span class="sxs-lookup"><span data-stu-id="769b4-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="769b4-116">在 .NET Framework 4 及更高版本中： PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="769b4-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="769b4-117">**.NET Framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="769b4-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769b4-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="769b4-118">See also</span></span>

- [<span data-ttu-id="769b4-119">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="769b4-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
