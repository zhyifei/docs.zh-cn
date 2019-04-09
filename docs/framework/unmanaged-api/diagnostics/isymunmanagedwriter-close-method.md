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
ms.openlocfilehash: 4d3497d3167715d3e8a04f10a6687260949e4a36
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104697"
---
# <a name="isymunmanagedwriterclose-method"></a><span data-ttu-id="47ecd-102">ISymUnmanagedWriter::Close 方法</span><span class="sxs-lookup"><span data-stu-id="47ecd-102">ISymUnmanagedWriter::Close Method</span></span>
<span data-ttu-id="47ecd-103">将符号提交到符号存储区后关闭的符号编写器。</span><span class="sxs-lookup"><span data-stu-id="47ecd-103">Closes the symbol writer after committing the symbols to the symbol store.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ecd-104">语法</span><span class="sxs-lookup"><span data-stu-id="47ecd-104">Syntax</span></span>  
  
```  
HRESULT Close();  
```  
  
## <a name="return-value"></a><span data-ttu-id="47ecd-105">返回值</span><span class="sxs-lookup"><span data-stu-id="47ecd-105">Return Value</span></span>  
 <span data-ttu-id="47ecd-106">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="47ecd-106">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47ecd-107">备注</span><span class="sxs-lookup"><span data-stu-id="47ecd-107">Remarks</span></span>  
 <span data-ttu-id="47ecd-108">此调用后，符号编写器将变为无效有关进一步的更新。</span><span class="sxs-lookup"><span data-stu-id="47ecd-108">After this call, the symbol writer becomes invalid for further updates.</span></span> <span data-ttu-id="47ecd-109">若要关闭的符号编写器无需处理符号，请使用[isymunmanagedwriter:: Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)方法相反。</span><span class="sxs-lookup"><span data-stu-id="47ecd-109">To close the symbol writer without committing the symbols, use the [ISymUnmanagedWriter::Abort](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md) method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47ecd-110">要求</span><span class="sxs-lookup"><span data-stu-id="47ecd-110">Requirements</span></span>  
 <span data-ttu-id="47ecd-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="47ecd-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ecd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="47ecd-112">See also</span></span>

- [<span data-ttu-id="47ecd-113">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="47ecd-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
