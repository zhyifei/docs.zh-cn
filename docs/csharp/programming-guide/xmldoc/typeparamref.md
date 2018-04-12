---
title: '&lt;typeparamref&gt;（C# 编程指南）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
caps.latest.revision: 15
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 296761f72d3d306c4f37632d7110e31b62c44734
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="3e20c-102">&lt;typeparamref&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3e20c-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="3e20c-103">语法</span><span class="sxs-lookup"><span data-stu-id="3e20c-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3e20c-104">参数</span><span class="sxs-lookup"><span data-stu-id="3e20c-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3e20c-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3e20c-105">The name of the type parameter.</span></span> <span data-ttu-id="3e20c-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="3e20c-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3e20c-107">备注</span><span class="sxs-lookup"><span data-stu-id="3e20c-107">Remarks</span></span>  
 <span data-ttu-id="3e20c-108">有关泛型类型中的类型参数及方法的详细信息，请参阅[泛型](../../../csharp/programming-guide/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="3e20c-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="3e20c-109">通过此标记，文档文件的使用者可显著设置字体格式，例如采用斜体。</span><span class="sxs-lookup"><span data-stu-id="3e20c-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="3e20c-110">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="3e20c-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3e20c-111">示例</span><span class="sxs-lookup"><span data-stu-id="3e20c-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="3e20c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3e20c-112">See Also</span></span>  
 [<span data-ttu-id="3e20c-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3e20c-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="3e20c-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="3e20c-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
