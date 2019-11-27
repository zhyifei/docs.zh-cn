---
title: GetScope 方法
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: 078168ae8860f18ff6f811dcc972e3eb3c857e1d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447207"
---
# <a name="getscope-method"></a><span data-ttu-id="9e295-102">GetScope 方法</span><span class="sxs-lookup"><span data-stu-id="9e295-102">GetScope Method</span></span>
<span data-ttu-id="9e295-103">获取导入范围。</span><span class="sxs-lookup"><span data-stu-id="9e295-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e295-104">语法</span><span class="sxs-lookup"><span data-stu-id="9e295-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e295-105">参数</span><span class="sxs-lookup"><span data-stu-id="9e295-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9e295-106">要导入到的程序集的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9e295-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9e295-107">要从中导入的文件的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="9e295-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9e295-108">要导入的从零开始的范围。</span><span class="sxs-lookup"><span data-stu-id="9e295-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9e295-109">接收作用域的[IMetaDataImport 接口](../metadata/imetadataimport-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="9e295-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9e295-110">返回值</span><span class="sxs-lookup"><span data-stu-id="9e295-110">Return Value</span></span>  
 <span data-ttu-id="9e295-111">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="9e295-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e295-112">要求</span><span class="sxs-lookup"><span data-stu-id="9e295-112">Requirements</span></span>  
 <span data-ttu-id="9e295-113">需要 alink</span><span class="sxs-lookup"><span data-stu-id="9e295-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e295-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e295-114">See also</span></span>

- [<span data-ttu-id="9e295-115">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="9e295-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9e295-116">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="9e295-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9e295-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="9e295-117">ALink API</span></span>](index.md)
