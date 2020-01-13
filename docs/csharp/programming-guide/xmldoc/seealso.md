---
title: <seealso> - C# 编程指南
ms.date: 07/20/2015
f1_keywords:
- cref
- <seealso>
- seealso
helpviewer_keywords:
- cref [C#], see also
- seealso C# XML tag
- cref [C#]
- cross-references [C#], tags
- <seealso> C# XML tag
ms.assetid: 8e157f3f-f220-4fcf-9010-88905b080b18
ms.openlocfilehash: 600affdfd8cb524a7fba479d3a68ad8b3e40098c
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75694915"
---
# <a name="seealso-c-programming-guide"></a><span data-ttu-id="61cd5-102">\<seealso>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="61cd5-102">\<seealso> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="61cd5-103">语法</span><span class="sxs-lookup"><span data-stu-id="61cd5-103">Syntax</span></span>  
  
```xml  
<seealso cref="member"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="61cd5-104">参数</span><span class="sxs-lookup"><span data-stu-id="61cd5-104">Parameters</span></span>  
 <span data-ttu-id="61cd5-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="61cd5-105">cref = " `member`"</span></span>  
 <span data-ttu-id="61cd5-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="61cd5-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="61cd5-107">编译器检查是否存在给定的码位元素，并将 `member` 传递到输出 XML 中的元素名称。`member`</span><span class="sxs-lookup"><span data-stu-id="61cd5-107">The compiler checks that the given code element exists and passes `member` to the element name in the output XML.`member`</span></span> <span data-ttu-id="61cd5-108">必须在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="61cd5-108">must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="61cd5-109">有关如何创建对泛型类型的 cref 引用的信息，请参阅 [\<see>](./see.md)。</span><span class="sxs-lookup"><span data-stu-id="61cd5-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="61cd5-110">备注</span><span class="sxs-lookup"><span data-stu-id="61cd5-110">Remarks</span></span>  
 <span data-ttu-id="61cd5-111">使用 \<seealso> 标记，可以指定想要在“另请参阅”部分中显示的文本。</span><span class="sxs-lookup"><span data-stu-id="61cd5-111">The \<seealso> tag lets you specify the text that you might want to appear in a See Also section.</span></span> <span data-ttu-id="61cd5-112">使用 [\<see>](./see.md) 从文本内指定链接。</span><span class="sxs-lookup"><span data-stu-id="61cd5-112">Use [\<see>](./see.md) to specify a link from within text.</span></span>  
  
 <span data-ttu-id="61cd5-113">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="61cd5-113">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="61cd5-114">示例</span><span class="sxs-lookup"><span data-stu-id="61cd5-114">Example</span></span>  
 <span data-ttu-id="61cd5-115">有关使用 \<seealso> 的示例，请参阅 [\<summary>](./summary.md)。</span><span class="sxs-lookup"><span data-stu-id="61cd5-115">See [\<summary>](./summary.md) for an example of using \<seealso>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61cd5-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="61cd5-116">See also</span></span>

- [<span data-ttu-id="61cd5-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="61cd5-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="61cd5-118">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="61cd5-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
