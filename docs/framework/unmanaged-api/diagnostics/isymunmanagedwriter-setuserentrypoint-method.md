---
title: "ISymUnmanagedWriter::SetUserEntryPoint 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.SetUserEntryPoint
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::SetUserEntryPoint
helpviewer_keywords:
- ISymUnmanagedWriter::SetUserEntryPoint method [.NET Framework debugging]
- SetUserEntryPoint method [.NET Framework debugging]
ms.assetid: d4dcc575-3ac8-4453-9be1-2b24f47363d7
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be7f348237fdcf0a136d34ce3b6b8548c16d5547
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="de430-102">ISymUnmanagedWriter::SetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="de430-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="de430-103">指定是为此模块的入口点的用户定义的方法。</span><span class="sxs-lookup"><span data-stu-id="de430-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="de430-104">例如，此入口点可能是用户的主要方法而不是之前 main 编译器生成的存根。</span><span class="sxs-lookup"><span data-stu-id="de430-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de430-105">语法</span><span class="sxs-lookup"><span data-stu-id="de430-105">Syntax</span></span>  
  
```  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="de430-106">参数</span><span class="sxs-lookup"><span data-stu-id="de430-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="de430-107">[in]用户输入的方法的元数据标记点。</span><span class="sxs-lookup"><span data-stu-id="de430-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="de430-108">返回值</span><span class="sxs-lookup"><span data-stu-id="de430-108">Return Value</span></span>  
 <span data-ttu-id="de430-109">如果该方法成功; 则为 S_OK否则为 E_FAIL 或某些其他错误代码。</span><span class="sxs-lookup"><span data-stu-id="de430-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de430-110">要求</span><span class="sxs-lookup"><span data-stu-id="de430-110">Requirements</span></span>  
 <span data-ttu-id="de430-111">**标头：** CorSym.idl、 CorSym.h</span><span class="sxs-lookup"><span data-stu-id="de430-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de430-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de430-112">See Also</span></span>  
 [<span data-ttu-id="de430-113">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="de430-113">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
