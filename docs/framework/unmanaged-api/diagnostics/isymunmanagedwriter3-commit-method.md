---
title: ISymUnmanagedWriter3::Commit 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.Commit
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::Commit
helpviewer_keywords:
- Commit method, ISymUnmanagedWriter3 interface [.NET Framework debugging]
- ISymUnmanagedWriter3::Commit method [.NET Framework debugging]
ms.assetid: f6961922-46ec-4d2c-8369-85f880731f37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ef45650b30fd57fb93d0e16eac6e34079745b1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526231"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="11a57-102">ISymUnmanagedWriter3::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="11a57-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="11a57-103">提交所做的更改写入到流的到目前为止。</span><span class="sxs-lookup"><span data-stu-id="11a57-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a57-104">语法</span><span class="sxs-lookup"><span data-stu-id="11a57-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="11a57-105">返回值</span><span class="sxs-lookup"><span data-stu-id="11a57-105">Return Value</span></span>  
 <span data-ttu-id="11a57-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="11a57-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a57-107">要求</span><span class="sxs-lookup"><span data-stu-id="11a57-107">Requirements</span></span>  
 <span data-ttu-id="11a57-108">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="11a57-108">**Header:** CorSym.idl , CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a57-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="11a57-109">See also</span></span>
- [<span data-ttu-id="11a57-110">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="11a57-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
