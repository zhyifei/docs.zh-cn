---
title: ExportTypeForwarder 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportTypeForwarder
helpviewer_keywords:
- ExportTypeForwarder method
ms.assetid: 55989fa9-ab43-4f08-8eb6-2eb56fa7ca76
topic_type:
- apiref
ms.openlocfilehash: 36c99477e9faead5e24799d5b0ae8901f1dd13c9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448707"
---
# <a name="exporttypeforwarder-method"></a><span data-ttu-id="98dfe-102">ExportTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="98dfe-102">ExportTypeForwarder Method</span></span>
<span data-ttu-id="98dfe-103">将类型转发器添加到给定程序集的类型表。</span><span class="sxs-lookup"><span data-stu-id="98dfe-103">Adds a type forwarder to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98dfe-104">语法</span><span class="sxs-lookup"><span data-stu-id="98dfe-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportTypeForwarder(  
    mdAssemblyRef   tkAssemblyRef,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="98dfe-105">参数</span><span class="sxs-lookup"><span data-stu-id="98dfe-105">Parameters</span></span>  
 `tkAssemblyRef`  
 <span data-ttu-id="98dfe-106">对类型转发器所引用的程序集的引用。</span><span class="sxs-lookup"><span data-stu-id="98dfe-106">Reference to the assembly to which the type forwarder refers.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="98dfe-107">要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="98dfe-107">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="98dfe-108">`ComType` 标志，如 `tdPublic` 或 `tdNested`。</span><span class="sxs-lookup"><span data-stu-id="98dfe-108">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="98dfe-109">此值可传递给[DefineExportedType 方法](../metadata/imetadataassemblyemit-defineexportedtype-method.md)。</span><span class="sxs-lookup"><span data-stu-id="98dfe-109">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="98dfe-110">接收导出类型的标记。</span><span class="sxs-lookup"><span data-stu-id="98dfe-110">Receives the token of the exported type.</span></span> <span data-ttu-id="98dfe-111">这仅适用于发出嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="98dfe-111">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="98dfe-112">返回值</span><span class="sxs-lookup"><span data-stu-id="98dfe-112">Return Value</span></span>  
 <span data-ttu-id="98dfe-113">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="98dfe-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98dfe-114">要求</span><span class="sxs-lookup"><span data-stu-id="98dfe-114">Requirements</span></span>  
 <span data-ttu-id="98dfe-115">需要 alink</span><span class="sxs-lookup"><span data-stu-id="98dfe-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98dfe-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="98dfe-116">See also</span></span>

- [<span data-ttu-id="98dfe-117">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="98dfe-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="98dfe-118">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="98dfe-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="98dfe-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="98dfe-119">ALink API</span></span>](index.md)
