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
ms.openlocfilehash: 8b51a9dc3a968c6bd2f5f9b149f13f88dc6a1e05
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83614742"
---
# <a name="isymunmanagedwritersetuserentrypoint-method"></a><span data-ttu-id="55371-102">ISymUnmanagedWriter::SetUserEntryPoint 方法</span><span class="sxs-lookup"><span data-stu-id="55371-102">ISymUnmanagedWriter::SetUserEntryPoint Method</span></span>
<span data-ttu-id="55371-103">指定用户定义的方法，该方法是此模块的入口点。</span><span class="sxs-lookup"><span data-stu-id="55371-103">Specifies the user-defined method that is the entry point for this module.</span></span> <span data-ttu-id="55371-104">例如，在 main 之前，此入口点可能是用户的 main 方法，而不是编译器生成的存根。</span><span class="sxs-lookup"><span data-stu-id="55371-104">For example, this entry point could be the user's main method instead of compiler-generated stubs before main.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55371-105">语法</span><span class="sxs-lookup"><span data-stu-id="55371-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUserEntryPoint(  
    [in] mdMethodDef entryMethod);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55371-106">参数</span><span class="sxs-lookup"><span data-stu-id="55371-106">Parameters</span></span>  
 `entryMethod`  
 <span data-ttu-id="55371-107">中方法的元数据标记，它是用户入口点。</span><span class="sxs-lookup"><span data-stu-id="55371-107">[in] The metadata token for the method that is the user entry point.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55371-108">返回值</span><span class="sxs-lookup"><span data-stu-id="55371-108">Return Value</span></span>  
 <span data-ttu-id="55371-109">如果该方法成功，则 S_OK;否则，E_FAIL 或其他一些错误代码。</span><span class="sxs-lookup"><span data-stu-id="55371-109">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55371-110">要求</span><span class="sxs-lookup"><span data-stu-id="55371-110">Requirements</span></span>  
 <span data-ttu-id="55371-111">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="55371-111">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55371-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="55371-112">See also</span></span>

- [<span data-ttu-id="55371-113">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="55371-113">ISymUnmanagedWriter Interface</span></span>](isymunmanagedwriter-interface.md)
