---
title: GUID_ManagedName 特性
ms.date: 03/30/2017
api_name:
- GUID_ManagedName
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GUID_ManagedName
helpviewer_keywords:
- GUID_ManagedName attribute
ms.assetid: 11e18095-e444-47bc-aff6-b887ac5dc01e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 48ad6e4d1d03d8362123e65f16907880b18893f9
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496386"
---
# <a name="guidmanagedname-attribute"></a><span data-ttu-id="7af4c-102">GUID_ManagedName 特性</span><span class="sxs-lookup"><span data-stu-id="7af4c-102">GUID_ManagedName Attribute</span></span>
<span data-ttu-id="7af4c-103">定义指定的组件对象模型 (COM) 库的托管命名空间名称的自定义接口特性。</span><span class="sxs-lookup"><span data-stu-id="7af4c-103">Defines a custom interface attribute that specifies the managed namespace name for a component object model (COM) library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7af4c-104">语法</span><span class="sxs-lookup"><span data-stu-id="7af4c-104">Syntax</span></span>  
  
```  
[  
   custom(GUID_ManagedName, value)  
]  
```  
  
## <a name="parameters"></a><span data-ttu-id="7af4c-105">参数</span><span class="sxs-lookup"><span data-stu-id="7af4c-105">Parameters</span></span>  
 `value`  
 <span data-ttu-id="7af4c-106">库管理的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="7af4c-106">The managed namespace name for the library.</span></span>  
  
## <a name="definition"></a><span data-ttu-id="7af4c-107">定义</span><span class="sxs-lookup"><span data-stu-id="7af4c-107">Definition</span></span>  
 <span data-ttu-id="7af4c-108">`GUID_ManagedName` 定义在 Cor.h，如下所示：</span><span class="sxs-lookup"><span data-stu-id="7af4c-108">`GUID_ManagedName` is defined in Cor.h as follows:</span></span>  
  
```  
// {0F21F359-AB84-41e8-9A78-36D110E6D2F9}  
EXTERN_GUID(GUID_ManagedName, 0xf21f359, 0xab84, 0x41e8, 0x9a, 0x78, 0x36, 0xd1, 0x10, 0xe6, 0xd2, 0xf9);  
```  
  
## <a name="remarks"></a><span data-ttu-id="7af4c-109">备注</span><span class="sxs-lookup"><span data-stu-id="7af4c-109">Remarks</span></span>  
 <span data-ttu-id="7af4c-110">自定义接口特性的类型库中定义的对象的元数据。</span><span class="sxs-lookup"><span data-stu-id="7af4c-110">A custom interface attribute defines metadata for an object in the type library.</span></span>  
  
 <span data-ttu-id="7af4c-111">使用<xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType>或<xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType>托管的名称检索该属性。</span><span class="sxs-lookup"><span data-stu-id="7af4c-111">Use <xref:System.Runtime.InteropServices.ComTypes.ITypeInfo2.GetCustData%2A?displayProperty=nameWithType> or <xref:System.Runtime.InteropServices.ComTypes.ITypeLib2.GetCustData%2A?displayProperty=nameWithType> to retrieve the managed name from the attribute.</span></span>  
  
 <span data-ttu-id="7af4c-112">有关详细信息，请参阅[接口特性](/cpp/windows/interface-attributes)Visual c + + 参考文档。</span><span class="sxs-lookup"><span data-stu-id="7af4c-112">For more information, see [Interface Attributes](/cpp/windows/interface-attributes) in the Visual C++ reference documentation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7af4c-113">示例</span><span class="sxs-lookup"><span data-stu-id="7af4c-113">Example</span></span>  
 <span data-ttu-id="7af4c-114">下面的示例演示库定义使用`GUID_ManagedName`属性。</span><span class="sxs-lookup"><span data-stu-id="7af4c-114">The following example shows a library definition using the `GUID_ManagedName` attribute.</span></span>  
  
```  
[  
   ...  
   custom(GUID_ManagedName, Microsoft.VisualStudio.CommandBars.dll")  
]  
library Microsoft_VisualStudio_CommandBars  
{  
   ...  
}  
```  
  
## <a name="requirements"></a><span data-ttu-id="7af4c-115">要求</span><span class="sxs-lookup"><span data-stu-id="7af4c-115">Requirements</span></span>  
 <span data-ttu-id="7af4c-116">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7af4c-116">**Header:** Cor.h</span></span>
