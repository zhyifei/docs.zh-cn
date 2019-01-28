---
title: '&lt;typeparamref&gt; - C# 编程指南'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: cfee16ad1cdc1e019a4133259c1603f5a0a09ac8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54536550"
---
# <a name="lttypeparamrefgt-c-programming-guide"></a><span data-ttu-id="da440-102">&lt;typeparamref&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="da440-102">&lt;typeparamref&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="da440-103">语法</span><span class="sxs-lookup"><span data-stu-id="da440-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="da440-104">参数</span><span class="sxs-lookup"><span data-stu-id="da440-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="da440-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="da440-105">The name of the type parameter.</span></span> <span data-ttu-id="da440-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="da440-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da440-107">备注</span><span class="sxs-lookup"><span data-stu-id="da440-107">Remarks</span></span>  
 <span data-ttu-id="da440-108">有关泛型类型中的类型参数及方法的详细信息，请参阅[泛型](../../../csharp/programming-guide/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="da440-108">For more information on type parameters in generic types and methods, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="da440-109">通过此标记，文档文件的使用者可显著设置字体格式，例如采用斜体。</span><span class="sxs-lookup"><span data-stu-id="da440-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="da440-110">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="da440-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="da440-111">示例</span><span class="sxs-lookup"><span data-stu-id="da440-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparamref_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="da440-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="da440-112">See also</span></span>

- [<span data-ttu-id="da440-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="da440-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="da440-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="da440-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
