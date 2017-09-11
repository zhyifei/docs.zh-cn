---
title: "&lt;param&gt;（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- param
- <param>
dev_langs:
- CSharp
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
caps.latest.revision: 15
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
ms.openlocfilehash: 1076405d60c85540eeaeba39821bd20bc628030d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="3255d-102">&lt;param&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="3255d-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="3255d-103">语法</span><span class="sxs-lookup"><span data-stu-id="3255d-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3255d-104">参数</span><span class="sxs-lookup"><span data-stu-id="3255d-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="3255d-105">方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="3255d-105">The name of a method parameter.</span></span> <span data-ttu-id="3255d-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="3255d-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="3255d-107">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="3255d-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3255d-108">备注</span><span class="sxs-lookup"><span data-stu-id="3255d-108">Remarks</span></span>  
 <span data-ttu-id="3255d-109">在方法声明的注释中，应使用 \<param> 标记来描述方法参数之一。</span><span class="sxs-lookup"><span data-stu-id="3255d-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="3255d-110">若要记录多个参数，请使用多个 \<param > 标记。</span><span class="sxs-lookup"><span data-stu-id="3255d-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="3255d-111">\<param> 标记的文本将显示在 IntelliSense、对象浏览器和代码注释 Web 报表中。</span><span class="sxs-lookup"><span data-stu-id="3255d-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="3255d-112">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="3255d-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3255d-113">示例</span><span class="sxs-lookup"><span data-stu-id="3255d-113">Example</span></span>  
 <span data-ttu-id="3255d-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="3255d-114">[!code-cs[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3255d-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3255d-115">See Also</span></span>  
 <span data-ttu-id="3255d-116">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="3255d-116">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="3255d-117">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="3255d-117">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

