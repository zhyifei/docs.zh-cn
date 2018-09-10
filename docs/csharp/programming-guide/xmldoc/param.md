---
title: '&lt;param&gt;（C# 编程指南）'
ms.date: 07/20/2015
f1_keywords:
- param
- <param>
helpviewer_keywords:
- <param> C# XML tag
- param C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: b4afa84aadc68ca2f0113023319f02a10dc17836
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2018
ms.locfileid: "43508210"
---
# <a name="ltparamgt-c-programming-guide"></a><span data-ttu-id="c4201-102">&lt;param&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="c4201-102">&lt;param&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="c4201-103">语法</span><span class="sxs-lookup"><span data-stu-id="c4201-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c4201-104">参数</span><span class="sxs-lookup"><span data-stu-id="c4201-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="c4201-105">方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="c4201-105">The name of a method parameter.</span></span> <span data-ttu-id="c4201-106">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="c4201-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="c4201-107">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="c4201-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4201-108">备注</span><span class="sxs-lookup"><span data-stu-id="c4201-108">Remarks</span></span>  
 <span data-ttu-id="c4201-109">在方法声明的注释中，应使用 \<param> 标记来描述方法参数之一。</span><span class="sxs-lookup"><span data-stu-id="c4201-109">The \<param> tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span> <span data-ttu-id="c4201-110">若要记录多个参数，请使用多个 \<param > 标记。</span><span class="sxs-lookup"><span data-stu-id="c4201-110">To document multiple parameters, use multiple \<param> tags.</span></span>  
  
 <span data-ttu-id="c4201-111">\<param> 标记的文本将显示在 IntelliSense、对象浏览器和代码注释 Web 报表中。</span><span class="sxs-lookup"><span data-stu-id="c4201-111">The text for the \<param> tag will be displayed in IntelliSense, the Object Browser, and in the Code Comment Web Report.</span></span>  
  
 <span data-ttu-id="c4201-112">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="c4201-112">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c4201-113">示例</span><span class="sxs-lookup"><span data-stu-id="c4201-113">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#1](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/param_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="c4201-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4201-114">See Also</span></span>

- [<span data-ttu-id="c4201-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c4201-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="c4201-116">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="c4201-116">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
