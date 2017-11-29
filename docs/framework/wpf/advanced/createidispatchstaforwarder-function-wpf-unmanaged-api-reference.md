---
title: "CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: cpp
api_name: CreateIDispatchSTAForwarder
api_location: PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 63195ce2a47add2606f528b18d0d1d58ab0d968c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d4ddf-102">CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="d4ddf-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d4ddf-103">此 API 支持的 Windows Presentation Foundation (WPF) 基础结构，不宜在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="d4ddf-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d4ddf-104">Windows Presentation Foundation (WPF) 基础结构用于线程和 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="d4ddf-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4ddf-105">语法</span><span class="sxs-lookup"><span data-stu-id="d4ddf-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d4ddf-106">参数</span><span class="sxs-lookup"><span data-stu-id="d4ddf-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d4ddf-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d4ddf-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="d4ddf-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="d4ddf-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="d4ddf-109">指向的指针`IDispatch`接口。</span><span class="sxs-lookup"><span data-stu-id="d4ddf-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="d4ddf-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="d4ddf-110">ppForwarder</span></span>  
 <span data-ttu-id="d4ddf-111">指向的地址的指针`IDispatch`接口。</span><span class="sxs-lookup"><span data-stu-id="d4ddf-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4ddf-112">要求</span><span class="sxs-lookup"><span data-stu-id="d4ddf-112">Requirements</span></span>  
 <span data-ttu-id="d4ddf-113">**平台：**请参阅[.NET Framework 系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d4ddf-113">**Platforms:** See [.NET Framework System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4ddf-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="d4ddf-114">**DLL:**</span></span>  
  
 <span data-ttu-id="d4ddf-115">在.NET Framework 3.0 和 3.5: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="d4ddf-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d4ddf-116">在.NET Framework 4 及更高版本： PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="d4ddf-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="d4ddf-117">**.NET framework 版本：**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4ddf-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ddf-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4ddf-118">See Also</span></span>  
 [<span data-ttu-id="d4ddf-119">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="d4ddf-119">WPF Unmanaged API Reference</span></span>](../../../../docs/framework/wpf/advanced/wpf-unmanaged-api-reference.md)
