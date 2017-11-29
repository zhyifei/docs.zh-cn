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
ms.openlocfilehash: 68c5d6662d8cbecca06268bd5010878c4e476f47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a><span data-ttu-id="b1c4f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod 方法</span><span class="sxs-lookup"><span data-stu-id="b1c4f-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod Method</span></span>
<span data-ttu-id="b1c4f-103">设置启动异步操作的开始方法。</span><span class="sxs-lookup"><span data-stu-id="b1c4f-103">Sets the starting method that initiates the async operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1c4f-104">语法</span><span class="sxs-lookup"><span data-stu-id="b1c4f-104">Syntax</span></span>  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1c4f-105">参数</span><span class="sxs-lookup"><span data-stu-id="b1c4f-105">Parameters</span></span>  
  
|<span data-ttu-id="b1c4f-106">参数</span><span class="sxs-lookup"><span data-stu-id="b1c4f-106">Parameter</span></span>|<span data-ttu-id="b1c4f-107">描述</span><span class="sxs-lookup"><span data-stu-id="b1c4f-107">Description</span></span>|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a><span data-ttu-id="b1c4f-108">返回值</span><span class="sxs-lookup"><span data-stu-id="b1c4f-108">Return Value</span></span>  
 <span data-ttu-id="b1c4f-109">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="b1c4f-109">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1c4f-110">要求</span><span class="sxs-lookup"><span data-stu-id="b1c4f-110">Requirements</span></span>  
 <span data-ttu-id="b1c4f-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b1c4f-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1c4f-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1c4f-112">See Also</span></span>  
 [<span data-ttu-id="b1c4f-113">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="b1c4f-113">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
