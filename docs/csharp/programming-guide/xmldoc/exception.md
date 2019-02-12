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
ms.openlocfilehash: fe304b9c6631591cf7a3d62fcecd2ed3ca05db9c
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257286"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="b419c-102">\<exception>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="b419c-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="b419c-103">语法</span><span class="sxs-lookup"><span data-stu-id="b419c-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b419c-104">参数</span><span class="sxs-lookup"><span data-stu-id="b419c-104">Parameters</span></span>  
 <span data-ttu-id="b419c-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="b419c-105">cref = " `member`"</span></span>  
 <span data-ttu-id="b419c-106">对当前编译环境中出现的一个异常的引用。</span><span class="sxs-lookup"><span data-stu-id="b419c-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="b419c-107">编译器检查是否存在给定的异常，并将 `member` 转换为输出 XML 中的规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="b419c-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="b419c-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="b419c-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="b419c-109">有关如何创建对泛型类型的 cref 引用的详细信息，请参阅[\<查看>](../../../csharp/programming-guide/xmldoc/see.md)。</span><span class="sxs-lookup"><span data-stu-id="b419c-109">For more information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="b419c-110">异常的说明。</span><span class="sxs-lookup"><span data-stu-id="b419c-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b419c-111">备注</span><span class="sxs-lookup"><span data-stu-id="b419c-111">Remarks</span></span>  
 <span data-ttu-id="b419c-112">\<exception> 标记让你指定可引发的异常。</span><span class="sxs-lookup"><span data-stu-id="b419c-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="b419c-113">此标记可应用于方法、属性、事件和索引器的定义。</span><span class="sxs-lookup"><span data-stu-id="b419c-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="b419c-114">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="b419c-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="b419c-115">有关异常处理的详细信息，请参阅[异常和异常处理](../../../csharp/programming-guide/exceptions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="b419c-115">For more information about exception handling, see [Exceptions and Exception Handling](../../../csharp/programming-guide/exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="b419c-116">示例</span><span class="sxs-lookup"><span data-stu-id="b419c-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/exception_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="b419c-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="b419c-117">See also</span></span>

- [<span data-ttu-id="b419c-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="b419c-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="b419c-119">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="b419c-119">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
