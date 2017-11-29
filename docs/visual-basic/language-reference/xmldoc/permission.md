---
title: "&lt;权限&gt;(Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- <permission> XML tag
- permission XML tag
ms.assetid: 0edf0500-5cd7-49c0-9255-64c48f972b77
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 67e11998e43a43f92c26eb5f7daa488d288823c8
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="ltpermissiongt-visual-basic"></a><span data-ttu-id="48689-102">&lt;权限&gt;(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48689-102">&lt;permission&gt; (Visual Basic)</span></span>
<span data-ttu-id="48689-103">指定成员所需的权限。</span><span class="sxs-lookup"><span data-stu-id="48689-103">Specifies a required permission for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48689-104">语法</span><span class="sxs-lookup"><span data-stu-id="48689-104">Syntax</span></span>  
  
```xml  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="48689-105">参数</span><span class="sxs-lookup"><span data-stu-id="48689-105">Parameters</span></span>  
 `member`  
 <span data-ttu-id="48689-106">对可从当前编译环境调用的成员或字段的引用。</span><span class="sxs-lookup"><span data-stu-id="48689-106">A reference to a member or field that is available to be called from the current compilation environment.</span></span> <span data-ttu-id="48689-107">编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。</span><span class="sxs-lookup"><span data-stu-id="48689-107">The compiler checks that the given code element exists and translates `member` to the canonical element name in the output XML.</span></span> <span data-ttu-id="48689-108">括起`member`用引号引起来 ("")。</span><span class="sxs-lookup"><span data-stu-id="48689-108">Enclose `member` in quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="48689-109">对成员访问权限的说明。</span><span class="sxs-lookup"><span data-stu-id="48689-109">A description of the access to the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="48689-110">备注</span><span class="sxs-lookup"><span data-stu-id="48689-110">Remarks</span></span>  
 <span data-ttu-id="48689-111">使用`<permission>`标记记录成员的访问权限。</span><span class="sxs-lookup"><span data-stu-id="48689-111">Use the `<permission>` tag to document the access of a member.</span></span> <span data-ttu-id="48689-112">使用<xref:System.Security.PermissionSet>类可指定访问成员。</span><span class="sxs-lookup"><span data-stu-id="48689-112">Use the <xref:System.Security.PermissionSet> class to specify access to a member.</span></span>  
  
 <span data-ttu-id="48689-113">使用 [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) 进行编译可以将文档注释处理到文件中。</span><span class="sxs-lookup"><span data-stu-id="48689-113">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48689-114">示例</span><span class="sxs-lookup"><span data-stu-id="48689-114">Example</span></span>  
 <span data-ttu-id="48689-115">此示例使用`<permission>`标记来描述的<xref:System.Security.Permissions.FileIOPermission>所需的`ReadFile`方法。</span><span class="sxs-lookup"><span data-stu-id="48689-115">This example uses the `<permission>` tag to describe that the <xref:System.Security.Permissions.FileIOPermission> is required by the `ReadFile` method.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#7](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/permission_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="48689-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48689-116">See Also</span></span>  
 [<span data-ttu-id="48689-117">XML 注释标记</span><span class="sxs-lookup"><span data-stu-id="48689-117">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
