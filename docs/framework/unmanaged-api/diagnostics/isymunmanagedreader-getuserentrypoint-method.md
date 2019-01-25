---
title: ISymUnmanagedReader::GetUserEntryPoint 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader.GetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader::GetUserEntryPoint
helpviewer_keywords:
- GetUserEntryPoint method [.NET Framework debugging]
- ISymUnmanagedReader::GetUserEntryPoint method [.NET Framework debugging]
ms.assetid: 3fd3a34c-d176-46e9-9996-fb1646cff9b0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a8519577bb2b9d3ff8fa2138ba007d04d9fde159
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54730147"
---
# <a name="isymunmanagedreadergetuserentrypoint-method"></a><span data-ttu-id="a3a44-102">ISymUnmanagedReader::GetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="a3a44-102">ISymUnmanagedReader::GetUserEntryPoint Method</span></span>
<span data-ttu-id="a3a44-103">如果有，请返回被指定为该模块的用户入口点的方法。</span><span class="sxs-lookup"><span data-stu-id="a3a44-103">Returns the method that was specified as the user entry point for the module, if any.</span></span> <span data-ttu-id="a3a44-104">例如，此方法可能是用户的主要方法而不是编译器生成存根 （stub） 之前的主要方法。</span><span class="sxs-lookup"><span data-stu-id="a3a44-104">For example, this method could be the user's main method rather than compiler-generated stubs before the main method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3a44-105">语法</span><span class="sxs-lookup"><span data-stu-id="a3a44-105">Syntax</span></span>  
  
```  
HRESULT GetUserEntryPoint (  
    [out, retval]  mdMethodDef  *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a3a44-106">参数</span><span class="sxs-lookup"><span data-stu-id="a3a44-106">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="a3a44-107">[out]指向一个变量来接收的入口点的指针。</span><span class="sxs-lookup"><span data-stu-id="a3a44-107">[out] A pointer to a variable that receives the entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a3a44-108">返回值</span><span class="sxs-lookup"><span data-stu-id="a3a44-108">Return Value</span></span>  
 <span data-ttu-id="a3a44-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="a3a44-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3a44-110">要求</span><span class="sxs-lookup"><span data-stu-id="a3a44-110">Requirements</span></span>  
 <span data-ttu-id="a3a44-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="a3a44-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3a44-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="a3a44-112">See also</span></span>
- [<span data-ttu-id="a3a44-113">ISymUnmanagedReader 接口</span><span class="sxs-lookup"><span data-stu-id="a3a44-113">ISymUnmanagedReader Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md)
