---
title: <permission> - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C# XML tag
- permission C# XML tag
ms.assetid: 769e93fe-8404-443f-bf99-577aa42b6a49
ms.openlocfilehash: ea0b8c37f6ef803fd36592376a7a8c0c334f719c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "57489392"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="75b5c-102">\<permission>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="75b5c-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="75b5c-103">语法</span><span class="sxs-lookup"><span data-stu-id="75b5c-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="75b5c-104">参数</span><span class="sxs-lookup"><span data-stu-id="75b5c-104">Parameters</span></span>  
 <span data-ttu-id="75b5c-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="75b5c-105">cref = " `member`"</span></span>  
 <span data-ttu-id="75b5c-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="75b5c-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="75b5c-107">编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="75b5c-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="75b5c-108">成员必须出现在双引号 (" ") 内。</span><span class="sxs-lookup"><span data-stu-id="75b5c-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="75b5c-109">有关如何创建对泛型类型的 cref 引用的信息，请参阅 [\<see>](../../../csharp/programming-guide/xmldoc/see.md)。</span><span class="sxs-lookup"><span data-stu-id="75b5c-109">For information on how to create a cref reference to a generic type, see [\<see>](../../../csharp/programming-guide/xmldoc/see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="75b5c-110">对成员访问权限的说明。</span><span class="sxs-lookup"><span data-stu-id="75b5c-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="75b5c-111">备注</span><span class="sxs-lookup"><span data-stu-id="75b5c-111">Remarks</span></span>  
 <span data-ttu-id="75b5c-112">使用 \<permission> 可以记录成员访问权限</span><span class="sxs-lookup"><span data-stu-id="75b5c-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="75b5c-113"><xref:System.Security.PermissionSet> 类可指定对成员的访问权限。</span><span class="sxs-lookup"><span data-stu-id="75b5c-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="75b5c-114">使用 [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="75b5c-114">Compile with [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75b5c-115">示例</span><span class="sxs-lookup"><span data-stu-id="75b5c-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="75b5c-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="75b5c-116">See also</span></span>

- [<span data-ttu-id="75b5c-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="75b5c-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="75b5c-118">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="75b5c-118">Recommended Tags for Documentation Comments</span></span>](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
