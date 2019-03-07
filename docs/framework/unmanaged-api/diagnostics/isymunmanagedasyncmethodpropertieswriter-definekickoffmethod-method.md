---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 24560ed4b0bb7ca04d5859280baa594fbb2e4097
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57473457"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="457fa-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="457fa-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="457fa-103">设置启动异步操作的开始方法。</span><span class="sxs-lookup"><span data-stu-id="457fa-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="457fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="457fa-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="457fa-105">参数</span><span class="sxs-lookup"><span data-stu-id="457fa-105">Parameters</span></span>  
  
|<span data-ttu-id="457fa-106">参数</span><span class="sxs-lookup"><span data-stu-id="457fa-106">Parameter</span></span>|<span data-ttu-id="457fa-107">描述</span><span class="sxs-lookup"><span data-stu-id="457fa-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="457fa-108">返回值</span><span class="sxs-lookup"><span data-stu-id="457fa-108">Return Value</span></span>  
 <span data-ttu-id="457fa-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="457fa-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="457fa-110">要求</span><span class="sxs-lookup"><span data-stu-id="457fa-110">Requirements</span></span>  
 <span data-ttu-id="457fa-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="457fa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="457fa-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="457fa-112">See also</span></span>
- [<span data-ttu-id="457fa-113">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="457fa-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
