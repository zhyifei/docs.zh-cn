---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 923c85a9dff11753a338fcfd3673d3590fca607a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940122"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="48c00-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="48c00-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="48c00-103">设置的 IL 偏移量的编译器生成 catch 处理程序包装异步方法。</span><span class="sxs-lookup"><span data-stu-id="48c00-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="48c00-104">生成 catch 的 IL 偏移量由调试器用于 catch 处理，就好像非用户代码即使它可能会出现在用户代码方法。</span><span class="sxs-lookup"><span data-stu-id="48c00-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="48c00-105">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="48c00-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48c00-106">语法</span><span class="sxs-lookup"><span data-stu-id="48c00-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48c00-107">参数</span><span class="sxs-lookup"><span data-stu-id="48c00-107">Parameters</span></span>  
  
|<span data-ttu-id="48c00-108">参数</span><span class="sxs-lookup"><span data-stu-id="48c00-108">Parameter</span></span>|<span data-ttu-id="48c00-109">描述</span><span class="sxs-lookup"><span data-stu-id="48c00-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="48c00-110">返回值</span><span class="sxs-lookup"><span data-stu-id="48c00-110">Return Value</span></span>  
 <span data-ttu-id="48c00-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="48c00-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48c00-112">要求</span><span class="sxs-lookup"><span data-stu-id="48c00-112">Requirements</span></span>  
 <span data-ttu-id="48c00-113">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="48c00-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48c00-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="48c00-114">See also</span></span>

- [<span data-ttu-id="48c00-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="48c00-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
