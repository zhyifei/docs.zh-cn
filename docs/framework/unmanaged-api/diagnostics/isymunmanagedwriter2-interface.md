---
title: ISymUnmanagedWriter2 接口
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter2
helpviewer_keywords:
- ISymUnmanagedWriter2 interface [.NET Framework debugging]
ms.assetid: 8e78faa4-cf43-44fb-a91d-94d6df692a25
topic_type:
- apiref
ms.openlocfilehash: c7f0235aa7096a790a0fd956081e330c8fdad9fe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438251"
---
# <a name="isymunmanagedwriter2-interface"></a><span data-ttu-id="04261-102">ISymUnmanagedWriter2 接口</span><span class="sxs-lookup"><span data-stu-id="04261-102">ISymUnmanagedWriter2 Interface</span></span>
<span data-ttu-id="04261-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span><span class="sxs-lookup"><span data-stu-id="04261-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span> <span data-ttu-id="04261-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span><span class="sxs-lookup"><span data-stu-id="04261-104">This interface extends the [ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04261-105">方法</span><span class="sxs-lookup"><span data-stu-id="04261-105">Methods</span></span>  
  
|<span data-ttu-id="04261-106">方法</span><span class="sxs-lookup"><span data-stu-id="04261-106">Method</span></span>|<span data-ttu-id="04261-107">描述</span><span class="sxs-lookup"><span data-stu-id="04261-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04261-108">DefineConstant2 方法</span><span class="sxs-lookup"><span data-stu-id="04261-108">DefineConstant2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineconstant2-method.md)|<span data-ttu-id="04261-109">Defines a name for a constant value.</span><span class="sxs-lookup"><span data-stu-id="04261-109">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="04261-110">DefineGlobalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="04261-110">DefineGlobalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-defineglobalvariable2-method.md)|<span data-ttu-id="04261-111">Defines a single global variable.</span><span class="sxs-lookup"><span data-stu-id="04261-111">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="04261-112">DefineLocalVariable2 方法</span><span class="sxs-lookup"><span data-stu-id="04261-112">DefineLocalVariable2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)|<span data-ttu-id="04261-113">在当前词法范围内定义单个变量。</span><span class="sxs-lookup"><span data-stu-id="04261-113">Defines a single variable in the current lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04261-114">要求</span><span class="sxs-lookup"><span data-stu-id="04261-114">Requirements</span></span>  
 <span data-ttu-id="04261-115">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="04261-115">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04261-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="04261-116">See also</span></span>

- [<span data-ttu-id="04261-117">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="04261-117">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="04261-118">ISymUnmanagedWriter 接口</span><span class="sxs-lookup"><span data-stu-id="04261-118">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)
- [<span data-ttu-id="04261-119">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="04261-119">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
