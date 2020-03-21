---
title: 创建IDispatchSTA转发器功能 - WPF非托管 API 引用
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174714"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="4a6c6-102">创建IDispatchSTA转发器功能（WPF非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="4a6c6-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="4a6c6-103">此 API 支持 Windows 演示基础 （WPF） 基础结构，不用于直接从代码中使用。</span><span class="sxs-lookup"><span data-stu-id="4a6c6-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="4a6c6-104">由 Windows 演示基础 （WPF） 基础结构用于线程和窗口管理。</span><span class="sxs-lookup"><span data-stu-id="4a6c6-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a6c6-105">语法</span><span class="sxs-lookup"><span data-stu-id="4a6c6-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a6c6-106">parameters</span><span class="sxs-lookup"><span data-stu-id="4a6c6-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="4a6c6-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="4a6c6-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="4a6c6-108">p调度委托</span><span class="sxs-lookup"><span data-stu-id="4a6c6-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="4a6c6-109">指向接口的`IDispatch`指针。</span><span class="sxs-lookup"><span data-stu-id="4a6c6-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="4a6c6-110">pp 转发器</span><span class="sxs-lookup"><span data-stu-id="4a6c6-110">ppForwarder</span></span>  
 <span data-ttu-id="4a6c6-111">指向接口地址的`IDispatch`指针。</span><span class="sxs-lookup"><span data-stu-id="4a6c6-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a6c6-112">要求</span><span class="sxs-lookup"><span data-stu-id="4a6c6-112">Requirements</span></span>  
 <span data-ttu-id="4a6c6-113">**平台：** 请参阅[.NET 框架系统要求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6c6-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a6c6-114">**Dll：**</span><span class="sxs-lookup"><span data-stu-id="4a6c6-114">**DLL:**</span></span>  
  
 <span data-ttu-id="4a6c6-115">在 .NET 框架 3.0 和 3.5 中：演示HostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="4a6c6-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="4a6c6-116">在 .NET 框架 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="4a6c6-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="4a6c6-117">**.NET 框架版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a6c6-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a6c6-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a6c6-118">See also</span></span>

- [<span data-ttu-id="4a6c6-119">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="4a6c6-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
