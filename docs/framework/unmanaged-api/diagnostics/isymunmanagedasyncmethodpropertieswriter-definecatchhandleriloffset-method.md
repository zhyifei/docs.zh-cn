---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce462c4e7e9c8fb11ee74a91f3ece2465a44a834
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33425426"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="0f7b9-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="0f7b9-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="0f7b9-103">设置 IL 偏移量的编译器生成 catch 处理程序包装异步方法。</span><span class="sxs-lookup"><span data-stu-id="0f7b9-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="0f7b9-104">生成 catch 的 IL 偏移量由调试器用于处理该 catch，就像它是非用户代码，即使它可能会出现在用户代码方法。</span><span class="sxs-lookup"><span data-stu-id="0f7b9-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="0f7b9-105">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="0f7b9-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f7b9-106">语法</span><span class="sxs-lookup"><span data-stu-id="0f7b9-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f7b9-107">参数</span><span class="sxs-lookup"><span data-stu-id="0f7b9-107">Parameters</span></span>  
  
|<span data-ttu-id="0f7b9-108">参数</span><span class="sxs-lookup"><span data-stu-id="0f7b9-108">Parameter</span></span>|<span data-ttu-id="0f7b9-109">描述</span><span class="sxs-lookup"><span data-stu-id="0f7b9-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="0f7b9-110">返回值</span><span class="sxs-lookup"><span data-stu-id="0f7b9-110">Return Value</span></span>  
 <span data-ttu-id="0f7b9-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="0f7b9-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f7b9-112">要求</span><span class="sxs-lookup"><span data-stu-id="0f7b9-112">Requirements</span></span>  
 <span data-ttu-id="0f7b9-113">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="0f7b9-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f7b9-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f7b9-114">See Also</span></span>  
 [<span data-ttu-id="0f7b9-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="0f7b9-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-interface.md)
