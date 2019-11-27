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
ms.openlocfilehash: 24279870e7406de649df56e8aad31252513e95c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446535"
---
# <a name="embedresource-method"></a><span data-ttu-id="2fa9b-102">EmbedResource 方法</span><span class="sxs-lookup"><span data-stu-id="2fa9b-102">EmbedResource Method</span></span>
<span data-ttu-id="2fa9b-103">声明嵌入的资源。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-103">Declares an embedded resource.</span></span> <span data-ttu-id="2fa9b-104">此方法并不实际嵌入资源。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-104">This method does not actually embed the resource.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2fa9b-105">语法</span><span class="sxs-lookup"><span data-stu-id="2fa9b-105">Syntax</span></span>  
  
```cpp  
HRESULT EmbedResource(  
    mdAssembly  AssemblyID,  
    mdToken     FileToken,  
    LPCWSTR     pszResourceName,  
    DWORD       dwOffset,  
    DWORD       dwFlags  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2fa9b-106">参数</span><span class="sxs-lookup"><span data-stu-id="2fa9b-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2fa9b-107">程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-107">ID of the assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2fa9b-108">包含资源的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-108">File token or assembly ID of file that contains the resource.</span></span>  
  
 `pszResourceName`  
 <span data-ttu-id="2fa9b-109">资源的名称。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-109">Name of the resource.</span></span>  
  
 `dwOffset`  
 <span data-ttu-id="2fa9b-110">RVA 中资源的偏移量。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-110">Offset of resource from RVA.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2fa9b-111">辅助功能标志，如 `mrPublic` 和 `mrPrivate`。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-111">Accessibility flags such as `mrPublic` and `mrPrivate`.</span></span> <span data-ttu-id="2fa9b-112">这些标志可能会传递给[DefineExportedType 方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-112">These flags may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2fa9b-113">返回值</span><span class="sxs-lookup"><span data-stu-id="2fa9b-113">Return Value</span></span>  
 <span data-ttu-id="2fa9b-114">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fa9b-115">要求</span><span class="sxs-lookup"><span data-stu-id="2fa9b-115">Requirements</span></span>  
 <span data-ttu-id="2fa9b-116">需要 alink。</span><span class="sxs-lookup"><span data-stu-id="2fa9b-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fa9b-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fa9b-117">See also</span></span>

- [<span data-ttu-id="2fa9b-118">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="2fa9b-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2fa9b-119">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="2fa9b-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2fa9b-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="2fa9b-120">ALink API</span></span>](index.md)
