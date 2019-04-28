---
title: ISymUnmanagedWriter::SetUserEntryPoint 方法
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.SetUserEntryPoint
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d14d542a8c1d8adeaf56dc1564e8e10121cd4064
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61650721"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="6781b-102">ISymUnmanagedWriter::SetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="6781b-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="6781b-103">指定是此模块的入口点的用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="6781b-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="6781b-104">例如，此入口点可能是用户的主要方法，而不是之前 main 编译器生成的存根。</span><span class="sxs-lookup"><span data-stu-id="6781b-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6781b-105">语法</span><span class="sxs-lookup"><span data-stu-id="6781b-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6781b-106">参数</span><span class="sxs-lookup"><span data-stu-id="6781b-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="6781b-107">[in]就是用户条目的方法的元数据标记点。</span><span class="sxs-lookup"><span data-stu-id="6781b-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6781b-108">返回值</span><span class="sxs-lookup"><span data-stu-id="6781b-108">Return Value</span></span>  
 <span data-ttu-id="6781b-109">如果方法成功，则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="6781b-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6781b-110">要求</span><span class="sxs-lookup"><span data-stu-id="6781b-110">Requirements</span></span>  
 <span data-ttu-id="6781b-111">**标头：** CorSym.idl CorSym.h</span><span class="sxs-lookup"><span data-stu-id="6781b-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6781b-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="6781b-112">See also</span></span>

- [<span data-ttu-id="6781b-113">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="6781b-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
