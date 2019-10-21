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
ms.openlocfilehash: 4e4204996c006ce6e943c9a09661001b0e0c2a14
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523476"
---
# <a name="exception-c-programming-guide"></a><span data-ttu-id="5e9a3-102">\<exception>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="5e9a3-102">\<exception> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="5e9a3-103">语法</span><span class="sxs-lookup"><span data-stu-id="5e9a3-103">Syntax</span></span>  
  
```xml  
<exception cref="member">description</exception>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e9a3-104">参数</span><span class="sxs-lookup"><span data-stu-id="5e9a3-104">Parameters</span></span>  
 <span data-ttu-id="5e9a3-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="5e9a3-105">cref = " `member`"</span></span>  
 <span data-ttu-id="5e9a3-106">对当前编译环境中出现的一个异常的引用。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-106">A reference to an exception that is available from the current compilation environment.</span></span> <span data-ttu-id="5e9a3-107">编译器检查是否存在给定的异常，并将 `member` 转换为输出 XML 中的规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-107">The compiler checks that the given exception exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="5e9a3-108">`member` 必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-108">`member` must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="5e9a3-109">有关如何设置 `member` 格式以引用泛型类型的详细信息，请参阅[处理 XML 文件](processing-the-xml-file.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-109">For more information on how to format `member` to reference a generic type, see [Processing the XML File](processing-the-xml-file.md).</span></span>
  
 `description`  
 <span data-ttu-id="5e9a3-110">异常的说明。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-110">A description of the exception.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e9a3-111">备注</span><span class="sxs-lookup"><span data-stu-id="5e9a3-111">Remarks</span></span>  
 <span data-ttu-id="5e9a3-112">\<exception> 标记让你指定可引发的异常。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-112">The \<exception> tag lets you specify which exceptions can be thrown.</span></span> <span data-ttu-id="5e9a3-113">此标记可应用于方法、属性、事件和索引器的定义。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-113">This tag can be applied to definitions for methods, properties, events, and indexers.</span></span>  
  
 <span data-ttu-id="5e9a3-114">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
 <span data-ttu-id="5e9a3-115">有关异常处理的详细信息，请参阅[异常和异常处理](../exceptions/index.md)。</span><span class="sxs-lookup"><span data-stu-id="5e9a3-115">For more information about exception handling, see [Exceptions and Exception Handling](../exceptions/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e9a3-116">示例</span><span class="sxs-lookup"><span data-stu-id="5e9a3-116">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#4)]  
  
## <a name="see-also"></a><span data-ttu-id="5e9a3-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="5e9a3-117">See also</span></span>

- [<span data-ttu-id="5e9a3-118">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5e9a3-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="5e9a3-119">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="5e9a3-119">Recommended Tags for Documentation Comments</span></span>](recommended-tags-for-documentation-comments.md)
