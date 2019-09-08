---
title: ImportTypes2 方法
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce09eca30e1edb9e1afc02216a07955a5fed4fd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787257"
---
# <a name="importtypes2-method"></a><span data-ttu-id="7cbc6-102">ImportTypes2 方法</span><span class="sxs-lookup"><span data-stu-id="7cbc6-102">ImportTypes2 Method</span></span>
<span data-ttu-id="7cbc6-103">启动类型的导入。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-103">Initiates the import of types.</span></span> <span data-ttu-id="7cbc6-104">调用此方法以开始从通过[ImportFile 方法](importfile-method.md)导入的每个范围导入类型。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7cbc6-105">语法</span><span class="sxs-lookup"><span data-stu-id="7cbc6-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7cbc6-106">参数</span><span class="sxs-lookup"><span data-stu-id="7cbc6-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="7cbc6-107">要导入的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="7cbc6-108">要从其导入的文件的 ID。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="7cbc6-109">要从中导入的从零开始的作用域。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="7cbc6-110">接收给定范围内的类型的枚举器句柄。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="7cbc6-111">可以选择接收[IMetaDataImport2 接口](../metadata/imetadataimport2-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="7cbc6-112">可以选择接收指定范围内的类型的计数。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7cbc6-113">返回值</span><span class="sxs-lookup"><span data-stu-id="7cbc6-113">Return Value</span></span>  
 <span data-ttu-id="7cbc6-114">如果该方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="7cbc6-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7cbc6-115">要求</span><span class="sxs-lookup"><span data-stu-id="7cbc6-115">Requirements</span></span>  
 <span data-ttu-id="7cbc6-116">需要 alink</span><span class="sxs-lookup"><span data-stu-id="7cbc6-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7cbc6-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="7cbc6-117">See also</span></span>

- [<span data-ttu-id="7cbc6-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="7cbc6-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="7cbc6-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="7cbc6-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="7cbc6-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="7cbc6-120">ALink API</span></span>](index.md)
