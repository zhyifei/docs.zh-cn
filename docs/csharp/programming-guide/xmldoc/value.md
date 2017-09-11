---
title: "&lt;value&gt;（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- <value>
dev_langs:
- CSharp
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
caps.latest.revision: 12
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
ms.openlocfilehash: 71c8d5ab2e99291f05ef362960b0eeac969e9de1
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ltvaluegt-c-programming-guide"></a><span data-ttu-id="659bf-102">&lt;value&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="659bf-102">&lt;value&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="659bf-103">语法</span><span class="sxs-lookup"><span data-stu-id="659bf-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="659bf-104">参数</span><span class="sxs-lookup"><span data-stu-id="659bf-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="659bf-105">属性的说明。</span><span class="sxs-lookup"><span data-stu-id="659bf-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="659bf-106">备注</span><span class="sxs-lookup"><span data-stu-id="659bf-106">Remarks</span></span>  
 <span data-ttu-id="659bf-107">\<value> 标记可以描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="659bf-107">The \<value> tag lets you describe the value that a property represents.</span></span> <span data-ttu-id="659bf-108">请注意，在 Visual Studio .NET 开发环境中通过代码向导添加属性时，将添加新属性的 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 标记。</span><span class="sxs-lookup"><span data-stu-id="659bf-108">Note that when you add a property via code wizard in the Visual Studio .NET development environment, it will add a [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="659bf-109">然后，应手动添加 \<value> 标记，描述属性表示的值。</span><span class="sxs-lookup"><span data-stu-id="659bf-109">You should then manually add a \<value> tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="659bf-110">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="659bf-110">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="659bf-111">示例</span><span class="sxs-lookup"><span data-stu-id="659bf-111">Example</span></span>  
 <span data-ttu-id="659bf-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="659bf-112">[!code-cs[csProgGuideDocComments#14](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/value_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="659bf-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="659bf-113">See Also</span></span>  
 <span data-ttu-id="659bf-114">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="659bf-114">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="659bf-115">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="659bf-115">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

