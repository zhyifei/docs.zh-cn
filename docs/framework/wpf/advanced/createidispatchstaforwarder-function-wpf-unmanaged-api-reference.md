---
title: CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 1a19b7699c7a9e2b663149ea31bccb67189e68c4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487819"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="754de-102">CreateIDispatchSTAForwarder 函数 （WPF 非托管 API 参考）</span><span class="sxs-lookup"><span data-stu-id="754de-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="754de-103">此 API 支持 Windows Presentation Foundation (WPF) 基础结构，不应在代码中直接使用。</span><span class="sxs-lookup"><span data-stu-id="754de-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="754de-104">Windows Presentation Foundation (WPF) 基础结构使用的线程和 windows 管理。</span><span class="sxs-lookup"><span data-stu-id="754de-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="754de-105">语法</span><span class="sxs-lookup"><span data-stu-id="754de-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="754de-106">参数</span><span class="sxs-lookup"><span data-stu-id="754de-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="754de-107">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="754de-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="754de-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="754de-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="754de-109">一个指向`IDispatch`接口。</span><span class="sxs-lookup"><span data-stu-id="754de-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="754de-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="754de-110">ppForwarder</span></span>  
 <span data-ttu-id="754de-111">指向的地址的指针`IDispatch`接口。</span><span class="sxs-lookup"><span data-stu-id="754de-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="754de-112">要求</span><span class="sxs-lookup"><span data-stu-id="754de-112">Requirements</span></span>  
 <span data-ttu-id="754de-113">**平台：** 请参阅[.NET Framework 系统需求](../../get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="754de-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="754de-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="754de-114">**DLL:**</span></span>  
  
 <span data-ttu-id="754de-115">在.NET Framework 3.0 和 3.5:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="754de-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="754de-116">在.NET Framework 4 及更高版本：PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="754de-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="754de-117">**.NET framework 版本：** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="754de-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="754de-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="754de-118">See also</span></span>
- [<span data-ttu-id="754de-119">WPF 非托管 API 参考</span><span class="sxs-lookup"><span data-stu-id="754de-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
