---
title: <param> （Visual Basic）
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: c62eab6b1fb1ba1cc7de83c12d7205cf0bbe46fa
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524729"
---
# <a name="param-visual-basic"></a><span data-ttu-id="21cdd-102">\<param > （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="21cdd-102">\<param> (Visual Basic)</span></span>
<span data-ttu-id="21cdd-103">定义参数名称和说明。</span><span class="sxs-lookup"><span data-stu-id="21cdd-103">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21cdd-104">语法</span><span class="sxs-lookup"><span data-stu-id="21cdd-104">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="21cdd-105">参数</span><span class="sxs-lookup"><span data-stu-id="21cdd-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="21cdd-106">方法参数的名称。</span><span class="sxs-lookup"><span data-stu-id="21cdd-106">The name of a method parameter.</span></span> <span data-ttu-id="21cdd-107">用双引号 (" ") 将名称引起来。</span><span class="sxs-lookup"><span data-stu-id="21cdd-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="21cdd-108">参数的说明。</span><span class="sxs-lookup"><span data-stu-id="21cdd-108">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="21cdd-109">备注</span><span class="sxs-lookup"><span data-stu-id="21cdd-109">Remarks</span></span>  
 <span data-ttu-id="21cdd-110">应在方法声明的注释中使用 `<param>` 标记来描述方法的参数之一。</span><span class="sxs-lookup"><span data-stu-id="21cdd-110">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="21cdd-111">@No__t_0 标记的文本将出现在以下位置：</span><span class="sxs-lookup"><span data-stu-id="21cdd-111">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="21cdd-112">IntelliSense 的参数信息。</span><span class="sxs-lookup"><span data-stu-id="21cdd-112">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="21cdd-113">有关详细信息，请参阅[使用 IntelliSense](/visualstudio/ide/using-intellisense)。</span><span class="sxs-lookup"><span data-stu-id="21cdd-113">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="21cdd-114">对象浏览器。</span><span class="sxs-lookup"><span data-stu-id="21cdd-114">Object Browser.</span></span> <span data-ttu-id="21cdd-115">有关详细信息，请参阅[查看代码的结构](/visualstudio/ide/viewing-the-structure-of-code)。</span><span class="sxs-lookup"><span data-stu-id="21cdd-115">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="21cdd-116">使用 [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="21cdd-116">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="21cdd-117">示例</span><span class="sxs-lookup"><span data-stu-id="21cdd-117">Example</span></span>  
 <span data-ttu-id="21cdd-118">此示例使用 `<param>` 标记来描述 `id` 参数。</span><span class="sxs-lookup"><span data-stu-id="21cdd-118">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="21cdd-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="21cdd-119">See also</span></span>

- [<span data-ttu-id="21cdd-120">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="21cdd-120">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
