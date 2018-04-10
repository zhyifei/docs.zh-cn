---
title: '&lt;value&gt;（C# 编程指南）'
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 9ea900c21c2c0477c626be5eff2403312d9e8609
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="01228-102">&lt;value&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="01228-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="01228-103">语法</span><span class="sxs-lookup"><span data-stu-id="01228-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="01228-104">参数</span><span class="sxs-lookup"><span data-stu-id="01228-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="01228-105">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="01228-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="01228-106">备注</span><span class="sxs-lookup"><span data-stu-id="01228-106">Remarks</span></span>  
 <span data-ttu-id="01228-107">\<value> 标记可以描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="01228-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="01228-108">请注意，在 Visual Studio .NET 开发环境中通过代码向导添加属性时，将添加新属性的 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 标记。</span><span class="sxs-lookup"><span data-stu-id="01228-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="01228-109">然后，应手动添加 \<value> 标记，描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="01228-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="01228-110">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="01228-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01228-111">示例</span><span class="sxs-lookup"><span data-stu-id="01228-111">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="01228-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="01228-112">See Also</span></span>  
 [<span data-ttu-id="01228-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="01228-113">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="01228-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="01228-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
