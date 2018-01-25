---
title: "&lt;typeparam&gt;（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: typeparam
helpviewer_keywords:
- <typeparam> C# XML tag
- typeparam C# XML tag
ms.assetid: 9b99d400-e911-4e55-99c6-64367c96aa4f
caps.latest.revision: "19"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: e1b8800e39b1ee5eeac8c5d3e4390ed3226b33a3
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="lttypeparamgt-c-programming-guide"></a><span data-ttu-id="652be-102">&lt;typeparam&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="652be-102">&lt;typeparam&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="652be-103">语法</span><span class="sxs-lookup"><span data-stu-id="652be-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="652be-104">参数</span><span class="sxs-lookup"><span data-stu-id="652be-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="652be-105">类型参数的名称。</span><span class="sxs-lookup"><span data-stu-id="652be-105">The name of the type parameter.</span></span> <span data-ttu-id="652be-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="652be-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="652be-107">类型参数的说明。</span><span class="sxs-lookup"><span data-stu-id="652be-107">A description for the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="652be-108">备注</span><span class="sxs-lookup"><span data-stu-id="652be-108">Remarks</span></span>  
 <span data-ttu-id="652be-109">在泛型类型或方法声明的注释中，应使用 `<typeparam>` 标记来描述类型参数。</span><span class="sxs-lookup"><span data-stu-id="652be-109">The `<typeparam>` tag should be used in the comment for a generic type or method declaration to describe a type parameter.</span></span> <span data-ttu-id="652be-110">为泛型类型或方法的每个类型参数添加标记。</span><span class="sxs-lookup"><span data-stu-id="652be-110">Add a tag for each type parameter of the generic type or method.</span></span>  
  
 <span data-ttu-id="652be-111">有关详细信息，请参阅[泛型](../../../csharp/programming-guide/generics/index.md)。</span><span class="sxs-lookup"><span data-stu-id="652be-111">For more information, see [Generics](../../../csharp/programming-guide/generics/index.md).</span></span>  
  
 <span data-ttu-id="652be-112">`<typeparam>` 标记的文本将显示在 IntelliSense、[对象浏览器窗口](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda)代码注释 Web 报表。</span><span class="sxs-lookup"><span data-stu-id="652be-112">The text for the `<typeparam>` tag will be displayed in IntelliSense, the [Object Browser Window](http://msdn.microsoft.com/library/3c7f1673-1f0d-41b1-94ca-a3dcfcb82cda) code comment web report.</span></span>  
  
 <span data-ttu-id="652be-113">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="652be-113">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="652be-114">示例</span><span class="sxs-lookup"><span data-stu-id="652be-114">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#13](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/typeparam_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="652be-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="652be-115">See Also</span></span>  
 [<span data-ttu-id="652be-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="652be-116">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="652be-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="652be-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="652be-118">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="652be-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
