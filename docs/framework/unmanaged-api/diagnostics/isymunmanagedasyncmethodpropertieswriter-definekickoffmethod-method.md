---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a476d92486d7f2523dfbcc8b25e9c11e26c55f2d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425610"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="3488b-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="3488b-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="3488b-103">设置启动异步操作的开始方法。</span><span class="sxs-lookup"><span data-stu-id="3488b-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3488b-104">语法</span><span class="sxs-lookup"><span data-stu-id="3488b-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3488b-105">参数</span><span class="sxs-lookup"><span data-stu-id="3488b-105">Parameters</span></span>  
  
|<span data-ttu-id="3488b-106">参数</span><span class="sxs-lookup"><span data-stu-id="3488b-106">Parameter</span></span>|<span data-ttu-id="3488b-107">描述</span><span class="sxs-lookup"><span data-stu-id="3488b-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="3488b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="3488b-108">Return Value</span></span>  
 <span data-ttu-id="3488b-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="3488b-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3488b-110">要求</span><span class="sxs-lookup"><span data-stu-id="3488b-110">Requirements</span></span>  
 <span data-ttu-id="3488b-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="3488b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3488b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="3488b-112">See Also</span></span>  
 [<span data-ttu-id="3488b-113">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="3488b-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
