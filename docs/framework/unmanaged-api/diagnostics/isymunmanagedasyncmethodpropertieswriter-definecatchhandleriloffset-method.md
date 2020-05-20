---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法
ms.date: 03/30/2017
ms.assetid: 92af7896-2201-408d-8b1b-23e28001eeac
ms.openlocfilehash: 58dde2fcce3f4bf578907171e5b575c30c678cfc
ms.sourcegitcommit: 7b1497c1927cb449cefd313bc5126ae37df30746
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "83441768"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinecatchhandleriloffset-method"></a><span data-ttu-id="5e00d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset 方法</span><span class="sxs-lookup"><span data-stu-id="5e00d-102">ISymUnmanagedAsyncMethodPropertiesWriter::DefineCatchHandlerILOffset Method</span></span>
<span data-ttu-id="5e00d-103">设置编译器生成的用于包装异步方法的 catch 处理程序的 IL 偏移量。</span><span class="sxs-lookup"><span data-stu-id="5e00d-103">Sets the IL offset for the compiler-generated catch handler that wraps an async method.</span></span>  
  
 <span data-ttu-id="5e00d-104">调试器使用生成的 catch 的 IL 偏移量来处理 catch，就像它是非用户代码，即使它可能出现在用户代码方法中也是如此。</span><span class="sxs-lookup"><span data-stu-id="5e00d-104">The IL offset of the generated catch is used by the debugger to handle the catch as if it were non-user code even though it might occur in a user code method.</span></span> <span data-ttu-id="5e00d-105">具体而言，它用于响应**CatchHandlerFound**异常事件。</span><span class="sxs-lookup"><span data-stu-id="5e00d-105">In particular, it is used in response to a **CatchHandlerFound** exception event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e00d-106">语法</span><span class="sxs-lookup"><span data-stu-id="5e00d-106">Syntax</span></span>  
  
```idl  
HRESULT DefineCatchHandlerILOffset(    [in] ULONG32 catchHandlerOffset);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e00d-107">参数</span><span class="sxs-lookup"><span data-stu-id="5e00d-107">Parameters</span></span>  
  
|<span data-ttu-id="5e00d-108">参数</span><span class="sxs-lookup"><span data-stu-id="5e00d-108">Parameter</span></span>|<span data-ttu-id="5e00d-109">说明</span><span class="sxs-lookup"><span data-stu-id="5e00d-109">Description</span></span>|  
|---------------|-----------------|  
|`catchHandlerOffset`||  
  
## <a name="return-value"></a><span data-ttu-id="5e00d-110">返回值</span><span class="sxs-lookup"><span data-stu-id="5e00d-110">Return Value</span></span>  
 <span data-ttu-id="5e00d-111">返回 `HRESULT`。</span><span class="sxs-lookup"><span data-stu-id="5e00d-111">Returns `HRESULT`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e00d-112">要求</span><span class="sxs-lookup"><span data-stu-id="5e00d-112">Requirements</span></span>  
 <span data-ttu-id="5e00d-113">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="5e00d-113">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e00d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e00d-114">See also</span></span>

- [<span data-ttu-id="5e00d-115">ISymUnmanagedAsyncMethodPropertiesWriter 接口</span><span class="sxs-lookup"><span data-stu-id="5e00d-115">ISymUnmanagedAsyncMethodPropertiesWriter Interface</span></span>](isymunmanagedasyncmethodpropertieswriter-interface.md)
