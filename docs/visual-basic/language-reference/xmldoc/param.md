---
title: '&lt;param&gt; (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c992c96303eb1441eaf667693b7aefb5361b196c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33602916"
---
# <a name="ltparamgt-visual-basic"></a><span data-ttu-id="87c7b-102">&lt;param&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="87c7b-102">&lt;param&gt; (Visual Basic)</span></span>
<span data-ttu-id="87c7b-103">定义的参数名称和描述。</span><span class="sxs-lookup"><span data-stu-id="87c7b-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87c7b-104">语法</span><span class="sxs-lookup"><span data-stu-id="87c7b-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="87c7b-105">参数</span><span class="sxs-lookup"><span data-stu-id="87c7b-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="87c7b-106">方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="87c7b-106">The name of a method parameter.</span></span> <span data-ttu-id="87c7b-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="87c7b-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="87c7b-108">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="87c7b-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87c7b-109">备注</span><span class="sxs-lookup"><span data-stu-id="87c7b-109">Remarks</span></span>  
 <span data-ttu-id="87c7b-110">`<param>`标记应使用方法声明的注释，用于描述方法的参数之一。</span><span class="sxs-lookup"><span data-stu-id="87c7b-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="87c7b-111">文本`<param>`标记将出现在以下位置：</span><span class="sxs-lookup"><span data-stu-id="87c7b-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
-   <span data-ttu-id="87c7b-112">IntelliSense 的参数信息。</span><span class="sxs-lookup"><span data-stu-id="87c7b-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="87c7b-113">有关详细信息，请参阅[使用 IntelliSense](/visualstudio/ide/using-intellisense)。</span><span class="sxs-lookup"><span data-stu-id="87c7b-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
-   <span data-ttu-id="87c7b-114">对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="87c7b-114">Object Browser.</span></span> <span data-ttu-id="87c7b-115">有关详细信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="87c7b-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="87c7b-116">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="87c7b-116">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87c7b-117">示例</span><span class="sxs-lookup"><span data-stu-id="87c7b-117">Example</span></span>  
 <span data-ttu-id="87c7b-118">此示例使用`<param>`标记来描述`id`参数。</span><span class="sxs-lookup"><span data-stu-id="87c7b-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/param_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="87c7b-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="87c7b-119">See Also</span></span>  
 [<span data-ttu-id="87c7b-120">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="87c7b-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
