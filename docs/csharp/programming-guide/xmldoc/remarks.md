---
title: <remarks> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: 822ca8feafe48402f8217c10ef37fcdb1576c27a
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587749"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="c90dd-102">\<remarks>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c90dd-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c90dd-103">语法</span><span class="sxs-lookup"><span data-stu-id="c90dd-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c90dd-104">参数</span><span class="sxs-lookup"><span data-stu-id="c90dd-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="c90dd-105">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="c90dd-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c90dd-106">备注</span><span class="sxs-lookup"><span data-stu-id="c90dd-106">Remarks</span></span>  
 <span data-ttu-id="c90dd-107">\<remarks> 标记用于添加有关某个类型的信息，从而补充由 [\<summary>](./summary.md) 指定的信息。</span><span class="sxs-lookup"><span data-stu-id="c90dd-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](./summary.md).</span></span> <span data-ttu-id="c90dd-108">此信息显示在对象浏览器窗口中。</span><span class="sxs-lookup"><span data-stu-id="c90dd-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="c90dd-109">使用 [/doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="c90dd-109">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c90dd-110">示例</span><span class="sxs-lookup"><span data-stu-id="c90dd-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#9)]  
  
## <a name="see-also"></a><span data-ttu-id="c90dd-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c90dd-111">See also</span></span>

- [<span data-ttu-id="c90dd-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c90dd-112">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="c90dd-113">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="c90dd-113">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
