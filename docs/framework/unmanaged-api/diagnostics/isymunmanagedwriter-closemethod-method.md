---
title: "ISymUnmanagedWriter::CloseMethod 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ISymUnmanagedWriter.CloseMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::CloseMethod
helpviewer_keywords:
- ISymUnmanagedWriter::CloseMethod method [.NET Framework debugging]
- CloseMethod method [.NET Framework debugging]
ms.assetid: b8025e04-f0e5-40c8-849c-8cd51323420e
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 21c4cdd42613f5e8b60c39426b4f169a034ce7a6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriterclosemethod-method"></a><span data-ttu-id="fb4f2-102">ISymUnmanagedWriter::CloseMethod 方法</span><span class="sxs-lookup"><span data-stu-id="fb4f2-102">ISymUnmanagedWriter::CloseMethod Method</span></span>
<span data-ttu-id="fb4f2-103">关闭当前方法。</span><span class="sxs-lookup"><span data-stu-id="fb4f2-103">Closes the current method.</span></span> <span data-ttu-id="fb4f2-104">一旦关闭方法，可以在其中定义没有更多的符号。</span><span class="sxs-lookup"><span data-stu-id="fb4f2-104">Once a method is closed, no more symbols can be defined within it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb4f2-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb4f2-105">Syntax</span></span>  
  
```  
HRESULT CloseMethod();  
```  
  
## <a name="return-value"></a><span data-ttu-id="fb4f2-106">返回值</span><span class="sxs-lookup"><span data-stu-id="fb4f2-106">Return Value</span></span>  
 <span data-ttu-id="fb4f2-107">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="fb4f2-107">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb4f2-108">惠?</span><span class="sxs-lookup"><span data-stu-id="fb4f2-108">Requirements</span></span>  
 <span data-ttu-id="fb4f2-109">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="fb4f2-109">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb4f2-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="fb4f2-110">See Also</span></span>  
 [<span data-ttu-id="fb4f2-111">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="fb4f2-111">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [<span data-ttu-id="fb4f2-112">OpenMethod 方法</span><span class="sxs-lookup"><span data-stu-id="fb4f2-112">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)
