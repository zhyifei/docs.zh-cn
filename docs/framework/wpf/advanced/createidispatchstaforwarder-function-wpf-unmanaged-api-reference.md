---
title: "CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 5139784fdc067c09d032c0bf37114e0eb1caac33
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d8d3b-102">CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d8d3b-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d8d3b-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="d8d3b-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d8d3b-104">Windows Presentation Foundation (WPF) 基础结构用于线程和 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="d8d3b-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8d3b-105">语法</span><span class="sxs-lookup"><span data-stu-id="d8d3b-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d8d3b-106">参数</span><span class="sxs-lookup"><span data-stu-id="d8d3b-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d8d3b-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d8d3b-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="d8d3b-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="d8d3b-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="d8d3b-109">指向的指针`IDispatch`接口。</span><span class="sxs-lookup"><span data-stu-id="d8d3b-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="d8d3b-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="d8d3b-110">ppForwarder</span></span>  
 <span data-ttu-id="d8d3b-111">指向的地址的指针`IDispatch`接口。</span><span class="sxs-lookup"><span data-stu-id="d8d3b-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d8d3b-112">惠?</span><span class="sxs-lookup"><span data-stu-id="d8d3b-112">Requirements</span></span>  
 <span data-ttu-id="d8d3b-113">**平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d8d3b-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8d3b-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="d8d3b-114">**DLL:**</span></span>  
  
 <span data-ttu-id="d8d3b-115">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d8d3b-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d8d3b-116">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d8d3b-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="d8d3b-117">**.NET framework 版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d8d3b-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8d3b-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8d3b-118">See Also</span></span>  
 [<span data-ttu-id="d8d3b-119">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="d8d3b-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
