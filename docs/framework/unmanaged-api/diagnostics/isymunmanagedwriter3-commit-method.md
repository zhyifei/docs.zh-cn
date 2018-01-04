---
title: "ISymUnmanagedWriter3::Commit 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter3.Commit
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 10c36f1972e3c55b22a472c81ec8499fcfde3405
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="269de-102">ISymUnmanagedWriter3::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="269de-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="269de-103">提交到目前为止写入到流的更改。</span><span class="sxs-lookup"><span data-stu-id="269de-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="269de-104">语法</span><span class="sxs-lookup"><span data-stu-id="269de-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="269de-105">返回值</span><span class="sxs-lookup"><span data-stu-id="269de-105">Return Value</span></span>  
 <span data-ttu-id="269de-106">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="269de-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="269de-107">惠?</span><span class="sxs-lookup"><span data-stu-id="269de-107">Requirements</span></span>  
 <span data-ttu-id="269de-108">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="269de-108">**Header:** CorSym.idl , CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="269de-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="269de-109">See Also</span></span>  
 [<span data-ttu-id="269de-110">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="269de-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
