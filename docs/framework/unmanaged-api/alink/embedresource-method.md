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
ms.openlocfilehash: 5f6140e5f85a7ee21773c96a5abdccadaddab92e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777455"
---
# <a name="embedresource-method"></a><span data-ttu-id="45aa2-102">EmbedResource 方法</span><span class="sxs-lookup"><span data-stu-id="45aa2-102">EmbedResource Method</span></span>
<span data-ttu-id="45aa2-103">声明嵌入的资源。</span><span class="sxs-lookup"><span data-stu-id="45aa2-103">Declares an embedded resource.</span></span> <span data-ttu-id="45aa2-104">此方法并不实际嵌入资源。</span><span class="sxs-lookup"><span data-stu-id="45aa2-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45aa2-105">语法</span><span class="sxs-lookup"><span data-stu-id="45aa2-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="45aa2-106">参数</span><span class="sxs-lookup"><span data-stu-id="45aa2-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="45aa2-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="45aa2-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="45aa2-108">包含资源的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="45aa2-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="45aa2-109">资源的名称。</span><span class="sxs-lookup"><span data-stu-id="45aa2-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="45aa2-110">RVA 中资源的偏移量。</span><span class="sxs-lookup"><span data-stu-id="45aa2-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="45aa2-111">辅助功能标志`mrPublic` ，例如`mrPrivate`和。</span><span class="sxs-lookup"><span data-stu-id="45aa2-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="45aa2-112">这些标志可能会传递给[DefineExportedType 方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="45aa2-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="45aa2-113">返回值</span><span class="sxs-lookup"><span data-stu-id="45aa2-113">Return Value</span></span>  
 <span data-ttu-id="45aa2-114">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="45aa2-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45aa2-115">要求</span><span class="sxs-lookup"><span data-stu-id="45aa2-115">Requirements</span></span>  
 <span data-ttu-id="45aa2-116">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="45aa2-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45aa2-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="45aa2-117">See also</span></span>

- [<span data-ttu-id="45aa2-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="45aa2-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="45aa2-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="45aa2-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="45aa2-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="45aa2-120">ALink API</span></span>](index.md)
