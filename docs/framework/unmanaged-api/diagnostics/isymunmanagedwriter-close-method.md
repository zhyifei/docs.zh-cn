---
title: ISymUnmanagedWriter::Close 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.Close
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::Close
helpviewer_keywords:
- Close method, ISymUnmanagedWriter interface [.NET Framework debugging]
- ISymUnmanagedWriter::Close method [.NET Framework debugging]
ms.assetid: 4cce59e1-80b9-4fc4-b3aa-126f1c5876bc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 780c19acd3d6980c0fb3e31d01e569a61fd04d6d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54647304"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="b40fa-102">ISymUnmanagedWriter::Close 方法</span><span class="sxs-lookup"><span data-stu-id="b40fa-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="b40fa-103">将符号提交到符号存储区后关闭的符号编写器。</span><span class="sxs-lookup"><span data-stu-id="b40fa-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b40fa-104">语法</span><span class="sxs-lookup"><span data-stu-id="b40fa-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="b40fa-105">返回值</span><span class="sxs-lookup"><span data-stu-id="b40fa-105">Return Value</span></span>  
 <span data-ttu-id="b40fa-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="b40fa-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b40fa-107">备注</span><span class="sxs-lookup"><span data-stu-id="b40fa-107">Remarks</span></span>  
 <span data-ttu-id="b40fa-108">此调用后，符号编写器将变为无效有关进一步的更新。</span><span class="sxs-lookup"><span data-stu-id="b40fa-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="b40fa-109">若要关闭的符号编写器无需处理符号，请使用[isymunmanagedwriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="b40fa-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b40fa-110">要求</span><span class="sxs-lookup"><span data-stu-id="b40fa-110">Requirements</span></span>  
 <span data-ttu-id="b40fa-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="b40fa-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b40fa-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b40fa-112">See also</span></span>
- [<span data-ttu-id="b40fa-113">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="b40fa-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
