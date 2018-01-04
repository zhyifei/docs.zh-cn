---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 691a46e20339b659b5df3136d4dca6c03a69d3d8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="fd897-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="fd897-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="fd897-103">设置启动异步操作的开始方法。</span><span class="sxs-lookup"><span data-stu-id="fd897-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd897-104">语法</span><span class="sxs-lookup"><span data-stu-id="fd897-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd897-105">参数</span><span class="sxs-lookup"><span data-stu-id="fd897-105">Parameters</span></span>  
  
|<span data-ttu-id="fd897-106">参数</span><span class="sxs-lookup"><span data-stu-id="fd897-106">Parameter</span></span>|<span data-ttu-id="fd897-107">描述</span><span class="sxs-lookup"><span data-stu-id="fd897-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="fd897-108">返回值</span><span class="sxs-lookup"><span data-stu-id="fd897-108">Return Value</span></span>  
 <span data-ttu-id="fd897-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="fd897-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd897-110">惠?</span><span class="sxs-lookup"><span data-stu-id="fd897-110">Requirements</span></span>  
 <span data-ttu-id="fd897-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fd897-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd897-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="fd897-112">See Also</span></span>  
 [<span data-ttu-id="fd897-113">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="fd897-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
