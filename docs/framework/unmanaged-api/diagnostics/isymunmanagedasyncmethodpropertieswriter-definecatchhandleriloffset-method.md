---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: b108c8c87d3afdbfacb569ab501274e5c45c2e2e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129178"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="2e2f0-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="2e2f0-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="2e2f0-103">设置编译器生成的用于包装异步方法的 catch 处理程序的 IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="2e2f0-104">调试器使用生成的 catch 的 IL 偏移量来处理 catch，就像它是非用户代码，即使它可能出现在用户代码方法中也是如此。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="2e2f0-105">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e2f0-106">语法</span><span class="sxs-lookup"><span data-stu-id="2e2f0-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e2f0-107">参数</span><span class="sxs-lookup"><span data-stu-id="2e2f0-107">Parameters</span></span>  
  
|<span data-ttu-id="2e2f0-108">参数</span><span class="sxs-lookup"><span data-stu-id="2e2f0-108">Parameter</span></span>|<span data-ttu-id="2e2f0-109">描述</span><span class="sxs-lookup"><span data-stu-id="2e2f0-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="2e2f0-110">返回值</span><span class="sxs-lookup"><span data-stu-id="2e2f0-110">Return Value</span></span>  
 <span data-ttu-id="2e2f0-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="2e2f0-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e2f0-112">要求</span><span class="sxs-lookup"><span data-stu-id="2e2f0-112">Requirements</span></span>  
 <span data-ttu-id="2e2f0-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="2e2f0-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e2f0-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e2f0-114">See also</span></span>

- [<span data-ttu-id="2e2f0-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="2e2f0-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
