---
title: ISymUnmanagedWriter4 接口
ms.date: 03/30/2017
ms.assetid: 4af5e8c0-987d-405e-b934-8b9e70fcae6e
ms.openlocfilehash: a656777461c50b5a1593917278eb54abda982dc2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134569"
---
# <a name="isymunmanagedwriter4-interface"></a><span data-ttu-id="bb5d7-102">ISymUnmanagedWriter4 接口</span><span class="sxs-lookup"><span data-stu-id="bb5d7-102">ISymUnmanagedWriter4 Interface</span></span>
<span data-ttu-id="bb5d7-103">ISymUnmanagedWriter4 接口。</span><span class="sxs-lookup"><span data-stu-id="bb5d7-103">ISymUnmanagedWriter4 interface.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb5d7-104">语法</span><span class="sxs-lookup"><span data-stu-id="bb5d7-104">Syntax</span></span>  
  
```idl  
[object,uuid(BC7E3F53-F458-4C23-9DBD-A189E6E96594),pointer_default(unique)]interface ISymUnmanagedWriter4 : ISymUnmanagedWriter3  
```  
  
## <a name="methods"></a><span data-ttu-id="bb5d7-105">方法</span><span class="sxs-lookup"><span data-stu-id="bb5d7-105">Methods</span></span>  
 <span data-ttu-id="bb5d7-106">此接口包含下列方法：</span><span class="sxs-lookup"><span data-stu-id="bb5d7-106">This interface contains the following methods:</span></span>  
  
|<span data-ttu-id="bb5d7-107">方法</span><span class="sxs-lookup"><span data-stu-id="bb5d7-107">Method</span></span>|<span data-ttu-id="bb5d7-108">描述</span><span class="sxs-lookup"><span data-stu-id="bb5d7-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="bb5d7-109">GetDebugInfoWithPadding 方法</span><span class="sxs-lookup"><span data-stu-id="bb5d7-109">GetDebugInfoWithPadding Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter4-getdebuginfowithpadding-method.md)|<span data-ttu-id="bb5d7-110">与[GetDebugInfo 方法](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)相同，不同之处在于，在终止 null 字符后使用零填充路径字符串，使字符串数据成为固定大小的 `MAX_PATH`。</span><span class="sxs-lookup"><span data-stu-id="bb5d7-110">Functions the same as [GetDebugInfo Method](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md) except that the path string is padded with zeros following the terminating null character to make the string data a fixed size of `MAX_PATH`.</span></span> <span data-ttu-id="bb5d7-111">仅当路径字符串长度本身小于 `MAX_PATH`时才会提供填充。</span><span class="sxs-lookup"><span data-stu-id="bb5d7-111">Padding is only given if the path string length itself is less than `MAX_PATH`.</span></span><br /><br /> <span data-ttu-id="bb5d7-112">这样可以更轻松地编写不同 PE 文件的工具。</span><span class="sxs-lookup"><span data-stu-id="bb5d7-112">This makes it easier to write tools that difference PE files.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bb5d7-113">要求</span><span class="sxs-lookup"><span data-stu-id="bb5d7-113">Requirements</span></span>  
 <span data-ttu-id="bb5d7-114">**标头：** CorSym，CorSym</span><span class="sxs-lookup"><span data-stu-id="bb5d7-114">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5d7-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bb5d7-115">See also</span></span>

- [<span data-ttu-id="bb5d7-116">诊断符号存储区接口</span><span class="sxs-lookup"><span data-stu-id="bb5d7-116">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
- [<span data-ttu-id="bb5d7-117">ISymUnmanagedWriter3 接口</span><span class="sxs-lookup"><span data-stu-id="bb5d7-117">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)
