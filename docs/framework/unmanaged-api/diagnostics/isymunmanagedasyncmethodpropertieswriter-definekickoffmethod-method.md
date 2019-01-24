---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38b4564aeb3c8ed4674e755e5691bb0a9d417bca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624149"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="809e8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="809e8-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="809e8-103">设置启动异步操作的开始方法。</span><span class="sxs-lookup"><span data-stu-id="809e8-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="809e8-104">语法</span><span class="sxs-lookup"><span data-stu-id="809e8-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="809e8-105">参数</span><span class="sxs-lookup"><span data-stu-id="809e8-105">Parameters</span></span>  
  
|<span data-ttu-id="809e8-106">参数</span><span class="sxs-lookup"><span data-stu-id="809e8-106">Parameter</span></span>|<span data-ttu-id="809e8-107">描述</span><span class="sxs-lookup"><span data-stu-id="809e8-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="809e8-108">返回值</span><span class="sxs-lookup"><span data-stu-id="809e8-108">Return Value</span></span>  
 <span data-ttu-id="809e8-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="809e8-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="809e8-110">要求</span><span class="sxs-lookup"><span data-stu-id="809e8-110">Requirements</span></span>  
 <span data-ttu-id="809e8-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="809e8-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="809e8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="809e8-112">See also</span></span>
- [<span data-ttu-id="809e8-113">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="809e8-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
