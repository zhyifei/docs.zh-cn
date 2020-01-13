---
title: <typeparamref> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- typeparamref
helpviewer_keywords:
- typeparamref C# XML tag
- <typeparamref> C# XML tag
ms.assetid: 6d8ffc58-12c5-4688-8db6-833a7ded5886
ms.openlocfilehash: 3e96d55d7cf60b2a9085cf065ef3b8193b173c5d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711670"
---
# <a name="typeparamref-c-programming-guide"></a><span data-ttu-id="4a144-102">\<typeparamref>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4a144-102">\<typeparamref> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4a144-103">语法</span><span class="sxs-lookup"><span data-stu-id="4a144-103">Syntax</span></span>  
  
```xml  
<typeparamref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="4a144-104">参数</span><span class="sxs-lookup"><span data-stu-id="4a144-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="4a144-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="4a144-105">The name of the type parameter.</span></span> <span data-ttu-id="4a144-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="4a144-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4a144-107">备注</span><span class="sxs-lookup"><span data-stu-id="4a144-107">Remarks</span></span>  
 <span data-ttu-id="4a144-108">有关泛型类型中的类型参数及方法的详细信息，请参阅[泛型](../generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="4a144-108">For more information on type parameters in generic types and methods, see [Generics](../generics/index.md).</span></span>  
  
 <span data-ttu-id="4a144-109">通过此标记，文档文件的使用者可显著设置字体格式，例如采用斜体。</span><span class="sxs-lookup"><span data-stu-id="4a144-109">Use this tag to enable consumers of the documentation file to format the word in some distinct way, for example in italics.</span></span>  
  
 <span data-ttu-id="4a144-110">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="4a144-110">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a144-111">示例</span><span class="sxs-lookup"><span data-stu-id="4a144-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#13)]  
  
## <a name="see-also"></a><span data-ttu-id="4a144-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a144-112">See also</span></span>

- [<span data-ttu-id="4a144-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="4a144-113">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4a144-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="4a144-114">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
