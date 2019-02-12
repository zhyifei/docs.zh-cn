---
title: <remarks> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- remarks C# XML tag
- <remarks> C# XML tag
ms.assetid: f8641391-31f3-4735-af7a-c502a5b6a251
ms.openlocfilehash: b290315cd9c36281c110bbf0c6246468a1a899b2
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55259158"
---
# <a name="remarks-c-programming-guide"></a><span data-ttu-id="8fffc-102">\<remarks>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="8fffc-102">\<remarks> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="8fffc-103">语法</span><span class="sxs-lookup"><span data-stu-id="8fffc-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8fffc-104">参数</span><span class="sxs-lookup"><span data-stu-id="8fffc-104">Parameters</span></span>  
 `Description`  
 <span data-ttu-id="8fffc-105">对成员的说明。</span><span class="sxs-lookup"><span data-stu-id="8fffc-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8fffc-106">备注</span><span class="sxs-lookup"><span data-stu-id="8fffc-106">Remarks</span></span>  
 <span data-ttu-id="8fffc-107">\<remarks> 标记用于添加有关某个类型的信息，从而补充由 [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md) 指定的信息。</span><span class="sxs-lookup"><span data-stu-id="8fffc-107">The \<remarks> tag is used to add information about a type, supplementing the information specified with [\<summary>](../../../csharp/programming-guide/xmldoc/summary.md).</span></span> <span data-ttu-id="8fffc-108">此信息显示在对象浏览器窗口中。</span><span class="sxs-lookup"><span data-stu-id="8fffc-108">This information is displayed in the Object Browser window.</span></span>  
  
 <span data-ttu-id="8fffc-109">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="8fffc-109">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8fffc-110">示例</span><span class="sxs-lookup"><span data-stu-id="8fffc-110">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#9](../../../csharp/programming-guide/xmldoc/codesnippet/CSharp/remarks_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="8fffc-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8fffc-111">See also</span></span>

- [<span data-ttu-id="8fffc-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8fffc-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8fffc-113">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="8fffc-113">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
