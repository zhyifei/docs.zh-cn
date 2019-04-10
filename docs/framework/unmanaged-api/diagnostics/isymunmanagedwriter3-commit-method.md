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
ms.openlocfilehash: f531b96211a1dd6072d62937b9f93fc17f105d4d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59149040"
---
# <a name="isymunmanagedwriter3commit-method"></a><span data-ttu-id="13af4-102">ISymUnmanagedWriter3::Commit 方法</span><span class="sxs-lookup"><span data-stu-id="13af4-102">ISymUnmanagedWriter3::Commit Method</span></span>
<span data-ttu-id="13af4-103">提交所做的更改写入到流的到目前为止。</span><span class="sxs-lookup"><span data-stu-id="13af4-103">Commits the changes written so far to the stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13af4-104">语法</span><span class="sxs-lookup"><span data-stu-id="13af4-104">Syntax</span></span>  
  
```  
HRESULT Commit();  
```  
  
## <a name="return-value"></a><span data-ttu-id="13af4-105">返回值</span><span class="sxs-lookup"><span data-stu-id="13af4-105">Return Value</span></span>  
 <span data-ttu-id="13af4-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="13af4-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13af4-107">要求</span><span class="sxs-lookup"><span data-stu-id="13af4-107">Requirements</span></span>  
 <span data-ttu-id="13af4-108">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="13af4-108">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13af4-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="13af4-109">See also</span></span>

- [<span data-ttu-id="13af4-110">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="13af4-110">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
