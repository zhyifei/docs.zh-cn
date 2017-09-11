---
title: "&lt;remarks&gt;（C# 编程指南）"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- remarks
- <remarks>
dev_langs:
- CSharp
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
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
ms.openlocfilehash: cd11865fb0d4c8d21294107542fe39ad7e2b690a
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="ltremarksgt-c-programming-guide"></a><span data-ttu-id="4b50f-102">&lt;remarks&gt;（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="4b50f-102">&lt;remarks&gt; (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="4b50f-103">语法</span><span class="sxs-lookup"><span data-stu-id="4b50f-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b50f-104">参数</span><span class="sxs-lookup"><span data-stu-id="4b50f-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="4b50f-105">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="4b50f-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b50f-106">备注</span><span class="sxs-lookup"><span data-stu-id="4b50f-106">Remarks</span></span>  
 <span data-ttu-id="4b50f-107">\<remarks> 标记用于添加有关某个类型的信息，从而补充由 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 指定的信息。</span><span class="sxs-lookup"><span data-stu-id="4b50f-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="4b50f-108">此信息显示在对象浏览器窗口中。</span><span class="sxs-lookup"><span data-stu-id="4b50f-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="4b50f-109">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="4b50f-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4b50f-110">示例</span><span class="sxs-lookup"><span data-stu-id="4b50f-110">Example</span></span>  
 <span data-ttu-id="4b50f-111">[!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4b50f-111">[!code-cs[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b50f-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="4b50f-112">See Also</span></span>  
 <span data-ttu-id="4b50f-113">[C# 编程指南](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4b50f-113">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 [<span data-ttu-id="4b50f-114">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="4b50f-114">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)

