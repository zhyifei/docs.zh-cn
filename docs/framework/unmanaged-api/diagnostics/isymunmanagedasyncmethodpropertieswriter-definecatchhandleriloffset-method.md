---
title: "ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3bae0e2dfb56883a674b282acd385ba45a25bebb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="717f3-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="717f3-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="717f3-103">设置 IL 偏移量的编译器生成 catch 处理程序包装异步方法。</span><span class="sxs-lookup"><span data-stu-id="717f3-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="717f3-104">生成 catch 的 IL 偏移量由调试器用于处理该 catch，就像它是非用户代码，即使它可能会出现在用户代码方法。</span><span class="sxs-lookup"><span data-stu-id="717f3-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="717f3-105">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="717f3-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="717f3-106">语法</span><span class="sxs-lookup"><span data-stu-id="717f3-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="717f3-107">参数</span><span class="sxs-lookup"><span data-stu-id="717f3-107">Parameters</span></span>  
  
|<span data-ttu-id="717f3-108">参数</span><span class="sxs-lookup"><span data-stu-id="717f3-108">Parameter</span></span>|<span data-ttu-id="717f3-109">描述</span><span class="sxs-lookup"><span data-stu-id="717f3-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="717f3-110">返回值</span><span class="sxs-lookup"><span data-stu-id="717f3-110">Return Value</span></span>  
 <span data-ttu-id="717f3-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="717f3-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="717f3-112">要求</span><span class="sxs-lookup"><span data-stu-id="717f3-112">Requirements</span></span>  
 <span data-ttu-id="717f3-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="717f3-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="717f3-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="717f3-114">See Also</span></span>  
 [<span data-ttu-id="717f3-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="717f3-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
