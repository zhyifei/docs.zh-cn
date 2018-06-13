---
title: EmbedResource 方法
ms.date: 03/30/2017
api_name:
- IALink.EmbedResource
- EmbedResource
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmbedResource
helpviewer_keywords:
- EmbedResource method
ms.assetid: 667bd954-6dc6-4020-a3cb-0e8224179993
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb1fc266c8451953c8b6a9c686f4a1c1951966e3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405393"
---
# <a name="embedresource-method"></a><span data-ttu-id="8fefa-102">EmbedResource 方法</span><span class="sxs-lookup"><span data-stu-id="8fefa-102">EmbedResource Method</span></span>
<span data-ttu-id="8fefa-103">声明嵌入的资源。</span><span class="sxs-lookup"><span data-stu-id="8fefa-103">Declares an embedded resource.</span></span> <span data-ttu-id="8fefa-104">此方法不会实际嵌入资源。</span><span class="sxs-lookup"><span data-stu-id="8fefa-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8fefa-105">语法</span><span class="sxs-lookup"><span data-stu-id="8fefa-105">Syntax</span></span>  
  
```  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fefa-106">参数</span><span class="sxs-lookup"><span data-stu-id="8fefa-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="8fefa-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="8fefa-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="8fefa-108">包含资源的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="8fefa-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="8fefa-109">资源的名称。</span><span class="sxs-lookup"><span data-stu-id="8fefa-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="8fefa-110">来自 RVA 的资源的偏移量。</span><span class="sxs-lookup"><span data-stu-id="8fefa-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8fefa-111">可访问性标志，如`mrPublic`和`mrPrivate`。</span><span class="sxs-lookup"><span data-stu-id="8fefa-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="8fefa-112">这些标志可能传递给[DefineExportedType 方法](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="8fefa-112">These flags may be passed to [DefineExportedType Method](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8fefa-113">返回值</span><span class="sxs-lookup"><span data-stu-id="8fefa-113">Return Value</span></span>  
 <span data-ttu-id="8fefa-114">如果该方法成功，则返回，则为 S_OK。</span><span class="sxs-lookup"><span data-stu-id="8fefa-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8fefa-115">要求</span><span class="sxs-lookup"><span data-stu-id="8fefa-115">Requirements</span></span>  
 <span data-ttu-id="8fefa-116">需要 alink.h。</span><span class="sxs-lookup"><span data-stu-id="8fefa-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8fefa-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fefa-117">See Also</span></span>  
 [<span data-ttu-id="8fefa-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="8fefa-118">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [<span data-ttu-id="8fefa-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="8fefa-119">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [<span data-ttu-id="8fefa-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="8fefa-120">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
