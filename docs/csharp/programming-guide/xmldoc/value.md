---
title: <value> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 3495a6c88d340342362d84d6ea3f12048d42b21f
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56982149"
---
# <a name="value-c-programming-guide"></a><span data-ttu-id="2ece6-102">\<value>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2ece6-102">\<value> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2ece6-103">语法</span><span class="sxs-lookup"><span data-stu-id="2ece6-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2ece6-104">参数</span><span class="sxs-lookup"><span data-stu-id="2ece6-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="2ece6-105">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="2ece6-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2ece6-106">备注</span><span class="sxs-lookup"><span data-stu-id="2ece6-106">Remarks</span></span>  
 <span data-ttu-id="2ece6-107">\<value> 标记可以描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="2ece6-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="2ece6-108">请注意，在 Visual Studio .NET 开发环境中通过代码向导添加属性时，将添加新属性的 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 标记。</span><span class="sxs-lookup"><span data-stu-id="2ece6-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="2ece6-109">然后，应手动添加 \<value> 标记，描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="2ece6-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="2ece6-110">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="2ece6-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2ece6-111">示例</span><span class="sxs-lookup"><span data-stu-id="2ece6-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a><span data-ttu-id="2ece6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="2ece6-112">See also</span></span>

- [<span data-ttu-id="2ece6-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2ece6-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="2ece6-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="2ece6-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
