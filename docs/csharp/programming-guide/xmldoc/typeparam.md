---
title: "&lt;typeparam&gt;（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeparam
dev_langs:
- CSharp
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: 19
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 8bb1d13976cf2cc9df4f573702168c6abdfff3d5
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="41e81-102">&lt;typeparam&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="41e81-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="41e81-103">语法</span><span class="sxs-lookup"><span data-stu-id="41e81-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41e81-104">参数</span><span class="sxs-lookup"><span data-stu-id="41e81-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="41e81-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="41e81-105">The name of the type parameter.</span></span> <span data-ttu-id="41e81-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="41e81-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="41e81-107">类型参数的说明。</span><span class="sxs-lookup"><span data-stu-id="41e81-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41e81-108">备注</span><span class="sxs-lookup"><span data-stu-id="41e81-108">Remarks</span></span>  
 <span data-ttu-id="41e81-109">在泛型类型或方法声明的注释中，应使用 `<typeparam>` 标记来描述类型参数。</span><span class="sxs-lookup"><span data-stu-id="41e81-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="41e81-110">为泛型类型或方法的每个类型参数添加标记。</span><span class="sxs-lookup"><span data-stu-id="41e81-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="41e81-111">有关详细信息，请参阅[泛型](../../../csharp/programming-guide/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="41e81-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="41e81-112">`<typeparam>` 标记的文本将显示在 IntelliSense、[对象浏览器窗口](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)代码注释 Web 报表。</span><span class="sxs-lookup"><span data-stu-id="41e81-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/en-us/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="41e81-113">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="41e81-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="41e81-114">示例</span><span class="sxs-lookup"><span data-stu-id="41e81-114">Example</span></span>  
 <span data-ttu-id="41e81-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="41e81-115">[!code-cs[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41e81-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41e81-116">See Also</span></span>  
 <span data-ttu-id="41e81-117">[C# 参考](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="41e81-117">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="41e81-118">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="41e81-118">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="41e81-119">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="41e81-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

