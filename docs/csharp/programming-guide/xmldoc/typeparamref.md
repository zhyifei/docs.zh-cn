---
title: <typeparamref> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: f01df27b920dcf3011a51015c771d2da3b442c4c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69587426"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="02594-102">\<typeparamref>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="02594-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="02594-103">语法</span><span class="sxs-lookup"><span data-stu-id="02594-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="02594-104">参数</span><span class="sxs-lookup"><span data-stu-id="02594-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="02594-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="02594-105">The name of the type parameter.</span></span> <span data-ttu-id="02594-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="02594-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02594-107">备注</span><span class="sxs-lookup"><span data-stu-id="02594-107">Remarks</span></span>  
 <span data-ttu-id="02594-108">有关泛型类型中的类型参数及方法的详细信息，请参阅[泛型](../generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="02594-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="02594-109">通过此标记，文档文件的使用者可显著设置字体格式，例如采用斜体。</span><span class="sxs-lookup"><span data-stu-id="02594-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="02594-110">使用 [/doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="02594-110">Compile with [/doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02594-111">示例</span><span class="sxs-lookup"><span data-stu-id="02594-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="02594-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="02594-112">See also</span></span>

- [<span data-ttu-id="02594-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="02594-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="02594-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="02594-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
