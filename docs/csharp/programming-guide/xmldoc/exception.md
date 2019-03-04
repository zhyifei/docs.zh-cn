---
title: <exception> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- exception
- <exception>
helpviewer_keywords:
- <exception> C# XML tag
- exception C# XML tag
ms.assetid: dd73aac5-3c74-4fcf-9498-f11bff3a2f3c
ms.openlocfilehash: b316927c5dfd5eda05bea653f9a601cca9865af3
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982058"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="37ad1-102">\<exception>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="37ad1-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="37ad1-103">语法</span><span class="sxs-lookup"><span data-stu-id="37ad1-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="37ad1-104">参数</span><span class="sxs-lookup"><span data-stu-id="37ad1-104">Parameters</span></span>  
 <span data-ttu-id="37ad1-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="37ad1-105">cref = " `member`"</span></span>  
 <span data-ttu-id="37ad1-106">对当前编译环境中出现的一个异常的引用。</span><span class="sxs-lookup"><span data-stu-id="37ad1-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="37ad1-107">编译器检查是否存在给定的异常，并将 `member` 转换为输出 XML 中的规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="37ad1-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="37ad1-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="37ad1-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="37ad1-109">有关如何创建对泛型类型的 cref 引用的详细信息，请参阅[\<查看>](../../../csharp/programming-guide/xmldoc/see.md)。</span><span class="sxs-lookup"><span data-stu-id="37ad1-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="37ad1-110">异常的说明。</span><span class="sxs-lookup"><span data-stu-id="37ad1-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="37ad1-111">备注</span><span class="sxs-lookup"><span data-stu-id="37ad1-111">Remarks</span></span>  
 <span data-ttu-id="37ad1-112">\<exception> 标记让你指定可引发的异常。</span><span class="sxs-lookup"><span data-stu-id="37ad1-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="37ad1-113">此标记可应用于方法、属性、事件和索引器的定义。</span><span class="sxs-lookup"><span data-stu-id="37ad1-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="37ad1-114">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="37ad1-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="37ad1-115">有关异常处理的详细信息，请参阅[异常和异常处理](../../../csharp/programming-guide/exceptions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="37ad1-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="37ad1-116">示例</span><span class="sxs-lookup"><span data-stu-id="37ad1-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="37ad1-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="37ad1-117">See also</span></span>

- [<span data-ttu-id="37ad1-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="37ad1-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="37ad1-119">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="37ad1-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
