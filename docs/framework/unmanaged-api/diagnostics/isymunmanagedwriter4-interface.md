---
title: ISymUnmanagedWriter4 接口
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: eaf2e8e60d9812ab6a31fb3b9050cbaae0f1a9d7
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609464"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="c2b00-102">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="c2b00-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="c2b00-103">ISymUnmanagedWriter4 接口。</span><span class="sxs-lookup"><span data-stu-id="c2b00-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2b00-104">语法</span><span class="sxs-lookup"><span data-stu-id="c2b00-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="c2b00-105">方法</span><span class="sxs-lookup"><span data-stu-id="c2b00-105">Methods</span></span>  
 <span data-ttu-id="c2b00-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="c2b00-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="c2b00-107">方法</span><span class="sxs-lookup"><span data-stu-id="c2b00-107">Method</span></span>|<span data-ttu-id="c2b00-108">说明</span><span class="sxs-lookup"><span data-stu-id="c2b00-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c2b00-109">GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="c2b00-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="c2b00-110">与[GetDebugInfo 方法](isymunmanagedwriter-getdebuginfo-method.md)相同，不同之处在于，在终止 null 字符后使用零填充路径字符串，使字符串数据成为固定大小的字符串数据 `MAX_PATH` 。</span><span class="sxs-lookup"><span data-stu-id="c2b00-110">Functions the same as [GetDebugInfo Method](isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="c2b00-111">仅当路径字符串长度本身小于时才会提供填充 `MAX_PATH` 。</span><span class="sxs-lookup"><span data-stu-id="c2b00-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="c2b00-112">这样可以更轻松地编写不同 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="c2b00-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2b00-113">要求</span><span class="sxs-lookup"><span data-stu-id="c2b00-113">Requirements</span></span>  
 <span data-ttu-id="c2b00-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="c2b00-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2b00-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c2b00-115">See also</span></span>

- [<span data-ttu-id="c2b00-116">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="c2b00-116">Diagnostics Symbol Store Interfaces</span></span>](diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="c2b00-117">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="c2b00-117">ISymUnmanagedWriter3 Interface</span></span>](isymunmanagedwriter3-interface.md)
