---
title: ExportNestedTypeForwarder 方法
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: cc81ccd1c754e3d34c54737f4560b4f81d5cc916
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438415"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="91bbb-102">ExportNestedTypeForwarder 方法</span><span class="sxs-lookup"><span data-stu-id="91bbb-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="91bbb-103">将嵌套类型的类型转发器添加到给定程序集的类型表。</span><span class="sxs-lookup"><span data-stu-id="91bbb-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91bbb-104">语法</span><span class="sxs-lookup"><span data-stu-id="91bbb-104">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="91bbb-105">参数</span><span class="sxs-lookup"><span data-stu-id="91bbb-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="91bbb-106">要从中导出的程序集的 ID。</span><span class="sxs-lookup"><span data-stu-id="91bbb-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="91bbb-107">定义类型的文件的文件标记或程序集 ID。</span><span class="sxs-lookup"><span data-stu-id="91bbb-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="91bbb-108">类型的标记。</span><span class="sxs-lookup"><span data-stu-id="91bbb-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="91bbb-109">父类型的标记。</span><span class="sxs-lookup"><span data-stu-id="91bbb-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="91bbb-110">要导出的完全限定的类型名称。</span><span class="sxs-lookup"><span data-stu-id="91bbb-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="91bbb-111">`ComType` 标志，如 `tdPublic` 或 `tdNested`。</span><span class="sxs-lookup"><span data-stu-id="91bbb-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="91bbb-112">接收导出类型的令牌。</span><span class="sxs-lookup"><span data-stu-id="91bbb-112">Receives token of export type.</span></span> <span data-ttu-id="91bbb-113">这仅适用于发出嵌套类型。</span><span class="sxs-lookup"><span data-stu-id="91bbb-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91bbb-114">返回值</span><span class="sxs-lookup"><span data-stu-id="91bbb-114">Return Value</span></span>  
 <span data-ttu-id="91bbb-115">如果方法成功，则返回 S_OK。</span><span class="sxs-lookup"><span data-stu-id="91bbb-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91bbb-116">要求</span><span class="sxs-lookup"><span data-stu-id="91bbb-116">Requirements</span></span>  
 <span data-ttu-id="91bbb-117">需要 alink</span><span class="sxs-lookup"><span data-stu-id="91bbb-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91bbb-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91bbb-118">See also</span></span>

- [<span data-ttu-id="91bbb-119">IALink 接口</span><span class="sxs-lookup"><span data-stu-id="91bbb-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="91bbb-120">IALink2 接口</span><span class="sxs-lookup"><span data-stu-id="91bbb-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="91bbb-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="91bbb-121">ALink API</span></span>](index.md)
