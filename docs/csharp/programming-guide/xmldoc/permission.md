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
ms.openlocfilehash: 454928d5dfd023639bc68f194f2f5ec9e2d7dc22
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "72523392"
---
# <a name="permission-c-programming-guide"></a><span data-ttu-id="2e59e-102">\<permission>（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="2e59e-102">\<permission> (C# Programming Guide)</span></span>
## <a name="syntax"></a><span data-ttu-id="2e59e-103">语法</span><span class="sxs-lookup"><span data-stu-id="2e59e-103">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2e59e-104">参数</span><span class="sxs-lookup"><span data-stu-id="2e59e-104">Parameters</span></span>  
 <span data-ttu-id="2e59e-105">cref = " `member`"</span><span class="sxs-lookup"><span data-stu-id="2e59e-105">cref = " `member`"</span></span>  
 <span data-ttu-id="2e59e-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="2e59e-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="2e59e-107">编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="2e59e-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="2e59e-108">成员必须出现在双引号 (" ") 内  。</span><span class="sxs-lookup"><span data-stu-id="2e59e-108">*member* must appear within double quotation marks (" ").</span></span>  
  
 <span data-ttu-id="2e59e-109">有关如何创建对泛型类型的 cref 引用的信息，请参阅 [\<see>](./see.md)。</span><span class="sxs-lookup"><span data-stu-id="2e59e-109">For information on how to create a cref reference to a generic type, see [\<see>](./see.md).</span></span>  
  
 `description`  
 <span data-ttu-id="2e59e-110">对成员访问权限的说明。</span><span class="sxs-lookup"><span data-stu-id="2e59e-110">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2e59e-111">备注</span><span class="sxs-lookup"><span data-stu-id="2e59e-111">Remarks</span></span>  
 <span data-ttu-id="2e59e-112">使用 \<permission> 可以记录成员访问权限</span><span class="sxs-lookup"><span data-stu-id="2e59e-112">The \<permission> tag lets you document the access of a member.</span></span> <span data-ttu-id="2e59e-113"><xref:System.Security.PermissionSet> 类可指定对成员的访问权限。</span><span class="sxs-lookup"><span data-stu-id="2e59e-113">The <xref:System.Security.PermissionSet> class lets you specify access to a member.</span></span>  
  
 <span data-ttu-id="2e59e-114">使用 [-doc](../../language-reference/compiler-options/doc-compiler-option.md) 进行编译以便将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="2e59e-114">Compile with [-doc](../../language-reference/compiler-options/doc-compiler-option.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2e59e-115">示例</span><span class="sxs-lookup"><span data-stu-id="2e59e-115">Example</span></span>  
 [!code-csharp[csProgGuideDocComments#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#8)]  
  
## <a name="see-also"></a><span data-ttu-id="2e59e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="2e59e-116">See also</span></span>

- [<span data-ttu-id="2e59e-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="2e59e-117">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="2e59e-118">建议的文档注释标记</span><span class="sxs-lookup"><span data-stu-id="2e59e-118">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
